# Задача 5: Выберите клиентов без буквы "А"

## 1. Описание задачи
Выберите фамилии, имена и адреса электронной почты клиентов, чьи имя и фамилия не содержат ни одной буквы «А» (латинская буква).
Отсортируйте результат по customer_id

## 2. Решение
```sql
SELECT last_name, first_name, email
FROM customer
WHERE last_name NOT LIKE'%A%' AND first_name NOT LIKE'%A%'
ORDER BY customer_id;
