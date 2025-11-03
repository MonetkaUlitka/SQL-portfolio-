### Задача: Найдите актеров популярнее, чем HENRY BERRY
### Описание: 
Найдите актёров более популярных чем HENRY BERRY (снявшихся в большем количестве фильмов).
Результат выведите в четыре столбца actor_id, first_name, last_name и film_count отсортированных по возрастанию популярности.
### Решение: 
```sql
SELECT a.actor_id, a.first_name, a.last_name, count(f.title) as film_count 
FROM actor a
JOIN film_actor fa
ON a.actor_id = fa.actor_id 
JOIN film f 
ON f.film_id = fa.film_id 
GROUP BY actor_id 
HAVING film_count > (
  SELECT count(f.title) as film_count 
  FROM film f 
  JOIN film_actor fa
  ON f.film_id = fa.film_id 
  JOIN actor a 
  ON a.actor_id = fa.actor_id 
  WHERE a.first_name = 'HENRY' and a.last_name = 'BERRY')
ORDER BY film_count ASC;
```


### Комментарий:
Долго думала, как правильно сделать подзапрос, так и не поняла как всё это оптимизировать, обратилась за помощью к нейронке, внизу прикладываю более "красивый" вариант.
```sql
SELECT 
    a.actor_id,
    a.first_name,
    a.last_name,
    COUNT(*) AS film_count
FROM 
    actor a
JOIN 
    film_actor fa ON a.actor_id = fa.actor_id
GROUP BY 
    a.actor_id, 
    a.first_name, 
    a.last_name
HAVING 
    COUNT(*) > (
        SELECT 
            COUNT(*)
        FROM 
            actor a_sub
        JOIN 
            film_actor fa_sub ON a_sub.actor_id = fa_sub.actor_id
        WHERE 
            a_sub.first_name = 'HENRY' 
            AND a_sub.last_name = 'BERRY'
    )
ORDER BY 
    film_count ASC;
