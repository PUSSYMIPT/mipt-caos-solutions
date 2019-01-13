# mipt-caos
Это решение задач из курса АКОСа на факультете ФИВТ МФТИ. Использовать на свой страх и риск. Не забывайте, что антиплагиат будет запущен, так что копировать и вставлять крайне не рекомендуется. АКОС это довольно полезный предмет сам по себе, так что возможно имеет смысл все-таки попробовать решать задачи самим, благо на самом деле они не такие сложные как кажутся. Но если вам правда что-то очень нужно, то можете использовать что-то от сюда.

---

Задача 6_2 является копипастой из машинного кода, использовать не рекомендуется.
Отсутствуют задачи 11_3 и 11_4 14_2 из курса. Ассемблерный код можно копировать, меня названия регистров и меток, плагиат это не чекает.


### [Problem sm02-0: c/ints/satsum](https://github.com/arovesto/mipt-caos/blob/master/task2_0.c)

Реализовать функцию с прототипом:

uint16_t satsum(uint16_t x, uint16_t y);

которая выполняет сложение с насыщением, то есть, в случае целочисленного переполнения возвращает максимально возможное целое число для данного типа данных.

В коде программы запрещено использовать константы, отличные от 0 и 1.

Запрещено использовать платформо-зависимые или компиляторо-зависимые функции, типы данных с повышенной разрядностью или вещественные типы даннх. 


### [Problem sm02-1: c/ints/bitset-calc](https://github.com/arovesto/mipt-caos/blob/master/task2_1.c)

Реализуйте калькулятор выражений над множествами в обратной польской записи.

На стандартном потоке ввода задается последовательность, состоящая из символов-значений, и символов-операций.

Значениями являются цифры от 0 до 9, и буквы английского алфавита (заглавные и строчные). Последовательности значений кодируют множества из 62 элементов.

Операциями являются:

    & - пересечение множеств;
    | - объединение множеств;
    ^ - симметрическая разность;
    ~ - дополнение текущего результата до полного множества.

В начальный момент времени, множество-результат является пустым. При чтении символов со стандартного потока ввода, когда встречается символ операции, то эта операция применяется к множеству-результату и последнему прочитанному множеству (как в обратной польской записи).

Вывести на экран полученное итоговое значение множества в нормализованной форме: сначала цифры, затем заглавные буквы, потом - строчные (упорядоченные по алфавиту).

Для хранения множеств использовать, суммарно, не более 16 байт памяти.


### [Problem sm02-2: c/texts/utf8-count-symbols](https://github.com/arovesto/mipt-caos/blob/master/task2_2.cpp)

На стандартном потоке ввода подается последовательность символов в кодировке UTF-8.

Посчитать количество символов, которые могут быть представлены в кодирове ASCII, и количество символов, которые не могут быть представлены в этой кодировке.

На стандартный поток вывода вывести последовательно два эти числа.

В случае ошибки декодирования потока данных, необходимо вывести результаты подсчёта, полученные на момент обнаружения ошибки, и завершить работу программы с кодом ошибки 1.

Запрещается использовать какие-либо функции стандартной библиотеки, за исключением функций ввода. Используйте только битовые операции.

Не забывайте о том, что символ перевода строки \n является легальным ASCII-символом.


### [Problem sm03-0: asm-arm/basics/expression](https://github.com/arovesto/mipt-caos/blob/master/task3_0.asm)

Реализуйте функцию с меткой f, которая вычисляет значение выражения y=Ax2+Bx+C

Значения A, B, C и x хранятся, соответсвенно, в регистрах r0, r1, r2 и r3.

Результат вычисления выражения сохраните в регистре r1.

Все аргументы и значение выражения представимы 32-разрядными знаковыми целыми числами.

Использовать оперативную память запрещено, - можно использовать только регистры.


### [Problem sm03-1: asm-arm/basics/memaccess](https://github.com/arovesto/mipt-caos/blob/master/task3_1.asm)

Реализуйте на языке ассемблера ARM функцию с сигнатурой:

int summ(int x0, int N, int *X)

