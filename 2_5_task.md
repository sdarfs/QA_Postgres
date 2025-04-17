## Написать запрос, который возвращает всех студентов, которые еще не сдали ни одного экзамена.
```sql
SELECT Students.s_id, Students.name, Students.start_year  FROM Students
LEFT JOIN Exams ON Students.s_id = Exams.s_id
WHERE Exams.s_id IS NULL;
```

<img width="603" alt="image" src="https://github.com/user-attachments/assets/30f6bddc-8cfa-418a-beb8-6f3753c9d085" />

