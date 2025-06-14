# HW-12.3
# 12.3 SQL. Часть 1

Задание можно выполнить как в любом IDE, так и в командной строке.

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

#### *Ответ:*
```sql
SELECT DISTINCT district
FROM address
WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
<img width="449" alt="Задание 1 1" src="https://github.com/user-attachments/assets/a19aefc1-d2e4-4a0d-ace6-452df9060dc4" />

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

#### *Ответ:*
```sql
SELECT payment_date, amount
FROM payment
WHERE amount > 10 AND payment_date BETWEEN '2005-06-15 00:00:00' AND '2005-06-18 23:59:59';
```
<img width="455" alt="Задание 2 2" src="https://github.com/user-attachments/assets/1e142d34-994f-4ea7-8288-805dcfdc8a53" />


### Задание 3
Получите последние пять аренд фильмов.

#### *Ответ:*
```sql
SELECT rental_date
FROM rental
ORDER BY rental_date DESC
LIMIT 5;
```
<img width="447" alt="Задание 3 2" src="https://github.com/user-attachments/assets/d8b74a42-4885-497d-861c-819e13e51570" />



### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

#### *Ответ:*
```sql
SELECT CONCAT((REPLACE(LOWER(first_name), 'll', 'pp')), " ", LOWER(last_name)) AS 'Имя и фамилия' , active
FROM customer
WHERE active = 1 AND first_name IN ('Kelly', 'Willie');
```
<img width="451" alt="Задание 4 2" src="https://github.com/user-attachments/assets/8648e47a-9fe4-4940-8de7-c9a9a61f0654" />


---
