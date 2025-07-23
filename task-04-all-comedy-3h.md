# Задача 4: Найти длинные комедии

## 1. Описание задачи
Найдите все комедии продолжительностью более трёх часов.
Напишите SQL запрос возвращающий результат состоящий из трёх столбцов: названия фильма, года выхода на экран и продолжительности в минутах отсортированный по длине фильма.

## 2. Решение
```sql
SELECT f.title, f.release_year, f.length
FROM film f
INNER JOIN film_category fc ON f.film_id = fc.film_id
INNER JOIN category c ON fc.category_id = c.category_id
WHERE f.length > 180 AND c.name = "Comedy"
ORDER BY f.length;
