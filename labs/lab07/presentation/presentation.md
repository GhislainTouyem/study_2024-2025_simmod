---
## Front matter
lang: ru-RU
title: Лабораторная работа 7.
subtitle: Модель M |M |1|∞
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
::: {.column width="50%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/presentation/image/moi.jpeg)

:::
::::::::::::::


# Цели и задачи

Рассмотрить пример моделирования в xcos системы массового обслуживания типа M |M |1|∞.

1. Реализовать модель системы массового обслуживания типа M|M|1|∞;
2. Построить график поступления и обработки заявок;
3. Построить график динамики размера очереди.


# Выполнение лабораторной работы

Зафиксируем начальные данные


![начальные данные](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/presentation/image/03.png){#fig:001 width=70%}


# Выполнение лабораторной работы

Суперблок, моделирующий поступление заявок 


![Суперблок, моделирующий поступление заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/presentation/image/01.png){#fig:002 width=70%}


# Выполнение лабораторной работы

Суперблок, моделирующий процесс обработки заявок 


![Суперблок, моделирующий обработку заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/presentation/image/02.png){#fig:003 width=30%}


# Выполнение лабораторной работы

Модель M |M |1|∞ в xcos 


![Модель M |M |1|∞ в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/presentation/image/05.png){#fig:004 width=50%}



# Результаты

Поступление и обработка заявок на 


![Поступление и обработка заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/presentation/image/09.png){#fig:005 width=60%}


# Результаты


Динамика размера очереди 


![Динамика размера очереди заявок](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab07/presentation/image/10.png){#fig:006 width=60%}


# Выводы

В процессе выполнения данной лабораторной работы я рассмотрел пример моделирования в xcos системы массового обслуживания типа M|M|1|∞.
:::

