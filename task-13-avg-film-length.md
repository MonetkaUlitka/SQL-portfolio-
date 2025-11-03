### Задача: Средняя продолжительность фильма по категории 
### Описание: 
Найдите среднюю продолжительность фильма для каждой категории.
Результат выведите в две колонки category и avg_film_length отсортировав по категории в алфавитном порядке.
### Решение: 
```sql
SELECT c.name as category, avg(f.length) as avg_film_length
FROM film f 
JOIN film_category fc 
ON f.film_id = fc.film_id 
JOIN category c 
ON c.category_id = fc.category_id 
GROUP BY c.name 
ORDER BY c.name asc; 
