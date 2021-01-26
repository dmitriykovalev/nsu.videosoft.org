---
layout: default
title: Бином.
---


# Бином

Рассмотрим алфавит $$A = \{a, b, c, d, e\}$$ и строки длины $$n$$. Всего
сообщений будет $$5^n$$. Каждые символ сообщения будет кодироваться числом
$$0, \ldots, 4$$.

Теперь рассмотрим такое представление:

$$
A = \{a, b, c, d, e\} = \{a, b, c\} \cup \{d, e\}.
$$

В этом случае кодирование будет происходить в два этапа. На *первом* этапе
определяем в какое подмножество $$\{a, b, c\}$$ или $$\{d, e\}$$ попал символ и
записываем соответственно $$0$$ или $$1$$. На *втором* этапе для всех символов
из первого подмножества записываем число $$0, 1, 2$$, а для второго $$0, 1$$.
Таким образом, все $$5^n$$ строк оказались закодированы в два этапа. Алфавит из
$$5$$ символов поделили на части из $$3$$ и $$2$$ элементов:

$$
5^n = {(3 + 2)}^n = \sum_{i=0}^n {n \choose i} 3^i 2^{n-i}
$$

Рассмотрим слагаемое из суммы. Число $${n \choose i} 3^i 2^{n-i}$$ -- это
количество строк, в которых символы $$a, b, c$$ в сумме встречаются $$i$$ раз.
Получается, что $${n \choose i}$$ фиксирует статистику, а число $$3^i 2^{n-i}$$
показывает сколько всего строк возможно с заданной статистикой.

Сначала для кодирование строки из $$n$$ символов требовалось $$\log{5^n}$$. Если
статистика заранее известна (отдельно закодирована), то нужно тратить только
$$\log{n \choose i} 3^i 2^{n-i}}$$. Для фиксированном сообщения мы не можем
менять статистику, но можем менять разбиение алфавита, чтобы минимизировать
$$3^i 2^{n-i}$$.