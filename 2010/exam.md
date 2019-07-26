---
layout: default
title: Диф. зачет (2010)
---

# Диф. зачет

1. [Множества][set], [мультимножества][multiset] и их перестановки.
2. [Энтропия Хартли][hartley-entropy] ([комбинаторная][combinatorial-entropy]) и [энтропия Шеннона][shannon-entropy]
3. Нетривиальные преобразования строк: [BWT], [MTF]
4. [Энумеративное кодирование][cover]. Общий подход. Кодирование:
   * Перестановок
   * Битовых строк с фиксированной статистикой
   * Произвольных строк с фиксированной статистикой (два подхода)
   * Произвольных строк с фиксированным алфавитом ([кодирование полиномом][polynom])
5. [Кодирование Хаффмана][huffman-coding] и его [обобщение][redundancy] для произвольных деревьев.
6. [Арифметическое кодирование][arithmetic-coding]. Принцип. [Барицентрические координаты][redundancy]. Симплексы.
7. Словарные методы кодирования: [LZ77], [LZ78], [LZW]. Неподвижная точка.
8. [Дискретное косинус-преобразование][DCT]. Алгоритм [JPEG].
9. Подходы к сжатию изображений:
   * Преобразование RGB в YUV с потерями (lossy) и без потерь (lossless).
   * Предикторы
   * Квантование
10. Подходы к сжатию видео.

Полезную информацию для подготовки можно найти в книге [«Методы сжатия данных. Устройство архиваторов, сжатие изображений и видео»](http://compression.ru/book/), а также в [этих источниках][books].

[huffman-coding]: http://compression.ru/download/articles/huff/huffman_1952_minimum-redundancy-codes.pdf
[arithmetic-coding]: http://en.wikipedia.org/wiki/Arithmetic_coding
[hartley-entropy]: http://en.wikipedia.org/wiki/Hartley_entropy
[shannon-entropy]: http://en.wikipedia.org/wiki/Entropy_(information_theory)
[set]: http://en.wikipedia.org/wiki/Set_(mathematics)
[multiset]: http://en.wikipedia.org/wiki/Multiset
[cover]: http://www-isl.stanford.edu/people/cover/papers/transIT/0073cove.pdf
[JPEG]: http://en.wikipedia.org/wiki/JPEG
[BWT]: http://en.wikipedia.org/wiki/BWT
[MTF]: http://en.wikipedia.org/wiki/Move-to-front_transform
[LZ77]: http://en.wikipedia.org/wiki/LZ77
[LZ78]: http://en.wikipedia.org/wiki/LZ78
[LZW]: http://en.wikipedia.org/wiki/LZW
[DCT]: http://en.wikipedia.org/wiki/Discrete_cosine_transform

[redundancy]: {{site.baseurl}}/conferences/redundancy2009/
[combinatorial-entropy]: {{site.baseurl}}/assets/content/pdf/entropy.pdf
[polynom]: {{site.baseurl}}/theory/polynom-coding/
[books]: {{site.baseurl}}/info/books

