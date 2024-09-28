---
## Front matter
lang: ru-RU
title: Презентация о выполнении. Индивидуальный проект. 
subtitle: Этап 3
author:
  - Сироджиддинов Камолиддин, НКНбд-01-21
institute:
  - Российский университет дружбы народов, Москва, Россия


## i18n babel
babel-lang: russian
babel-otherlangs: english
##mainfont: Arial
##monofont: Courier New
##fontsize: 8pt

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---

# Цель работы 

Исследование и применение инструмента Hydra для подбора имени пользователя и пароля с использованием brute-force атаки на HTTP POST форму, а также анализ результатов выполнения.

## Исходные данные:

IP сервера: `178.72.90.181`
Сервис: `HTTP` на стандартном `80` порту
Форма авторизации:
Метод отправки данных - `POST` по адресу:
`http://178.72.90.181/cgi-bin/luci`,
Параметры формы:
`username=root&password=test_password`
Сообщение при неудачной аутентификации:
`"Invalid username and/or password! Please try again."`
Используемая утилита: `Hydra`

## Подготовка к работе


### 1. Обновление системы

![1](./image/1.png)

### 2. Создание словаря паролей

![2](./image/2.png)

### 3.Пример содержимого файла:

![3](./image/3.png)



### 4. Описание команды для выполнения brute-force атаки

![4](./image/4.png)


### Пример вывода попыток Hydra:

```csharp
[DATA] attacking service http-post-form on port 80
[80][http-post-form] host: 178.72.90.181   login: root   password: admin
[STATUS] attack finished for 178.72.90.181 (valid password found)
```

# Заключение
В ходе работы было продемонстрировано использование инструмента Hydra для проведения атаки на HTTP POST форму методом brute-force. С помощью указанной команды удалось успешно подобрать пароль для пользователя.

Полученный результат подтверждает эффективность метода brute-force при наличии недостаточно защищённого веб-сервиса с простыми паролями и отсутствием дополнительных защитных механизмов (например, блокировки после нескольких неудачных попыток входа).

