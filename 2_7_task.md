## Вывести список курсов со средним баллом по экзамену. Список отсортирован по убыванию среднего балла.

SELECT
c.c_no,
c.title,
ROUND(AVG(e.score), 2) AS average_score  FROM Courses c JOIN Exams e ON c.c_no = e.c_no
WHERE e.score IS NOT NULL  
GROUP BY c.c_no, c.title  
ORDER BY average_score DESC; 


<img width="623" alt="image" src="https://github.com/user-attachments/assets/44336f19-aea4-4752-8fec-7c65bc9d9b4f" />