Функция должна вычислять значение x0+∑xi, где 0<e;i<N


### [Problem sm03-2: asm-arm/basics/eqsolution](https://github.com/arovesto/mipt-caos/blob/master/task3_2.asm)

Реализуйте функцию solve, с прототипом

int solve(int A, int B, int C, int D);
      

которая находит минимальное значение x ∈[0,254], которое является одним из корней уравнения: Ax3+Bx2+Cx+D=0.

Все аргументы и значение выражения представимы 32-разрядными знаковыми целыми числами.

Не забывайте про сохраняемые регистры; можно использовать для этого память на стеке.

Гарантируется, что на тестовых данных существует целочисленное решение.


### [Problem sm04-0: asm-arm/structs/simplestruct](https://github.com/arovesto/mipt-caos/blob/master/task4_0.S)

Заданы описание структуры и прототип функции:

#include <stdint.h>

typedef struct {
    uint8_t  u8;
    uint16_t u16;
    uint32_t u32;
} values_t;

extern uint64_t
calculate(const values_t *values);
      

Реализуйте на языке ассемблера ARM-32 эту функцию, которая вычисляет значение values->u8 + values->u16 +  values->u32.

Запрещается выделять дополнительную память на стеке, для решения этой задачи достаточно только четырех регистров.

Процессор работает в режиме Little-Endian, используются стандартные соглашения о вызовах gnueabi и стандартные Си-соглашения о выравнивании.


### [Problem sm04-1: generic/ieee754/classify](https://github.com/arovesto/mipt-caos/blob/master/task4_1.asm)

Реализуйте функцию с прототипом:

typedef enum {
    PlusZero      = 0x00,
    MinusZero     = 0x01,
    PlusInf       = 0xF0,
    MinusInf      = 0xF1,
    PlusRegular   = 0x10,
    MinusRegular  = 0x11,
    PlusDenormal  = 0x20,
    MinusDenormal = 0x21,
    SignalingNaN  = 0x30,
    QuietNaN      = 0x31
} float_class_t;

extern float_class_t
classify(double *value_ptr);
      

которая классифицирует специальные значения вещественного числа, на которое указывает value_ptr, в соответствии со стандартом IEEE 754.

При решении допускается использовать только побитовые операции, включая сдвиги.


### [Problem sm04-2: generic/ieee754/fitint](https://github.com/arovesto/mipt-caos/blob/master/task4_2.asm)

Реализуйте функцию с прототипом:

extern int
check_int(uint32_t u32); /* retval: 0 - false, 1 - true */

которая проверяет, может ли число u32 быть представлено типом float:

float f = u32;
uint64_t y = f;
assert(u32==y);
      

Функция должна вернуть 1, если число может быть представлено типом float, или 0, - если не может.

Допускается исользовать только побитовые операции.


### [Problem sm04-3: asm-arm/structs/fieldsort](https://github.com/arovesto/mipt-caos/blob/master/task4_3.asm)

Заданы описание структуры и прототип функции:

typedef struct Person {
    uint32_t  id;
    uint8_t   age;
    char      first_name[20];
    char      last_name[20];
} person_t;

extern void
sort_by_age(int N, person_t *persons);

Реализуйте функию sort_by_age, которая сортирует массив persons из N элементов в порядке возрастания поля age.

Можно использовать любой алгоритм сортировки, в том числе имеющий сложность O(N2).


### [Problem sm05-0: asm-arm/basics/globalvars](https://github.com/arovesto/mipt-caos/blob/master/task5_0.asm)

Реализуйте функцию calculate, которая вычисляет значение выражения: R=(A*B)+(C*D), где A, B, C, и D - это глобальные переменные типа uint32_t, объявленные во внешнем модуле компиляции, а R, - глобальная переменная типа uint32_t в текущем модуле компиляции.


### [Problem sm05-1: asm-arm/basics/format_io](https://github.com/arovesto/mipt-caos/blob/master/task5_1.asm)

Реализуйте программу, которая вычисляет сумму двух целых десятичных чисел. Размер типа равен размеру машинного слова.

