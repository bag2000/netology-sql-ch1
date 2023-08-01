## SQL. Часть 1 - Поляков Р.В.
### Задание 1  
#### Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.
```
select distinct district
from address
where left (district, 1) = 'K' and right (district, 1) = 'a';
```
