---
title: "Лекция 2: Основные этапы решения задач на ЭВМ"
---

> _Природа больше любит женщин, а мужчины - расходный материал._

***

## Введение

**Программирование** - процесс создания и модификации программ.

Программы = алгоритмы + структуры данных

_Цель программирования_ - описание процесса обработки информации.

**Данные** - формализованное представление фактов, пригодное для обработки.

**Информация** — осмысленное представление данных после их обработки.

**Знания** — обработанная информация, применимая для решения задач и принятия решений.

***

## Основные этапы решения задач на ЭВМ

1. **Постановка задачи:** определение целей и требований.
2. **Анализ и исследование:** изучение методов и определение входных и выходных данных.
3. **Разработка математической модели:** формулировка задачи через математические уравнения.
4. **Проектирование алгоритма:** создание последовательности действий для решения задачи.
5. **Программирование:** написание кода.
6. **Тестирование и отладка**.
7. **Эксплуатация и сопровождение: внедрение и поддержка**.
8. **Анализ результатов**.

***

## Классификация языков программирования

Языки разделены по уровню абстракции, парадигме (императивные, функциональные, объектно-ориентированные и др.), а также по типам, степени типизации, времени компиляции и кроссплатформенности.

Язык программирования C относится к следующим классификациям:

1. **Императивный язык:** C основан на последовательных инструкциях, определяющих порядок выполнения операций.
2. **Процедурный язык:** В C поддерживаются процедуры и функции, позволяющие структурировать код.
3. **Язык со статической типизацией:** Типы переменных и выражений проверяются на этапе компиляции, что позволяет находить ошибки раньше.
4. **Язык со слабой типизацией:** В C разрешено неявное преобразование типов, что иногда может приводить к потере точности или ошибкам.
5. **Язык низкого уровня:** C позволяет напрямую работать с памятью и аппаратными ресурсами, что делает его пригодным для системного программирования и разработки операционных систем.
6. **Компилируемый язык:** Код на C необходимо компилировать в машинный код, после чего он может быть выполнен на целевом процессоре.

***

## Алгоритм и его свойства

**Алгоритм** - понятное и точное предписание исполнителю выполнить конечную последовательность команд, приводящую от исходных данных к искомому результату.

Свойства алгоритма:

1. **Определенность:** Алгоритм должен быть однозначным, исключающим произвольность толкования любого из предписаний и заданного порядка исполнения.
2. **Результативность:** Реализация вычислительного процесса должна привести к выдаче результатов или сообщения о невозможности решения задачи.
3. **Массовость:** Алгоритм должен решать не одну частную задачу, а класс задач, т.е. возможность использования алгоритма для решения однотипных задач с различными исходными данными.
4. **Дискретность:** Возможность расчленения вычислительного процесса на отдельные этапы, элементарные операции.

При всем многообразии алгоритмов решения задач в них можно выделить три основных вида вычислительных процессов:

1. Линейный;
2. Ветвящийся;
3. Циклический.

Пример программы на C с условной структурой (разветвляющийся алгоритм), которая находит корни квадратного уравнения:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double a, b, c, discriminant, root1, root2;
    printf("Enter coefficients a, b, and c: ");
    scanf("%lf %lf %lf", &a, &b, &c);
    discriminant = b * b - 4 * a * c;

    if (discriminant > 0) {
        root1 = (-b + sqrt(discriminant)) / (2 * a);
        root2 = (-b - sqrt(discriminant)) / (2 * a);
        printf("Roots are: %.2lf and %.2lf\n", root1, root2);
    } else if (discriminant == 0) {
        root1 = -b / (2 * a);
        printf("Root is: %.2lf\n", root1);
    } else {
        printf("No real roots.\n");
    }
    return 0;
}
```

??? note "Важный нюанс при компиляции с `<math.h>` в Linux и FreeBSD"
    При компиляции программы на C, использующей `<math.h>`, на Linux и FreeBSD необходимо указывать флаг `-lm`, иначе возникнут ошибки линковки. Это связано с тем, что в этих ОС математическая библиотека (`libm`) отделена от стандартной библиотеки C и требует явного подключения. На Windows это не требуется, так как `libm` встроена в стандартную библиотеку.

    `gcc -Wall -g -o example.out 1.c **-lm**`

Пример циклического алгоритма на C для вычисления значений функции для диапазона значений:

```c
#include <stdio.h>

int main() {
    int x;
    double b = 5.0, result;

    for (x = -10; x <= 10; x += 2) {
        result = x * x + b;
        printf("f(%d) = %.2f\n", x, result);
    }
    return 0;
}
```

Способы записи алгоритмов:

* вербальный (словесный);
* формульно-словесный;
* графический (получил наибольшее распространение);
* язык операторных схем;
* алгоритмический язык;
* UML-диаграммы и т.д.

***

> [_I've got a bike, you can ride it if you like_](https://www.youtube.com/watch?v=POlaR26dD1Y)
