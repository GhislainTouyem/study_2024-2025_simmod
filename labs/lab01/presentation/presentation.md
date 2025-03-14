---
## Front matter
lang: ru-RU
title: Лабораторная работа 1
subtitle: Простые модели компьютерной сети
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

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab01/presentation/image/moi.jpeg)

:::
::::::::::::::


# Цели и задачи

Приобретить навыков моделирования сетей передачи данных с помощью сред-
ства имитационного моделирования NS-2, а также анализ полученных результатов
моделирования.

1. Создать шаблон сценария для NS-2;
2. Выполнить простой пример описания топологии сети, состоящей из двух узлов и одного соединения;
3. Выполнить пример с усложнённой топологией сети;
4. Выполнить пример с кольцевой топологией сети;
5. Выполнить упражнение.


# Выполнение лабораторной работы

Простой пример описания топологии сети, состоящей из двух узлов и одного соединения
 
![Визуализация простой модели сети с помощью nam](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab01/presentation/image/1.jpg)


# Выполнение лабораторной работы

Пример с усложнённой топологией сети

![Мониторинг очереди в визуализаторе nam](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab01/presentation/image/2.jpg)


# Выполнение лабораторной работы

Пример с кольцевой топологией сети


![Передача данных по кратчайшему пути сети с кольцевой топологией](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab01/presentation/image/3.jpg)


# Выполнение лабораторной работы

Когда соединение будет разорвано, информация о топологии будет обновлена, и пакеты будут отсылаться по новому маршруту через узлы n(6), n(5) и n(4)

![Маршрутизация данных по сети с кольцевой топологией в случае разрыва соединения](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab01/presentation/image/4.jpg)


# Упражнение

![Изменённая кольцевая топология сети](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab01/presentation/image/5.jpg)


# Упражнение

![Разрыв](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab01/presentation/image/6.jpg)


# Выводы

В процессе выполнения данной лабораторной работы я приобрела навыки моделирования сетей передачи данных с помощью средства имитационного моделирования NS-2, а также проанализировала полученные результаты моделирования.
