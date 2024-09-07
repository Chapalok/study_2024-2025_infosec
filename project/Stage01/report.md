---
# Front matter
title: "Отчёт о выполнении. Индивидуальный проект. Этап 1"
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

Установить дистрибутив Kali Linux в виртуальную машину.

В качестве среды виртуализации предлагается использовать VirtualBox.

Сайт Kali Linux: https://www.kali.org/

Учётные данные по умолчанию: логин: root, пароль: toor.

# Ход работы 

1. В рамках первого шага я перешел на официальный сайт *Kali Linux* (www.kali.org) и скачал последнюю версию дистрибутива в формате ISO.

![Рис.1](./image/5.png)

2. Создал новую виртуальную машину (ВМ) в *VirtualBox*, что позволило мне настроить виртуальную машину для установки *Kali Linux*.
   
![Рис.2](./image/1.png)
   
3. Создал новый виртуальный жесткий диск для ВМ.
   
   ![Рис.3](./image/4.png)

4. Подключил ISO-образ *Kali Linux*
5. Запустил ВМ
   ![Рис.4](./image/6.png)
6. Прошел установку и добавил пользователя с именем **root**, пароль **toor**.
   ![Рис.6](./image/2.png)
   ![Рис.5](./image/3.png)
   
# Выводы
После выполнения всех шагов, у меня была успешно установлена *Kali linux* в ВМ.
