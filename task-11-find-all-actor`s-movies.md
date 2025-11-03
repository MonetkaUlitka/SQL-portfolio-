### Задача: Найти все фильмы актера 
### Описание: 
Найдите все фильмы в которых снимался HENRY BERRY.
Выведите результирующую таблицу из трёх колонок title, release_year и rating отсортированных по рейтингу.
### Решение: 
```sql
SELECT f.title, f.release_year, f.rating 
FROM actor a 
JOIN film_actor fm 
ON a.actor_id = fm.actor_id
JOIN film f 
ON f.film_id = fm.film_id 
WHERE a.first_name = 'HENRY' and a.last_name = 'BERRY'
ORDER BY f.rating 
