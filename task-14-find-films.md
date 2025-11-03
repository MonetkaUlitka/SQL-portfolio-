### Задача: Найти кол-во фильмов, в которых актер принимал участие 
### Описание: 
Найдите количество фильмов в которых принимал участие HENRY BERRY.
Результирующую колонку назовите film_count.
### Решение: 
```sql
SELECT count(f.title) as film_count 
FROM film f 
JOIN film_actor fa
ON f.film_id = fa.film_id 
JOIN actor a 
ON a.actor_id = fa.actor_id 
WHERE a.first_name = 'HENRY' and a.last_name = 'BERRY'