Можно использовать функции стандартной библиотеки языка Си scanf и printf.

В качестве точки входа можно считать функцию main.


### [Problem sm05-2: asm-arm/basics/char-filter-digits](https://github.com/arovesto/mipt-caos/blob/master/task5_2.asm)

Напишите программу, которая читает со стандартного потока ввода последовательность символов, и выводит только те из них, которые являются десятичными цифрами от 0 до 9.

Можно использовать функции стандартной библиотеки языка Си: fgetc и fputc.

В качестве точки входа можно считать функцию main.


### [Problem sm05-3: asm-arm/basics/reverse-print-chars](https://github.com/arovesto/mipt-caos/blob/master/task5_3.asm)

Реализуйте программу, которая считывает символы со стандартного потока ввода, а затем выводит их в обратном порядке.

Можно использовать функции стандартной библиотеки языка Си: fgetc, fputc, realloc и free.

В качестве точки входа можно считать функцию main.


### [Problem sm06-0: asm-x86/basics](https://github.com/arovesto/mipt-caos/blob/master/task6_0.asm)

Реализуйте две функции на языке ассемблера x86 (IA-32) с сигнатурами:

extern int N;
extern int *A;
extern int *B;
extern int *R;

extern void summ();
extern void everyday795(int X, int Y);
      

Первая функция вычисляет значения Ri=Ai+Bi для всех i от 0 до N.

Вторая функция:

    вводит с клавиатуры знаковое целое число;
    умножает его на X;
    прибавляет к нему Y;
    выводит результат на экран.



### [Problem sm06-1: asm-x86/arrays](https://github.com/arovesto/mipt-caos/blob/master/task6_1.asm)

Реализуйте функцию на языке ассемблера x86 (IA-32) с сигнатурой:

extern void summ(int N, const int *A, const int *B, int *R);
      

Функция вычисляет значения Ri=Ai+Bi для всех i от 0 до N.

Память для хранения массива-результата уже выделена.


### [Problem sm06-2: asm-x86/mergesort](https://github.com/arovesto/mipt-caos/blob/master/task6_2.S)

Реализуйте функцию на языке ассемблера x86 (IA-32) с сигнатурой:

exten void mergesort(int from, int to, const int *in, int *out);
      

Функция выполняет сортировку целых чисел слиянием (Merge Sort).

Параметры from и to - это индексы левой и правой границ областей сортировки; in - исходный массив, out - указатель на выделенную память для хранения результата.

Используйте память только на стеке, использование кучи запрещено.


### [Problem sm07-0: asm-x86/fpu-sse/fpu-sse-intro](https://github.com/arovesto/mipt-caos/blob/master/task7_0.S)

Реализуйте на языке ассемблера x86 (IA-32) две функции с сигнатурами:

extern double
calc(double A, double B, double C, int D);

extern void
vector_sum(int N, const float *A, const float *B, float *R);

Первая функция вычисляет значение выражения (A+B)/(C+D) и возвращает результат. Можно использовать как вычисления с помощью i387 FPU, так и с помощью инструкций SSE.

Вторая функция вычисляет поэлементную сумму R[i]=A[i]+B[i]. Гарантируется, что число N больше нуля и кратно 4, а адреса массивов выровнены в памяти по границе 32 байта. Используйте векторные инструкции для вычисления. 


### [Problem sm07-1: asm-x86/fpu-sse/trig-macloren-series](https://github.com/arovesto/mipt-caos/blob/master/task7_1.s)

Реализуйте на языке ассемблера x86 (IA-32) функцию с сигнатурой:

extern double my_sin(double x)

которая вычисляет значение sin(x).

Запрещено использовать встроенные тригонометрические инструкции.

Для вычислений используйте известный вам из курса Математического анализа способ разложения функции в ряд. Точность результата должна быть маскимально возможной для типа данных double. 


### [Problem sm07-2: asm-x86/fpu-sse/vector-dot-product](https://github.com/arovesto/mipt-caos/blob/master/task7_2.S)

