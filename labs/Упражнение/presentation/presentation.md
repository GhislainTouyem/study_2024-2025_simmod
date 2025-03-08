---
## Front matter
lang: ru-RU
title: Компонентное моделирование
subtitle: Scilab,подсистема xcos
author:
  - Туем Г.
institute:
  - Российский университет дружбы народов, Москва, Россия
  

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Туем Гислен
  * Студент
  * НКНбд-01-22
  * Российский университет дружбы народов
  * [1032225069@pfur.ru](mailto:1032225069@pfur.ru)
  

:::
::: {.column width="30%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/presentation/image/moi.jpeg)

:::
::::::::::::::


## Цели и задачи

Выполнить упражнение по ознакомлению с программой xcos.

Постройте с помощью xcos фигуры Лиссажу со следующими параметрами:
1. A = B = 1, a = 2, b = 2, δ = 0; pi/4; pi/2; 3pi/4; pi;

2. A = B = 1, a = 2, b = 4, δ = 0; pi/4; pi/2; 3pi/4; pi;

3. A = B = 1, a = 2, b = 6, δ = 0; pi/4; pi/2; 3pi/4; pi;

4. A = B = 1, a = 2, b = 3, δ = 0; pi/4; pi/2; 3pi/4; pi.


# Выполнение лабораторной работы

Математическое выражение для кривой Лиссажу:

x(t) = A sin(at + δ),
y(t) = B sin(bt),

![модели в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/presentation/image/01.png)


# Выполнение лабораторной работы

1. A = B = 1, a = 2, b = 2, δ = 0; pi/4; pi/2; 3pi/4; pi;

δ = 0
![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/presentation/image/02.png){#fig:002 width=70%}


# Выполнение лабораторной работы

2. A = B = 1, a = 2, b = 4, δ = 0; pi/4; pi/2; 3pi/4; pi;

δ = pi/4

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/presentation/image/08.png)


# Выполнение лабораторной работы

3. A = B = 1, a = 2, b = 6, δ = 0; pi/4; pi/2; 3pi/4; pi;

δ = pi/2

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/presentation/image/14.png)

# Выполнение лабораторной работы

4. A = B = 1, a = 2, b = 3, δ = 0; pi/4; pi/2; 3pi/4; pi;

δ = pi

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/Упражнение/report/image/21.png)


