---
## Front matter
lang: ru-RU
title: Лабораторная работа 2.
subtitle: Исследование протокола TCP и алгоритма управления очередью RED
author:
  - Туем Г.
institute:
  - Российский университет дружбы народов, Москва, Россия
 
date: 

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
  * Студен
  * НКНбд-01-22
  * Российский университет дружбы народов
  * [1032225069@pfur.ru](mailto:1032225069@pfur.ru)
  

:::
::: {.column width="30%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab02/presentation/image/moi.jpeg)

:::
::::::::::::::


## Цель работы

- Исследовать протокол TCP и алгоритм управления очередью RED


## Задание 

- Реализавать пример с дисциплиной RED
- Изменить в модели на узле s1 тип протокола TCP с Reno на NewReno, затем на Vegas. Сравнить и пояснить результаты.
- Внесите изменения при отображении окон с графиками (измените цвет фона, цвет траекторий, подписи к осям, подпись траектории в легенде).


## Реализация модели


![Код Реализации модели](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab02/presentation/image/1.jpg)


## Выполнение работы 


![График динамики размера окна TCP и динамики длины очереди и средней длины очереди](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab02/presentation/image/2.jpg)




## Измениние тип протокола TCP


![Измениние в модели на узле s1 тип протокола TCP с Reno на NewReno](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab02/presentation/image/3.jpg)


## Измениние тип протокола TCP

![Измениние в модели на узле s1 тип протокола TCP с Reno на Vegas](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab02/presentation/image/4.jpg)


## Сравниние и поясниние результаты.

![Reno/Newreno/Vegas](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab02/presentation/image/5.jpg)


## изменение отображении

![измениние цвет фона,цвет траекторий, подписи к осям, подпись траектории в легенде](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab02/presentation/image/6.jpg)


## Вывод

- В процессе выполниния данной лабораторной работы я исследавал протокол TCP и алгоритм управления очередью RED.


