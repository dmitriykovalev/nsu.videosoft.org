---
layout: default
title: Алиса и Боб. Сжатие данных.
---

# Алиса и Боб. Сжатие по Хаффману.

Как может помочь Алисе и Бобу кодирование по Хаффману?  Рассмотрим конкретный
пример. Пусть Алиса и Боб пользуются алфавитом из 3-х символов:

$$
A, B, C.
$$

Ну вот так у них сложилось. И пусть они хотят обменяться сообщением из $$5$$
символов. Если вернутся к введенным ранее обозначениям, то $$N = 3$$, $$n = 5$$.
Получается, что всего таких сообщений может быть

$$
N^n = 3^5 = 243
$$

штуки. Теперь пусть известна статистика встречаемости символов, т.е.:

$$
n(A) = 2, n(B) = 2, n(C) = 1.
$$

Согласно озвученному подходу нужно занумеровать все такие сообщения, а всего их

$$
\frac{5!}{2!2!1!} = 120/4 = 30
$$

штук.  Итого, получаем, что коэффициент сжатия

$$
k = 243/30 = 8.1.
$$

А что по Хаффману? После построения дерева Хаффамана получим, что
$$A = 0, B = 10, C = 11$$. Таким образом, длина нашего сообщения закодированного
по Хаффману равна $$2 \cdot 1 + 2 \cdot 2 + 1 \cdot 2 = 8$$ бит. Как известно,
$$8$$ бит позволяют закодировать $$2^8 = 256$$ сообщений, что больше чем даже
число всех возможных сообщений! Коэффициент сжатия при этом
$$k_1 = 243/256 = 0.949.$$ Т.е. стало хуже.

Пусть статистика несколько другая, менее равномерная:

$$
n(A) = 2, n(B) = 1, n(C) = 1.
$$

Тогда всего нужных сообщений

$$
\frac{5!}{3! \cdot 1! \cdot 1!} = 120 / 6 = 20.
$$

Хаффман дает такое же дерево, что и в прошлый раз, но длина сообщения уже
$$3 \cdot 1 + 1 \cdot 2 + 1 \cdot 2 = 7$$ бит. Значит число соcтояний уже
$$2^7 = 128$$ и коэффициент сжатия $$k_2 = 243/128 = 1.898$$ против
$$k_1 = 243/20 = 12.15$$.

Если все так плохо, то вообще зачем нужен этот Хаффман?

А вот зачем. Рассмотрим сообщение более длинное, скажем из 10 символов над тем
же алфавитом.  Статистика такая:

$$
n(A) = 7, n(B) = 2, n(C) = 1.
$$

Что получается здесь:

$$
\frac{10!}{7!2!1!} = \frac{10 \cdot 9 \cdot 8}{2} = 360.
$$

Всего сообщений $$3^{10} = 59049$$. Коэффициент сжатия: $$k = 59049/360 = $$
Дерево у нас будет такое же, поэтому длинна сообщения по Хаффману:
$$7 \cdot 1 + 2 \cdot 2 + 1 \cdot 2 = 7 + 4 + 2 = 13.  2^13 = 8192$$.

Написать про то, как сложно вычислять и насколько большие числа получаются.
Хаффман в данном случае используется как хорошее приближение, которое в пределе
дает то, что нужно. Расписать саму суть Хаффмана = табличка с горизонтальными и
вертикальными рядами.
