---
## Front matter
title: "Лабораторная работа 7."
subtitle: "Модель M |M |1|∞"
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

Рассмотрить пример моделирования в xcos системы массового обслуживания типа M |M |1|∞.

# Задание

1. Реализовать модель системы массового обслуживания типа M|M|1|∞;
2. Построить график поступления и обработки заявок;
3. Построить график динамики размера очереди.

# Выполнение лабораторной работы

Зафиксируем начальные данные: λ = 0, 3, μ = 0, 35, z0 = 6. Суперблок, модели-
рующий поступление заявок (рис. [-@fig:001]).

![начальные данные](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/report/image/03.png){#fig:001 width=70%}


# Выполнение лабораторной работы
Суперблок, моделирующий поступление заявок, представлен на (рис. [-@fig:002]). Тут у нас заявки поступают в систему по пуассоновскому закону. Поступает заявка в суперблок, идет в синхронизатор входных и выходных сигналов, происходит равномерное распределение на интервале [0;1] (также заявка идет в обработчик событий), далее идет преобразование в экспоненциальное распределение с параметром λ, далее заявка опять попадает в обработчик событий и выходит из суперблока.

![Суперблок, моделирующий поступление заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/report/image/01.png){#fig:002 width=70%}

Суперблок, моделирующий процесс обработки заявок, представлен на (рис. [-@fig:003]). Тут происходит обработка заявок в очереди по экспоненциальному закону.

![Суперблок, моделирующий обработку заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/report/image/02.png){#fig:003 width=70%}


И наш Модель M |M |1|∞ в xcos на (рис. [-@fig:004])

![Модель M |M |1|∞ в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/report/image/05.png){#fig:004 width=70%}


# Результаты 

Поступление и обработка заявок на (рис. [-@fig:005])

![Поступление и обработка заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/report/image/09.png){#fig:005 width=70%}


Динамика размера очереди на (рис. [-@fig:006])

![Динамика размера очереди заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/report/image/10.png){#fig:006 width=70%}

# Выводы

В процессе выполнения данной лабораторной работы я рассмотрел пример моделирования в xcos системы массового обслуживания типа M|M|1|∞.


# Список литературы{.unnumbered}

::: 
{#http://www.skf-mtusi.ru/umo/090301vmt/48.1/lr%20i%20pz%20Scilab.pdf}
:::
