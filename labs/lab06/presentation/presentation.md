---
## Front matter
lang: ru-RU
title: Лабораторная работа 6
subtitle: Модель «хищник–жертв»
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

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/moi.jpeg)

:::
::::::::::::::


# Цели и задачи

- Реализовать модель «хищник–жертва»
- Реализовать модели «хищник – жертва» в xcos
- Реализовать модели «хищник – жертва» с помощью блока Modelica в xcos
- Упражнение: реализовать модель «хищник – жертва» в OpenModelica.

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


## Реализовать модели «хищник – жертва» в xcos

![Задать переменные окружения в xcos для модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/03.png)





## Реализовать модели «хищник – жертва» в xcos

![Модель «хищник–жертва» в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/05.png)




## Реализовать модели «хищник – жертва» в xcos

![Задать начальные значения в блоках интегрирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/01.png)




## Реализовать модели «хищник – жертва» в xcos

![Задать начальные значения в блоках интегрирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/02.png)




## Реализовать модели «хищник – жертва» в xcos

![Динамика изменения численности хищников и жертв модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/06.png)




## Реализовать модели «хищник – жертва» в xcos

![Фазовый портрет хищников и жертв модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/07.png)





## Реализовать модели «хищник – жертва» с помощью блока Modelica в xcos

![Параметры блока Modelica для модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/08.png)





## Реализовать модели «хищник – жертва» с помощью блока Modelica в xcos

![Параметры блока Modelica для модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/10.png)





## Реализовать модели «хищник – жертва» с помощью блока Modelica в xcos

Результат моделирования совпадёт с первым

![Модель «хищник–жертва» в xcos с применением блока Modelica](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/11.png)





## Упражнение: реализовать модель «хищник – жертва» в OpenModelica.

![инамика изменения численности хищников и жертв модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/12.png)





## Упражнение: реализовать модель «хищник – жертва» в OpenModelica.

![Фазовый портрет модели ](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab06/presentation/image/13.png)





# Выводы

В процессе выполнения данной лабораторной реализована модель "хищник-жертва" в xcos,  с помощью блока Modelica в xcos и в OpenModelica.




