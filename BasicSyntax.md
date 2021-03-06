## Java Basic Syntax

[1. Что такое виртуальная машина?](#1-Что-такое-виртуальная-машина)

[2. К какому типа языка программирование относиться Java?](#2-К-какому-типа-языка-программирование-относиться-Java)

[3. Из каких компонентов состоит Java (JDK, JRE, JVM)?](#3-Из-каких-компонентов-состоит-Java-JDK-JRE-JVM)

[4. Для чего используется JDK?](#4-Для-чего-используется-JDK)

[5. Для чего используется JRE?](#5-Для-чего-используется-JRE)

[6. Для чего используется VM?](#6-Для-чего-используется-VM)

[7. Расскажите про примитивные типы?](#7-Расскажите-про-примитивные-типы)

[8. Описать шаги для компиляции и запуска приложения в консоли (javac java)?](#8-Описать-шаги-для-компиляции-и-запуска-приложения-в-консоли-javac-java)

[9. Что такое "оператор условия"?](#9-Что-такое-оператор-условия)

[10. Какие типы операторов условия существуют?](#10-Какие-типы-операторов-условия-существуют)

[11. Расскажите про булевы операции || &&? Расскажите элементы таблицы истинности?](#11-расскажите-про-булевы-операции---расскажите-элементы-таблицы-истинности)

[12. Что такое тернарное условие?](#12-Что-такое-тернарное-условие)

[13. Что такое циклы и для чего они используются?](#13-Что-такое-циклы-и-для-чего-они-используются)

[14. Для чего используется цикл for?](#14-Для-чего-используется-цикл-for)

[15. Для чего используется цикл foreach?](#15-Для-чего-используется-цикл-foreach)

[16. Для чего используется цикл while?](#16-Для-чего-используется-цикл-while)

[17. Для чего используется цикл do while?](#17-Для-чего-используется-цикл-do-while)

[18. Что такое массив?](#18-Что-такое-массив)

[19. Как создать массив?](#19-Как-создать-массив)

[20. Как присвоить значение ячейке массива?](#20-Как-присвоить-значение-ячейке-массива)

[21. Как можно пройти по всем элементам массива?](#21-Как-можно-пройти-по-всем-элементам-массива)

[22. Как можно найти элемент в массиве?](#22-Как-можно-найти-элемент-в-массиве)

[23. Что будет, если записать элемент по индексу -1?](#23-Что-будет-если-записать-элемент-по-индексу--1)

[24. Как удалить ячейку в массиве?](#24-Как-удалить-ячейку-в-массиве)

[25. Как отредактировать ячейку в массиве?](#25-Как-отредактировать-ячейку-в-массиве)

[26. Что такое автобоксинг и анбоксинг?](#26-Что-такое-автобоксинг-и-анбоксинг)

[27. Как в Java передаются параметры в методы?](#27-Как-в-Java-передаются-параметры-в-методы)

[28. Почему нельзя изменить ссылку на объект в методе?](#28-Почему-нельзя-изменить-ссылку-на-объект-в-методе)

[29. Почему нельзя сравнивать ссылочные типы по оператору ==?](#29-Почему-нельзя-сравнивать-ссылочные-типы-по-оператору-)

[30. Почему примитивные типы можно сравнивать через оператор ==?](#30-Почему-примитивные-типы-можно-сравнивать-через-оператор-)

[31. Какие объекты могут быть использованы в операторе switch?](#31-Какие-объекты-могут-быть-использованы-в-операторе-switch)

## 1. Что такое виртуальная машина?

Виртуальная машина — это программная и/или аппаратная система, эмулирующая аппаратное обеспечение гостевой (target)
платформы и исполняющая программы для target-платформы на host-платформе (платформа-хозяин) или виртуализирующая 
некоторую платформу и создающая на ней среды, изолирующие друг от друга программы и даже операционные системы.

т.е. по-простому VM - это программная копия физического компьютера, которая выполняет ПО написанное под конкретную платформу,
переводя скомпилированный байт-код в машинные операции.

Java virtual machine (JVM) - это программа, предназначенная для выполнения других программ. JVM является сердцем языка 
программирования Java. Когда мы запускаем программу, JVM несёт ответственность за преобразование байт-кода в машинный 
код. JVM предоставляет основные функции, такие как управление памятью Java, сборкой мусора. JVM является виртуальной 
машиной, потому что обеспечивает интерфейс, который не зависит от операционной системы и аппаратных средств. Эта 
независимость от аппаратного обеспечения и операционной системы дает Java-программам возможность выполняться на любом 
устройстве без необходимости внесения изменений - Write once, run anywhere (Напиши раз - запускай где угодно).

[к оглавлению](#java-basic-syntax)

## 2. К какому типа языка программирование относиться Java?

Java является строго типизированным объектно-ориентированным языком программирования общего назначения.

[к оглавлению](#java-basic-syntax)

## 3. Из каких компонентов состоит Java (JDK, JRE, JVM)?

JDK нужен для разработки (это компилятор, отладчик и т.д.). JRE нужен для запуска Java программ. JDK и JRE содержат
JVM, которая нужна для запуска программ на Java. JVM является сердцем языка программирования Java и обеспечивает 
независимость от платформы.

+ JVM — это часть платформы Java, которая исполняет программы;

+ JRE — это элемент Java, расположенный на диске, создающий и запускающий JVM;

+ JDK - позволяет разработчикам создавать Java-программы, которые могут выполняться и запускаться посредством JVM и JRE.
  JDK = JRE + компилятор

[Что такое JDK? Введение в средства разработки Java](https://topjava.ru/blog/what-is-the-jdk)

[к оглавлению](#java-basic-syntax)

## 4. Для чего используется JDK?

Java Development Kit является основным компонентом среды Java и предоставляет все инструменты, исполняемые и бинарные 
файлы, которые нужны для компиляции, отладки и выполнения программы на Java. JDK является платформо-зависимым 
программным обеспечением, поэтому есть отдельные инсталляторы для Windows, Mac и Unix-систем. Можно сказать, что JDK 
является надстройкой JRE, так как он содержит JRE с Java-компилятором, отладчиком и базовыми классами.

+ Техническое определение: JDK — это реализация спецификации платформы Java, включающая в себя компилятор и библиотеки классов.

+ Обобщенное определение: JDK — это программный пакет, который вы загружаете для создания Java приложений.

[к оглавлению](#java-basic-syntax)

## 5. Для чего используется JRE?

JRE является реализацией JVM, которая предоставляет платформу для выполнения Java-программ. JRE состоит из виртуальной 
машины Java, бинарных файлов и других классов. JRE не содержит инструменты для разработки (компилятор Java, отладчик и 
т.д.). Если вы хотите запустить любую Java программу, вы должны установить JRE.

[к оглавлению](#java-basic-syntax)

## 6. Для чего используется VM?

JVM имеет две основные функции: 1) Позволяет запускать Java-приложения на любых устройствах или операционных системах 
(принцип - "Написал один раз, запускай везде"). 2) Управляет и оптимизирует память, используемую приложением.

[к оглавлению](#java-basic-syntax)

## 7. Расскажите про примитивные типы?

В Java есть 8 примитивных типов, которые делят на 4 группы, вот они:
1) Целые числа - byte, short, int, long
2) Числа с плавающей точкой (иначе вещественные) - float, double
3) Логический - boolean.
4) Символьный - char.

Целочисленные типы различаются между собой только диапазонами возможных значений.

+ `byte` (целые числа, 1 байт или 8 бит, интервал значений [-128, 127] т.е. 2^7, т.к. отрицательные, ноль и положительные)
+ `short` (целые числа, 2 байта или 16 бит, [-32768, 32767])
+ `int` (целые числа, 4 байта, [-2147483648, 2147483647])
+ `long` (целые числа, 8 байт, [-9223372036854775808, 9223372036854775807])
+ `float` (вещественные числа, 4 байта, [-3.4E+38, 3.4E+38])
+ `double` (вещественные числа, 8 байт, [-1.7E+308, 1.7E+308])
+ `char` (символ `Unicode`, 2 байта, [0, 65536])
+ `boolean` (значение истина/ложь, используется `int`, зависит от JVM)

Примитивы передаются по значению.

**Классы-обертки** - соответствуют примитивным типам, однако являются ссылочными, содержат методы для преобразования типов,
а также другие константы и методы полезные при работе с примитивами.

+ `Byte`
+ `Short`
+ `Integer`
+ `Long`
+ `Float`
+ `Double`
+ `Character`
+ `Boolean`

Классы-обертки позволяют нивелировать недостатки, которые есть у примитивных типов. Самый очевидный из них — примитивы 
не имеют методов.


**Пример 1.** у примитивов нет метода `toString()`, поэтому, например, нельзя преобразовать число типа `int` в строку.
А вот с классом-оберткой `Integer` — запросто.
```java
public static void main(String[] args) {
   Integer i = new Integer(432);
   String s = i.toString();
}
```

**Пример 2.** сложности с обратным преобразованием. Допустим, у нас есть строка, которая содержит число.                                                    
В случае с примитивным типом `int` это число из строки нельзя достать и превратить, собственно, в число.
Но благодаря классам-оберткам такая возможность имеется.

```java
public static void main(String[] args) {
   String s = "1166628";
   Integer i = Integer.parseInt(s);
   System.out.println(i);
}
```

**Автобоксинг** - помещение примитивного типа в класс-обертку.

**Анбоксинг** - присвоение значения класса-обертки примитивному типу.

[к оглавлению](#java-basic-syntax)

## 8. Описать шаги для компиляции и запуска приложения в консоли (javac java)?

Создаем класс - файл с расширением *.java
`Main.java`

Переходим в каталог, где лежит данный файл,
и запускаем компилятор javac, где указываем что компилируем и куда складываем
`javac -d куда Main.java`

На выходе получаем файл `Main.class` - это байт-код.

Далее запускаем байт-код, расширение можно не указывать
`java -cp откуда Main arg0 arg1 arg2`

[Работа с Java в командной строке](https://habr.com/ru/post/125210/)

[к оглавлению](#java-basic-syntax)

## 9. Что такое "оператор условия"?

Операторы условия позволяют направить работы программы по одному из путей в зависимости от определенных условий. 

[к оглавлению](#java-basic-syntax)

## 10. Какие типы операторов условия существуют?

В языке Java используются следующие условные конструкции: if..else и switch..case. Выражение if/else проверяет 
истинность некоторого условия и в зависимости от результатов проверки выполняет определенный код, который помещен в 
блоке после фигурных скобок. Конструкция switch/case аналогична конструкции if/else, так как позволяет обработать сразу
несколько условий. После ключевого слова switch в скобках идет сравниваемое выражение. значение этого выражения 
последовательно сравнивается со значениями, помещенными после операторов case. И если совпадение найдено, то будет 
выполнен соответствующий блок case.

+ Конструкция `if-else`
```java
if (условие) {
    оператор1;
    оператор2;
} else {
    оператор1;
    оператор2; 
}
```  
+ Множественное условие `switch`
```java
switch(i) {
    case 1:
        System.out.println("Тест работает.");
        break;
    case 2:
        System.out.println("Тест добрый.");
        break;
    case 3:
        System.out.println("Тест поможет вам.");
        break;
    }
``` 

+ Тернарный оператор `Логическое_выражение ? Выражение1 : Выражение2`
```java
int largerNum = lowNum < highNum ? highNum : lowNum; 
```

[к оглавлению](#java-basic-syntax)

## 11. Расскажите про булевы операции || &&? Расскажите элементы таблицы истинности?

Логические операторы работают только с операндами типа boolean. Все логические операторы с двумя операндами объединяют 
два логических значения, образуя результирующее логическое значение. Таблица логических операторов в Java.

+ `&` - Логическое AND (И)
+ `&&` - Сокращенное AND
+ `|` - Логическое OR (ИЛИ)
+ `||` - Сокращенное OR
+ `^` - Логическое XOR (Исключающее OR(ИЛИ))

|  `A`  |  `B`  | `A and B` | `A & B` | `A ^ B` | `!A`  |
| ----- | ----- | --------- | ------- | ------- | ----- |
| false | false |   false   |  false  |  false  | true  |
| true  | false |   false   |  true   |  true   | false |
| false | true  |   false   |  true   |  true   | true  |
| true  | true  |   true    |  true   |  false  | false |

Кроме стандартных операторов AND (&) и OR (|) существуют сокращенные операторы && и ||.

Результат выполнения оператора OR равен true, когда значение операнда A равно true, независимо от значения операнда B. 
Аналогично, результат выполнения оператора AND равен false, когда значение операнда A равно false, независимо от 
значения операнда B. Получается, что нам не нужно вычислять значение второго операнда, если результат можно определить 
уже по первому операнду. Это становится удобным в тех случаях, когда значение правого операнда зависит от значения 
левого.

[к оглавлению](#java-basic-syntax)

## 12. Что такое тернарное условие?

В языке Java есть также специальный тернарный условный оператор, которым можно заменить определенные типы операторов 
if-then-else - это оператор ?:

Тернарный оператор использует три операнда. Выражение записывается в следующей форме: 
`ЛогическоеУсловие` **?** `Выражение 1` **:** `Выражение2`

[к оглавлению](#java-basic-syntax)

## 13. Что такое циклы и для чего они используются?

Цикл - это выполнение одного и того же кода определенное количество раз. Циклом называется многократное выполнение 
одних и тех же действий. Например, чтобы программа сосчитала от 1, скажем, до миллиона, в ней нужно записать цикл. 
Цикл - это та часть кода, которая выполняется заданное количество раз.

[к оглавлению](#java-basic-syntax)

## 14. Для чего используется цикл for?

Цикл for проводит инициализацию перед первым шагом цикла. Затем выполняется проверка условия цикла, и в конце каждой 
итерации происходит изменение управляющей переменной.Любое из трех выражений цикла (инициализация, логическое выражение 
или шаг) можно пропустить. Перед выполнением каждого шага цикла проверяется условие цикла. Если условие окажется ложным,
то выполнение цикла прервется. Как правило, цикл for используют для перебора.

`for` - цикл типа "n-раз"
```java
for (int i = 0; i < n; i++) {
    оператор1;
    оператор2;
} 
```

[к оглавлению](#java-basic-syntax)

## 15. Для чего используется цикл foreach?

Цикл foreach - это разновидность цикла for, которая используется для перебора элементов массивов и коллекций. 
Конструкция foreach не требует ручного изменения переменной-шага для перебора - цикл автоматически выполняет эту работу.
Имеет вид: for(тип итер_пер : коллекция). В цикле foreach итерационная переменная доступна только для чтения, так как 
она связана только с исходным массивом. Даже если вы измените её значение, то это не повлияет на работу с массивом.

```java
//argv - коллекция/массив
for (String str: argv) {
    оператор1;
    оператор2;
} 
```

[к оглавлению](#java-basic-syntax)

## 16. Для чего используется цикл while?

Когда заранее неизвестно количество повторений, используется цикл while. Он повторяет оператор или блок операторов до 
тех пор, пока значение его управляющего выражения истинно. Всегда перед выполнением цикла идет предварительное 
вычисление логического выражения (условие входа в цикл).

`while` - цикл "пока"
```java
while (условие) {
    оператор1;
    оператор2;
} 
```

[к оглавлению](#java-basic-syntax)

## 17. Для чего используется цикл do while?

Два основных отличия от цикла while. Тело цикла как минимум выполняется один раз и логическое условие проверяется после 
выполнения тела цикла. Как пример где можно встретить - если обязательно нужно о чем-то спросить пользователя, а от его 
ответа зависит, будет ли выведено опять вопрос пользователю.

```java
do {
    оператор1;
    оператор2;
} while (условие);
```

[к оглавлению](#java-basic-syntax)

## 18. Что такое массив?

Массив - это структура данных, в которой хранятся элементы одного типа. Его можно представить, как набор пронумерованных 
ячеек, в каждую из которых можно поместить какие-то данные (один элемент данных в одну ячейку).

[к оглавлению](#java-basic-syntax)

## 19. Как создать массив?

Как и любой другой объект, создать массив Java, то есть зарезервировать под него место в памяти, можно с помощью оператора new. 
Делается это так: 
```java
type[] array = new type[length];
```
Где `type` - это тип массива, а `length` - его длина, выраженная в целых числах. После создания массива с помощью new, 
в его ячейках записаны значения по умолчанию. Для численных типов это будет `0`, для boolean - `false`, для ссылочных 
типов - `null`. Длину массива нельзя изменить после его создания.

Так же можно не указывать кол-во элементов, а сразу их объявить:
```java
int[] array = new int[]{1, 2, 3};
int[] array_quick = {1, 2, 3};
```

Можно сделать безымянный массив:
```java
new int[]{1, 2, 3, 4, 5};
```

[к оглавлению](#java-basic-syntax)

## 20. Как присвоить значение ячейке массива?

Обращение к элементу массива происходит по имени массива, за которым следует значение индекса элемента, заключенного в 
квадратные скобки. Соответственно, чтобы присвоить значение ячейке массива, нужно обратиться к ячейке массива по только 
что сказанной мной конструкции и элементу массива можно будет присвоить значение.

Присвоение ячейке с индексом `0`. Пример:
```java
array[0] = 1;
```

[к оглавлению](#java-basic-syntax)

## 21. Как можно пройти по всем элементам массива?

С помощью циклов `for` или `foreach`

Первый вариант:
```java
for(int value : values) {
    System.out.println(value);
}
```
Второй вариант:
```java
for(int i = 0; i < values.length; i++) {
    System.out.println(values[i]);
}
```

[к оглавлению](#java-basic-syntax)

## 22. Как можно найти элемент в массиве?

Стандартным перебором и условным оператором, или же бинарным поиском.

[к оглавлению](#java-basic-syntax)

## 23. Что будет, если записать элемент по индексу -1?

Будет выброшено исключение - `ArrayIndexOutOfBoundsException`. Программа немедленно прекратит выполнение. Не может быть
индекса -1. Индексация начинается с 0.

[к оглавлению](#java-basic-syntax)

## 24. Как удалить ячейку в массиве?

Длину массива изменить нельзя. Удалить ячейку невозможно. Можно только изменить значение в конкретной ячейке обратившись по индексу.

[к оглавлению](#java-basic-syntax)

## 25. Как отредактировать ячейку в массиве?

Обращение к элементу массива происходит по имени массива, за которым следует значение индекса элемента, заключенного в 
квадратные скобки. Чтобы отредактировать значение ячейки массива, нужно обратиться к ячейке массива по только что 
сказанной мной конструкции и можно, как и обычной переменной присвоить значение через знак равно и какое-либо значение.

[к оглавлению](#java-basic-syntax)

## 26. Что такое автобоксинг и анбоксинг?

**автобоксинг** - автоматическая ковенвертация компилятором между примитивными типами и классами обертками.
`Character ch = 'a';`
Компилятор делает автоматическое преобразование по типу `Integer.valueOf(i)`

Преобразование происходит в случаях:
+ когда параметр передается в метод в котором ожидается класс обертками;
+ когда идет присвоение классу обертке.

**анбоксинг** - обратная операция преобразование из обертки в примитив.

Например:
```java
Integer i; 
i = i % 2;
``` 
Т.к. операция % применима только к примитивам, то происходит `i.intValue() % 2`

Преобразование происходит в случаях:
+ когда параметр передается в метод в котором ожидается класс-обертка;
+ когда идет присвоение классу-обертке.

[к оглавлению](#java-basic-syntax)

## 27. Как в Java передаются параметры в методы?

**В Java параметры в методы передаются по значению.** т.е. в методе создается локальная переменная аргумента и
ей присваивается значение передаваемого параметра. Всегда:

+ для примитивов передается копия значения,

+ для объектов передается **копия** ссылки (а не сама ссылка).
  Это значит, что нельзя поменять ссылку в методе. Можно только поменять сам объект по ссылке.
  В примере ниже после выхода из метода в stroka сохранится ссылка на "MY SIMPLE STRING";

```java
public class TestClass { 
    
    public static void changeIt(String stroka) { 
        stroka = "ANOTHER SIMPLE STRING"; 
    }

    public static void main(String[] args) { 
        String stroka = "MY SIMPLE STRING"; 
        System.out.println(stroka); //"MY SIMPLE STRING"
        changeIt(stroka); //передается копия ссылки!!!
        System.out.println(stroka); // "MY SIMPLE STRING" не изменилось
    } 
}
```

[к оглавлению](#java-basic-syntax)

## 28. Почему нельзя изменить ссылку на объект в методе?

Потому что в метод передается не ссылка, а объект, который содержит копию ссылки.

Внутри метода можно изменить локальную ссылку на объект, но это не повлияет на ссылку, которую передали в метод.

[к оглавлению](#java-basic-syntax)

## 29. Почему нельзя сравнивать ссылочные типы по оператору ==?

Потому, что будут сравниваться адреса в памяти на которые указывают ссылки, а не сами объекты. И они буду отличаться.

Чтобы сравнить объекты нужно использовать метод `equals()`

[к оглавлению](#java-basic-syntax)

## 30. Почему примитивные типы можно сравнивать через оператор ==?

Потому, что они эти типы содержат значения, и оператором `==` буду сравниваться значения этих переменных.

[к оглавлению](#java-basic-syntax)

## 31. Какие объекты могут быть использованы в операторе switch?

Можно использовать простые типы `byte`, `short`, `char`, `int`. Также можно использовать строки `String` и `Enum`,
а также специальные классы, которые являются обёрткой для примитивных типов: `Character`, `Byte`, `Short`, `Integer`.

[к оглавлению](#java-basic-syntax)
