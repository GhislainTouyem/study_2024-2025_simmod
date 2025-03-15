---
## Front matter
title: "Лабораторная работа 6"
subtitle: "Модель «хищник–жертв»"
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

Реализовать модель «хищник–жертва»

# Задание

- Реализовать модели «хищник – жертва» в xcos
- Реализовать модели «хищник – жертва» с помощью блока Modelica в xcos
- Упражнение: реализовать модель «хищник – жертва» в OpenModelica.


# Выполнение лабораторной работы

## Реализовать модели «хищник – жертва» в xcos

Модель «хищник–жертва» (модель Лотки — Вольтерры) представляет собой модель
межвидовой конкуренции. В математической
форме модель имеет вид: 

x'= ax - bxy
y'= cxy - dy

где x — количество жертв; y — количество хищников; a, b, c, d — коэффициен-
ты, отражающие взаимодействия между видами: a — коэффициент рождаемости
жертв; b — коэффициент убыли жертв; c — коэффициент рождения хищников; d —
коэффициент убыли хищников.

Зафиксируем начальные данные: a = 2, b = 1, c = 0, 3, d = 1, x(0) = 2, y(0) = 1.
В меню Моделирование, Задать переменные окружения зададим значения коэф-
фициентов a, b, c, d (рис. [-@fig:001]).

![Задать переменные окружения в xcos для модели (](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/03.png){#fig:001 width=70%}


Для реализации модели в дополнение к блокам CLOCK_c, CSCOPE, TEXT_f,MUX, INTEGRAL_m, GAINBLK_f, SUMMATION, PROD_f потребуется блок CSCOPXY — регистрирующее устройство для построения фазового портрета.
Готовая модель «хищник–жертва».
Первое уравнение модели задано верхним блоком интегрирования, блоком произведения и блоками задания коэффициентов a и b.
Второе уравнение модели задано нижним блоком интегрирования и блоками задания коэффициентов c и d.
Для суммирования слагаемых правых частей уравнений используем блоки суммирования с соответствующими знаками перед коэффициентами. Выходы блоков суммирования соединяем с входами блоков интегрирования. Выходы блоков интегрирования соединяем с мультиплексором, который в свою очередь позволяет вывести на один график сразу обе кривые: динамику численности жертв и динамику численности хищников(рис. [-@fig:002]).

![Модель «хищник–жертва» в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/05.png){#fig:002 width=70%}


В параметрах блоков интегрирования необходимо задать начальные значения
x(0) = 2, y(0) = 1 (рис. [-@fig:003], рис. [-@fig:004]).


![Задать начальные значения в блоках интегрирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/01.png){#fig:003 width=70%}


![Задать начальные значения в блоках интегрирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/02.png){#fig:004 width=70%}


Результат моделирования представлен на (рис. [-@fig:005], рис. [-@fig:006]).

![Динамика изменения численности хищников и жертв модели при a = 2, b = 1, c = 0, 3, d = 1, x(0) = 2, y(0) = 1](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/06.png){#fig:005 width=70%}


![Фазовый портрет хищников и жертв модели при a = 2, b = 1, c = 0, 3, d = 1, x(0) = 2, y(0) = 1](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/07.png){#fig:006 width=70%}


## Реализовать модели «хищник – жертва» с помощью блока Modelica в xcos

Для реализации модели с помощью языка Modelica потребуются следующие блоки xcos: CLOCK_c, CSCOPE, CSCOPXY, TEXT_f, MUX, CONST_m и MBLOCK (Modelica generic).
Как и ранее, задаём значения коэффициентов a, b, c, d .
Готовая модель «хищник–жертва» представлена.
Параметры блока Modelica представлены на рис. 6.7. Переменные на входе (“a”,“b”, “c”, “d”) и выходе (“x”, “y”) блока заданы как внешние (“E”).

Код на языке Modelica:
```
class generic
////automatically generated ////
    //input variables
    Real a,b,c,d;
    //output variables
    // Real x,y;
////do not modif above this line ////
    Real x(start=2), y(start=1);
// Модель хищник-жертва
equation
    der(x)=a*x-b*x*y;
    der(y)=c*x*y-d*y;
end generic;
```

Параметры блока Modelica для модели (рис. [-@fig:007], рис. [-@fig:008]).


![Параметры блока Modelica для модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/08.png){#fig:007 width=70%}


![Параметры блока Modelica для модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/10.png){#fig:008 width=70%}


Модель «хищник–жертва» в xcos с применением блока Modelica(рис. [-@fig:009]).

![Модель «хищник–жертва» в xcos с применением блока Modelica](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/11.png){#fig:009 width=70%}


Результат моделирования совпадёт с (рис. [-@fig:005], рис. [-@fig:006]).


## Упражнение: реализовать модель «хищник – жертва» в OpenModelica.

Построим графики изменения численности популяций и фазовый портрет(рис. [-@fig:010], рис. [-@fig:011]).
Код на языке OpenModelica:
```
parameter Real a=2;
parameter Real b=1;
parameter Real c=0.3;
parameter Real d=1;
parameter Real x0=2;
parameter Real y0=1;

Real x(start=x0);
Real y(start=y0);

equation
  der(x)=a*x-b*x*y;
  der(y)=c*x*y-d*y;
```

![инамика изменения численности хищников и жертв модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/12.png){#fig:010 width=70%}

![Фазовый портрет модели ](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/report/image/13.png){#fig:011 width=70%}


# Выводы

В процессе выполнения данной лабораторной реализована модель "хищник-жертва" в xcos,  с помощью блока Modelica в xcos и в OpenModelica.

