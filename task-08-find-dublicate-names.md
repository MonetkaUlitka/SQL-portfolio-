# Задача 8: Найти повторяющиеся имена актеров.
## 1. Описание: 
Найдите все имена встречающиеся более одного раза. В результате получите таблицу из двух колонок first_name и count.
## 2. Решение: 
```sql
SELECT first_name, count(first_name) AS count from actor 
GROUP BY first_name 
HAVING count > 1 
