---
## Front matter
title: "Лабораторная работа 9"
subtitle: "Модель «Накорми студентов»"
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

Реализовать модель "Накорми студентов" в CPN Tools.

# Задание

* Реализовать модель "Накорми студентов" в CPN Tools;
* Вычислить пространство состояний, сформировать отчет о нем и построить граф.

# Выполнение лабораторной работы

Рассмотрим пример студентов, обедающих пирогами. Голодный студент становится сытым после того, как съедает пирог.

Таким образом, имеем:
- два типа фишек: «пироги» и «студенты»;
- три позиции: «голодный студент», «пирожки», «сытый студент»;
- один переход: «съесть пирожок».

Сначала нарисуем граф сети. Для этого с помощью контекстного меню создаём новую сеть, добавляем позиции, переход и дуги (рис. [-@fig:001]).

![Граф сети модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/report/image/1.png){#fig:001 width=70%}

В меню задаём новые декларации модели: типы фишек, начальные значения
позиций, выражения для дуг. Для этого наведя мышку на меню Standart declarations,
правой кнопкой вызываем контекстное меню и выбираем New Decl и адаем тип s фишкам, относящимся к студентам, тип p — фишкам, относящимся к пирогам, задаём значения переменных x и y для дуг и начальные значения мультимножеств init_stud и init_food(рис. [-@fig:002]).

![Задание деклараций модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/report/image/2.png){#fig:002 width=70%}

В результате получаем работающую модель(рис. [-@fig:003]).

![модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/report/image/3.png){#fig:003 width=70%}


После запуска фишки типа «пирожки» из позиции «еда» и фишки типа «студен-
ты» из позиции «голодный студент», пройдя через переход «кушать», попадают
в позицию «сытый студент» и преобразуются в тип «студенты»(рис. [-@fig:004]).

![Запуск модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/report/image/4.png){#fig:004 width=70%}


# Упражнение

Вычислим пространство состояний. Прежде, чем пространство состояний может быть вычислено и проанализировано, необходимо сформировать код пространства состояний. Этот код создается, когда используется инструмент Войти в пространство состояний. Вход в пространство состояний занимает некоторое время. Затем, если ожидается, что пространство состояний будет небольшим, можно просто применить инструмент Вычислить пространство состояний к листу, содержащему страницу сети. Сформируем отчёт о пространстве состояний и проанализируем его. Чтобы сохранить отчет, необходимо применить инструмент Сохранить отчет о пространстве состояний к листу, содержащему страницу сети и ввести имя файла отчета.


Из полученного отчета можно узнать:

* В графе есть 4 узла и 3 дуги (4 состояния и 3 перехода).
* Указаны границы значений для каждого элемента: голодные студенты (максимум - 3, минимум - 0), сытые студенты (максимум - 3, минимум - 0), еда (максимум - 5, минимум - 2, минимальное значение 2, так как в конце симуляции остаются пирожки).
* Также указаны границы мультимножеств.
* Маркировка home равная 4.
* Маркировка dead равная 4.
* В конце указано, что нет бесконечных последовательностей вхождений.
Фрагмент отчёта о пространстве состояний(рис. [-@fig:005]).

![Фрагмент отчёта о пространстве состояний](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/report/image/5.png){#fig:005 width=70%}

Построим граф пространства состояний(рис. [-@fig:006]).

![граф пространства состояний](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/report/image/6.png){#fig:006 width=70%}


# Выводы

В процессе выполнения данной лабораторной работы я реализовал модель "Накорми студентов" в CPN Tools.

Более подробно в [@Моделирование_информационных_процессов]

# Список литературы{.unnumbered}

::: {#refs}
:::
