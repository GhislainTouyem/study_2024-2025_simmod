---
## Front matter
title: "Лабораторная работа 5"
subtitle: "Модель эпидемии (SIR)"
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

построить  модель SIR в xcos и в OpenModelicaв xcos.

# Задание

1. Реализовать модель SIR в в xcos;
2. Реализовать модель SIR с помощью блока Modelica в в xcos;
3. Реализовать модель SIR в OpenModelica;
4. Реализовать модель SIR с учётом процесса рождения / гибели особей в xcos (в том числе и с использованием блока Modelica), а также в OpenModelica;
6. Построить графики эпидемического порога при различных значениях параметров модели(в частности изменяя параметр μ);
Сделать анализ полученных графиков в зависимости от выбранных значений параметров модели.

# Выполнение лабораторной работы

Задача о распространении эпидемии описывается системой дифференциальных уравнений:

s'=−βs(t)i(t);
i'=βs(t)i(t)−νi(t);
r'=νi(t),

где β- скорость заражения, ν- скорость выздоровления.


# Реализация модели в xcos

Зафиксируем начальные данные: β = 1, ν = 0, 3, s(0) = 0, 999, i(0) = 0, 001,
r(0) = 0.(рис. [-@fig:001]).

![задать переменные окружения в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/01.png){#fig:001 width=70%}


Для реализации модели потребуются следующие блоки xcos:
– CLOCK_c — запуск часов модельного времени;
– CSCOPE — регистрирующее устройство для построения графика;
– TEXT_f — задаёт текст примечаний;
– MUX — мультиплексер, позволяющий в данном случае вывести на графике сразу
несколько кривых;
– INTEGRAL_m — блок интегрирования
– GAINBLK_f — в данном случае позволяет задать значения коэффициентов β и ν;
– SUMMATION — блок суммирования;
– PROD_f — поэлементное произведение двух векторов на входе блока.(рис. [-@fig:002]).

![Модель SIR в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/02.png){#fig:002 width=70%}


В параметрах верхнего и среднего блока интегрирования необходимо задать
начальные значения s(0) = 0, 999 и i(0) = 0, 001 (рис. [-@fig:003],[-@fig:004]).


![Задать начальные значения в блоках интегрирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/03.png){#fig:003 width=70%}

![Задать начальные значения в блоках интегрирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/04.png){#fig:004 width=70%}

В меню Моделирование, Установка необходимо задать конечное время интегри-
рования(рис. [-@fig:005]).


![Задать конечное время интегрирования в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/05.png){#fig:005 width=70%}


Результат моделирования представлен на (рис. [-@fig:007])

![Эпидемический порог модели SIR ](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/07.png){#fig:007 width=70%}



# Реализация модели с помощью блока Modelica в xcos

Готовая модель SIR представлена на (рис. [-@fig:012]).
Для реализации модели с помощью языка Modelica помимо блоков CLOCK_c,
CSCOPE, TEXT_f и MUX требуются блоки CONST_m — задаёт константу; MBLOCK
(Modelica generic) — блок реализации кода на языке Modelica.

![Модель SIR в xcos с применением блока Modelica ](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/12.png){#fig:012 width=70%}


Параметры блока Modelica представлены на (рис. [-@fig:010],[-@fig:011]). Переменные на входе (“beta”,“nu”) и выходе (“s”, “i”, “r”) блока заданы как внешние (“E”).



![Параметры блока Modelica для модели ](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/10.png){#fig:010 width=70%}


![Параметры блока Modelica для модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/11.png){#fig:011 width=70%}


## Код на языке Modelica
```
class generic
////automatically generated ////
    //input variables
    Real beta,nu;
    //output variables (комментируем, т.к.
    // начальные значения задаем в самом блоке):
    // Real s,i,r;
////do not modif above this line ////
    // Начальные значения:
    Real s(start=.999), i(start=.001), r(start=.0);
    // модель SIR:
equation
    der(s)=-beta*s*i;
    der(i)=beta*s*i-nu*i;
    der(r)=nu*i;
end generic;
```
## Результат моделирования (рис. [-@fig:006])


![Результат моделирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/06.png){#fig:006 width=70%}


# Упражнение 

В качестве упражнения нам надо построить модель SIR на OpenModelica. Синтаксис почти такой же как и на Modelica. Нужно задать параметры, начальные значения и систему дифференциальных уравнений.

```
model lab

  parameter Real I_0 = 0.001;
  parameter Real R_0 = 0;
  parameter Real S_0 = 0.999;
  parameter Real beta = 1;
  parameter Real nu = 0.3;
  
  
  Real s(start=S_0);
  Real i(start=I_0);
  Real r(start=R_0);
  
equation
  der(s)=-beta*s*i;
  der(i)=beta*s*i-nu*i;
  der(r)=nu*i;


end lab;
```
Результат модель SIR в OpenModelica(рис. [-@fig:036]).


![Результат модель SIR в OpenModelica](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/36.png){#fig:036 width=70%}



# Задание для самостоятельного выполнения


Предположим, что учитываются демографические процессы, в частности, что смертность
в популяции полностью уравновешивает рождаемость, а все рожденные индивидуу-
мы появляются на свет абсолютно здоровыми. Тогда получим следующую систему
уравнений :

s'= −βs(t)i(t) + μ(N − s(t));
i'= βs(t)i(t) − νi(t) − μi(t);
r'= νi(t) − μr(t),

где μ — константа, которая равна коэффициенту смертности и рождаемости.


Реализуем эту модель в xcos. Тут нам понадобятся три блока суммирования и 4 блока констант (добавляется константа ν)

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/17.png)


Результат модель (рис. [-@fig:021]).

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/21.png){#fig:021 width=70%}


Теперь реализуем модель SIR с учетом демографических процессов в xcos с помощью блоков Modelica (рис. [-@fig:022]).


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/22.png){#fig:022 width=70%}


Результат модель (рис. [-@fig:037]).

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/37.png){#fig:037 width=70%}


Реализуем модель SIR с учетом демографических процессов на OpenModelica.

```
  parameter Real I_0 = 0.001;
  parameter Real R_0 = 0;
  parameter Real S_0 = 0.999;
  parameter Real N = 1;
  parameter Real beta = 1;
  parameter Real nu = 0.3;
  parameter Real mu = 0.5;
  
  Real s(start=S_0);
  Real i(start=I_0);
  Real r(start=R_0);
  
equation
  der(s)=-beta*s*i + mu*i + mu*r;
  der(i)=beta*s*i-nu*i - mu*i;
  der(r)=nu*i - mu*r;
```
Выполнив симуляцию, получим следующий график (рис. [-@fig:030]).


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/30.png){#fig:030 width=70%}


Теперь построим графики при разных значениях параметров.

1. β=1, ν=0.3,μ=0.2(рис. [-@fig:038])


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/38.png){#fig:038 width=70%}



2. β=1, ν=0.3,μ=0.3(рис. [-@fig:039])


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/39.png){#fig:039 width=70%}



3. β=1, ν=0.3,μ=0.8(рис. [-@fig:040])


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/40.png){#fig:040 width=70%}



4. β=1, ν=0.1,μ=0.1(рис. [-@fig:042])


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/report/image/42.png){#fig:042 width=70%}


Исходя из анализа графиков, можно сделать вывод, что чем выше значение любого из параметров, тем быстрее система достигает стационарного состояния. При высоком коэффициенте заражения β система быстро проходит через пик развития эпидемии и достигает стационарного состояния.

# Выводы

В процессе выполнения данной лабораторной работы была построена модель SIR в xcos и OpenModelica.
