## Java Basic Syntax

[1. Что такое виртуальная машина?](#1-Что-такое-виртуальная-машина)

[2. К какому типу языка программирование относится Java?](#2-К-какому-типу-языка-программирование-относится-Java)

[3. Из каких компонентов состоит Java (JDK, JRE, JVM)?](#3-Из-каких-компонентов-состоит-Java-JDK-JRE-JVM)

[4. Для чего используется JDK?](#4-Для-чего-используется-JDK)

[5. Для чего используется JRE?](#5-Для-чего-используется-JRE)

[6. Для чего используется VM?](#6-Для-чего-используется-VM)

[7. Что такое переменная?](#7-Что-такое-переменная)

[8. Расскажите про примитивные типы?](#8-Расскажите-про-примитивные-типы)

[9. Описать шаги для компиляции и запуска приложения в консоли (javac java)?](#9-Описать-шаги-для-компиляции-и-запуска-приложения-в-консоли-javac-java)

[10. Расскажите о конструкциях ветвления (if, else, switch, тернарное выражение)?](#10-Расскажите-о-конструкциях-ветвления-if-else-switch-тернарное-выражение)

[11. Расскажите о таблице истинности?](#11-Расскажите-о-таблице-истинности)

[12. Расскажите про отличия || &&.](#12-Расскажите-про-отличия-)

[13. Что такое тернарное условие?](#13-Что-такое-тернарное-условие)

[14. Что такое циклы и для чего они используются?](#14-Что-такое-циклы-и-для-чего-они-используются)

[15. Для чего используется цикл for?](#15-Для-чего-используется-цикл-for)

[16. Для чего используется цикл foreach?](#16-Для-чего-используется-цикл-foreach)

[17. Для чего используется цикл while?](#17-Для-чего-используется-цикл-while)

[18. Для чего используется цикл do while?](#18-Для-чего-используется-цикл-do-while)

[19. Что такое массив?](#19-Что-такое-массив)

[20. Как создать массив?](#20-Как-создать-массив)

[21. Как присвоить значение ячейке массива?](#21-Как-присвоить-значение-ячейке-массива)

[22. Как можно пройти по всем элементам массива?](#22-Как-можно-пройти-по-всем-элементам-массива)

[23. Как можно найти элемент в массиве?](#23-Как-можно-найти-элемент-в-массиве)

[24. Что будет, если записать элемент по индексу -1?](#24-Что-будет-если-записать-элемент-по-индексу--1)

[25. Как удалить ячейку в массиве?](#25-Как-удалить-ячейку-в-массиве)

[26. Как отредактировать ячейку в массиве?](#26-Как-отредактировать-ячейку-в-массиве)

[27. Что такое Java code conventions?](#27-Что-такое-java-code-conventions)

[28. Что такое Unicode?](#28-Что-такое-unicode)

[29. Что такое автобоксинг и анбоксинг?](#29-Что-такое-автобоксинг-и-анбоксинг)

[30. Как в Java передаются параметры в методы?](#30-Как-в-Java-передаются-параметры-в-методы)

[31. Почему нельзя изменить ссылку на объект в методе?](#31-Почему-нельзя-изменить-ссылку-на-объект-в-методе)

[32. Почему нельзя сравнивать ссылочные типы по оператору ==?](#32-Почему-нельзя-сравнивать-ссылочные-типы-по-оператору-)

[33. Почему примитивные типы можно сравнивать через оператор ==?](#33-Почему-примитивные-типы-можно-сравнивать-через-оператор-)

[34. Какие объекты могут быть использованы в операторе switch?](#34-Какие-объекты-могут-быть-использованы-в-операторе-switch)

## 1. Что такое виртуальная машина?

Виртуальная машина - это программная копия физического компьютера, которая выполняет ПО написанное под конкретную платформу,
переводя скомпилированный байт-код в машинные операции. Виртуальная машина позволяет запустить байт-код на любых операционных системах.

Java virtual machine (JVM) - это программа, предназначенная для выполнения других программ. JVM является сердцем языка 
программирования Java. Когда мы запускаем программу, JVM несёт ответственность за преобразование байт-кода в машинный 
код. JVM предоставляет основные функции, такие как управление памятью Java, сборкой мусора. JVM является виртуальной 
машиной, потому что обеспечивает интерфейс, который не зависит от операционной системы и аппаратных средств. Эта 
независимость от аппаратного обеспечения и операционной системы дает Java-программам возможность выполняться на любом 
устройстве без необходимости внесения изменений - Write once, run anywhere (Напиши раз - запускай где угодно).

[к оглавлению](#java-basic-syntax)

## 2. К какому типу языка программирование относится Java?

Язык Java был создан в 1995 году в компании Sun Microsystems под руководством Джеймса Гослинга и Патрика Нотона.
Работа над этим языком началась четырьмя годами ранее, тогда он назывался Oak. Но лишь в 1995 Java стал называться именно 
так. Изначально он задумывался как язык для различных бытовых устройств – кофеварок, телевизоров и так далее. На тот 
момент стало понятно, что для создания универсального инструмента для работы с совершенно разными устройствами требовалось 
что-то новое. Поэтому было решено, что java-код будет компилироваться в промежуточный байт-код (каждая инструкция кодируется 
1 байтом) для виртуальной машины, а она уже, в свою очередь, выполняет байт-код для каждой конкретной платформы.

Разработчики Java уделяли большое внимание переносимости, надежности и безопасности — тем аспектам, которые были важны 
именно в рамках сети Интернет. Инженеры из Sun большую часть своего времени работали с Unix-системами и языком C, который 
был популярным на то время, а потому и сам Java получил С-подобный синтаксис. Вообще язык Java в некотором смысле был 
призван использовать все возможности языков C/C++, но при этом решить большую часть проблем, которые возникали при работе 
с ними. Java стал полностью объектно-ориентированным языком, а быстрорастущее количество сетевых библиотек, а также 
поддержка многопоточности, только увеличивали популярность языка.

Java является строго типизированным объектно-ориентированным языком программирования общего назначения.

[к оглавлению](#java-basic-syntax)

## 3. Из каких компонентов состоит Java (JDK, JRE, JVM)?

Исторически, вы загружали только JRE, если вас интересовали только программы Java. JRE включает, помимо прочего, 
виртуальную машину Java (JVM) и инструмент командной строки «java».

Для разработки новых программ на Java вам нужно было загрузить JDK. JDK включает в себя все, что есть в JRE, а также 
компилятор javac и несколько других инструментов, таких как javadoc (генератор документации Java) и jdb (отладчик Java).

JDK и JRE содержат JVM, которая нужна для запуска программ на Java. JVM является сердцем языка программирования Java и 
обеспечивает независимость от платформы.

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

## 7. Что такое переменная?

Переменная - это поименованная область памяти, в которую мы можем сохранить данные, осуществлять доступ к этим данным или 
изменять их. Простыми словами, переменная в программировании, и в Java в том числе, является основной единицей хранения 
информации. В Java у переменной должен быть **тип**, **имя** и **значение**.

+ **Тип** - это тип данных переменной, которую необходимо создать. Переменная может быть как примитивного типа, так и являться 
  экземпляром какого-либо класса.
+ **Имя** или **Идентификатор** - любую переменную нужно как-то обозвать. А даем мы имя переменной сразу после указания 
  типа данных. Именем переменной может быть любая последовательность букв, цифр, но имя не может начинаться с цифры! При 
  наименовании переменной так же учитывается регистр символов. abc и ABC будут разными именами. Еще можно встретить 
  переменные, имя которых начинается с символа валюты доллара: $ Например: double $pi = 3.14. Переменные принято называть 
  в lowerCamelCase стиле. 
+ Важно запомнить, что если где-то в коде Java, а также во многих других языках, увидите знак равенства =, нужно понимать, 
  что это не сравниваются два значения. Это **оператор присваивания**. Его задача: взять значение, которое стоит справа от него,
  и записать в память переменной, которая стоит слева от него. Другими словами присвоить. Важно, чтобы значения справа 
  и слева были одного типа данных в противном случае получаем ошибку.
+ Процесс присвоения начального **значения** называется инициализацией переменной. И не обязательно инициализировать переменную 
  во время ее объявления. Java позволяет сделать это и позже.

[к оглавлению](#java-basic-syntax)

## 8. Расскажите про примитивные типы?

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

Кроме того, есть ключевое слово void — в java оно типом не является и может использоваться только перед именем функции,
указывая, что она ничего не возвращает.

[к оглавлению](#java-basic-syntax)

## 9. Описать шаги для компиляции и запуска приложения в консоли (javac java)?

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

## 10. Расскажите о конструкциях ветвления (if, else, switch, тернарное выражение)?

Операторы условия позволяют направить работы программы по одному из путей в зависимости от определенных условий.

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

## 11. Расскажите о таблице истинности?

Таблица истинности — таблица, описывающая логическую функцию.

Под «логической функцией» в данном случае понимается функция, у которой значения переменных (параметров функции) и значение 
самой функции выражают логическую истинность. Например, в двузначной логике они могут принимать значения «истина» либо «ложь» 
(true либо false, 1 либо 0).

|  `A`  |  `B`  | `A and B` | `A or B` | `A ^ B` | `!A`  |
| ----- | ----- | --------- | ------- | ------- | ----- |
| false | false |   false   |  false  |  false  | true  |
| true  | false |   false   |  true   |  true   | false |
| false | true  |   false   |  true   |  true   | true  |
| true  | true  |   true    |  true   |  false  | false |

[к оглавлению](#java-basic-syntax)

## 12. Расскажите про отличия || &&.

Логические операторы работают только с операндами типа boolean. Все логические операторы с двумя операндами объединяют 
два логических значения, образуя результирующее логическое значение. Таблица логических операторов в Java.

+ `&` - Логическое AND (И)
+ `&&` - Сокращенное AND
+ `|` - Логическое OR (ИЛИ)
+ `||` - Сокращенное OR
+ `^` - Логическое XOR (Исключающее OR(ИЛИ))

Кроме стандартных операторов AND (&) и OR (|) существуют сокращенные операторы && и ||.

Результат выполнения оператора OR равен true, когда значение операнда A равно true, независимо от значения операнда B. 
Аналогично, результат выполнения оператора AND равен false, когда значение операнда A равно false, независимо от 
значения операнда B. Получается, что нам не нужно вычислять значение второго операнда, если результат можно определить 
уже по первому операнду. Это становится удобным в тех случаях, когда значение правого операнда зависит от значения 
левого.

[к оглавлению](#java-basic-syntax)

## 13. Что такое тернарное условие?

В языке Java есть также специальный тернарный условный оператор, которым можно заменить определенные типы операторов 
if-then-else - это оператор ?:

Тернарный оператор использует три операнда. Выражение записывается в следующей форме: 
`ЛогическоеУсловие` **?** `Выражение 1` **:** `Выражение2`

[к оглавлению](#java-basic-syntax)

## 14. Что такое циклы и для чего они используются?

Цикл - это выполнение одного и того же кода определенное количество раз. Циклом называется многократное выполнение 
одних и тех же действий. Например, чтобы программа сосчитала от 1, скажем, до миллиона, в ней нужно записать цикл. 
Цикл - это та часть кода, которая выполняется заданное количество раз.

[к оглавлению](#java-basic-syntax)

## 15. Для чего используется цикл for?

Цикл for проводит инициализацию перед первым шагом цикла. Затем выполняется проверка условия цикла, и в конце каждой 
итерации происходит изменение управляющей переменной. Любое из трех выражений цикла (инициализация, логическое выражение 
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

## 16. Для чего используется цикл foreach?

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

## 17. Для чего используется цикл while?

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

## 18. Для чего используется цикл do while?

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

## 19. Что такое массив?

Массив - это структура данных, в которой хранятся элементы одного типа. Его можно представить, как набор пронумерованных 
ячеек, в каждую из которых можно поместить какие-то данные (один элемент данных в одну ячейку).

[к оглавлению](#java-basic-syntax)

## 20. Как создать массив?

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

В случае с массивом ссылок на объекты важно помнить, что при создании массива сами объекты не создаются. К примеру, 
код ```Thread threads = new Thread [20]``` создаст массив из двадцати null'ов, никаких конструкторов вызываться не будет.

[к оглавлению](#java-basic-syntax)

## 21. Как присвоить значение ячейке массива?

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

## 23. Как можно найти элемент в массиве?

Стандартным перебором и условным оператором, или же бинарным поиском в отсортированном массиве.

[к оглавлению](#java-basic-syntax)

## 24. Что будет, если записать элемент по индексу -1?

Будет выброшено исключение - `ArrayIndexOutOfBoundsException`. Программа немедленно прекратит выполнение. Не может быть
индекса -1. Индексация начинается с 0.

[к оглавлению](#java-basic-syntax)

## 25. Как удалить ячейку в массиве?

Длину массива изменить нельзя. Удалить ячейку невозможно. Можно только изменить значение в конкретной ячейке обратившись по индексу.

[к оглавлению](#java-basic-syntax)

## 26. Как отредактировать ячейку в массиве?

Обращение к элементу массива происходит по имени массива, за которым следует значение индекса элемента, заключенного в 
квадратные скобки. Чтобы отредактировать значение ячейки массива, нужно обратиться к ячейке массива по только что 
сказанной мной конструкции и можно, как и обычной переменной присвоить значение через знак равно и какое-либо значение.

[к оглавлению](#java-basic-syntax)

## 27. Что такое Java code conventions?

**Java Code Conventions** - это соглашение по правилам оформления кода.

Это соглашение, в котором описаны рекомендации к написанию базовых конструкций языка Java - оформление отступов, пробелов, 
наименование переменных, методов и т.д. Благодаря таким соглашениям унифицируется "почерк" разработчика. Код, написанный в 
едином стиле, проще читать, акцентируя внимание на деталях, а не на попытках понять как устроен сам код.

Разработчики пришли к единому мнению о создании соглашений по оформлению кода по нескольким причинам:

- Основная часть кода пишется при создании приложения, дальше идет поддержка существующего кода - редактирование, 
  добавление новых функций, удаление старых функций и т.д.
- Единое оформление помогает читать и понимать код быстрее. Это важно, так как над проектом может работать не только 
  отдельная группа разработчиков, а несколько таких групп, включая другие отделы компании, которые тоже работают с кодом.
- В процессе работы одни разработчики могут сменяться другими, и единое оформление позволит быстрее разобраться в новом 
  проекте новым сотрудникам.

Нужно иметь в виду, что в каждой компании могут быть свои особенности по оформлению кода. Соглашения - это просто 
рекомендации по оформлению кода.

[к оглавлению](#java-basic-syntax)

## 28. Что такое Unicode?

В Java символы представлены набором символов Unicode (Юникод). Набор символов Юникод включает в себя полный набор символов
на многих языках мира. Юникод унифицирует разнообразные символы разных языков мира, то есть каждый уникальный символ имеет 
свой уникальный номер в таблице Юникод. В том числе, например, латинская и кириллическая буквы "А" имеют каждая свои 
уникальные коды. В зависимости от версии, в Java поддерживаются разные версии Юникода, символов которой на момент написания 
этого урока насчитывается почти 144 тысячи. Для хранения символов в Java используется тип char, который занимает 2 байта
памяти - диапазон от 0 до 65535. Отрицательных значений char не имеет. Более 65536 значений из таблицы Юникод в Java в 
виде типа данных char не представить, символы вне диапазона 0-65535 представляются типом String или Character, но это 
очень редкое явление, так как все символы самых популярных языков мира находятся в начале таблицы.

В таблице Юникод символы записаны в шестнадцатеричном виде (U+xxxx). В Java представить символ Юникода можно в виде 
\u + номер символа в шестнадцатеричном виде из таблицы Юникод.

В типе char хранится не сам символ, а его код из набора символов Юникод. Не путать Юникод с кодировкой! Юникод - это 
просто таблица с уникальными кодами символов, а кодировка - это алгоритм перевода чисел в двоичный формат. По умолчанию 
виртуальная машина Java (JVM) использует кодировку UTF-8. Все наши файлы должны быть в кодировке UTF-8, чтобы не возникало
конфликтов между кодировками.

[к оглавлению](#java-basic-syntax)

## 29. Что такое автобоксинг и анбоксинг?

**автобоксинг** - автоматическая конвертация компилятором между примитивными типами и классами обертками.
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

## 30. Как в Java передаются параметры в методы?

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

## 31. Почему нельзя изменить ссылку на объект в методе?

Потому что в метод передается не ссылка, а объект, который содержит копию ссылки.

Внутри метода можно изменить локальную ссылку на объект, но это не повлияет на ссылку, которую передали в метод.

[к оглавлению](#java-basic-syntax)

## 32. Почему нельзя сравнивать ссылочные типы по оператору ==?

Потому, что будут сравниваться адреса в памяти на которые указывают ссылки, а не сами объекты. И они буду отличаться.

Чтобы сравнить объекты нужно использовать метод `equals()`

[к оглавлению](#java-basic-syntax)

## 33. Почему примитивные типы можно сравнивать через оператор ==?

Потому, что эти типы содержат значения, и оператором `==` буду сравниваться значения этих переменных.

[к оглавлению](#java-basic-syntax)

## 34. Какие объекты могут быть использованы в операторе switch?

Можно использовать простые типы `byte`, `short`, `char`, `int`. Также можно использовать строки `String` и `Enum`,
а также специальные классы, которые являются обёрткой для примитивных типов: `Character`, `Byte`, `Short`, `Integer`.

[к оглавлению](#java-basic-syntax)
