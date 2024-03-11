# Калькулятор *codeby.games*


- **Платформа:** codeby.games
- **Категория:** Web
- **Название таска:** Calculator
- **Сложность:** Легкий
- **Ключевые техники:** WAF Bypass, Command Injection

## Ход решения

В задании дан IP адрес веб-сервиса:  `62.173.140.174:16016`
Открываем ресурс в браузере.
![image](https://github.com/JustBruh/CTF-Writeups/assets/60921666/142c570e-1cd6-495b-a326-04d40f00dfb6)

### Попытка 1: WAF Bypass

Согласно названию таска, выполняет он соответствующие
функции поскольку видим форму для пользовательского ввода и упоминание
примененного WAF попробуем его обойти. 
Первым делом вставляем произвольный скрипт надеясь на его
выполнение, реакция веб-ресурса далее на рисунке.
![image](https://github.com/JustBruh/CTF-Writeups/assets/60921666/d479708f-ad56-4538-bbc8-438b148701ca)

### Попытка 2: Command injection

Очевидно двигаемся в верном направлении, попробуем применить
другой метод, введем произвольную команду терминала экранируя ее
спецсимволами (кавычки скобки слэши и т. д.) сработал вариант с
апострофами.
![image](https://github.com/JustBruh/CTF-Writeups/assets/60921666/803e2ea2-dd8f-4483-a00f-dcf2154205cc)

### Обнаружен Index.php

Имеется файл index.php видимо с кодом страницы пробуем
просмотреть содержимое.

В самом конце index.php находим флаг CODEBY{f1lt3r_byp4ss3r}.
![image](https://github.com/JustBruh/CTF-Writeups/assets/60921666/8a2ac3be-429a-4888-96ca-518937ccb90e)

## Источники

- WAF Bypass: [HackTricks](https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/waf-bypass)
- Command Injection: [HackTricks](https://book.hacktricks.xyz/pentesting-web/command-injection)
