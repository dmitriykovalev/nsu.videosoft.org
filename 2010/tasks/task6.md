---
layout: default
permalink: /2010/tasks/task6/
title: Задание №6. Свой алгоритм сжатия изображений (2010)
---

# Задание №6. Свой алгоритм сжатия изображений

Нужно реализовать свой собственный алгоритм сжатия изображений. Можно делать сжатие без потерь (lossless) или с потерями (lossy). Плюсом будет наличие обоих режимов в одной программе. Алгоритм сжатия без потерь должен работать заведомо лучше, чем простое zip-сжатие. Для алгоритма с потерями обязательно иметь параметр *quality*, который определяет уровень потерь. Чем больше значение этого параметра, тем меньше вносится искажений. Алгоритм обязан работать на изображениях *любых* размеров. Очевидное требование для алгоритма без потерь (lossless): декодированное изображение должно в точности совпадать с исходным.

При кодировании на вход программы попадает изображение в формате *BMP* и значение *quality*, на выходе бинарный файл --- собственный формат для закодированного изображения. При декодировании все наоборот.

Делать можно как отдельное консольное приложение, так и расширить программу из [задания №1][task1], добавив пункт меню "Save".

Для тестирования алгоритма рекомендуется использовать [стандартные изображения][test-data].

## Рекомендации

Ряд рекомендаций, которые можно применить для своего алгоритма сжатия.

### Кодирование по частям

После предикторов и квантования получается числовая последовательность, которую нужно закодировать согласно энтропии. Можно кодировать последовательность целиком, но лучше это делать по частям. Например, можно поделить изображения на прямоугольные блоки и кодировать данные из каждого блока отдельно.

### Контуры и границы

Контуры и границы (резкие перепады яркости) изображения несут важную информацию. Даже малейшие их искажения очень хорошо заметны глазу. По этой причине те части изображения, которые содержат границу, нужно квантовать поменьше, а "гладкие" части побольше. Это позволяет улучшить коэффициент сжатия и снизить вносимые искажения.

### Пространство YUV

Пространство YUV позволяет отделить яркость (канал Y) от цветовой составляющей (каналы U, V) изображения. Глаз человека сильнее реагирует на изменения яркости, чем цвета. Поэтому каналы U, V можно "искажать" больше, чем Y. Например, можно выбросить каждый второй пиксель по горизонтали и вертикали и получить лишь четверть от исходных данных. Восстанавливать выброшенные пиксели нужно с помощью интерполяции.

### Наилучший предиктор

Можно попытаться разбить изображение на прямоугольные блоки и для каждого блока выбрать наилучший предиктор. Наилучший предиктор используется для предсказания всех значений блока. Выбирается на основе минимальной энтропии значений из блока после предсказания и квантования.


[test-data]: {{site.baseurl}}/info/test-data/
[task1]: {{site.baseurl}}/2010/tasks/task1/
