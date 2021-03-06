---
layout: default
permalink: /2010/tasks/task2/
title: Задание №2. Энумеративное кодирование (2010)
---

# Задание №2. Энумеративное кодирование

В обеих частях задания необходимо использовать (или реализовать самостоятельно) "длинную" арифметику для работы с большими числами. Обе программы должны работать с файлами (на входе и на выходе). Каждая программа должна представлять из себя консольное приложение. Для кодирования использовать опцию `-encode`, а для декодирования опцию `-decode`, далее в аргументах программы следует имя входного файла и имя выходного файла, например:

```
program -encode input.txt output.txt
```

или

```
program -decode input.txt output.txt
```

Обязательно должно выполняться `decode(encode(s)) = s` для обеих программ.

## Все строки фиксированной длины

Реализовать энумеративное кодирование строк длины $$N$$ над алфавитом размера $$K$$. Кодирование --- по входной строке (набор чисел) вычислить ее номер (размер алфавита $$К$$, т.е. это максимальное число в строке плюс один).
Декодирование --- по заданному $$K$$ и номеру строки вычислить саму строку. [Некоторые подробности][polynom].

Файлы для кодирования/декодирования:

* Входной/выходной файл: на первой строке последовательность чисел через
запятую (также могут быть пробелы)
* Выходной/входной файл: на первой строке значение $$N$$, на второй значение
 $$K$$, на третьей --- номер строки

## Битовые строки с фиксированным весом

Реализовать энумеративное кодирование битовых строк длины $$N$$ c весом $$K$$ при помощи биномиальных коэффициентов. Кодирование --- по входной строке вычислить ее номер ($$N$$ и $$K$$ подсчитываются непосредственно по строке).
Декодирование --- по заданным $$N$$, $$K$$ и номеру строки вычислить саму строку. [Статья][cover] про энумеративное кодирование.

Файлы для кодирования/декодирования:

* Входной/выходной файл: на первой строке последовательность из нулей и единиц без пробелов
* Выходной/входной файл: на первой строке значение $$N$$, на второй значение $$K$$, на третьей --- номер строки.

## Примечания

Проверить подсчет биномиальных коэффициентов можно на сайте [Wolfram Alpha][wolfram]. [Посмотреть][binomial] пример вычисления биномиального коэффициента $$12000  \choose 560$$.

Кодирование с биномиальными коэффициентами соответствует номеру строки, если строки расположить в лексикографическом порядке. Следовательно, строка вида $$0 \ldots 01 \ldots 1$$ должна иметь номер $$0$$, а строка $$1...10...0$$ максимальный номер (биномиальный коэффициент минус один).

Для проверки: номер строки

$$
01110001110000000111100001101010101000000000001110000000000000011110000111010101111
$$

равен

$$
56855656176045263895097,
$$

где $$N=83$$ и $$K=32$$.

[polynom]: {{site.baseurl}}/theory/polynom-coding/
[wolfram]: http://www.wolframalpha.com/
[cover]: http://www-isl.stanford.edu/people/cover/papers/transIT/0073cove.pdf
[binomial]: http://www.wolframalpha.com/input/?i=12000+chose+560
