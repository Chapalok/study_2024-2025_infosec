---
# Front matter
title: "Отчёт о выполнении. Индивидуальный проект. Этап 3"
author: "Сироджиддинов Камолиддин, НКНбд-01-21"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
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
Установка Hydra: Для начала работы с Hydra была произведена установка инструмента на операционной системе с использованием следующих команд:
![1](./image/1.png)

### 2. Создание словаря паролей
В процессе атаки использовался заранее подготовленный файл со списком паролей. Для его создания был использован текстовый редактор:
![2](./image/2.png)

Пример содержимого файла:
![3](./image/3.png)



### 3. Описание команды для выполнения brute-force атаки
 Была составлена и использована следующая команда Hydra:
![4](./image/4.png)


##  Результаты работы
### Пример вывода попыток Hydra:

```csharp
[DATA] attacking service http-post-form on port 80
[80][http-post-form] host: 178.72.90.181   login: root   password: admin
[STATUS] attack finished for 178.72.90.181 (valid password found)
```

### Файл результата (hydra_result.log):

``` bash
178.72.90.181:80 http-post-form /cgi-bin/luci root:admin
```

### Анализ:
Пароль для пользователя root был успешно подобран. В результате успешной brute-force атаки удалось получить доступ к системе, используя комбинацию root:admin.

# Заключение
В ходе работы было продемонстрировано использование инструмента Hydra для проведения атаки на HTTP POST форму методом brute-force. С помощью указанной команды удалось успешно подобрать пароль для пользователя.

Полученный результат подтверждает эффективность метода brute-force при наличии недостаточно защищённого веб-сервиса с простыми паролями и отсутствием дополнительных защитных механизмов (например, блокировки после нескольких неудачных попыток входа).



