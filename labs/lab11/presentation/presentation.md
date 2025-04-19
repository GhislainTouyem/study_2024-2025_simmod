---
## Front matter
lang: ru-RU
title: Лабораторная работа 11
subtitle: Модель системы массового обслуживания M |M |1
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
  * [1032225069"pfur.ru](mailto:1032225069"pfur.ru)

:::
::: {.column width="30%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/moi.jpeg)

:::
::::::::::::::


## Цели и задачи

Реализовать модель M|M|1 в CPN tools.
 - Реализовать в CPN Tools модель системы массового обслуживания M|M|1.
 - Настроить мониторинг параметров моделируемой системы и нарисовать графики очереди.
 
 
# Выполнение лабораторной работы

Постановка задачи

В систему поступает поток заявок двух типов, распределённый по пуассоновскому закону. Заявки поступают в очередь сервера на обработку. Дисциплина очереди - FIFO. Если сервер находится в режиме ожидания (нет заявок на сервере), то заявка поступает на обработку сервером.

# Выполнение лабораторной работы

![Граф сети системы обработки заявок в очереди](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/01){#fig:001 width=70%}


# Выполнение лабораторной работы

![Граф генератора заявок системы](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/17){#fig:002 width=70%}

# Выполнение лабораторной работы

![Граф процесса обработки заявок на сервере системы](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/18){#fig:003 width=70%}

# Выполнение лабораторной работы

![декларации системы.](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/02){#fig:004 width=70%}

# Выполнение лабораторной работы

![Параметры элементов основного графа системы обработки заявок в очереди](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/03){#fig:005 width=70%}

# Выполнение лабораторной работы

![Параметры элементов генератора заявок системы](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/04){#fig:006 width=70%}


# Выполнение лабораторной работы

![Параметры элементов обработчика заявок системы](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/05){#fig:007 width=70%}

# Выполнение лабораторной работы

![Функция Predicate монитора Ostanovka](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/11){#fig:008 width=70%}

# Выполнение лабораторной работы

![Функция Observer монитора Queue Delay](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/10){#fig:009 width=70%}

# Выполнение лабораторной работы

![График изменения задержки в очереди](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/12){#fig:010 width=70%}

# Выполнение лабораторной работы

![Функция Observer монитора Queue Delay Real](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/13){#fig:011 width=70%}

# Выполнение лабораторной работы

![Функция Observer монитора Long Delay Time](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/13){#fig:012 width=70%}

# Выполнение лабораторной работы

![Определение longdelaytime в декларациях](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/15){#fig:013 width=70%}

# Выполнение лабораторной работы

![Периоды времени, когда значения задержки в очереди превышали заданное значение](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab11/presentation/image/16){#fig:014 width=70%}

# Выводы

В процессе выполнения данной лабораторной работы я реализовала модель системы массового обслуживания M|M|1 в CPN Tools.


