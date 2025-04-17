## Написать запрос, который возвращает всех студентов, которые еще не сдали ни одного экзамена.
### I вариант


SELECT Students.s_id, Students.name, Students.start_year  FROM Students
LEFT JOIN Exams ON Students.s_id = Exams.s_id
WHERE Exams.s_id IS NULL;


<img width="603" alt="image" src="https://github.com/user-attachments/assets/30f6bddc-8cfa-418a-beb8-6f3753c9d085" />

### II вариант


SELECT s_id, name FROM Students WHERE s_id NOT IN (SELECT DISTINCT s_id FROM Exams);

<img width="699" alt="image" src="https://github.com/user-attachments/assets/4d461023-f74d-49cd-9adc-9de778d8b593" />