Реализуйте на языке ассемблера x86 (IA-32) функцию с сигнатурой:

extern float dot_product(int N, const float *A, const float *B);

которая вычисляет скалярное произведение векторов A и B.

Гарантируется, что N больше нуля, но не гарантируется, что N кратно четырём.

Значения исходных векторов хранятся в произвольных адресах памяти, поэтому выравнивание для них не гарантируется.

Необходимо минимизировать количество выполняемых вычислительных инструкций, используя векторные вычисления. Доступен набор команд SSE 4.2.


### [Problem sm07-3: generic/sse-matrix-mul](https://github.com/arovesto/mipt-caos/blob/master/task7_3.c)

Напишите программу умножения двух вещественных матриц типа float.

Используйте векторные инструкции таким образом, чтобы минимизировать количество вычислений. Гарантируется поддержка SSE 4.2. Можно использовать стандарт Си-2011.

Запрещается использовать OpenMP (для тех, кто знаком с этой технологией).

При чтении данных со стандартного потока ввода необходимо размещать данные в памяти наиболее выгодным для умножения матриц способом.
Input format

На стандартном потоке ввода задается два целых положительных числа M и N, - соответственно количество строк и столбцов первой матрицы.

Далее последовательно идут данные для первой и второй матриц.


### [Problem sm08-0: asm-x86/syscalls/hello-world](https://github.com/arovesto/mipt-caos/blob/master/task8_0.asm)

Реализуйте на языке ассемблера x86 (IA-32) программу, которая выводит "Hello, World!".

Использование стандартной библиотеки Си запрещено.

Точка входа в программу - функция _start.


### [Problem sm08-1: asm-x86/syscalls/copy-stream](https://github.com/arovesto/mipt-caos/blob/master/task8_1.S)

Реализуйте на языке ассемблера x86 (IA-32) программу, которая копирует содержимое со стандартного потока ввода на стандартный поток вывода.

Использование стандартной библиотеки Си запрещено.

Точка входа в программу - функция _start.


### [Problem sm08-2: asm-x86/syscalls/reverse-print-lines](https://github.com/arovesto/mipt-caos/blob/master/task8_2.S)

Реализуйте на языке ассемблера x86 (IA-32) программу, которая читает со стандартного потока ввода текст, после чего выводит все строки текста в обратном порядке.

Использование стандартной библиотеки Си запрещено.

Точка входа в программу - функция _start.


### [Problem sm09-0: files-io/read-filter-write](https://github.com/arovesto/mipt-caos/blob/master/task9_0.c)

Программе в аргументах командной строки передаются три имени файла. Первый аргумент - входной файл, два остальных - выходные.

Реализуйте программу, которая читает символы из первого файла, во второй файл записывает только цифры, а в третий - всё остальное.

Разрешается использовать только низкоуровневый ввод-вывод POSIX.

Если входной файл не существует, то нужно завершить работу с кодом 1.

Если не возможно создать один из выходных файлов, то завершить работу с кодом 2.

При возникновении других ошибок ввода-вывода - завершить работу с кодом 3.


### [Problem sm09-1: files-io/print-list-posix](https://github.com/arovesto/mipt-caos/blob/master/task9_1.c)

Программе в аргументе командной строки передается имя файла с бинарными данными в Little-Endian.

Файл хранит внутри себя односвязный список элементов:

struct Item
{
  int value;
  uint32_t next_pointer;
};

Поле value храние значение элемента списка, поле next_pointer - позицию в файле (в байтах), указывающую на следующий элемент. Признаком последнего элемента является значение next_pointer, равное 0.

Расположение первого элемента списка (если он существует) - строго в нулевой позиции в файле, расположение остальных - случайным образом.

Выведите на экран значения элементов в списке в текстовом представлении.

Для работы с файлом использовать только низкоуровневый ввод-вывод POSIX.


### [Problem sm09-2: files-io/sort-file-contents](https://github.com/arovesto/mipt-caos/blob/master/task9_2.c)

Программе в аргументе командной строки передается имя файла с бинарными данными в Little-Endian, который содержит целые знаковые 32-разрядные числа.

