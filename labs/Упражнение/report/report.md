---
## Front matter
title: "Компонентное моделирование"
subtitle: "Scilab,подсистема xcos"
author: "Туем Гислен"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Выполнить упражнение по ознакомлению с программой xcos.

# Задание

Постройте с помощью xcos фигуры Лиссажу со следующими параметрами:
1. A = B = 1, a = 2, b = 2, δ = 0; pi/4; pi/2; 3pi/4; pi;

2. A = B = 1, a = 2, b = 4, δ = 0; pi/4; pi/2; 3pi/4; pi;

3. A = B = 1, a = 2, b = 6, δ = 0; pi/4; pi/2; 3pi/4; pi;

4. A = B = 1, a = 2, b = 3, δ = 0; pi/4; pi/2; 3pi/4; pi.

# Выполнение лабораторной работы

Математическое выражение для кривой Лиссажу:

x(t) = A sin(at + δ),
y(t) = B sin(bt),

где A, B — амплитуды колебаний, a, b — частоты, δ — сдвиг фаз.
В модели, изображённой на рис. II.1.3, использованы следующие блоки xcos:
– CLOCK_c — запуск часов модельного времени;
– GENSIN_f — блок генератора синусоидального сигнала;
– CANIMXY — анимированное регистрирующее устройство для построения графика
типа y = f (x);
– TEXT_f — задаёт текст примечаний.

Предположим, что в модели заданы следующие параметры: A = B = 1, a = 3,
b = 2, δ = pi/2.

модели в xcos и получим график, изображённый на (рис. [-@fig:001]).

![модели в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/01.png){#fig:001 width=70%}

# Выполнение лабораторной работы

Постройте с помощью xcos фигуры Лиссажу со следующими параметрами:

1. A = B = 1, a = 2, b = 2, δ = 0; pi/4; pi/2; 3pi/4; pi;

# Выполнение лабораторной работы

δ = 0

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/02.png){#fig:002 width=70%}

# Выполнение лабораторной работы

δ = pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/03.png){#fig:003 width=70%}

# Выполнение лабораторной работы

* δ = pi/2

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/04.png){#fig:004 width=70%}

# Выполнение лабораторной работы

δ = 3pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/05.png){#fig:005 width=70%}

# Выполнение лабораторной работы

δ = pi

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/06.png){#fig:006 width=70%}

# Выполнение лабораторной работы

2. A = B = 1, a = 2, b = 4, δ = 0; pi/4; pi/2; 3pi/4; pi;

# Выполнение лабораторной работы

δ = 0

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/07.png){#fig:007 width=70%}

# Выполнение лабораторной работы

δ = pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/08.png){#fig:008 width=70%}

# Выполнение лабораторной работы

δ = pi/2

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/09.png){#fig:009 width=70%}

# Выполнение лабораторной работы

* δ = 3pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/10.png){#fig:010 width=70%}

# Выполнение лабораторной работы

δ = pi

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/11.png){#fig:011 width=70%}

# Выполнение лабораторной работы

3. A = B = 1, a = 2, b = 6, δ = 0; pi/4; pi/2; 3pi/4; pi;

# Выполнение лабораторной работы

δ = 0

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/12.png){#fig:012 width=70%}

# Выполнение лабораторной работы

δ = pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/13.png){#fig:013 width=70%}

# Выполнение лабораторной работы

δ = pi/2

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/14.png){#fig:014 width=70%}

# Выполнение лабораторной работы

* δ = 3pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/15.png){#fig:015 width=70%}

# Выполнение лабораторной работы

δ = pi

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/16.png){#fig:016 width=70%}

# Выполнение лабораторной работы

4. A = B = 1, a = 2, b = 3, δ = 0; pi/4; pi/2; 3pi/4; pi;

# Выполнение лабораторной работы

δ = 0

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/17.png){#fig:017 width=70%}

# Выполнение лабораторной работы

δ = pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/18.png){#fig:018 width=70%}

# Выполнение лабораторной работы

δ = pi/2

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/19.png){#fig:019 width=70%}

# Выполнение лабораторной работы

δ = 3pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/20.png){#fig:020 width=70%}

# Выполнение лабораторной работы

δ = pi

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/21.png){#fig:021 width=70%}

# Выводы

В результате выполнения данной лабораторной работы я выполнила упражнение по ознакомлению с программой xcos
