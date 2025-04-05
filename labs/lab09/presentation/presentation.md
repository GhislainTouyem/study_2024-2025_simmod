---
## Front matter
lang: ru-RU
title: Лабораторная работа 9
subtitle: Модель «Накорми студентов»
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
  * Российский университет дружбы народов
  * [1032225069@pfur.ru](mailto:1032225069@pfur.ru)

:::
::: {.column width="30%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/presentation/image/moi.jpeg)

:::
::::::::::::::


# Цели и задачи

Реализовать модель "Накорми студентов" в CPN Tools.

- Реализовать модель "Накорми студентов" в CPN Tools;
- Вычислить пространство состояний, сформировать отчет о нем и построить граф.

# Выполнение лабораторной работы

Рассмотрим пример студентов, обедающих пирогами. Голодный студент становится сытым после того, как съедает пирог. Сначала нарисуем граф сети.

![Граф сети модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/presentation/image/1.png){#fig:001 width=50%}


# Выполнение лабораторной работы

В меню задаём новые декларации модели

![Задание деклараций модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/presentation/image/2.png){#fig:002 width=50%}

# Выполнение лабораторной работы

В результате получаем работающую модель

![модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/presentation/image/3.png){#fig:003 width=50%}

# Выполнение лабораторной работы

После запуска фишки типа «пирожки» из позиции «еда» и фишки типа «студенты» из позиции «голодный студент», пройдя через переход «кушать», попадают в позицию «сытый студент» и преобразуются в тип «студенты»

![Запуск модели «Накорми студентов»](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/presentation/image/4.png){#fig:004 width=50%}

# Упражнение

Вычислим пространство состояний.

![Фрагмент отчёта о пространстве состояний](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/presentation/image/5.png){#fig:005 width=50%}


# Упражнение

Построим граф пространства состояний

![граф пространства состояний](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab09/presentation/image/6.png){#fig:006 width=50%}


# Выводы

В процессе выполнения данной лабораторной работы я реализовал модель "Накорми студентов" в CPN Tools.

:::

