---
## Front matter
lang: ru-RU
title: Лабораторная работа 5
subtitle: Модель эпидемии (SIR)
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

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/moi.jpeg)

:::
::::::::::::::


# Цели и задачи

Построить  модель SIR в xcos и в OpenModelicaв xcos.

1. Реализовать модель SIR в в xcos;
2. Реализовать модель SIR с помощью блока Modelica в в xcos;
3. Реализовать модель SIR в OpenModelica;
4. Реализовать модель SIR с учётом процесса рождения / гибели особей в xcos (в том числе и с использованием блока Modelica), а также в OpenModelica;
6. Построить графики эпидемического порога при различных значениях параметров модели(в частности изменяя параметр μ);
Сделать анализ полученных графиков в зависимости от выбранных значений параметров модели.

# Выполнение лабораторной работы

Задача о распространении эпидемии описывается системой дифференциальных уравнений:


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/43.png)

где β- скорость заражения, ν- скорость выздоровления.
 

# Реализация модели в xcos


Зафиксируем начальные данные: β = 1, ν = 0, 3, s(0) = 0, 999, i(0) = 0, 001,
r(0) = 0.

![задать переменные окружения в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/01.png)

# Реализация модели в xcos

![Модель SIR в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/02.png)

# Реализация модели в xcos

![Эпидемический порог модели SIR ](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/07.png)


# Реализация модели с помощью блока Modelica в xcos


![Модель SIR в xcos с применением блока Modelica ](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/12.png)


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

![Результат моделирования](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/06.png)


# Упражнение 

Результат модель SIR в OpenModelica


![Результат модель SIR в OpenModelica](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/36.png)


# Задание для самостоятельного выполнения

Предположим, что учитываются демографические процессы, в частности, что смертность
в популяции полностью уравновешивает рождаемость, а все рожденные индивидуу-
мы появляются на свет абсолютно здоровыми. Тогда получим следующую систему
уравнений :


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/15.png)

# Задание для самостоятельного выполнения

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/17.png)

# Задание для самостоятельного выполнения

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/21.png)

# Задание для самостоятельного выполнения

Теперь реализуем модель SIR с учетом демографических процессов в xcos с помощью блоков Modelica


![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/22.png)

# Задание для самостоятельного выполнения

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/37.png)


# Задание для самостоятельного выполнения

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/30.png)

# Задание для самостоятельного выполнения 

Теперь построим графики при разных значениях параметров.

![β=1, ν=0.3,μ=0.2](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/38.png)

# Задание для самостоятельного выполнения 

![β=1, ν=0.3,μ=0.3](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/39.png)

# Задание для самостоятельного выполнения 

![β=1, ν=0.1,μ=0.1](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab05/presentation/image/42.png)


Исходя из анализа графиков, можно сделать вывод, что чем выше значение любого из параметров, тем быстрее система достигает стационарного состояния. При высоком коэффициенте заражения β система быстро проходит через пик развития эпидемии и достигает стационарного состояния.












