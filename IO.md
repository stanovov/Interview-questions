## IO

[1. Что такое поток ввода-вывода?](#1-Что-такое-поток-вводавывода)

[2. Что такое Java IO?](#2-Что-такое-java-io)

[3. Что такое Java NIO?](#3-Что-такое-java-nio)

[4. Что такое Scanner?](#4-Что-такое-scanner)

[5. Как работает Scanner внутри?](#5-Как-работает-scanner-внутри)

[6. Какие базовые методы существуют в Scanner?](#6-Какие-базовые-методы-существуют-в-scanner)

[7. Что такое байтовый поток? Как он реализован внутри?](#7-Что-такое-байтовый-поток-Как-он-реализован-внутри)

[8. Что такое символьный поток? Как он реализован внутри?](#8-Что-такое-символьный-поток-Как-он-реализован-внутри)

[9. Что такое буферизированный поток?](#9-Что-такое-буферизированный-поток)

[10. Что такое форматированный вывод? Какие механизмы позволяют осуществить форматированный вызов?](#10-Что-такое-форматированный-вывод-Какие-механизмы-позволяют-осуществить-форматированный-вызов)

[11. Как осуществляется ввод и вывод из командной строки?](#11-Как-осуществляется-ввод-и-вывод-из-командной-строки)

[12. Что такое класс Console? Расскажите его АПИ.](#12-Что-такое-класс-console-Расскажите-его-АПИ)

[13. Что такое поток данных? Data stream.](#13-Что-такое-поток-данных-data-stream)

[14. Что такое поток объектов, Object stream.](#14-Что-такое-поток-объектов-object-stream)

[15. Что такое Path? Как он реализуется на разных ОС?](#15-Что-такое-path-как-он-реализуется-на-разных-ОС)

[16. Как получить список файлов?](#16-Как-получить-список-файлов)

[17. Как проверить что файловая сущность является файлом или папкой?](#17-Как-проверить-что-файловая-сущность-является-файлом-или-папкой)

[18. Как удалить файл?](#18-Как-удалить-файл)

[19. Как переместить файл?](#19-Как-переместить-файл)

[20. Как управлять аттрибутами файла?](#20-Как-управлять-аттрибутами-файла)

[21. Как создать файл?](#21-Как-создать-файл)

[22. Как создать директорию?](#22-Как-создать-директорию)

[23. Как записать в файл?](#23-Как-записать-в-файл)

[24. Как прочитать данные из файла?](#24-Как-прочитать-данные-из-файла)

[25. Что такое сокет?](#25-Что-такое-сокет)

[26. Какие виды сокетов есть в Java? С каким протоколом они работают?](#26-Какие-виды-сокетов-есть-в-java-С-каким-протоколом-они-работают)

[27. Как отправить через сокет сообщение?](#27-Как-отправить-через-сокет-сообщение)

[28. Что такое логирование?](#28-Что-такое-логирование)

[29. Какие уровни логирования вы знаете?](#29-Какие-уровни-логирования-вы-знаете)

[30. Какая библиотека для логгирования используется в курсе? Как ее настроить?](#30-Какая-библиотека-для-логгирования-используется-в-курсе-Как-её-настроить)

[31. Опишите из каких элементов состоит формат JSON?](#31-Опишите-из-каких-элементов-состоит-формат-json)

[32. Как преобразовать POJO в/из json?](#32-Как-преобразовать-pojo-виз-json)

[33. Опишите из каких элементов состоит формат XML?](#33-Опишите-из-каких-элементов-состоит-формат-xml)

[34. Как преобразовать POJO в/из xml?](#34-Как-преобразовать-pojo-виз-xml)

## 1. Что такое поток ввода/вывода?

Объект, из которого можно считать данные, называется **потоком ввода**, а объект, в который можно записывать данные - 
**потоком вывода**. Например, если надо считать содержание файла, то применяется поток ввода, а если надо записать в 
файл - поток вывода.

В основе всех классов, управляющих потоками байтов, находятся два абстрактных класса: **InputStream** (представляющий 
потоки ввода) и **OutputStream** (представляющий потоки вывода). Но поскольку работать с байтами не очень удобно, то для
работы с потоками символов были добавлены абстрактные классы **Reader** (для счтения потоков символов) и **Writer** (для
записи потоков символов). Все остальные классы, работающие с потоками, являются наследниками этих абстрактных классов.

[к оглавлению](#io)

## 2. Что такое Java IO?

IO API – (Input & Output) в первую очередь это Java API, которые облегчают работу с потоками.
В `java.io` существуют так называемые потоки ввода и вывода (`InputStream` and `OutputStream`).

В основном `java.io` предназначен для чтения и записи данных в ресурс:

1. файл
2. при работе с сетевым подключением
3. `System.err`, `System.in`, `System.out`
4. при работе с буфером

**Классы Java IO API**

**Базовые**

+ `InputStream` /` OutputStream` - абстрактные классы, определяющие байтовый поток ввода/вывода
+ `Reader` / `Writer` - абстрактные классы, определяющие символьный поток ввода/вывода
+ `InputStreamReader` / `OutputStreamWriter` Входной/выходной потоки, транслирующий байты в символы/символы в байты

**Массивы**
+ `ByteArrayInputStream` / `ByteArrayOutputStream` - позволяет использовать буфер в памяти (массив байтов) в качестве 
  источника данных для входного потока / все данные, посылаемые в этот поток, размещаются в предварительно созданном 
  буфере.
+ `CharArrayReader` / `CharArrayWriter` - читает/пишет из символьного массива.

**Files**
+ `FileInputStream` / `FileOutputStream` - Чтение/Запись данных побайтово в файл на диске.
+  `RandomAccessFile` - Чтение/Запись файлов с произвольным доступом. метод `seek()` позволяет переместиться к 
   определенной позиции и изменить хранящееся там значение. При использовании RandomAccessFile необходимо знать 
   структуру файла. Класс `RandomAccessFile` содержит методы для чтения и записи примитивов и строк UTF-8.
  `RandomAccessFile` может открываться в режиме чтения ("r") или чтения/записи ("rw"). Также есть режим "rws", когда файл
  открывается для операций чтения-записи и каждое изменение данных файла немедленно записывается на физическое устройство.
+ `FileReader` / `FileWriter` - входной/выходной потоки, читающий/записывающий в файл.

**Буферизация**
+ `BufferedInputStream` / `BufferedOutputStream` - буферизируемые байтовые потоки. Нужны для повышения производительности.
+ `BufferedReader` / `BufferedWriter` - буферизируемые символьные потоки. Нужны для повышения производительности.

[к оглавлению](#io)

## 3. Что такое Java NIO?

Пакет `java.nio` был представлен в Java 1.4. В отличие от **java I/O** в **java NIO** введен поток данных, 
ориентированный на буфер и канал, для операций ввода/вывода, что в результате обеспечивает более быстрое выполнение и 
лучшую производительность.

Также **NIO API** предлагает селекторы, которые вводят функциональность прослушивания нескольких каналов для событий
ввода-вывода асинхронным или неблокирующим способом. В NIO наиболее трудоемкие операции ввода-вывода, включая заполнение
и опустошение буферов для операционной системы, которые увеличиваются в скорости.

Основные абстракции API-интерфейсов NIO следующие:

+ Буферы, которые являются контейнерами для данных, набором символов и связанных с ними декодеров и кодеров, которые 
преобразуются между байтами и символами Unicode.
  
+ Каналы различных типов, которые представляют соединения с объектами, способными выполнять операции ввода-вывода

+ Селекторы и клавиши выбора, которые вместе с выбираемыми каналами определяют мультиплексированный неблокирующий 
  механизм ввода/вывода.
  
[к оглавлению](#io)

## 4. Что такое Scanner?

Класс `Scanner` можно применять для чтения данных, вводимых с консоли, из файла, символьной строки или из другого 
источника, реализующего интерфейс `Readable` или `ReadableByteChannel`. Например, класс `Scanner` можно использовать для
чтения числа с клавиатуры и присвоения его значения переменной.

[к оглавлению](#io)

## 5. Как работает Scanner внутри?

Как только объект типа `Scanner` будет создан, его очень просто использовать для чтения отформатирванных вводимых данных.
Объект типа `Scanner` читает лексемы из некоторого базового источника, указываемого при создании этого объекта. С точки 
зрения класса `Scanner` *лексема* - это порция вводимых данных, разграничиваемая рядом разделителей, которыми по 
умолчанию являются пробелы. Лексема читается по совпадению с конкретным *регулярным выражением*, задающим формат данных.
В составе этого класса входит немало предопределенных шаблоном для сопоставления с элементарными типами данных вроде `int`
и `double`, а также символьными строками. 

[к оглавлению](#io)

## 6. Какие базовые методы существуют в Scanner?

В классе `Scanner` определяются два ряда методов, которые позволяют читать вводимые данные. 

К первому ряду относятся методы типа `hasNextX`. Эти методы определяют, доступен ли указанный тип ввода. Например, в 
результате вызова метода`hasNextInt()` возвращается логическое значение `true` только в том случае, если следующая 
читаемая лексема оказывается целым числом.

Если же требуемые данные доступны, они читаются одним из методом типа `nextX`. Например, чтобы прочитать следующее целое
число, следует вызвать метод `nextInt()`. 

Чтобы определить, где начинаются и оканчиваются лексемы, в классе `Scanner` применяются *разделители*. По умолчанию в 
качестве разделителей выбираются пробельные символы. Но тип разделителей можно изменить, вызвав метод `useDelimiters()`.

Текущий шаблон разделителей можно получить, вызвав метод `delimiter()`.

`findInLine()` - этот метод осуществляет поиск на совпадение с указанным шаблоном в следующей строке текста. Если
совпадение обнаружено, то соответствующая этому шаблону лексема употребляется и возвращается. В противном случае 
возвращается `null`. 

`findWithinHorizon()` - этот метод пытается обнаружить совпадение с указанным шаблоном в последующем `количестве` 
символов. При удачном исходе метода возвращает результат свопадения с заданным *шаблоном*, а иначе - пустое значение 
`null`. Если параметр *количество* принимает нулевое значение, поиск осуществляется во всех вводимых данных до тех пор, 
пока не будет обнаружено совпадение или достигнут конец вводимых данных.

`skip()` - если обнаружено совпадение с заданным шаблоном, метод просто пропускает его и возвращает ссылку на вызывающий 
объект. Если же совпадение с шаблоном не обнаружено, метод `skip()` генерирует исключение.

[к оглавлению](#io)

## 7. Что такое байтовый поток? Как он реализован внутри?

1) Байтовый поток в Java - классы во главе иерархии это InputStream/OutputStream.
2) В потоке можно прочитать или записать один или несколько байтов.
3) Внутри есть абстрактный метод read() / write(int b), для чтения/записи одного байта. Реализация этого метода и 
   определяет фактическую реализацию потока.
4) Также есть метод read(byte[] buf) / write(byte[] buf) для записи сразу массива байтов.

[к оглавлению](#io)

## 8. Что такое символьный поток? Как он реализован внутри?

1) Символьный поток в Java - классы во главе иерархии это Reader/Writer.
2) В потоке можно прочитать или записать один или несколько символов (char, 2 байта).
3) Внутри есть один абстрактный метод:
   read(char[] cbuf, int off, int len) или
   write(char cbuf[], int off, int len)
   Реализация этого метода и определяет фактическую реализацию работы объекта.
4) Также дополнительно есть метод read() / write(int c) для чтения/записи одного символа или write(String) для записи 
   строки (набора символов).

[к оглавлению](#io)

## 9. Что такое буферизированный поток?

Для оптимизации операций ввода-вывода используются буферизуемые потоки. Эти потоки добавляют к стандартным специальный
буфер в памяти, с помощью которого повышается производительность при чтении и записи потоков.
`BufferedInputStream` и `BufferedOutputStream` байтовые / `BufferedReader` и `BufferedWriter` символьные.
Это может сделать программу намного эффективней, т.к. каждый такой запрос часто инициировал доступ к диску, сетевое
действие, или некоторую другую работу, которая относительно дорога.

[к оглавлению](#io)

## 10. Что такое форматированный вывод? Какие механизмы позволяют осуществить форматированный вызов?

В версии 5.0 в Java были добавлены гибкие и мощные средства форматирования в виде класса Formatter из пакета java.util.
Не обязательно вручную вызывать его методы, так как в Java 5.0 такая возможность добавлена в некоторые классы вводы/вывода
(включая printf()) и класс String. Достаточно вызвать статический метод String.format(), передав ему значение и 
инструкции по форматированию.

На простейшем уровне форматирование состоит из двух главных частей:
1. Инструкции форматирования
2. Аргумент или аргументы, которые будут форматироваться. Тип аргумента не произвольный - он должен быть совместим со 
спецификаторами в инструкциях форматирования.
   
Знак процента в инструкции, это как некоторая переменная, которая представляет второй (третий, четвертый и т.д.) 
аргумент метода. Все, что находится между знаком процента и индикатором типа включительно - это спецификатор 
форматирования.

Спецификатор форматирования может содержать до пяти разных частей. Порядок следования важен. Формат - 
`%[номер аргумента][флаги][ширина][.разрядность]тип`. Тип обязателен, всё остальное опционно.

+ %a	Шестнадцатеричное число с плавающей точкой
+ %b	Булево значение
+ %c	Символ
+ %d	Десятичное целое
+ %e	Число в научной записи
+ %f	Десятичное число с плавающей точкой
+ %h	Хеш-код от аргумента
+ %o	Восьмеричное целое
+ %n	Символ переноса строки
+ %t	Время
+ %x	Шестнадцатеричное целое

[к оглавлению](#io)

## 11. Как осуществляется ввод и вывод из командной строки?

Класс `System` содержит также три переменные предопределенных потоков ввода-вывода: `in`, `out` и `err`
+ Переменная `System.out` ссылается на стандартный поток вывода. По умолчанию это консоль.
+ Переменная `System.in` ссылается на стандартный поток ввода, которым по умолчанию является клавиатура.
+ `System.err` - для ошибок.

**Перенаправление стандартного ввода-вывода**

Класс `System` позволяет вам перенаправить стандартный ввод, вывод и поток ошибок. Для эотого используются простые 
статические методы:

+ `setIn(InputStream)`
+ `setOut(PrintStream)`
+ `setErr(PrintStream)`

Перенаправление стандартного вывода особенно полезно тогда, когда ваша программа выдает слишком много сообщений сразу, и
вы попросту не успеваете читать их, поскольку они заменяются новыми сообщениями. Перенаправление ввода удобно для 
программ, работающих с командной строкой, в которых необходимо поддержать некоторую последовательность введенных 
пользователем данных.

[к оглавлению](#io)

## 12. Что такое класс Console? Расскажите его АПИ.

Альтернатива стандратным потокам ввода / вывода класс `Console`.

Для создание экземпляра используется `System.console()`. Метод может вернуть `null`, если консоль недоступна.
Консоль позволяет вводить пароль используя метод `readPassword` (не видны символы при вводе, не сохраняется в памяти).

+ `flush()` выводит на консоль все данные из буфера.
+ `format()` выводит на консоль строку с использованием форматирования.
+ `printf()` выводит на консоль строку с использованием форматирования (фактически то же самое, что и предыдущий метод)
+ `String readLine()` считывает с консоли введенную пользователем строку.
+ `char[] readPassword()` считывает с консоли введенную пользователем строку,
  при этом символы строки не отображаются на консоли.

Важно, что доступ к консоли мы можем получить только из самой консоли. При запуске, например, в Netbeans вызов 
System.console() будет возвращать значение null. Поэтому при работе с консолью желательно проверять полученное значение
на null.

[к оглавлению](#io)

## 13. Что такое поток данных? Data stream.

Классы `DataOutputStream` и `DataInputStream` позволяют записывать и считывать данные примитивных типов
(`boolean`, `char`, `byte`, `short`, `int`, `long`, `float` and `double`).
+ `DataOutputStream.writeDouble`
+ `DataInputStream.readDouble`

[к оглавлению](#io)

## 14. Что такое поток объектов, Object stream.

`ObjectOutputStream` используется для конвертации объектов в поток. В java это называется сериализация.
Объект преобразоыванный таким образом может быть сохранен в базу данных, передан по сети и т.п.
Для записи в файл можно использовать `FileOutputStream`.
Объект который передается в потоке должен реализовывать интерфейс `java.io.Serializable`.
```java
FileOutputStream fos = new FileOutputStream("EmployeeObject.ser");
ObjectOutputStream oos = new ObjectOutputStream(fos);
// write object to file
oos.writeObject(emp);
```

При сериализации используют переменную `SerialVersionUID`.
Во время сериализации, среда выполнения Java создает номер версии для класса, так что она может десереализировать
его позже. В Java этот номер версии известен как `SerialVersionUID`. Если во время десериализации, `SerialVersionUID`
не соответствует, то процесс завершится с исключением

`SerialVersionUID` используется для указании версии сериализованных данных.
+ Когда мы не объявляем `SerialVersionUID` в нашем классе, среда выполнения Java делает это за нас, но этот процесс
  чувствителен ко многим метаданным класса включая количество полей, тип полей, модификаторы доступа полей, интерфейсов,
  которые реализованы в классе и пр. Вы можете найти точную информацию в документации о сериализации от Oracle.
+ Рекомендуется объявлять `SerialVersionUID` как `private static final long` переменную во избежание механизма по умолчанию.

[к оглавлению](#io)

## 15. Что такое Path? Как он реализуется на разных ОС?

Java 7 представляет новую абстракцию для пути, а именно интерфейс `Path`. Он используется в новых функциях и API,
по всему NIO.2. Объект пути содержит имена каталогов и файлов, которые составляют полный путь до файла/каталога,
представленного объектом `Path`.

`Path` содержит методы для извлечения элементов пути, манипуляций с ними и их добавления.

Путь к файлу, в разных системх может записываться по разному, `\` или `/`, поэтому лучше
использовать `File.separator` для построения пути
```java
// Cоздание объекта Path через вызов статического метода get() класса Paths 
Path testFilePath = Paths.get("/home/heorhi/testfile.txt"); 
         
//Пример строки создания объекта Path пути для запуска в Windows 
Path testFilePath = Paths.get("D:\\test\\testfile.txt");
``` 

[к оглавлению](#io)

## 16. Как получить список файлов?

+ Без учета подпапок
```java
File file = new File("dir");
File[] filesArr = file.listFiles();
String[] filesNames = file.list();
```
+ С учетом подпапок
```java
public void listFilesForFolder(final File folder) {
    for (final File fileEntry : folder.listFiles()) {
        if (fileEntry.isDirectory()) {
            listFilesForFolder(fileEntry);
        } else {
            System.out.println(fileEntry.getName());
        }
    }
}
final File folder = new File("/home/you/Desktop");
listFilesForFolder(folder);
```

**Java 8**
+ Java NIO без учета подпапок
```java
Stream<Path> stramFiles = Files.list(Paths.get("dir"));
```
+ С учетом подпапок. Files.walk API is available from Java 8.
```java
try (Stream<Path> paths = Files.walk(Paths.get("/home/you/Desktop"))) {
    paths
        .filter(Files::isRegularFile)
        .forEach(System.out::println);
}
```
+ В Java есть встроенный механизм - FileVisitor.
```java
package ru.job4j.io;

import java.io.IOException;
import java.nio.file.FileVisitResult;
import java.nio.file.FileVisitor;
import java.nio.file.Path;
import java.nio.file.attribute.BasicFileAttributes;

import static java.nio.file.FileVisitResult.CONTINUE;

public class PrintFiles implements FileVisitor<Path> {


  @Override
  public FileVisitResult preVisitDirectory(Path dir, BasicFileAttributes attrs) throws IOException {
    return CONTINUE;
  }

  @Override
  public FileVisitResult visitFile(Path file, BasicFileAttributes attrs) throws IOException {
    System.out.println(file.toAbsolutePath());
    return CONTINUE;
  }

  @Override
  public FileVisitResult visitFileFailed(Path file, IOException exc) throws IOException {
    return CONTINUE;
  }

  @Override
  public FileVisitResult postVisitDirectory(Path dir, IOException exc) throws IOException {
    return CONTINUE;
  }
}

class Search { 
    public static void main(String[] args) throws IOException {
        Path start = Paths.get(".");
        Files.walkFileTree(start, new PrintFiles()); 
    }
}
```

[к оглавлению](#io)

## 17. Как проверить что файловая сущность является файлом или папкой?

```java
File file = new File("/Users/pankaj/source.txt");
File dir = new File("/Users/pankaj");
File notExists = new File("/Users/pankaj/notafile");
        
System.out.println("/Users/pankaj/source.txt is file?" + file.isFile());
System.out.println("/Users/pankaj/source.txt is directory?" + file.isDirectory());
        
System.out.println("/Users/pankaj is file?" + dir.isFile());
System.out.println("/Users/pankaj is directory?" + dir.isDirectory());
        
System.out.println("/Users/pankaj/notafile is file?" + notExists.isFile());
System.out.println("/Users/pankaj/notafile is directory?" + notExists.isDirectory());
```
С использованием `path`
```java
Path file = new File(path).toPath();
boolean exists =      Files.exists(file);        // Check if the file exists
boolean isDirectory = Files.isDirectory(file);   // Check if it's a directory
boolean isFile =      Files.isRegularFile(file); // Check if it's a regular file
```

[к оглавлению](#io)

## 18. Как удалить файл?

**Using `java.io.File.delete()` function:**
```java
File file = new File("/Users/pankaj/file.txt");

if(file.delete()) {
    System.out.println("/Users/pankaj/file.txt File deleted");
} else {
    System.out.println("File /Users/pankaj/file.txt doesn't exist");
}    
```
**Using `java.nio.file.files.deleteIfExists(Path p)`**
```java
Files.deleteIfExists(Paths.get("C:\\Users\\Mayank\\Desktop\\445.txt")); 
```

[к оглавлению](#io)

## 19. Как переместить файл?

`Java.io.File` не содержит метода готового файла make move,
но вы можете обойти эту проблему с помощью следующих двух альтернатив :

+ `File.renameTo()` (может не сработать на разных файловых системах. Надо проверять результат)
+ Copy to new file and delete the original file.

Для Java 7:

+ `Files.move(Paths.get("/foo.txt")`, `Paths.get("bar.txt")`, `StandardCopyOption.REPLACE_EXISTING);`

[к оглавлению](#io)

## 20. Как управлять аттрибутами файла?

**Базовые атрибуты** (доступны во всех ОС):

+ File type
+ File size
+ Created time
+ Owner of the file
+ Last time modified
+ Last time accessed
+ Hidden
+ System file
+ Regular file
+ isDirectory

**`FileAttributeView`** - базовый интерфейс с подинтерфейсами

+ `BasicFileAttributeView`
+ `DosFileAttributeView`
+ `PosixFileAttributeView`
+ `UserDefinedFileAttributeView`
+ `AclFileAttributeView`
+ `FileOwnerAttributeView`

```java
Path path = FileSystems.getDefault().getPath("c:/test", "somefile.txt");
BasicFileAttributeView basicView = Files.getFileAttributeView(path, BasicFileAttributeView.class);
basicView.readAttributes().lastAccessTime().toMillis();;  // will return the last time the file was read.
basicView.readAttributes().lastModifiedTime().toMillis();  // will return the last time the file was changed.
basicView.readAttributes().creationTime().toMillis();  // will return the creation time.
```

```java
DosFileAttributeView dosView = Files.getFileAttributeView(path,DosFileAttributeView.class);
dosView.setHidden(true);
dosView.setReadOnly(true);
dosView.setSystem(true);
dosView.setArchive(true);
```

[к оглавлению](#io)

## 21. Как создать файл?

Четыре способа:
1. `File file = new File(absoluteFilePath);`

   `file.createNewFile();`

2. `FileOutputStream fos = new FileOutputStream("name.txt");`

   `fos.close();`

3. `String fileData = "Pankaj Kumar";`

   `Files.write(Paths.get("name.txt"), fileData.getBytes());`

4. `Path path = Paths.get("name.txt");`

   `Files.createFile(path);`

[к оглавлению](#io)

## 22. Как создать директорию?

Два способа:
+ `new File("/path/directory").mkdirs();`

+ `Files.createDirectories(Paths.get("/path/to/directory"));`

[к оглавлению](#io)

## 23. Как записать в файл?

+ **BufferedWritter**
```java
    BufferedWriter writer = new BufferedWriter(new FileWriter("c:/temp/samplefile1.txt"));
    writer.write(fileContent);
    writer.close();
```

+ **FileWriter/PrintWriter**
```java
    FileWriter fileWriter = new FileWriter("c:/temp/samplefile2.txt");
    fileWriter.write(fileContent);
    fileWriter.close();
```

+ **FileOutputStream**
```java
    FileOutputStream fos = new FileOutputStream("c:/temp/samplefile4.txt");
    byte[] strToBytes = fileContent.getBytes();
    fos.write(strToBytes);
    
    fos.close();
```

+ **DataOutputStream**
```java
    FileOutputStream fos = new FileOutputStream("c:/temp/samplefile5.txt");
    DataOutputStream dataOutStream = new DataOutputStream(new BufferedOutputStream(fos));
    dataOutStream.writeUTF(fileContent);
     
    dataOutStream.close();
```

+ **FileChannel**
```java
    RandomAccessFile stream = new RandomAccessFile("c:/temp/samplefile6.txt", "rw");
    FileChannel channel = stream.getChannel();
    byte[] strBytes = fileContent.getBytes();
    ByteBuffer buffer = ByteBuffer.allocate(strBytes.length);
    buffer.put(strBytes);
    buffer.flip();
    channel.write(buffer);
    stream.close();
    channel.close();
```
+ **Java 7 Path**
```java
    Path path = Paths.get("c:/temp/samplefile7.txt");     
    Files.write(path, fileContent.getBytes());
```

**Summary**
+ Если мы попытаемся записать в файл, который не существует, файл будет создан первым, и исключение не будет создано (кроме использования метода Path).
+ Всегда закрывайте выходной поток после записи содержимого файла, чтобы освободить все ресурсы. Это также поможет не повредить файл.
+ Используейте PrintWriter для записи форматированного текста.
+ Используйте FileOutputStream для записи двоичных данных.
+ Используйте DataOutputStream для записи примитивных типов данных.
+ Используйте FileChannel для записи файлов большего размера.

[к оглавлению](#io)

## 24. Как прочитать данные из файла?

+ **BufferedReader**
```java
    BufferedReader br = new BufferedReader(new FileReader(file)); 
          
    String st; 
    while ((st = br.readLine()) != null) 
        System.out.println(st); 
    }
```

+ **FileReader**
```java
    FileReader fr = 
        new FileReader("C:\\Users\\pankaj\\Desktop\\test.txt"); 
      
    int i; 
    while ((i=fr.read()) != -1) 
    System.out.print((char) i);      
```
+ **Scanner**
```java
    Scanner sc = new Scanner(file); 
      
    // we just need to use \\Z as delimiter 
    sc.useDelimiter("\\Z"); 
      
    System.out.println(sc.next());
```
+ **Reading the whole file in a List**
```java
    data = new String(Files.readAllBytes(Paths.get(fileName)));
```

[к оглавлению](#io)

## 25. Что такое сокет?

Сокет (socket — разъём) - программный интерфейс для обмена данными между процессами. Процессы могут исполняться как на 
одном компьютере, так на разных, связанных сетью. Иначе говоря, сокет - объект, представляющий конечную точку соединения.
Сокет определяется IP-адресом компьютера и номером порта. Для протокола TCP номер порта - целое число от 0 до 65535.

[к оглавлению](#io)

## 26. Какие виды сокетов есть в Java? С каким протоколом они работают?

Класс java.net.ServerSocket используется серверными приложениями для получения порта и прослушивания клиентских запросов.

Класс java.net.Socket представляет собой сокет, который клиент и сервер используют для связи друг с другом. Клиент 
получает объект сокета, создав его, тогда как сервер получает объект сокета из возвращаемого значения метода accept().

В Java сокеты обеспечивают механизм связи между двумя компьютерами, использующими TCP. **TCP** - TCP - это протокол 
управления передачей, который обеспечивает надежную связь между двумя приложениями. В Java TCP обычно используется 
через Интернет-протокол, который называется TCP/IP.

[к оглавлению](#io)

## 27. Как отправить через сокет сообщение?

Самый простой способ обмена:

На клиенте:

```java
public static void main(String[] args) throws IOException {
    Socket socket = new Socket("localhost", 8000);
    BufferedReader in = new BufferedReader(
            new InputStreamReader(
                    socket.getInputStream()));
    BufferedWriter out = new BufferedWriter(
            new OutputStreamWriter(
                    socket.getOutputStream()));

    out.write("Hello, it's a client!");
    out.newLine();
    out.flush();
    String word = in.readLine();
    System.out.println("Server: " + word);

    out.close();
    in.close();
    socket.close();
}
```

На сервере:

```java
public static void main(String[] args) throws IOException {
    ServerSocket serverSocket = new ServerSocket(8000);
    Socket socket = serverSocket.accept();
    BufferedReader in = new BufferedReader(
            new InputStreamReader(
                    socket.getInputStream()));
    BufferedWriter out = new BufferedWriter(
            new OutputStreamWriter(
                    socket.getOutputStream()));

    String word = in.readLine();
    System.out.println("Client: " + word);
    out.write("Hello, it's a server!");
    out.newLine();
    out.flush();

    out.close();
    in.close();
    socket.close();
}
```

[к оглавлению](#io)

## 28. Что такое логирование?

Логгирование - это процесс записи в файл полезной информации о работе программы.

Полученный файл называют лог-файлом. Если приложение работает плохо, то первое что проверяют - это лог файл.

"Посмотри в лог" - это значит открыть файл логгирования и посмотреть наличие Exception.

[к оглавлению](#io)

## 29. Какие уровни логирования вы знаете?

+ OFF: никакие логи не записываются, все будут проигнорированы;
+ FATAL: ошибка, после которой приложение уже не сможет работать и будет остановлено, например, JVM out of memory error;
+ ERROR: уровень ошибок, когда есть проблемы, которые нужно решить. Ошибка не останавливает работу приложения в целом. Остальные запросы могут работать корректно;
+ WARN: обозначаются логи, которые содержат предостережение. Произошло неожиданное действие, несмотря на это система устояла и выполнила запрос;
+ INFO: лог, который записывает важные действия в приложении. Это не ошибки, это не предостережение, это ожидаемые действия системы;
+ DEBUG: логи, необходимые для отладки приложения. Для уверенности в том, что система делает именно то, что от нее ожидают, или описания действия системы: “method1 начал работу”;
+ TRACE: менее приоритетные логи для отладки, с наименьшим уровнем логирования;
+ ALL: уровень, при котором будут записаны все логи из системы.

[к оглавлению](#io)

## 30. Какая библиотека для логгирования используется в курсе? Как ее настроить?

В курсе используется библиотека Log4j.

Настройка библиотеки:
1. Добавьте зависимость log4j.
   
```xml
<dependency>
    <groupId>log4j</groupId>
    <artifactId>log4j</artifactId>
    <version>1.2.17</version>
</dependency>
```
2. Создайте файл /src/main/resources/log4j.properties. В нём указываются настройки. Содержимое файла:
```text
log4j.rootLogger=DEBUG, console
log4j.appender.console=org.apache.log4j.ConsoleAppender
log4j.appender.console.layout=org.apache.log4j.PatternLayout
log4j.appender.console.layout.ConversionPattern=%d{ISO8601} %5p %c:%M:%L - %m%n
```

**log4j.properties**
1. Запись в консоль, файл или базу данных. Log4j позволяет записывать информацию не только в консоль или файл, но так же
   в базу данных или отправлять по почте.
   
```text
log4j.appender.console=org.apache.log4j.ConsoleAppender
```

2. Формат записи. В логах удобно получать информацию о времени выполнении классе и строчке кода, где была сделана запись.
```text
log4j.appender.console.layout=org.apache.log4j.PatternLayout
log4j.appender.console.layout.ConversionPattern=%d{ISO8601} %5p %c:%M:%L - %m%n
```
Дата: `%d{ISO8601}`

Уровень сообщения: `%5p`

Класс, метод, строчка: `%c:%M:%L`

Текст сообщения: `%m%n`

3. Уровень логгирования.
```text
log4j.rootLogger=DEBUG, console
```

Также в Java используется библиотека slf4j. Она позволяет абстрагироваться от конкретных библиотек. Это позволяет 
придерживаться единого стиля логгирования для проектов.

Для настройки необходимо добавить зависимость slf4j. И использовать другие импорты `import org.slf4j.Logger` и `import org.slf4j.LoggerFactory`.

```xml
<dependency>
  <groupId>org.slf4j</groupId>
  <artifactId>slf4j-log4j12</artifactId>
  <version>1.7.30</version>
</dependency>
```

[к оглавлению](#io)

## 31. Опишите из каких элементов состоит формат JSON?

Примитивные типы данных в JSON:

+ число (целое или вещественное).
+ литералы true, false и null.
+ строка —символы юникода, заключённые в двойные кавычки.

Ссылочные типы данных:

+ Объект - заключается в фигурные скобки ({ и }) и содержит разделенный запятой список пар имя/значение.
+ Массив - заключается в квадратные скобки ([ и ]) и содержит разделенный запятой список значений.

[к оглавлению](#io)

## 32. Как преобразовать POJO в/из json?

**JSON-Java (org.json)** легковесная функциональная библиотека для работы с JSON, которая дополнительно умеет 
преобразовывать JSON в XML, HTTP header, Cookies и др. В отличие от Jackson или Gson, JSON-Java преобразует json-строку 
не в объект пользовательского класса (способ Data bind), а в объекты своей библиотеки JSONObject, JSONArray 
(способ Tree Model).

1. Необходимо добавить зависимость в Maven:
```xml
<dependency>
  <groupId>org.json</groupId>
  <artifactId>json</artifactId>
  <version>20200518</version>
</dependency>
```
2. Для корректного преобразования в строку с помощью org.json необходимо добавить геттеры к полям, которые хотим 
   преобразовывать в json.
   
Варианты преобразования:
```java
public static void main(String[] args) {

    /* JSONObject из json-строки строки */
    JSONObject jsonContact = new JSONObject("{\"phone\":\"+7(924)111-111-11-11\"}");

    /* JSONArray из ArrayList */
    List<String> list = new ArrayList<>();
    list.add("Student");
    list.add("Free");
    JSONArray jsonStatuses = new JSONArray(list);

    /* JSONObject напрямую методом put */
    final Person person = new Person(false, 30, new Contact("11-111"), "Worker", "Married");
    JSONObject jsonObject = new JSONObject();
    jsonObject.put("sex", person.isSex());
    jsonObject.put("age", person.getAge());
    jsonObject.put("contact", jsonContact);
    jsonObject.put("statuses", jsonStatuses);

    /* Выведем результат в консоль */
    System.out.println(jsonObject.toString());

    /* Преобразуем объект person в json-строку */
    System.out.println(new JSONObject(person).toString());
}
```

[к оглавлению](#io)

## 33. Опишите из каких элементов состоит формат XML?

1. **Объявление XML** 
   
Это первая строка, которая должна идти в файле, под расширением XML. В ней указывается кодировка и версия XML
```xml
<?xml version="1.1" encoding="UTF-8" ?>
```
2. **Теги** 
   
Теги - это основные детали из которых строится документ. Тег имеет имя и располагается между <>. 

Тег бывает открывающим располагается внутри <> и закрывающим располагается внутри < />. 

Между открывающим и закрывающим тегом уже располагаются либо другие теги либо текст той сущности, что мы описываем через тег.

Пример:
```xml
<device>Lenovo Thinkpad</device>
```

Пример:
```xml
<device>
    <producer>Lenovo</producer>
    <model>Thinkpad</model>
</device>
```
Если между открывающим и закрывающим тегом ничего нет, то можно написать сокращенную запись:
```xml
<model/>
```
3. **Атрибуты**

Атрибуты - это часть синтаксиса, которая позволяет определить свойста элементов.

Атрибуты пишутся в открывающем теги, после его имени в формате: `имяАтрибут="его значение"`

Например:
```xml
<size width="100" height="100"/>
```

4. **Комментарии**

Комментарии как однострочные, так и многострочные пишутся внутри <!-- и -->

```xml
<!-- комментарии -->
```

[к оглавлению](#io)

## 34. Как преобразовать POJO в/из xml?

1. Для начала нам нужно добавить зависимости на библиотеку JAXB с помощью которой мы будет делать преобразования:

```xml
<dependency>
    <groupId>javax.xml.bind</groupId>
    <artifactId>jaxb-api</artifactId>
    <version>2.3.1</version>
</dependency>
<dependency>
    <groupId>javax.activation</groupId>
    <artifactId>activation</artifactId>
    <version>1.1.1</version>
</dependency>
<dependency>
    <groupId>org.glassfish.jaxb</groupId>
    <artifactId>jaxb-runtime</artifactId>
    <version>2.3.1</version>
</dependency>
```
2. Для использования JAXB нам нужно в модели добавить дефолтные конструкторы.

3. Для того чтобы сериализовать и десериализовать нам нужно добавить аннотации JAXB, которую дадут библиотеке информацию
   о том как парсить объект.

   1. xml обязательно должен иметь корневой тег, в котором все и будет располагаться. Для его обозначения служит 
      @XmlRootElement. Эту аннотацию нужно ставить над сущностью, которая будет корневой.
      
   2. Над вложенными сущностями нам нужно поставить просто @XmlElement

   3. Для того чтобы поле считалось атрибутом нужно поставить  @XmlAttribute, по умолчанию поле парсится как тег

   4. Мы можем указать также как мы хотим читать/писать объект. По геттерам/сеттерам или напрямую по полям 
      (используется рефлексия). Мы будем использовать доступ по полям. Для этих целей служит аннотация @XmlAccessType

[к оглавлению](#io)
