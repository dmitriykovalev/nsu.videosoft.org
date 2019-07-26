---
layout: default
title: Задание №2 (2009)
---

# Задание №2

Добавить поддержку двух моделей изображения:

* [YUV]
  * Без потерь (lossless)
  * С потерями (lossy)
* Битовые плоскости для RGB, но значения каналов представлены в кодах Грея [Gray Codes]

Добавить вывод [гистограммы](http://en.wikipedia.org/wiki/Image_histogram) для каждого канала (для всего изображения -- по желанию).


## Преобразование RGB в YUV и обратно

Без потерь:

| RGB => YUV           | YUV => RGB           |
|----------------------|----------------------|
| `u = r - g`          | `g = y - (u + v)/4`  |
| `v = b - g`          | `r = u + g`          |
| `y = (u + v)/4 + g`  | `b = v + g`          |


С потерями:

| RGB => YUV                                | YUV => RGB                        |
|-------------------------------------------|-----------------------------------|
| `y = round(0.299*r + 0.587*g + 0.114*b)`  | `b = clip(y + 1.770*u)`           |
| `u = round(0.565*(b - y))`                | `g = clip(y - 0.344*u - 0.714*v)` |
| `v = round(0.713*(r - y))`                | `r = clip(y + 1.403*v)`           |


**Вспомогательные функции:**

```
int round(double value)
{
    return static_cast<int>(value + (value < 0 ? -0.5 : 0.5));
}

int clip(double value)
{
   const int n = round(value);

   if (n < 0)
       return 0;

   if (n > 255)
       return 255;

   return n;
}
```

## Преобразование числа в код Грея

```
unsigned int gray(unsigned int value) {
    return value ^ (value >> 1);
}
```

[Gray Codes]: http://en.wikipedia.org/wiki/Gray_codes
[YUV]: http://en.wikipedia.org/wiki/YUV