Отсортируйте данные в этом файле.

Обратите внимание на ограничение по памяти: размер файла может быть во много раз больше доступной памяти.

Используйте только низкоуровневые операции POSIX.

Можно создавать произвольное количество вспомогательных файлов в текущем каталоге, суммарный размер которых не превышает двукратного размера исходного файла.


### [Problem sm09-3: files-io/print-list-winapi](https://github.com/arovesto/mipt-caos/blob/master/task9_3.c)

Задача, аналогичная print-list-posix, но требуется решение под Windows.

Программе в аргументе командной строки передается имя файла с бинарными данными в Little-Endian.

Файл хранит внутри себя односвязный список элементов:

struct Item
{
  int value;
  uint32_t next_pointer;
};

Поле value храние значение элемента списка, поле next_pointer - позицию в файле (в байтах), указывающую на следующий элемент. Признаком последнего элемента является значение next_pointer, равное 0.

Расположение первого элемента списка (если он существует) - строго в нулевой позиции в файле, расположение остальных - случайным образом.

Выведите на экран значения элементов в списке в текстовом представлении.

Для работы с файлом использовать только низкоуровневый ввод-вывод WinAPI.


### [Problem sm10-0: posix/filesystem/file-list-summ-size](https://github.com/arovesto/mipt-caos/blob/master/task10_0.c)

Программе на стандартном потоке ввода передаётся список имён файлов.

Необходимо посчитать суммарный размер в байтах всех файлов, которые являются регулярными.


### [Problem sm10-1: posix/filesystem/find-invalid-executables](https://github.com/arovesto/mipt-caos/blob/master/task10_1.c)

Программе на стандартном потоке ввода передаётся список имён файлов.

