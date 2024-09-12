---
# Front matter
title: "Отчет по лабораторной работе №2. Дискреционное разграничение прав в Linux. Основные атрибуты."
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

Получение практических навыков работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

# Ход работы

1. Создаю учётную запись пользователя *guest* (использую учётную запись администратора) `useradd guest`.

![Создание новой учетной записи](img/01.png)

2. Задаю пароль для пользователя *guest* (использую учётную запись ад-
министратора) `passwd guest`.

![Введение пароля](img/02.png)

3. Вошел в систему от имени пользователя *guest*.

![Вход в систему](img/03.png)

4. Определил директорию, в которой я нахожусь командой `pwd`. Она является домашней директорией.

![Определение директории](img/4.png)

5. Уточнил имя пользователя командой `whoami`.

![Уточнение имени пользователя](img/5.png)

6. Уточнил имя пользователя, группу, а также группы, куда входит пользователь, командой `id`.

![Вывел данные пользователя](img/6.png)

7. Сравнил полученную информацию об имени пользователя с данными, выводимыми в приглашении командной строки.

8. Просмотрел файл */etc/passwd* командой `cat /etc/passwd`.

![Просмотр файла /etc/passwd](img/8.png)

9. Определил существующие в системе директории командой `ls -l /home/`.

![Существующие директории](img/9.png)

10. Проверил установленные расширенные атрибуты на поддиректориях, находящихся в директории */home*, командой `lsattr /home`.

![Расширенные атрибуты](img/10.png)

11. Создал в домашней директории поддиректорию dir1 командой `mkdir dir1`.

![dir1](img/11.png)

12. Снял с директории dir1 все атрибуты командой `chmod 000 dir1`.

![Снятие атрибутов](img/12.png)

13. Попытался создать в директории dir1 файл file1 командой `echo "test" > /home/guest/dir1/file1`, но отказали в доступе.

![Попытка создать файл file1](img/13.png)

14. Заполнил таблицу полученной информацией.

![Права директорий](img/14.png)

15. Проанализировал полученную таблицу и определил, какие минимальные права доступа на директорию и на файл необходимы для различных операций.

![Минимальные права](img/15.png)

# Выводы

В результате лабораторной работы мной были получены навыки работы с атрибутами файлов, закреплены знания о правах доступа в системах на базе ОС Linux, а также были выявлены минимальные необходимые права доступа для выполнения операций над файлами и директориями.

# Библиография

1. Методические материалы курса