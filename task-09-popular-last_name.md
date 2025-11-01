# Задача 9: Самая популярная среди актеров фамилия.
## 1. Описание: 
Найдите самую популярную среди актеров фамилию.
Результат должен содержать две колонки - фамилию last_name и количество актеров носящих её count.
## 2. Решение: 
```sql
SELECT last_name, count(last_name) AS count from actor
GROUP BY last_name 
ORDER BY count DESC
LIMIT 1;
