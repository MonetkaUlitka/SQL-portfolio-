# Задача 6: Найти адреса с помощью JOIN
## 1. Описание: 
Напишите запрос, который возвращает адреса и почтовые индексы всех адресов, расположенных в London, с помощью JOIN.
## 2. Решение: 
```sql
SELECT a.address, a.postal_code 
FROM address a 
JOIN city c
ON a.city_id = c.city_id 
WHERE c.city = 'London'
