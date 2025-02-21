---
## Front matter
lang: ru-RU
title: Лабораторная работа 3.
subtitle: Моделирование стохастических процессов
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
  * С.Б: 1032225069

:::
::: {.column width="30%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/moi.jpeg)

:::
::::::::::::::


## Цели и задачи

Провестить моделирование СМО.

# Задание

- Реализавать модели на NS-2
- Вывистить Теоретическая вероятность потери и Теоретическая средняя длина очереди
- сосдать график поведения длины очереди в GNUplot

# Выполнение лабораторной работы


Создание объекта Simulator и задаём значения параметров системы
![код час1](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/1.jpg)



# Выполнение лабораторной работы



Задаём распределения интервалов времени поступления пакетов и размера пакетов
![код час2](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/2.jpg)


# Выполнение лабораторной работы


делаем мониторинг очереди
![Код час3](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/3.jpg)



# Выполнение лабораторной работы



Планировщик событий, расчет загрузки системы и вероятности потери пакетов и запуск модели
![код час4](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/4.jpg)



# Выполнение лабораторной работы


После запуски модели у нас эти данны: Теоретическая вероятность потери и Теоретическая средняя длина очереди.
![Теоретическая вероятность потери и Теоретическая средняя длина очереди](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/5.jpg)


## График в GNUplot


код для рисование графики

![код для рисование графики](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/6.jpg)


## График в GNUplot

График поведения длины очереди

![График поведения длины очереди](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab03/presentation/image/7.jpg)



# Выводы

Во время выполнения этой лаборатории я изучил симуляцию CMO.



