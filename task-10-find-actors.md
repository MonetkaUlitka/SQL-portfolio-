### Задача: Найти всех актеров по фильму
### Описание: 
Найдите всех актёров снимавшихся в фильме ANGELS LIFE.
Выведите результирующую таблицу из двух колонок first_name, last_name отсортированных по фамилии в алфавитном порядке.
### Решение: 
```sql
SELECT a.first_name, a.last_name 
FROM actor a 
JOIN film_actor fa 
ON a.actor_id = fa.actor_id 
JOIN film f 
ON f.film_id = fa.film_id 
WHERE f.title = 'ANGELS LIFE'
ORDER BY a.last_name;
