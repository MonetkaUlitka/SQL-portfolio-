# Задача 6: Найти полные имена клиентов.
## 1. Описание: 
Найдите всех клиентов магазина с id 2 (store_id = 2).
Выберите их в виде таблицы с двумя столбцами, где первый столбец — full_name — имя и фамилия клиента с одним пробелом между ними, а второй столбец — адрес электронной почты клиента. 
Отсортируйте результат по фамилии в алфавитном порядке.
## 2. Решение: 
```sql
SELECT CONCAT( c.first_name, ' ', c.last_name) as full_name, c.email
FROM customer c 
JOIN store s 
ON c.store_id = s.store_id 
WHERE s.store_id = 2
ORDER BY c.last_name;
