### 1. Задание по теории тестирования - PlanTest.pdf
Вы подключаетесь к команде разработки web интернет-магазина в роли QA инженера. 
Через данный сайт посетитель может: 
- Просматривать каталог товаров;
- Добавлять заинтересовавшие товары в корзину;
- Оформить заказ;
- Выбрать способ доставки;
- Оплатить заказ онлайн через сторонний сервис.
На данный момент разрабатывается первая альфа-версия, которая будет готова через две недели. Само приложение должно быть выпущено через 3 месяца. После выпуска приложения выделяется 1 месяц на поддержку.

Результатом выполнения задания должен быть отчёт/план/стратегия в свободной форме, в котором весь период разработки разбит на этапы, по пунктам описаны ваши действия на том или ином этапе. Он должен быть максимально конкретным, презентабельным и развёрнутым. Конкретные тест-кейсы приводить не нужно, но описать, как вы будете тестировать функционал - стоит. Также стоит указать сроки (понедельно), ресурсы (имеющиеся и сторонние) и способы их использования. 
В данном задании необходимо применить знания теории и методологии тестирования: 
- Пирамида тестирования
- Виды/Типы тестирования
- Уровни тестирования
- Тест-дизайн
- Тестовая документация
- Метрики качества
- Жизненный цикл разработки и тестирования
- Оценка трудоемкости
- Управление рисками
- Анализ требований
### 2. Задание по основам баз данных - Набор файлов *.md

1) Установить PostgreSQL (желательно в Docker)
Если через Docker - описать какие команды использовал

2) Создать БД academy.
Приложить скрипт

3) Добавить таблицы по приложенной схеме рис. 1 (названия полей, связи между таблицами должны соответствовать схеме, остальное (ограничения целостности, уникальность, значения по умолчанию, проверки, типы данных) на усмотрение стажера).
Приложить скрипт

<img width="563" alt="image" src="https://github.com/user-attachments/assets/461ba0fb-0d4e-4ea8-aa3f-b65825b749d2" />

Рисунок 1: схема таблиц базы данных academy

4) Добавить несколько записей в таблицы. 
Приложить скрипт

5) Написать запрос, который возвращает всех студентов, которые еще не сдали ни одного экзамена.
Приложить скрипт

6) Написать запрос, который возвращает список студентов и количество сданных им экзаменов. Только для студентов, у которых есть сданные экзамены.
Приложить скрипт

7) Вывести список курсов со средним баллом по экзамену. Список отсортирован по убыванию среднего балла.
Приложить скрипт
8) Сгенерировать скрипт, который наполняет таблицы произвольными данными (можно с помощью psql, можно с помощью любого языка программирования).
Приложить скрипт генерации данных

