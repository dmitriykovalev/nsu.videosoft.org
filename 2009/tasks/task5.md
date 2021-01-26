---
layout: default
title: Задание №5 (2009)
---

# Задание №5

Все следующие задания направлены на разработку собственного алгоритма сжатия изображений. На данном этапе нужно сделать следующее:

* Добавить в интерфейс программы команду "Compress" для сжатия открытой картинки. Сначала команда будет, во-первых, спрашивать имя файла, во-вторых, показывать диалог, в котором можно выбрать качество сжатия. Обязательно должно быть сжатие без потерь (lossless) и несколько вариантов сжатия с потерями (lossy). Например, можно сделать ползунок "quality". Значение "100%" означает lossless, любое другое значение -- lossy.
* Добавить возможность открывать файлы, сохраненные предыдущей командой.
* Добавить возможность сохранять открытую картинку в bmp файл.

Пока алгоритм вашего сжатия еще не разработан предлагается делать следующее:

* Для lossless сжатия: последовательно записывать значения из R, G, B каналов в файл (по 8 бит).
* Для lossy сжатия: последовательно записывать проквантованные значения из R, G, B каналов в файл. В данном случае квантование понимается просто как "отбрасывание" младших битов. Количество отброшенных битов зависит от параметра "quality". В результате придется тратить не 8 бит, а меньше на каждое значение канала.

Цель такого "сжатия" в том, чтобы была сделана возможность записи **битов** в файл. Это будет нужно в дальнейшем при реализации собственного алгоритма сжатия.