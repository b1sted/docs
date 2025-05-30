---
title: "Лекция 6: Организация ввода-вывода в Си"
description: "Подробное руководство по организации ввода-вывода в языке C: стандартные потоки, работа с файлами, форматированный и низкоуровневый ввод-вывод, буферизация, текстовые и бинарные потоки. Практические примеры и объяснение ключевых концепций."
---

> "_Кто рано встает — тому весь день спать хочется." <br/> 
> &mdash; Джейсон Стейтем_

***

## Введение в ввод-вывод (ВВ) в C

**Ввод-вывод** (input-output, IO/ВВ) — это взаимодействие между обработчиком информации (например, компьютером) и внешним миром (человеком или другой системой обработки информации). ВВ включает получение данных системой (ввод) и отправку данных из системы (вывод).

Подсистема ввода-вывода играет ключевую роль в производительности вычислительных систем, так как определяет время отклика и общее быстродействие. Все операции ввода-вывода в Си организованы через **потоки** — последовательности байтов, которые связываются с устройствами ввода-вывода или файлами. Буферизация потоков позволяет ускорить работу, минимизируя обращения к внешним устройствам.

***

## Типы систем ввода-вывода

### Основные подходы:
- **Обработка ВВ центральным процессором (CPU)**
- **Обработка ВВ специальными процессорами ВВ (IOP)**, как в AS/400 или S/390.
- **Параллельная обработка ВВ**, что позволяет увеличивать производительность.

### Основные функции подсистемы ВВ
- Организация параллельной работы устройств ВВ и процессора.
- Согласование скоростей обмена и кэширование данных.
- Разделение устройств и данных между процессами.
- Обеспечение логического интерфейса для взаимодействия.
- Поддержка драйверов и различных файловых систем.
- Поддержка синхронных и асинхронных операций ВВ.

***

## Средства ввода-вывода в языке C

### Стандартные потоки

При запуске программы в Си создаются три стандартных потока:

- `stdin` — стандартный поток ввода (клавиатура).
- `stdout` — стандартный поток вывода (экран).
- `stderr` — поток вывода сообщений об ошибках.

```c
#include <stdio.h>

int main() {
    printf("Введите символ: ");
    int c = getchar();
    printf("Вы ввели: ");
    putchar(c);
    return 0;
}
```

***

## Форматированный ввод и вывод

Функции форматированного ввода и вывода:

- `scanf` — ввод данных с форматированием.
- `printf` — вывод данных с форматированием.

Пример:

```c
#include <stdio.h>

int main() {
    int a;
    float b;
    printf("Введите целое число и число с плавающей точкой: ");
    scanf("%d %f", &a, &b);
    printf("Целое число: %d, число с плавающей точкой: %.2f\n", a, b);
    return 0;
}
```

***

## Работа с файлами

Файлы обрабатываются через указатели типа `FILE*`. Основные операции:

### Открытие и закрытие файлов
```c
FILE *fp;
fp = fopen("example.txt", "w");
if (fp == NULL) {
    perror("Ошибка открытия файла");
    return -1;
}
fclose(fp);
```

### Чтение и запись данных

Чтение из файла:
```c
char buffer[100];
fp = fopen("example.txt", "r");
if (fp == NULL) {
    perror("Ошибка открытия файла");
    return -1;
}
while (fgets(buffer, sizeof(buffer), fp) != NULL) {
    printf("%s", buffer);
}
fclose(fp);
```

Запись в файл:
```c
fp = fopen("example.txt", "w");
if (fp == NULL) {
    perror("Ошибка открытия файла");
    return -1;
}
fprintf(fp, "Запись в файл\n");
fclose(fp);
```

***

## Низкоуровневый ввод-вывод

Функции низкоуровневого ввода-вывода (`open`, `read`, `write`, `close`) напрямую взаимодействуют с ОС.

Пример:
```c
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>

int main() {
    int fd = open("example.txt", O_RDONLY);
    if (fd == -1) {
        perror("Ошибка открытия файла");
        return -1;
    }
    char buffer[100];
    int bytesRead = read(fd, buffer, sizeof(buffer) - 1);
    if (bytesRead > 0) {
        buffer[bytesRead] = '\0';
        printf("Содержимое файла: %s\n", buffer);
    }
    close(fd);
    return 0;
}
```

***

## Буферизация и обработка ошибок

Буферизация потоков позволяет ускорить операции ВВ. Ошибки проверяются с помощью функций `ferror` и `clearerr`:

```c
FILE *fp = fopen("example.txt", "r");
if (fp == NULL) {
    perror("Ошибка открытия файла");
    return -1;
}
int ch = fgetc(fp);
if (ch == EOF) {
    if (ferror(fp)) {
        perror("Ошибка чтения файла");
        clearerr(fp);
    } else {
        printf("Достигнут конец файла.\n");
    }
}
fclose(fp);
```

***

## Различия текстовых и бинарных потоков

- **Текстовый поток** преобразует данные (например, `\n` -> CR+LF).
- **Бинарный поток** сохраняет данные без преобразования.

Пример открытия в текстовом и бинарном режимах:
```c
FILE *textFile = fopen("text.txt", "w");
FILE *binaryFile = fopen("binary.bin", "wb");
```

***

## Заключение

Подсистема ввода-вывода в языке C включает как высокоуровневые функции стандартной библиотеки (`stdio.h`), так и низкоуровневые системные вызовы. Эти механизмы обеспечивают гибкость и производительность при работе с файлами и устройствами.

***

> [_Seen all good things and bad_](https://www.youtube.com/watch?v=IOax8WSeEGM\&pp=ygUTaG93IGNhbiB5b3UgYmUgc3VyZQ%3D%3D)
