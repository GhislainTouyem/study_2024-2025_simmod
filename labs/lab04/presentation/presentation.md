---
## Front matter
lang: ru-RU
title: Лабораторная работа 4
subtitle: Задание для самостоятельного выполнения
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
  * Группа НКНбд-01-22
  * Российский университет дружбы народов
  * [1032225069@pfur.ru](mailto:1032225069@pfur.ru)

:::
::: {.column width="30%"}

![](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab04/presentation/image/moi.jpeg)

:::
::::::::::::::

# Вводная часть

## Цели и задачи

Выполнить задание для самостоятельного
выполнения.

- Для приведённой схемы разработать имитационную модель в пакете NS-2.
- Построить график изменения размера окна TCP (в Xgraph и в GNUPlot);
- Построить график изменения длины очереди и средней длины очереди на первом
маршрутизаторе.
- Оформить отчёт о выполненной работе.



## Выполнение лабораторной работы
```
# создание объекта Simulator
set ns [new Simulator]

# открытие на запись файла out.nam для визуализатора nam
set nf [open out.nam w]

# все результаты моделирования будут записаны в переменную nf
$ns namtrace-all $nf

# открытие на запись файла трассировки out.tr
# для регистрации всех событий
set f [open out.tr w]
# все регистрируемые события будут записаны в переменную f
$ns trace-all $f

Agent/TCP set window_ 32
Agent/TCP set pktSize_ 500

```

## Выполнение лабораторной работы

```
# процедура finish
proc finish {} {
	global tchan_
	# подключение кода AWK:
	set awkCode {
	{
		if ($1 == "Q" && NF>2) {
			print $2, $3 >> "temp.q";
			set end $2
	}
		else if ($1 == "a" && NF>2)
			print $2, $3 >> "temp.a";
	}
}


exec rm -f temp.q temp.a
exec touch temp.a temp.q

```
## Выполнение лабораторной работы

```
set f [open temp.q w]
puts $f "0.Color: Purple"
close $f

set f [open temp.a w]
puts $f "0.Color: Purple"
close $f

exec awk $awkCode all.q

# Запуск xgraph с графиками окна TCP и очереди:
exec xgraph -fg pink -bg purple -bb -tk -x time -t "TCPRenoCWND" WindowVsTimeRenoOne &
exec xgraph -fg pink -bg purple -bb -tk -x time -t "TCPRenoCWND" WindowVsTimeRenoAll &
exec xgraph -bb -tk -x time -y queue temp.q &
exec xgraph -bb -tk -x time -y queue temp.a &
exec nam out.nam &
exit 0
}
```
## Выполнение лабораторной работы

```
# Формирование файла с данными о размере окна TCP:
proc plotWindow {tcpSource file} {
	global ns
	set time 0.01
	set now [$ns now]
	set cwnd [$tcpSource set cwnd_]
	puts $file "$now $cwnd"
	$ns at [expr $now+$time] "plotWindow $tcpSource $file"
}

set r1 [$ns node]
set r2 [$ns node]

$ns simplex-link $r1 $r2 20Mb 15ms RED
$ns simplex-link $r2 $r1 15Mb 20ms DropTail
$ns queue-limit $r1 $r2 300

set N 20
for {set i 0} {$i < $N} {incr i} {
	set n1($i) [$ns node]
	$ns duplex-link $n1($i) $r1 100Mb 20ms DropTail
	set n2($i) [$ns node]
	$ns duplex-link $n2($i) $r2 100Mb 20ms DropTail

	set tcp($i) [$ns create-connection TCP/Reno $n1($i) TCPSink $n2($i) $i]
	set ftp($i) [$tcp($i) attach-source FTP]
}

```

## Выполнение лабораторной работы

```
# Мониторинг размера окна TCP:
set windowVsTimeOne [open WindowVsTimeRenoOne w]
puts $windowVsTimeOne "0.Color: White"
set windowVsTimeAll [open WindowVsTimeRenoAll w]
puts $windowVsTimeAll "0.Color: White"

set qmon [$ns monitor-queue $r1 $r2 [open qm.out w] 0.1];
[$ns link $r1 $r2] queue-sample-timeout;

# Мониторинг очереди:
set redq [[$ns link $r1 $r2] queue]
$redq set thresh_ 75
$redq set maxthresh_ 150
$redq set q_weight_ 0.002
$redq set linterm_ 10

set tchan_ [open all.q w]
$redq trace curq_
$redq trace ave_
$redq attach $tchan_

for {set i 0} {$i < $N} {incr i} {
	$ns at 0.0 "$ftp($i) start"
	$ns at 0.0 "plotWindow $tcp($i) $windowVsTimeAll"
}

$ns at 0.0 "plotWindow $tcp(1) $windowVsTimeOne"

# at-событие для планировщика событий, которое запускает
# процедуру finish через 20s после начала моделирования
$ns at 20.0 "finish"
# запуск модели
$ns run
```
## Выполнение лабораторной работы

![Схема моделируемой сети при N=20](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab04/presentation/image/10.jpg){#fig:001 width=70%}


## Изменение размера окна TCP на линке 1-го источника при N=20

![Изменение размера окна TCP на линке 1-го источника при N=20](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab04/presentation/image/5.jpg){#fig:002 width=70%}

## Изменение размера окна TCP на всех источниках при N=20

![Изменение размера окна TCP на всех источниках при N=20](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab04/presentation/image/6.jpg){#fig:003 width=70%}

## Изменение размера длины очереди на линке (R1–R2) при N=20, qmin = 75, qmax = 150

![Изменение размера длины очереди на линке (R1–R2) при N=20, qmin = 75, qmax = 150](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab04/presentation/image/7.jpg){#fig:004 width=70%}


## Изменение размера средней длины очереди на линке (R1–R2) при N=20, qmin = 75, qmax = 150


![Изменение размера средней длины очереди на линке (R1–R2) при N=20, qmin = 75, qmax = 150](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab04/presentation/image/8.jpg){#fig:005 width=70%}


## Выполнение лабораторной работы

![Резултати после запуска в GNUPlot](/home/ghislain/work/study/2024-2025/Имитационное моделирование/simmod/labs/lab04/presentation/image/11.jpg){#fig:006 width=70%}


# Выводы

В результате выполнения данной лабораторной работы была разработана имитационная модель в пакете NS-2, построены графики изменения размера окна TCP, изменения длины очереди и средней длины очереди.