Необходимо вывести на стандартный поток вывода имена "неправильных" выполняемых файлов, то есть файлов, которые отмечены как исполняемые, но при этом они заведомо не могут быть выполнены в системе (не начинаются с корректной строки #!, содержащей запускаемый интерпретатор, и не являются ELF-файлами).


### [Problem sm10-2: posix/filesystem/manage-symlinks](https://github.com/arovesto/mipt-caos/blob/master/task10_2.c)

Программе на стандартном потоке ввода передаётся список имён файлов.

Если файл является символической ссылкой, то нужно вывести абсолютное имя того файла, на который эта ссылка указывает.

Если файл является регулярным, то необходимо создать символическую ссылку в текущем каталоге, приписав в названии файла префикс link_to_.


### [Problem sm11-0: posix/filesystem/list-recent-files](https://github.com/arovesto/mipt-caos/blob/master/task11_0.c)

Программе передаются два аргумента: имя каталога и три целых числа, - год, месяц и день.

Вывести на стандартный поток вывода список имен файлов указанного каталога, которые были модифицированы начиная с указанной даты (по местному часовому поясу).


### [Problem sm11-1: posix/time/time-diff](https://github.com/arovesto/mipt-caos/blob/master/task11_1.c)

Реализуйте программу, которая читает со стандартного потока ввода строки - временные метки в формате:

YYYY-MM-DD HH:mm

Где YYYY - год, MM - месяц, DD - день, HH - час в 24-часовом формате, mm - минуты.

Гарантируется, что ввод содержит не менее двух строк.

На стандартный поток вывода необходимо вывести интервалы времени в минутах, прошедшие между соседними временными метками.

Не забывайте учитывать возможные переводы стрелок зимнего/летнего времени, а также законодательные инициативы по отмене/введению перевода часов на летнее время.


### [Problem sm11-2: posix/filesystem/find-and-summ-size](https://github.com/arovesto/mipt-caos/blob/master/task11_2.c)

Программе в качестве аргумента строки передается имя каталога.

Необходимо посчитать суммарный размер всех регулярных файлов в этом каталоге и во всех вложенных подкаталогах.

Результат вывести на стандартный поток вывода.


### [Problem sm12-0: posix/mmap/find-substrings-in-file](https://github.com/arovesto/mipt-caos/blob/master/task12_0.c)

Программе передаются два аргумента: имя файла, и строка для поиска.

Необходимо найти все вхождения строки в текстовом файле, используя отображение на память с помощью системного вызова mmap.

На стандартный поток вывода вывести список всех позиций (с нуля) в файле, где втречаются строка.


### [Problem sm12-1: posix/mmap/print-list-using-mmap](https://github.com/arovesto/mipt-caos/blob/master/task12_1.c)

Программе в аргументе командной строки передается имя файла с бинарными данными в Little-Endian.

Файл хранит внутри себя односвязный список элементов:

struct Item
{
  int value;
  uint32_t next_pointer;
};

Поле value храние значение элемента списка, поле next_pointer - позицию в файле (в байтах), указывающую на следующий элемент. Признаком последнего элемента является значение next_pointer, равное 0.

Расположение первого элемента списка (если он существует) - строго в нулевой позиции в файле, расположение остальных - случайным образом.

Выведите на экран значения элементов в списке в текстовом представлении.

Используйте отображение содержимого файла на память.


### [Problem sm12-2: posix/mmap/make-spiral-file](https://github.com/arovesto/mipt-caos/blob/master/task12_2.c)

Программе передаются три аргумента: имя файла, положительное целое число N - размер квадратной матрицы, и положительное число W - ширина клетки матицы в символах.

Необходимо в указанном файле сформировать текст, который содержит матрицу, состоящую из чисел от 1 до N2, таким образом, чтобы числа заполняли её по спирали, по часовой стрелке.

Числа должны быть выровнены по правой границе ячейки матрицы.

Используйте mmap для записи в файл.

Можно использовать функции форматного вывода для преобразования числа в строку.


### [Problem sm13-0: posix/fork/test-proc-limit](https://github.com/arovesto/mipt-caos/blob/master/task13_0.c)

Определите экспериментальным способом, какое максимальное колчичество процессов можно запустить с установленными в ejudge лимитами.

Запрещается использовать getrlimit, и другие явные способы определения ограничений.


### [Problem sm13-1: posix/fork/proc-print-numbers](https://github.com/arovesto/mipt-caos/blob/master/task13_1.c)

Программе передается аргумент - целое число N > 0.

Необходимо создать N-1 дополнительных процессов таким образом, чтобы у каждого процесса было не более одного дочернего процесса.

Каждый из процессов должен вывести на стандартный поток ввода ровно одно число таким образом, чтобы вы выходе получилась строка:

1 2 3 4 ... N

Внимание! В этой задаче будет сравнение с учетом пробельных символов. Между числами должен быть ровно один пробел, а завершается строка символом перевода строки.


### [Problem sm13-2: posix/fork/proc-count-words](https://github.com/arovesto/mipt-caos/blob/master/task13_2.c)

На стандартном потоке ввода задается строка текста, которая состоит слова (последовательности непробельных символов), между которыми может быть произвольное количество пробельных символов, включая перевод строки.

Необходимо посчитать количество слов, если изветно, что их не больше, чем 255, и вывести это значение на стандартный поток вывода.

Используйте создание новых процессов таким образом, чтобы каждый процесс читал не более одного слова, например, c помощью scanf("%s", ...).

Вывод результата возможен только из того процесса, который запущен самым первым (т.е. из исходной программы).

Итоговая программа должна вернуться с кодом возврата 0.

Размер каждого слова не превышает 4096 байт.


### [Problem sm14-0: posix/exec/exec-python](https://github.com/arovesto/mipt-caos/blob/master/task14_0.c)

Программе на стандартный поток ввода задается некоторое арифметическое выражение в синтаксисе языка python3.

Необходимо вычислисть это выражение, и вывести результат.

Использовать дополнительные процессы запрещено.


### [Problem sm14-1: posix/exec/exec-gcc](https://github.com/arovesto/mipt-caos/blob/master/task14_1.c)

Программе на стандартном потоке ввода задается выражение в синтаксисе языка Си.

Необходимо вычислить значение этого выражения (итоговый результат представим типом int) и вывести его на стандартный поток вывода.
