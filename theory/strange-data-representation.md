---
layout: default
permalink: /theory/strange-data-representation/
title: Об одном странном представлении данных
---


# Об одном странном представлении данных

Пусть дана битовая строка. Читаем строку слева направо. Сопоставим *нулю*
операцию умножения на $$x$$, а *единице* операцию дифференцирования
$$\frac{d}{dx}$$. В качестве базовой функции возьмем $$\exp(-\frac{x^2}{2})$$.

Например, строка **100**
означает

$$
   x \cdot x \cdot \frac{d}{dx} \exp\left(-\frac{x^2}{2}\right) =
   -x^3 \exp\left(-\frac{x^2}{2}\right).
$$

Полученную функцию умножим на $$\exp(\frac{x^2}{2})$$ и получаем $$-x^3$$.
Таким образом, всякой битовой строке сопоставили многочлен.

Вот таблица для 4-х битовых последовательностей:

| Строка | Преобразование                                                                                           | Результат      |
|--------|----------------------------------------------------------------------------------------------------------|----------------|
| 0000   | $$\displaystyle{x \cdot x \cdot x \cdot x \cdot \exp\left(-\frac{x^2}{2}\right)}$$                       | $$x^4$$        |
| 0001   | $$\displaystyle{x \cdot x \cdot x \cdot \frac{d}{dx} \cdot \exp\left(-\frac{x^2}{2}\right)}$$            | $$-x^4$$       |
| 0010   | $$\displaystyle{x \cdot x \cdot \frac{d}{dx} \cdot x \cdot \exp\left(-\frac{x^2}{2}\right)}$$            | $$-x^4 + x^2$$ |
| 0011   | $$\displaystyle{x \cdot x \cdot \frac{d}{dx} \cdot \frac{d}{dx} \cdot \exp\left(-\frac{x^2}{2}\right)}$$ | $$x^4 - x^2$$  |
| ...    | ...                                                                                                      | ...            |


Остальную часть таблицы предлагается заполнить в качестве упражнения.

Любопытно найти закономерности в полученной таблице. Например, если число
**единиц** нечетно, то в полиноме при $$x^4$$ коэффициент отрицательный. В одну
сторону понятно -- по битовой строке можно построить полином, степень которого
равна длине строки.

**Вопрос:** как по полиному определить, соответствует ли ему какая-нибудь
строка? Если да, то какая?

**Ключевые слова:** Алгебра Вейля, операторы рождения и уничтожения в
квантовой механике, полиномы Эрмита.
