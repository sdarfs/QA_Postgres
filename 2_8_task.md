## Сгенерировать скрипт, который наполняет таблицы произвольными данными (можно с помощью psql, можно с помощью любого языка программирования).

```sql

-- Очистка таблиц с сбросом идентификаторов
TRUNCATE TABLE Exams;
TRUNCATE TABLE Students RESTART IDENTITY CASCADE;
TRUNCATE TABLE Courses RESTART IDENTITY CASCADE;

-- Функция для генерации случайных строк
CREATE OR REPLACE FUNCTION random_string(length INTEGER)
RETURNS TEXT AS $$
DECLARE
  chars TEXT[] := '{a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,q,r,s,t,u,v,w,x,y,z}';
  result TEXT := '';
  i INTEGER := 0;
BEGIN
  IF length < 0 THEN
    RAISE EXCEPTION 'Given length cannot be less than 0';
  END IF;
  
  FOR i IN 1..length LOOP
    result := result || chars[1+random()*(array_length(chars, 1)-1)];
  END LOOP;
  
  RETURN result;
END;
$$ LANGUAGE plpgsql VOLATILE;

-- Генерация 20 случайных студентов
DO $$
DECLARE
  i INTEGER;
BEGIN
  FOR i IN 1..20 LOOP  
    INSERT INTO Students (name, start_year)
    VALUES (
      'Student ' || i || ' ' || random_string(5), 
      2020 + (random() * 4)::INTEGER 
    );
  END LOOP;
END $$;

-- Генерация 10 случайных курсов
DO $$
DECLARE
  i INTEGER;
BEGIN
  FOR i IN 1..10 LOOP  
    INSERT INTO Courses (title, hours)
    VALUES (
      'Course ' || i || ' ' || random_string(8), 
      30 + (random() * 40)::INTEGER  
    );
  END LOOP;
END $$;

-- Генерация 50 случайных экзаменов
DO $$
DECLARE
  i INTEGER;
  student_id INTEGER;
  course_id INTEGER;
BEGIN
  FOR i IN 1..50 LOOP  
    student_id := (random() * 20 + 1)::INTEGER;   -- Случайный s_id (от 1 до 20)
    course_id := (random() * 10 + 1)::INTEGER;    -- Случайный c_no (от 1 до 10)

    IF EXISTS (SELECT 1 FROM Students WHERE s_id = student_id) AND
       EXISTS (SELECT 1 FROM Courses WHERE c_no = course_id) THEN
      INSERT INTO Exams (s_id, c_no, score)
      VALUES (
        student_id,
        course_id,
        CASE WHEN random() < 0.8 THEN  
          50 + (random() * 50)::INTEGER 
        ELSE
          NULL  
        END
      );
    END IF;
  END LOOP;
END $$;

-- Проверка данных
SELECT * FROM Students LIMIT 5;
SELECT * FROM Courses LIMIT 5;
SELECT * FROM Exams LIMIT 5;
```
