## Написать запрос, который возвращает список студентов и количество сданных им экзаменов. Только для студентов, у которых есть сданные экзамены.
```sql
SELECT 
    s.s_id,
    s.name,
    COUNT(e.c_no) AS exams_passed
FROM 
    Students s
JOIN 
    Exams e ON s.s_id = e.s_id
GROUP BY 
    s.s_id, s.name
HAVING 
    COUNT(e.c_no) > 0;
```
<img width="253" alt="image" src="https://github.com/user-attachments/assets/a6484c83-6080-43a4-9501-52410ecca939" />

