## SQL. Часть 1 - Поляков Р.В.
### Задание 1  
#### Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.
```
select distinct district
from address
where left (district, 1) = 'K' and right (district, 1) = 'a';
```
### Задание 2  
#### Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.
```
select payment_id, amount, payment_date
from payment
where (payment_date between '2005-06-15' and '2005-06-18 23:59:59') and amount > 10;
```
### Задание 3  
#### Получите последние пять аренд фильмов.
```
select rental_id, rental_date 
from rental
order by rental_date desc
limit 5;
```
### Задание 4  
#### Одним запросом получите активных покупателей, имена которых Kelly или Willie.
Сформируйте вывод в результат таким образом:  
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,  
- замените буквы 'll' в именах на 'pp'.  
```
select customer_id, replace(lower(first_name), 'll', 'pp')
from customer
where first_name = 'Kelly' or first_name = 'Willie';
```
