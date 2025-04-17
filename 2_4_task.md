## Добавление в таблицу Students

INSERT INTO Students (name, start_year) VALUES ('Ivan',2019), ('Oleg',2019),('Mark',2021), ('Diana',2019), ('Daria',2021), ('Mia',2021);

SELECT * FROM Students;

<img width="1045" alt="image" src="https://github.com/user-attachments/assets/3152ffcb-94c9-4569-9ef0-e12cbbe14cac" />

## Добавление в таблицу Courses 

INSERT INTO Courses (title, hours) VALUES ('Web Development',60), ('Maths',80),('Programming',40), ('Maths and Logic',40), ('Functional Programming',90) ;

SELECT * FROM Courses;

<img width="1163" alt="image" src="https://github.com/user-attachments/assets/5be4b6e5-88dc-47f1-b994-bfda2481d3f7" />

## Добавление в таблицу Exams
INSERT INTO Exams (s_id, c_no, score) VALUES (1, 1, 65), (1, 2, 82), (1, 3, 100), (2, 1, 100), (2, 2, 90), (2,3, 100), (4,1,25), (4,2, NULL),(4, 3, 50), (3,3,100), (3,4, 99), (3,5,85), 
(5,3,100),(5,4,100),(5,5,100),(6,3,NULL), (6,4, NULL), (6,5, NULL)  ;

SELECT * FROM Exams;

<img width="1265" alt="image" src="https://github.com/user-attachments/assets/f6c4fe77-cb75-4600-bef2-bce304859fbf" />
