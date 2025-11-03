### Задача: Распределение фильмов по категориям
### Описание: 
Подсчитайте количество фильмов относящихся к каждой из категорий.
Выведите результирующую таблицу из двух столбцов category - название категории и count - количество фильмов в ней в порядке убывания количества.
### Решение: 
```sql
SELECT c.name as category, count(fc.film_id) as count 
FROM category c 
JOIN film_category fc
ON c.category_id = fc.category_id 
JOIN film f 
ON f.film_id = fc.film_id 
GROUP BY c.name 
ORDER BY count desc; 

