---
## Front matter
lang: ru-RU
title: Лабораторная работа 8
subtitle: Модель TCP/AQM
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
::: {.column width="90%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/moi.jpeg)

:::
::::::::::::::


# Цели и задачи
Реализовать модель TCP/AQM в xcos и OpenModelica.

- Построить модель TCP/AQM в xcos;
- Построить графики динамики изменения размера TCP окна W(t) и размера очереди Q(t);
- Построить модель TCP/AQM в OpenModelica;

# Реализация в xcos

![переменные](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/04){#fig:001 width=70%}

# Реализация в xcos

![модель TCP/AQM в xcos](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/07){#fig:002 width=50%}

# Реализация в xcos

![Динамика изменения размера TCP окна W (t) и размера очереди Q(t)](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/06){#fig:003 width=50%}

# Реализация в xcos

![Фазовый портрет (W, Q)](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/05){#fig:004 width=50%}


# Реализация в xcos

![Динамика изменения размера TCP окна W (t) и размера очереди Q(t) при C = 0, 9](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/10){#fig:007 width=50%}

# Реализация в xcos

![Фазовый портрет (W, Q) при C = 0, 9](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/09){#fig:008 width=70%}

# Реализация модели в OpenModelica
```
model lab8
parameter Real N=1;
parameter Real R=1;
parameter Real K=5.3;
parameter Real C=0.9;
Real W(start=0.1);
Real Q(start=1);
equation
der(W)= 1/R - W*delay(W, R)/(2*R)*K*delay(Q, R);
der(Q)= if (Q==0) then max(N*W/R-C,0) else (N*W/R-C);
end lab8;
```

# Реализация модели в OpenModelica

![Динамика изменения размера TCP окна W (t) и размера очереди Q(t) при C = 0, 9 в OpenModelica.](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/11){#fig:009 width=70%}

# Реализация модели в OpenModelica

![Фазовый портрет (W, Q) при C = 0, 9 в OpenModelica.](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab08/presentation/image/12){#fig:010 width=70%}

# Выводы
В процессе выполнения данной лабораторной работы я реализовала модель TCP/AQM в xcos и OpenModelica.

