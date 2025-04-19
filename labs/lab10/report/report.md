---
## Front matter
title: "Лабораторная работа 10"
subtitle: "Задача об обедающих мудрецах"
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

Реализовать модель задачи об обедающих мудрецах в CPN Tools.

# Задание

- Реализовать модель задачи об обедающих мудрецах в CPN Tools;
- Вычислить пространство состояний, сформировать отчет о нем и построить граф.


# Выполнение лабораторной работы

## Постановка задачи

Пять мудрецов сидят за круглым столом и могут пребывать в двух состояниях -- думать и есть. Между соседями лежит одна палочка для еды. Для приёма пищи необходимы две палочки. Палочки -- пересекающийся ресурс. Необходимо синхронизировать процесс еды так, чтобы мудрецы не умерли с голода.

1. Рисуем граф сети. Для этого с помощью контекстного меню создаём новую сеть, добавляем позиции, переходы и дуги (рис. [-@fig:001]).

Начальные данные:

позиции: мудрец размышляет (philosopher thinks), мудрец ест (philosopher eats), палочки находятся на столе (sticks on the table)
переходы: взять палочки (take sticks), положить палочки (put sticks)


![Граф сети задачи об обедающих мудрецах](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab10/report/image/1){#fig:001 width=70%}


2. В меню задаём новые декларации модели: типы фишек, начальные значения позиций, выражения для дуг(рис. [-@fig:002]):
– n — число мудрецов и палочек (n = 5);
– p — фишки, обозначающие мудрецов, имеют перечисляемый тип PH от 1 до n;
– s — фишки, обозначающие палочки, имеют перечисляемый тип ST от 1 до n;
– функция ChangeS(p) ставит в соответствие мудрецам палочки (возвращает номера палочек, используемых мудрецами); по условию задачи мудрецы сидят по кругу и мудрец p(i) может взять i и i + 1 палочки, поэтому функция ChangeS(p) определяется следующим образом: fun ChangeS (ph(i))= 1`st(i)++st(if = n then 1 else i+1)


![Задание деклараций задачи об обедающих мудрецах](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab10/report/image/2){#fig:002 width=70%}

В результате получаем работающую модель (рис. [-@fig:003])..
После запуска модели наблюдаем, что одновременно палочками могут воспользоваться только два из пяти мудрецов (рис. [-@fig:004]).

![Модель задачи об обедающих мудрецах](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab10/report/image/3){#fig:003 width=70%}

![Запуск модели задачи об обедающих мудрецах](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab10/report/image/4){#fig:004 width=70%}

# Упражнение

Вычислите пространство состояний. Сформируйте отчёт о пространстве состояний и проанализируйте его. Постройте граф пространства состояний

Вычислим пространство состояний. Прежде, чем пространство состояний может быть вычислено и проанализировано, необходимо сформировать код пространства состояний. Этот код создается, когда используется инструмент Войти в пространство состояний. Вход в пространство состояний занимает некоторое время. Затем, если ожидается, что пространство состояний будет небольшим, можно просто применить инструмент Вычислить пространство состояний к листу, содержащему страницу сети. Сформируем отчёт о пространстве состояний и проанализируем его. Чтобы сохранить отчет, необходимо применить инструмент Сохранить отчет о пространстве состояний к листу, содержащему страницу сети и ввести имя файла отчета.

Из отчета можем узнать, что:

- есть 11 состояний и 30 переходов между ними;
- указаны границы значений для каждого элемента: думающие мудрецы (максимум - 5, минимум - 3), мудрецы едят (максимум - 2, минимум - 0), палочки на столе (максимум - 5, минимум - 1, минимальное значение 2, так как в конце симуляции остаются пирожки);
- указаны границы в виде мультимножеств;
- маркировка home для всех состояний;
- маркировка dead равна None;
- указано, что бесконечно часто происходят события положить и взять палочку.


![пространство состояний](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab10/report/image/6){#fig:005 width=70%}


![граф пространства состояний](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab10/report/image/5){#fig:006 width=70%}

# Выводы


В процессе выполнения данной лабораторной работы я реализовал модель задачи об обедающих мудрецах в CPN Tools.
Более подробно в [@Моделирование_информационных_процессов]


# Список литературы{.unnumbered}

::: {#refs}
:::
