## Подключаемся к созданной базе данных
```
postgres=#  \c academy
```

### Создание таблицы Students
- s_id первичный ключ
- name имя
- start_year год начала(поэтому integer, хранить как дату полную необязательно)
  
```sql
CREATE TABLE IF NOT EXISTS Students(
  s_id SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  start_year INTEGER NOT NULL
);
```
```
academy=# \d
```
<img width="947" alt="image" src="https://github.com/user-attachments/assets/c61a32e6-7572-4f97-a97c-09ad836e35a9" />

### Вывод созданной таблицы
```
academy=# \d Students
```
<img width="729" alt="image" src="https://github.com/user-attachments/assets/ba6d342a-b87d-4a9c-8994-e27b474e9d63" />

### Создание таблицы Courses 
- c_no первичный ключ
- title название курса,  имеется проверка, чтобы значение было уникальным
- hours количество часов, имеется проверка, чтобы значение было больше 0
```sql
CREATE TABLE Courses(
  c_no SERIAL PRIMARY KEY,
  title VARCHAR(200) NOT NULL UNIQUE,
  hours INTEGER NOT NULL CHECK (hours >0)
);
```

### Вывод созданной таблицы

```
academy-# \d Courses
```

![image](https://github.com/user-attachments/assets/80b47538-46e0-4f98-a571-d06607b9b187)

### Создание таблицы Exams 
- c_no ключ курса
- s_id ключ студента
- score рейтинг, значение лежит в диапазоне [0;100]
```sql
CREATE TABLE Exams (
  s_id INTEGER NOT NULL,
  c_no INTEGER NOT NULL,
  score INTEGER,
  PRIMARY KEY (s_id, c_no),
  FOREIGN KEY (s_id) REFERENCES Students(s_id) ON DELETE CASCADE,
   FOREIGN KEY (c_no) REFERENCES Courses(c_no) ON DELETE CASCADE,
  CHECK (score >= 0 AND score <= 100)
);
```

### Вывод созданной таблицы

```
academy=# \d Exams
```

<img width="1254" alt="image" src="https://github.com/user-attachments/assets/c9fae8cd-1f99-49d0-826a-bcbe5df2e57a" />


