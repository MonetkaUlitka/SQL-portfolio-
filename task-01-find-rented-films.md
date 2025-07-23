# Задача 1: Найти фильмы взятые в прокат

## 1. Описание задачи
Найдите все фильмы взятые в прокат KATIE ELLIOTT. Выведите результат в два столбца title и rating.
Отсортируйте список так, чтобы сначала шли фильмы "для взрослых" (с рейтингом R), а затем все остальные по алфавиту.

## 2. Решение
```sql
SELECT f.title, f.rating FROM customer c
JOIN rental r ON c.customer_id = r.customer_id
JOIN inventory i ON r.inventory_id = i.inventory_id
JOIN film f ON i.film_id = f.film_id 
WHERE c.first_name = 'Katie' AND c.last_name = 'Elliott'
ORDER BY rating = 'R' DESC, title ASC; 
