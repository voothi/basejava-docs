# Курс BaseJava (обновленный и переработанный)

## Разработка Web приложения "База данных резюме"
  -  используем: Java 8, 
  - <a href="https://zeroturnaround.com/rebellabs/java-tools-and-technologies-landscape-2016-trends/#java-ides-adoption">IntelliJ IDEA</a>,
    <a href="https://zeroturnaround.com/rebellabs/java-tools-and-technologies-landscape-2016-trends/#java-vcs-adoption">GitHib/Git</a>, 
    Сервлеты, JSP, JSTL, Tomcat, JUnit, PostgreSQL, GSON, JAXB
  - хранение резюме
     -  в памяти на основе массива, отсортированного массива, списка и ассоциированного массива (Map)
     -  в файловой системе (File API и <a href="http://www.quizful.net/post/java-nio-tutorial">Java 7 NIO File API</a>)
        - в стандартной и кастомной сериализации Java
        - в формате JSON (<a href="https://github.com/google/gson">Google Gson</a>)
        - в формате XML (<a href="https://ru.wikipedia.org/wiki/Java_Architecture_for_XML_Binding">JAXB</a>)
     -  в реляционной базе <a href="https://ru.wikipedia.org/wiki/PostgreSQL">PostgreSQL</a>
  -  деплой веб приложения
     - в контейнер сервлетов <a href="http://tomcat.apache.org/">Tomcat</a>
     - в облачный сервис <a href="https://www.heroku.com/">Heroku</a>

## Рекомендуемые книги
- <a href="http://myflex.org/books/java4kids/java4kids.htm">YAKOV FAIN: Программирование на Java для начинающих</a>
- <a href="https://habrahabr.ru/post/153373/">Книги по Java: от новичка до профессионала</a>
- <a href="http://scanlibs.com/java-effektivnoe-programmirovanie-2-e-izdanie">Джошуа Блох: Java. Эффективное программирование, 2-е издание</a>
- <a href="http://www.labirint.ru/books/87603/">Гамма, Хелм, Джонсон: Приемы объектно-ориентированного проектирования. Паттерны проектирования</a>
- <a href="http://www.bookvoed.ru/book?id=639284">Редмонд Э.: Семь баз данных за семь недель. Введение в современные базы данных и идеологию NoSQL.</a>

##  Ресуры в сети
- [EduTools плагин от JetBrains для изучения Kotlin, Java, Python, Scala, ...](http://javaops.ru/view/story/story21#edutools)
- [Руководство по Java Core](http://proselyte.net/tutorials/java-core/)
- [Java. Базовый курс (доступен также через плагин JetBrains EduTools)](https://stepik.org/course/Java-Базовый-курс-187)
- <a href="http://www.intuit.ru/studies/courses/16/16/info">intuit: Программирование на Java</a>
- <a href="http://sernam.ru/book_java.php">Основы программирования на Java: учебное пособие</a>

Занятие 1
=========
- [x] Пройдено
  
[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Первое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson01.md)

- Обзор курса и методики обучения
- Подготовка и настройка рабочего окружения
- Подходы, применяемые при разработке ПО
- Обзор инструментов и технологий, используемых Java-разработчиками
- Введение в язык Java: история создания, JVM, JIT-компиляция
- Системы управления версиями. Git
- Домашнее задание

***

Вступительное  
Сдал HW1

Занятие 2
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Второе занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson02.md)
 
 - Введение в объектно-ориентированное программирование
 - Принципы ООП
 - Модификаторы доступа
 - Классы-обертки
 - Классы и объекты
 - Структура памяти java-программы: Heap (куча), Stack (стек)
 - Типы данных
 - Пакетная организация файлов
 - Домашнее задание

***

## Видео 1. Принципы ООП
* Что-то щелкает на видео у меня
* ?fix: 1 19 Свойства -> Принципы
* Григорий - оптик по образованию (?)
* Выделить основные объекты, вокруг которых будут строиться другие
    * Выделить детали, основные
        * Пример
            * игра - руль
        * что мы можем отбросить
        * в компьютере модель
            * абстракция
                * идеальная
                    * нельзя ничего убрать
* 20 04 Object_s_ - ?
* ?q: 20 51 строки - представление в памяти будет в одной ячейке?
* ?q: 
  * В какой области памяти находится описание объектов - Класс? Стек?
  * В какой сами объекты? Хип?

$hack: IDEA
Alt F8 можно посмотреть объекты в режиме debug

* 46 31 Логически - не очень понятно в каком контексте.

* ?q: Что в результате мы получаем
    * Пример с классом Resume
      * uuid член класса какой имеет по отношению к объекту класса тип связи (композиция - ?)

        * аргегация

        * композиция

## Видео 2. Структура памяти: куча, стек, регистры, константы
* getClass() 

## Видео 3. Типы данных. Пакеты
* Типы данных 
    * Ссылочные
        * Данные хранятся в Heap
        * В Stack хранится только адрес этих ссылочных данных
        * И т.д. разворачивается объектная модель
    * equals() 
```
    отличается от ==

    2 40 Что определяет идентичность объектов, которые в хранятся в Heap
    == - сравнивает адреса, хранимые в Stack, объектов, размещенных в Heap
    r1.equals(r2) - by default реализация ==. Возможно переопределить
        На видео не очень точно - сравниваются не объекты как ==, а значения их адресов в Stack.
    
    04 19 Ссылочные типы принято сравнивать логически
        по equals(), переопределяя
            пример
                резюме - логически 1 объект
                    имеет неизменный uuid
                        если из app записали/извлекли в файл/БД
                            получили
                                в Heap 2 разных объекта
                        поэтому, сравнивать нужно логически
                            при этом, они могут быть разными объектами в памяти
    r1.uuid = "uuid";
        при вызове
            сначала создался ссылочный объект (ссылочный тип)
            r1 типа Resume 
            в Heap
                от него создался еще 1 объект (ссылочный тип)
                uuid типа String
                в Heap
                    который ссылается на еще 1 объект (константный тип)
                    в Metaspace
                    
                    константные строки хранятся в Metaspace
                
                    ?q: Константные и примитивные значения - отличия?
                    ?q: test: Если сравнить 2 строки, то они должны быть true? !a: Да
                    
                    
        "uuid" - константный объект
            хранится в Metaspace
    toString()
        не рассмотрели
```    
                                
 

* Автобоксинг
```
Обертки над примитивными типами. Автоматом происходит. 
Используется в Collections
```

* Пакет
``` 

Уровень абстракции
Уникальность требуется, чтобы не было коллизий при загрузке классов.
FQDN наоборот.
Создаем вложенные пакеты.
webapp - может быть несколько приложений.
Представление в ФС
    Пакет - каталог
    Класс - файл
После перемещения, в класс вставляется 
package ...

$hack: test: IDEA
Ctrl T получить себе коммит - проверить (?)
Alt Enter добавить класс

import добавляет с FQDN класса
    показывает точный путь к файлу класса
        решает коллизии при совпадении в разных пакетах
```
    
* Области видимости
```

модификатор доступа default по умолчанию - неявно
т.е. r1.uuid я к uuid не могу обратиться из другого пакета.
Пакеты по иерархии не раскрываются - это обособленные контейнеры. Нужно явно каждый раз inport-ить.

Через . к члену класса обращаться в Java не принято. Применять get set -ы.
    Кроме типо
        структур или 
        PODO (?)
    Можно добавить код в сеттер, 
        преобразующий
        проверяющий данные на вход
        можем менять реализацию
            ---
            элемент инкапсуляции

Модификаторы доступа к членам класса
public 
открыт
  всем
protected
открыт только
    пакет
    наследники
default
открыт только
    пакет
private
открыт только
    класс

Пакетами 
    реализуется инкапсуляция
    дополнительный уровень группировки
        Можно накладывать ограничения на уровне пакетов - общение между ними.
```

## Видео 4. Домашнее задание HW2
```

Не храним дырки
    переменная

5 15 update
при 
            ---
    save 
        если есть в storage
    ---
    update
    delete
    ---
        если нет в storage
            ---
            при ошибке выводить err через sout
            return null;    
```
+?q: На что указывает объект типа String uuid > value = char[5]@460 объекта в debug
Тип объекта и адрес в памяти
https://www.youtube.com/watch?v=DrQqZj5OIZc


## Домашнее задание HW2
+ Еще раз прочитайте, как правильно оформлять код
+ Настройте IDEA на автоматическое удаление неиспользуемых импортов
+ Поместите классы в пакеты, как это показано в уроке.
По пакетам - см. Хорстманн Т1, 176 стр. Пакеты не связаны - это контейнеры. Пользуемся import.
+ Реализуйте и протестируйте ru.voothi.webapp.storage.ArrayStorage.update(ru.voothi.webapp.model.Resume resume)
+ Сделайте проверки:
+ в update/delete/get - резюме есть в storage?
+ в save- резюме нет в storage?
+ сделайте в save проверку на переполнение
+ выведите соответствующие предупреждения для всех, указанных выше проверок - System.out.println("ru.voothi.webapp.model.Resume ...")
+ Избавьтесь от дублирования в коде ru.voothi.webapp.storage.ArrayStorage
+ Посмотрите на методы класса java.util.Arrays. Некоторые из них помогут упростить реализацию ваших методов clear() и getAll()
***
?- isElementOfArray и getIndex делают одно и то же, просто возвращают разные значения. isElementOfArray  можно удалить
: Заменить не удалось
+ setSize(SIZE_AFTER_CLEAR);
просто size = 0
***
+ STORAGE_SIZE_CREATE слово CREATE лишнее - это же переменная, а не метод. Глаголов в именах переменных быть не должно
+ counterElementsOfStorage
  можно просто counter или size
+ поле типа int при создании объекта и так автоматически инициализируется 0. явно это делать не нужно
+ в методе int size() { уже ни какая логика не нужно. Просто return counterElementsOfStorage
+ после очистки null выводиться не должны.
    А иначе это означает, что ты
      не обнулил счетчик резюме после очистки
    counterElementsOfStorage = 0;
+ в delete создавать новый массив не нужно. Делай все на текущем
Исходный, заполненный
mass  |1|2|3|4|
index  0 1 2 3

Удалил элемент index = 0
mass  | |2|3|4|
index  0 1 2 3

* Сохранить размерность массива
* Новый не создавать

Сдвиг элементов index + 1 на 1 позицию влево
        <2 3 4
mass  | |2|3|4|
index  0 1 2 3
- STORAGE_SIZE = 10000
***
. Исправить resume.uuid = uuid; прямое обращение. Нарушение принципа ООП - Инкапсуляция.
. Названия классов - ?
. return 0; ru.voothi.webapp.storage.ArrayStorage.java есть нуль, а в switch ru.voothi.webapp.MainArray.java - нет. Почему?
. Почему printAll не в ru.voothi.webapp.storage.ArrayStorage?
Предложение: вынести в отдельную структуру
. printAll() ru.voothi.webapp.MainArray.java переменная all - ? Нет контекста у названия. В ru.voothi.webapp.MainTestArrayStorage.java
её нет.
  . Дублирование кода printAll() в ru.voothi.webapp.MainArray.java, ru.voothi.webapp.MainTestArrayStorage.java
. Название. Лучше поменять на create, судя по текущей реализации в коде. Иначе,
Почему в save() создаем новый экземпляр объекта?
                case "save":
                    resume = new ru.voothi.webapp.model.Resume();
. get ru.voothi.webapp.storage.ArrayStorage.java @Overwrite toString(), кастомно, для вывода массива резюме.

## Ревью
Resume
+ toStringSuper - в классах модели принято переопределять метод toString, чтобы он кастомизировал вывод объекта модели, 
метод toStringSuper это избыточно и неправильно, он только усложняет восприятие кода
ArrayStorage
+ начиная с Java7 числа можно писать так 10_000, так улучшается читаемость длинных чисел
+ инициализируй поле хранилища при обьявлении, удали конструктор
+ clear - обнуляй только заполненую часть хранилища
- isPresentInMemory - удали этот метод, он нигде не используется
+ save - не нужно делать вывод об успешном сохранении
+ get - не надо итерироваться по массиву дважды..
  + return null перенеси в блок else
+ delete - удаляешь элементы без проверки их наличия
  + не было требования сохранять порядок элементов при удалении, попробуй использовать более “дешевый“ 
способ удаления, просто поменяв резюме местами
MainArray
>протестируйте ArrayStorage.update(Resume resume)
+ добавь тест для update в этом тестовом классе
Util
+ этот класс усложнил простой вывод в консоль, в нем нет надобности, обычного sout пока достаточно, 
в следующих уроках мы вместо них будем бросать исключения
+ Комментарии должны использоваться, чтобы дать краткий обзор кода и предоставить дополнительную 
информацию, которую нельзя легко получить из кода непосредственно, удали комментарии которые описывают очевидное
+ пиши в начале коммита номер ДЗ - WH2

Занятие 3
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Третье занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson03.md)

- Разбор домашнего задания
- Обзор суперкласса Object
- Связь между equals() и hashCode()
- Статические методы и переменные
- Программирование с помощью интерфейсов
- Абстрактные классы
- Сложность алгоритмов
- Паттерн проектирования Шаблонный метод 
- Домашнее задание

***

## Видео. Разбор домашнего задания
+ Просмотр видео
- Коммиты:
    HW1
    Introduce package and encapsulation
    lesson03 HW02

Именование и модификаторы доступа
Рефакторинг getIndex в get()
$hack: IDEA Control Alt V
$hack: IDEA Control Alt N (inline обратная операция)
Восстановление проекта из-за ошибки Git merge
$hack: IDEA ПКМ - Local history, можно на файле, можно на каталоге в проекте вызывать.

## Видео 1. Объектная модель в Java
+- Просмотр видео
- Коммиты:
    Lesson03 equals&hashCode, static
    Lesson03 implements interface
- Ресурсы просмотреть:
    Модификатор static
    10 заметок о модификаторе static в Java
    Класс Object. Контракт equals/hashCode
    Абстрактные классы (youtube)
    Интерфейсы
    Полиморфизм
    Отличия абстрактного класса от интерфейса
    Дополнительно:
        Что такое полиморфизм?
        Ключевое слово static (youtube)
        Интерфейсы, абстрактные классы, полиморфизм (youtube)
        Разбираемся с hashCode() и equals()

Спрашивают на собеседовании
    Методы Object
        ---
        equals
        hashcode
        ---
            Какой контракт?

        clone
            не рекомендуется
                Блох
                    Эффективное программирование
                ?q: конструктор копирования
                Exceptions
            клонирует
                дублирует область памяти
            в куче будет

 ?q: 03 10 Речь про копирование ссылки на агрегированный объект?

 $hack: IDEA
 Control N - Просмотр всех методов
 Control F12 все методы
        finalize
            мы не знаем когда GC освобождает память
                GC
                    вызвать его мы можем
                        System.gc
                            нет гарантий, что JVM вызовется

            ---
            notify
            ...
            wait
            ...
            ---
                многопоточность
                    много сложностей

        equals
            08 40 для нашей программы переопределяем
$hack: IDEA
Alt Ins

            12 54 Какими свойствами должен обладать equals
                собеседование

?q: Как я могу при коммите не включать пробелы?

fix: 14 18 реализовано на уровне С... Но, JVM на С++ написана 
https://en.wikipedia.org/wiki/HotSpot 
https://github.com/sourcemirror/jdk-8-hotspot

$hack: IDEA
Ctrl Q читать JavaDoc

11 45 добавить JavaDoc интернет
Shift F1

Статические методы
Посылаем сообщение не объекту в Heap, а классу, т.е. объекту в MetaSpace

$hack: IDEA
Ctrl P
показать параметры метода

смотреть чаще реализацию методов

$hack: IDEA Alt Enter выбрать слово из правописания

из static к объектам полям класса не могу получить доступ, т.к. не понятно из какого объекта брать значение

хороший тон - объявлять поля и переменные final. Это не значит, что

для методов класса final встечается не часто в обычном программировании

$hack: IDEA Shift F6 рефакторинг переменной в static final

из числа в константу
32 49 Ctrl Alt C
extract constant
    поменять на private

в контексте методов
    от объекта к классу можно использовать static члены класса
    наоборот - нельзя
        нельзя вызвать из статич метода поле объекта
https://gist.github.com/voothi/6601a2d291edd7aac693e5e190e67664

this
перекрытие переменных - учли в геттерах ...

большой класс - проблема с декомпозицией

43 45 интерфейсы
в инт не может быть чл. класса
это контракт
по умолчанию интерфейсы public

## Видео 2. Сложность алгоритмов
+- Просмотр видео
Временная сложность алгоритма (wiki)
Вычислительная сложность (wiki)
Алгоритмы и структуры данных для начинающих: сложность алгоритмов
Time complexity
Бинарное дерево поиска (youtube)
Дополнительно
    Легко написанная книга по алгоритмам и их сложности Грокаем алгоритмы

3_3_Абстрактные классы, сложность алгоритмов

Создаем класс AbstractArrayStorage
Оптимизация
    перебор млн элементов в массиве
        временная сложность алгоритма time complexity
    есть ещё

        пространственная сложность
            вычислительная (временная + простр-ая)
O - сложность
зависимость
06 20 разбор документа pdf цикл
есть курсы на cousera и др.
нужно знать алгоритмы
    какие есть
    какая сложность

можно взять середину отсортированного массива
лог по осн. 2 от н
если лог от н в задаче, то что-то связано с сортировкой
и поиском в таком списке

SortedArrayStorage - реализация на основе отсортированного списка
можем отсортировать в порядке uuid-ов,
    уникальны
    возрастание
    убывание

общее Sorted и обычный
массив
    размер
    size

полиморфизм
общее - в абстрактном классе,
    он не обязан импл-ть все методы интерфейса

абстрактный класс
    мы не можем создать объект
        не можем инстанцировать такой объект

ставим protected

перенесли метод size в абстракт

## Видео 3. Паттерн проектирования Шаблонный метод
+- Просмотр видео
- Коммиты:
    Lesson03 abstract storage & sorted storage
Ресурсы:

Паттерн проектирования — Шаблонный метод (wiki)
Шаблонный метод (Template Method) (youtube)
Шаблонный метод
Дополнительно
    Книга из известной серии Head First — Паттерны проектирования

3_4_Паттерн проектирования шаблонный метод.mp4

Двоичный поиск
Шаблонный метод
    Опеределили алгоритм
        в абстр классе
            в get()
                в качестве шага
                используем абстр метод, реализация которого переопределяется в субклассах

getUpdate в Sorted...
    двоичный поиск
        резюме в массиве (отсортированном) и по ключу
            должны мочь сравниваться бизнес-логически
                должен быть equals переопределен в Resume
        элементы должны быть отсортированы

$hack: IDEA
Ctrl ЛКМ - провалиться по вызову
Ctrl Shift - автодополнение, на методе показать варианты параметров
Ctrl Alt Left, Right - перемещение по вызовам

?q: int mid = (low + high) >>> 1;

Resume ошибка cast
    Интерфейс Comparable

$hack: IDEA
Ctrl N - ищем интерфейс Comparable

15 15
compareTo
-1
0
> 0

имплементируем Comparable в Resume

проверять перед checkin изменения
Alt Left Right перемещение

не передавать пробелы в классах, - отдельно

21 50 как делать реверт

force push на master делать в prod нельзя

insert binary search
    подсказка

$hack: IDEA
Ctrl Shift R - Replace замена по проекту

## Видео 4. Домашнее задание HW3
+ Просмотр видео
+ Перед тем, как приступить к ДЗ, приведите свой проект в соответствии с коммитами. 
  Обратите внимание, что packages в видео и коммитах — отличаются
- Закончите реализацию AbstractArrayStorage, ArrayStorage, SortedArrayStorage, используя паттерн 
  Шаблонный метод
- В SortedArrayStorage храните элементы отсортированными:
    сортировать весь массив не надо
    не используйте Arrays.sort() или самописные методы для сортировки
    для сортировки воспользуйтесь Arrays.binarySearch (бинарный поиск). Разберитесь с тем, какие 
    значения он возвращает

int binarySearch()
если x >= 0, то найден, индекс ключа
если x < 0, то не найден, индекс x
x возвращаемый int
x = -i - 1
тогда индекс вставки для сохранения порядка сортировки
i = -x - 1

Написать реализации
+ убрать дублирование кода которое образуется после реализации

Алгоритм
save()
рассчет i по getIndex()
if найден (x >= 0)
    не вставляем
    выводим сообщение с элементом и его индексом
if else (i = size)
    вставляем в конец
        на позицию size
else
    вставляем на позицию i

update()
delete()
clear()
getAll()

! LENGTH = 10_000

## Ошибка NPE в реализованном методе get() для массива

### Ошибка
```log
Get r1: uuid1
Size: 3
Exception in thread "main" java.lang.NullPointerException
	at ru.voothi.webapp.storage.ArrayStorage.get(ru.voothi.webapp.storage.ArrayStorage.java:32)
	at ru.voothi.webapp.MainTestArrayStorage.main(ru.voothi.webapp.MainTestArrayStorage.java:21)

Process finished with exit code 1
```


### Код

Класс
https://github.com/voothi/basejava/blob/e8f0bf45ffc8289970c19d48f2a4dcd17030af9e/src/ru.voothi.webapp.storage.ArrayStorage.java

имеет метод,

```java
ru.voothi.webapp.model.Resume get(String uuid) {
    ru.voothi.webapp.model.Resume resume = null;
    for (ru.voothi.webapp.model.Resume element : storage) {
        if (element.getUuid().equals(uuid)) {
            resume = element;
            break;
        }
    }
    return resume;
}
```
который вызывается из метода main() в Классе (для тестирования)
https://github.com/voothi/basejava/blob/d8d4b370e9b9b7075ee3193eb1046fc37f891e5f/src/ru.voothi.webapp.MainTestArrayStorage.java
```java
System.out.println("Get dummy: " + ARRAY_STORAGE.get("dummy"));
```

### Решения
- Хранить количество реально добавленных объектов 
    и при переборке массива через for 
        до количества вставленных объектов
- Flag "заполненности" чтобы сначала заполнить нулевые элементы
***
- Синтаксически if (uuid.equals(Optional.ofNullable(element.getUuid).orElse(null)) { ... }
- Переход на ArrayList

Занятие 4
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Четвертое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson04.md)

- Разбор домашнего задания
- Работа со строками: String, StringBuilder, StringBuffer
- String literal pool
- Исключения (Exceptions)
- Конструктор
- Ключевые слова: this, super
- Reflection
- Аннотации в Java 8
- Введение в модульное тестирование. JUnit
- Домашнее задание

***

## Разбор домашнего задания  
[Разбор домашнего задания](https://drive.google.com/open?id=0B_4NpoQW1xfpQXVMb2xjRXJPdUU)

**Коммиты:**
 - [`lesson04 HW03`](https://github.com/JavaWebinar/basejava/tree/afc0cc5111434375f9da00e225ed7cbb15bbd4b7/src/ru/javawebinar/basejava/storage)

---

* [x] Задание разобрал
## Работа со строками
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
1. [Работа со строками](https://drive.google.com/open?id=0B_4NpoQW1xfpSWVLYk51M2JpRnM)

**Коммиты:**
 - [`Lesson04 String`](https://github.com/JavaWebinar/basejava/blob/7f5a5d70a63fbeea40539397b1c4b2cfb3bd272f/src/ru/javawebinar/basejava/MainString.java)

**Ресурсы:**
- [Строки в Java](https://urvanov.ru/2016/04/20/java-8-строки/)
- [Кодировка в Java](http://www.skipy.ru/technics/encodings.html)
- [Ошибки при использовании строк](http://www.skipy.ru/technics/strings.html)
- [Обработка строк в Java](https://habrahabr.ru/post/260767/)
- **Дополнительно:**
  - [StringBuilder vs StringBuffer](https://stackoverflow.com/questions/355089/difference-between-stringbuilder-and-stringbuffer?rq=1)
  - [String vs StringBuffer vs StringBuilder](https://www.journaldev.com/538/string-vs-stringbuffer-vs-stringbuilder)
  - [String literal pool](http://java67.blogspot.ru/2014/08/difference-between-string-literal-and-new-String-object-Java.html)


### Аннотация видео
* Важно пользоваться преимуществом Java - возможностью разобраться с реализацией API

Чаще смотреть src API

* Проговорили, что есть 3 основные большие библиотеки Java, в которых также есть методы работы со строками
capitalize, например

Apache Commons

Guava

Spring в себе содержит библиотеку

* Иммутабельность String
* MetaSpace - место, где хранятся String qu уточнить.
* Наружу - браузер, др. кодировка уже UTF-8
1-6 байт на символ

Так просто не получится определить позицию символа как во внутреннем представлении Java, в которой используется 
формат кодировки UTF-16, занимающей строго 2 байта на 1 символ.

Сколько каждый символ занимает нужно уже знать.

Загрузки процессора, который работает с вебом - 80% CPU занимает процесс конвертации на сервере в Java.

* Примеры разобрал 

https://github.com/voothi/java-my-experiments/commit/62c5410a8ba12ec41534fb02487f732d950e35f6
## Исключения
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
2. [Исключения](https://drive.google.com/open?id=0B_4NpoQW1xfpQ1BaQjc3Y3N1MTQ)

**Коммиты:**
 - [`Lesson04 Exceptions`](https://github.com/JavaWebinar/basejava/tree/da03245d2fdafa86d1f02ea242c072ca52e19f26/src/ru/javawebinar/basejava)

**Ресурсы:**
  - [Исключения (Exceptions)](http://proglang.su/java/exceptions)
  - [Статья про исключения](http://developer.alexanderklimov.ru/android/java/exception.php)
  - Про исключения также можно почитать в книге Джошуа Блоха - ["Java. Эффективное программирование"](https://www.ozon.ru/context/detail/id/21724143/)
  - [Конструктор](http://info.javarush.ru/javarush_articles/2015/12/04/Конструкторы-классов-Java-JDK-1-5-.html)
  - [Ключевые слова: this, super](http://info.javarush.ru/grishin/2015/03/31/Разница-между-ключевыми-словами-this-и-super-в-Java.html)
  - **Дополнительно:**
    - [Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/)
    - [Checked vs unchecked exception explanation](https://stackoverflow.com/questions/6115896/java-checked-vs-unchecked-exception-explanation)

![image](https://cloud.githubusercontent.com/assets/18701152/15581283/4c2f5348-2374-11e6-8fd2-e4de02d2c389.png)

### Аннотация видео
Классы исключений наследуются от __Класса__ Throwable

Есть у него
* Методы 
* Конструкторы

Семейство небольшое
* Error
  * checked

Ошибки, не поддающиеся обработке
JVM

* Exception
  * RuntimeException (lang)
    * unchecked
  * sql
    * checked
  * io
    * checked
  
checked - была ошибкой. Во многих других языках этот подход не применяется - Scala, др.

Книга Дж. Блох.[B](https://ru.wikipedia.org/wiki/%D0%91%D0%BB%D0%BE%D1%85,_%D0%94%D0%B6%D0%BE%D1%88%D1%83%D0%B0)

Сделать - Exception дорогая операция.
* Используется только для исключительных ситуаций.
* Бывает, делают для перехода вверх по вызовам.
С Java 6 бошлее-менее не дорогая стала.

Можем сделать базовый класс
* Отнаследовать от него для более конкретного Exception

07 24 Пример наследования

06 30 Создаем Exception
* extends RuntimeException
Резюме существует
... не существует в storage
лучше хранить в них информацию в доступном для понимания формате
uuid

11 00 Конструктор

Resume.java
* Добавляем конструктор
* Удаляем setUuid

15 44 Параметры по умолчанию - их нет в Java

Конструкторы - вложенные от сложного к простому. Со всеми параметрами - вызывается из конструктора.

17 30 Переходим к конструкторам Exception
IDEA Alt Enter

18 07 super
Должен идти первым в конструкторе subclass

* Пример с методом todo()

Не рекомендуется исопльзовать переопределенный метод в конструкторе субкласса

Не до конца сконструированны объект получаем

23 00 throw new

25 40 Второй конструктор - для msg

Ловить, перебрасывать, обрабатывать будем позже
## Reflection. Аннотации. Модульное тестирование
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
3. [Reflection. Аннотации. Модульное тестирование](https://drive.google.com/open?id=0B_4NpoQW1xfpT0dGZWlJbnN3bU0)

**Коммиты:**
 - [`Lesson04 Reflection and JUnit`](https://github.com/JavaWebinar/basejava/tree/c77bb7c73022fa411262c1da56953f3ef3ca3cc7)
 
**Ресурсы:**
 - [Java 8 аннотации](https://urvanov.ru/2016/03/30/java-8-аннотации/)
 - [Reflection для начинающих](https://youtu.be/XJQuBXWADZg) (youtube)
 - [Руководство по Java Reflection API](http://javadevblog.com/polnoe-rukovodstvo-po-java-reflection-api-refleksiya-na-primerah.html)
 - [Java Reflection Example Tutorial](https://www.journaldev.com/1789/java-reflection-example-tutorial)
 - **Дополнительно:**
   - [The Reflection API](https://docs.oracle.com/javase/tutorial/reflect/)
   - [What is reflection and why is it useful?](https://stackoverflow.com/questions/37628/what-is-reflection-and-why-is-it-useful)
> В нашем проекте Reflection используют JUnit и будут использовать библиотеки работы с XML и JSON
 - [Фреймворк для модульного тестирования JUnit](http://junit.org/)
 - [Тестирование с помощью JUnit (Test Case)](http://www.javenue.info/post/19)
 - [Тестирование кода Java с помощью фреймворка JUnit](https://www.youtube.com/watch?v=z9jEVLCF5_w) (youtube)

### Аннотация видео
Аннотации

@Overrite
* переопределение метода в subclass
* проверка на этапе компиляции


@Overload
* перегруженные методы
* сигнатуры одинаковые

Reflection
* Аннотации в runtime можно получить через отражения
* Смотрели, когда делали getClass

04 30 MainReflection

IDEA Alt F8 debug
Evaluate Expression

Класс как болванка

Все поля класса
* resume.getClass().getDeclaredFields()
* Получить имя
resume.getClass().getDeclaredFields()[0].getName()

IDEA Ctrl F2 stop debug

IDEA Ctrl Alt V сделать переменную из значения

07 22 Unhandled (checked) Exception должны быть объявлены

Если checked в методе, тогда нужно
* Оборачивать в методе и ловить или
* Добавить в сигнатуру метода throws, т.е. пробросить выше (?)

* Можнго добавлять unchecked через , вместе с checked

08 36 
Потеря инкапсуляции
Есть интерфейс
Имплементируем
В одной из реализаций в методе есть checked
Здесь обрабатывать его неможем, нужно пробросить выше

Меняем интерфейс, он становится зависимым от реализации
теряется инкапсуляция

Ловить и преоборачивать в RuntimeException.
Проглатывает, логирует+проглатывает, переоборачивает - что делают программисты.

10 51
Позволяет менять private final поля
Шутка про собеседование
field.setAccessible(true);

13 08 Менять поля - сериализация, может использоваться.

13 10 ДЗ resume.toString взять через reflection
Взять getAnnotation - вызять анннотацию у объекта

До Java 5 было без аннотаций

14 40 JUnit Долбавляем

Тесты не идут в прод. В артефикт.

Создали test в том же пакете, но другом каталоге (корень)
* Пометил как root test

Могут запускаться при сборке проекта

15 55 Модульные JUnit тесты - самые простые

IDEA Shift Ctrl N
Navigate

Тесты одинаковы для всех реализаций

Будем использовать наследование тестов

IDEA Shift Ctrl T
Create Test

23 50 
@Before

25 55 get not found (Exist)
* Проверяем, что резюме отсутствует в нашем storage
* getNotExist
  * По правильному должен броситься Exception, тогда не прошел

Смотреть какие еще есть

После каждого JUnit
* @After

Единственный раз до создания класса и после
* @BeforeClass
* @AfterClass

28 40 HW
* Реализовать тесты

* Подать реализацию storage в AbstractArrayStorageTest
* Делаем abstract AbstractArrayStorageTest
* Делаем ArrayStorageTest extend AbstractStorageTest

JUnit понимает, что нельзя создать от него объект

* Делаем SortedArrayStorageTest extend AbstractStorageTest

## Домашнее задание HW4
- [x] Реализуйте тесты: `AbstractArrayStorageTest`, `ArrayStorageTest` и `SortedArrayStorageTest`
- [x] В `MainReflection` сделайте вызов метода `toString` через отражение, и выведите результат

### Подсказки по HW4

- `SortedArrayStorageTest` должен запускаться с `SortedArrayStorage`
- `ArrayStorageTest` c `ArrayStorage`
- тестировать правильность сортировки не надо
- логика реализации теста на переполнение массива (`StorageException`):
  - заполняем массив, но не вызываем у него переполнение
  - если исключение вылетит раньше, чем массив будет заполнен, то тест должен провалиться 
    (см. [`Assert.fail()`](https://stackoverflow.com/questions/3869954/whats-the-actual-use-of-fail-in-junit-test-case))
  - если исключение вылетает, когда пытаемся добавить в полностью заполненный массив еще одно резюме - тест пройден
- добавьте конструктор в `AbstractArrayStorageTest`, который инициализирует `Storage storage`, 
  а в наследниках добавьте конструкторы, которые будут вызывать `super()` с нужным хранилищем

### Ревью 1
- [x] удали неиспользуемые импорты
- [x] update - assertTrue - используй assertSame, этот метод выдаст более подробное сообщение 
  в случае провала теста
- [x] getAll - для сравнения массивов на совпадение элементов используй Assert.assertArrayEquals
- [x] saveOverflow - fail() - выводи информативное сообщение
перед заполнением хранилища лучше его очистить
- [x] не надо было делать свой порядок в тестах, они должны быть сгруппироваными по смыслу т.е. 
  к какому методу относится тест

### Ревью 2
Не все замечания были поняты и сделаны правильно  
- getAll - resumesExpected -  
- [x] 1. заполняй тестовыми резюме RESUME_1/2/3
- [x] 2. проверку размера полученного массива верни как было
- saveOverflow
- [x] 1. перед блоком try очищай хранилище
- [x] 2. System.out.println("Fill storage"); - удали этот вывод
- [x] 3. storage.clear(); это в пункте 1 нужно
- [x] 4. Assert.fai l("ИНФОРМАТИВНОЕ СООБЩЕНИЕ ЗДЕСЬ ВЫВОДИТЬ");

Занятие 5
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Пятое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson05.md)

- Разбор домашнего задания
- Иерархия классов Коллекций
- Списки (List)
- Множества (Set)
- Ассоциативные массивы (Map)
- Введение в Iterator
- Тестирование коллекций 
- Домашнее задание

***

## Разбор домашнего задания  
- [ ] ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
  [Разбор домашнего задания](https://drive.google.com/open?id=0B_4NpoQW1xfpN2J2bmxyV3dXME0)   
**Коммиты:**
- [x] [`lesson05 HW04`](https://github.com/JavaWebinar/basejava/tree/4127131819b6385602017f59ca1269c8638ec892)

  - [x] Учесть ошибку
  > В коммите содержится ошибка: в методе `AbstractArrayStorageTest.saveOverflow` цикл идет 
  до `STORAGE_LIMIT + 1` включительно, а надо до `STORAGE_LIMIT`

### Аннотация видео

IDEA Ctrl Alt V - переменную рефакторить  

throws - объявили в методе, не бросаем  

Семейство объектов - мапперы  

Смотрим вкладку дебагера Threads  

Before исполняется перед каждым методом  

Инстанс класса AbstractArrayStorageTest создается также перед каждым методом  
- Статика 1 раз создается
- Конструктор и др. - каждый раз

IDEA Ctrl D Дубликат выделенного  

06 20 Импорт статического метода - не нужно приписывать название класса  

IDEA F3 Где еще используется UUID, Esc затем нажали  

20 05 UseCase. Менеджер приходит с Feature. Обычный и побочный сценарий UseCase  

Посмотрели где у нас есть Exceptions и наметили, соответственно, где нужно реализовать в методах теста.  

IDEA Ctrl E Файлы просмотреть  

Не стоит в одном методе делать больше 1 UseCase (Сценария)  

28 05 try-catch объяснение. Это не проброс наверх, а обработка на месте.  

IDEA Alt F1 Навигация Select in  

28 46 Видимость методов - в том же пакете, хоть и разные корни директорий.  

Rule Optional можно более расширенно работать. Время засекать и др.  

IDEA Ctrl Shift V Можно вставлять из истории буфера обмена  

Объектная модель Resume - возможно, что на сл. уроке  

32 46 Resume вводим поле fullName - ?  
Деалем минимально необходимое  
Это думали делать для update. На сл. уроке решили поменять  

35 15 Почему не будет работать в update assertTrue сравнение в памяти в дальнейшем. Пример с сериализацией и БД.  
Будет другой объект в Куче.  

IDEA Ctrl N Navigate Навигация - переключаемся на другой класс (вкладку)  

39 34  
IDEA Можно делать дебаг выборочно метода с выбором реализации  

39 48  
IDEA Alt F8 как просматривать элемент в дебаге

42 30  
IDEA  
Откатить к тому, что было - условие в строке (i > 0)

IDEA Ctrl F3 -> F3 Найти выделенное  

## Контейнеры/коллекции   
- [ ] ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
  [Контейнеры/коллекции](https://drive.google.com/file/d/0B_4NpoQW1xfpc21aYXY4WW9CMHc)  
**Коммиты:**  
 - [ ] [`Lesson05 Static initializer block and Collections`](https://github.com/JavaWebinar/basejava/tree/6def59a3c6e1a20804d9414f95240f2b973a6ba6)  

### Аннотация видео  
Интерфейс Iterable  
Интерфейс Collection  
Разобрали методы  

iterator  
- nasNext  
- next  
- remove  

До Java 8 не было default в interface  

Удаление элемента foreach  

08 57  

12 04 Условаие Objects.equals(...) - комментарий такой, что если один параметров NULL, то пройдет  

Получаем iterator от коллекции  
Итерируемся по iterator  

22 00 Set для чего нужен - схлопывание коллекций
2 главные реализации:  
- HashSet  
- TreeSet основан на 3 Map

Элементы не дублируются

25 56 List

Упорядоченная коллекция. Появляется индекс в коллекции  
Можно производить операции по индексу  

ArrayList   

LinkedList  

Не лучшая для выбора эмемента  
Удобно, быстро удалять из середины  

FIFO  
LIFO  

На собеседованиях Set, List  

33 20 ArrayList

35 31 Сравнение ArrayList и LinkedList
ArrayList  
CRUD  

Меньше памяти занимет, чем LinkedList  

Хорош для хранения, без удаления/добавления(вставки) в середину, т.к. происходит сдвиг

37 00 Смотрим HashMap, на мапы, т.к. Set-ы реализованы на мапах  
37 38 Map

Как устроен HashMap - нужно знать. Собеседование.

Ключи уникальны как и у Set. Можно класть ключ/значение

IDEA Shift Alt Ins - выделение по вертикали

Ассоциативный массив

**Ресурсы:**  
- [Контейнеры/коллекции](http://en.wikipedia.org/wiki/Java_collections_framework)
- [List, Set, Map, Queue, Iterator, ListIterator](http://www.intuit.ru/studies/courses/16/16/lecture/27131?page=2)
- [Структуры данных в картинках](http://habrahabr.ru/users/tarzan82/topics/)
- [Внутренняя работа HashMap в Java](https://habr.com/post/421179/)
- [Инициализация полей в Java](http://www.quizful.net/post/java-fields-initialization)
- [Java собеседование по коллекциям](http://habrahabr.ru/post/162017/)
- [Часто задаваемые на собеседованиях вопросы по классам коллекциям в Java](http://info.javarush.ru/translation/2013/10/08/Часто-задаваемые-на-собеседованиях-вопросы-по-классам-коллекциям-в-Java-Часть-2-.html#1)
- [Собеседование по Java — коллекции](http://javastudy.ru/interview/collections/)
- [Collection.toArray(new T[0]) or Collection.toArray(new T[size]), that's the question](https://shipilev.net/blog/2016/arrays-wisdom-ancients)

## Домашнее задание
домашнее задание состоит из двух частей:
- [x] 1) Выделите общий класс `AbstractStorage` и реализуйте подкласс `ListStorage`. 
  Для этого вам необходимо вынести в `AbstractStorage` максимум кода, исключив тем самым его дублирование.
- [x] 2) Приступать только после проверки первой части наставником. Реализуйте подкласс `MapStorage`. 
  Сделайте классы для тестирования `ListStorage` и `MapStorage`.

- [x] Выбор реализации `List` и `Map` за вами
- [x]  [Шаблонный метод (шаблон проектирования)](https://ru.wikipedia.org/wiki/Шаблонный_метод_(шаблон_проектирования))
>  Поведенческий шаблон проектирования, определяющий основу алгоритма и позволяющий наследникам переопределять 
> некоторые шаги алгоритма, не изменяя его структуру в целом

- [x] В итоге у вас должна получиться подобная иерархия наследования классов
![image](https://user-images.githubusercontent.com/29703461/34365360-6dae30b2-eaa0-11e7-89d2-e7630ae73827.png)

### Замечания к выполнению домашнего задания
- [x]  int size и STORAGE_LIMIT относятся только к массивам, в List и Map нет необходимости их использовать, 
  будем считать их условно безразмерными
- [x]  при поиске uuid не надо использовать методы, которые сравнивают объекты Resume по equals, в следующих 
  уроках добавим еще поля в Resume и в equals и данный вариант не подойдет

Занятие 6
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Шестое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson06.md)

- Разбор домашнего задания
- Autoboxing and Unboxing
- Паттерн проектирования Итератор
- Вложенные классы
- Внутренние классы
- Локальные классы
- Анонимные классы
- Введение в лямбды
- Функциональный интерфейс
- Домашнее задание

***

## Разбор домашнего задания
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор домашнего задания](https://drive.google.com/open?id=0B_4NpoQW1xfpUFJpRVZvNVVpeDg)

**Коммиты:**
- [`lesson06 HW05`](https://github.com/JavaWebinar/basejava/tree/82748583a0454aa3dd2cbf38d83de1cb49fa3ee3)

**Ресурсы:**
- [Автоупаковка и распаковка в Java](https://habrahabr.ru/post/329498/)
- [Преобразования Integer и int](https://habrahabr.ru/post/104231/)
- [Класс-обертка](https://www.youtube.com/watch?v=T99Dpp29jrU) (youtube)
- **Дополнительно:**
  - [Autoboxing and Unboxing](https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html)
  - [Why do we use autoboxing and unboxing in Java?](https://stackoverflow.com/questions/27647407/why-do-we-use-autoboxing-and-unboxing-in-java)

### Аннотация видео
Создать AbstractStorage  
вынести в него  
Проверки  
- exist
- notexist  
  
Реализовать ListStorage  

Ctrl N нахожим aas

Alt F1 выбор в

01 05 делаем не метод, а класс  
04 08 Shift F6 getIndex - getSearchKey  
05 50 isExist  
07 50 Ctrl R replace замена int index на searchKey  
08 13 Sile limits убираем, т.к. в мапах и др. у нас нет ограничений   
09 47  
17 13 Ctrl I AbstractArrayStorage  
19 00 Ковариация. Сужаем возвращаемый тип  
20 16 Явное преобразование  
21 15 Почему кастить Object не хорошо - ошибка Runtime  
36 26 Тесты пройдены
50 06 Создать новый тест Ctrl Shift T  

## Iterator / Iterable. Вложенные, внутренние, локальные и анонимные классы
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Iterator / Iterable. Вложенные, внутренние, локальные и анонимные классы](https://drive.google.com/file/d/1htZCFoU8j47a00yy-OOvnC27Ktmn1_Hz)

**Коммиты:**
- [`Lesson06 Iterator, Comparator and Inner Classes`](https://github.com/JavaWebinar/basejava/tree/e7531643b410435c07a998a1428fb9a4de2d30bb/src/ru/javawebinar/basejava)

**Ресурсы:**
- [Паттерн проектирования Итератор](https://refactoring.guru/ru/design-patterns/iterator/java/example)
- [Iterator / Iterable](http://www.javenue.info/post/101)
- **Дополнительно:**
  - [Iterator in Java](https://www.journaldev.com/13460/java-iterator)
- [Вложенные классы в Java](https://habrahabr.ru/post/342090/) 
- [Вложенные, внутренние, локальные и анонимные классы](http://pr0java.blogspot.ru/2015/08/1.html)
- [Локальные и анонимные классы](http://easy-code.ru/lesson/local-anonymous-nested-classes-java). 
- [Интерфейсы Comparable и Comparator](https://metanit.com/java/tutorial/5.6.php)
- [Анонимные классы в Java](https://www.youtube.com/watch?v=P3uicghNPLg) (youtube)
- [Nested (static) классы в Java](https://www.youtube.com/watch?v=svOwVvSWeus) (youtube)
- [Inner (non-static) классы в Java](https://www.youtube.com/watch?v=LflAy_LOwwQ) (youtube)
- **Дополнительно**
  - [Вложенные, внутренние, локальные и анонимные классы [eng]](https://docs.oracle.com/javase/tutorial/java/javaOO/nested.html)

### Аннотация видео
0017 Паттерн Итератор  

1218 оговорка про первый элемент RESUME_1, т.к. могли бы удалить RESUME_2 при remove(1)  

1356 Перечисления var args...  
Это массив значений  
Могут быть только последними  

1606 Внутренний и вложенный класс  
- Внутренний  
НЕ статический static  
Связан с внешним классом ссылкой - есть веявное  
поле во внутреннем классе, хранящее ссылку на внешн.  
Вместе создаются при инициализации внешнего.  
?: Вместе удаляются, а как со static вложенным классом?

- Вложенный  
Статический static  
Не связан с внешним ссылкой.  
По смыслу, в контексте - размещение внутри.  

easy-code - разбор по статье.  

По дефолту лучше делать static. Нужно думать - ориентир для других программистов.  

1825 Локальные классы  
На посл. проекте у Г. использовались лок. классы  
Класс объявлен внутри метода  
Собес - спросили  
Нужен для удобства  
Инкапсуляция - данные, которые нужны только в данном методе  
Оптимизация Java 6 - классы может размещать в стеке.  
Если ссылка за пределы метода никуда не выходит, то JVM создает класс  
в стеке.  
Такой класс ограничен только данным методом и не будет виден  
ни откуда ещё.  

2137 Оговорка - у нас есть (метод) Resume  
Убираем Resume импл. Comparable для сравнения для сотрировки  
SorArrStTes  
Интерфейс Компаратор в последнем параметре binarySearch  
2440 Сравнение Comparable Comparator
Comparable  
Этот объект может быть сравним с самим собой  
Comparator  
Сравнивание двух объектов между собой  
?: Разобраться в разнице  
Подали в binarySearch последним параметром реализацию  
класса Comporator (ResumeComporator) 

2225 Анонимные классы  
Разбираем Comparable на базе 
2354 

2613 оговорка - не класса, а интерфейса
?:

2639 static  
Анонимные классы  
$1  
IDEA Alt F8  
Evaluate Expression  
Имя получает в Runtime  

0546 Нестатический внутренний класс  
связан с родительским невидимой ссылкой  
У вложенного есть ссылка на родителя  
У него есть спрятанное поле  
Можно посмотреть в байт-коде  

0810 ArrayList.this.cursor  

## Новое в Java 8
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Новое в Java 8](https://drive.google.com/open?id=0B_4NpoQW1xfpcVJFa2ljeEloTXc)

**Коммиты:**
- [`Lesson06 Lambda`](https://github.com/JavaWebinar/basejava/blob/7a80322a4861ccc1e1eacaef2aac078820699667/src/ru/javawebinar/basejava/storage/SortedArrayStorage.java)

**Ресурсы:**
- [Нововведения в java 8](https://habrahabr.ru/post/216431/)
- [Лямбда-выражения в Java 8](https://www.youtube.com/watch?v=DNC6Lknn2AE) (youtube)
- [Функциональный интерфейс](https://geekbrains.ru/posts/java_interfaces)
- [Лямбды в Java 8](https://habrahabr.ru/post/224593/)
- **Дополнительно:**
  - [Java 8 Functional Interfaces](https://www.journaldev.com/2763/java-8-functional-interfaces)
  - [Lambda expressions](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html)

### Аннотация видео
Java 8 нам дала Stream API, Lambda
Lambda - сокращенное название реализации интерф-са,  
у которого есть 1 метод.  
Comparator  
@FunctionalInterface - метка, для программиста, в Runtime  
Только 1 метсод, который нужно реализовать  
comparable  
И такие интерфейсы можно реализацию заменить на  
лямбду.  
Runnable, Callable  
IDEA Ctrl N
Alt F1 Preview...

Один из самых частых  
Supplier
Consumer - для печати может быть  
Function - конвертатор, один принимает, и 2 возвращает  
До 8-ой версии это бралось из других библиотек  
0617 Как читать лямбду  
()
принимает 2 аргумента и возвращаетм после ->  
лямбды на уровне JVM реализуется не  
анонимными классами, т.к. он дороже - создается  
объект $1, потом GC собирается  
А лямбды - dynamic invoke - динамическая оптимизация  
RINO может работать внутри JVM  
эффективнее, чем анонимный класс.  
Делать за тем, что рекомендует IDEA.  
Java 8 появились ссылки на методы, ссылки  
на конструкторы.  

1042 default методы в интерфейсах  
дефолтная реализация либо на существующих  
методах интерфейса или на утильных  

Из каждой коллекции можно сделать Stream

## Домашнее задание HW6
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Домашнее задание HW6](https://drive.google.com/open?id=0B_4NpoQW1xfpbm9PMXFDN0RuR1k)

- [x] Рефакторинг:
  - [x] метод `saveOverflow()` должен исполняться только для массивов
  - [x] в конструктор `Resume` добавьте второй параметр — `fullName`
  - [x] во всех реализациях `Storage` замените метод `Resume[] getAll()` на `List<Resume> getAllSorted()`
- [ ] Подумайте, что еще, может выступать в качестве `search key` в реализации на основе `Map` 
  (не путайте `key` и `search key` - это разные сущности). Выразите свои идеи в коде 
  (в итоге у вас в проекте должны быть два класса, реализованных на основе мапы)
- [ ] Переделайте компаратор, учтя тот случай, что `fullName` разных людей может совпадать
- [x] Из-за того, что количество тестовых классов растет, воспользуйтесь 
  [аннотациями](http://javastudy.ru/junit/junit-suite-tests/) JUnit, которые помогут упростить их запуск. 
  Форматируйте класс-запуска тестов в соответствии с 
  [этой](https://drive.google.com/file/d/1XHFbxNLekyAWCPJROPJcxmJydjg0K3eH/view?usp=sharing) картинкой

### Ревью 1
+ Resume  
- [x] включи поле fullName в equals, hashCode  
+ SortedArrayStorage  
- [x] RESUME_COMPARATOR - попробуй переписать при помощи   
- [x] строка 9 лишняя  
+ AbstractStorage  
- [x] getAllSorted - перенеси к остальным публичным методам  

#### Comparator.comparing   
Статический метод comparing() принимает  
функцию извлечения ключей,  
приво­дящую обобщенный тип Т к сравниваемому типу (например, String). 

Эта функция 
применяется к сравниваемым объектам, а  
сравнение производится  
по возвращаемым ею ключам.  
Допустим, имеется массив объектов типа Person.  
Ниже показано, как отсортировать их по имени.  

Arrays.sort(people, Comparator.comparing(Person::getName)); 
https://docs.oracle.com/javase/tutorial/java/javaOO/methodreferences.html

Занятие 7
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Седьмое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson07.md)

- Разбор домашнего задания
- женерики (Generic)
- Введение в логирование. Log4J
- Стандартный логер - Java Logging API
- Паттерн проектирования - Синглтон
- Перечисляемые типы (Enum)
- Объектная модель
- Домашнее задание

***

## Разбор домашнего задания
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор домашнего задания](https://drive.google.com/open?id=0B_4NpoQW1xfpT1BwLUNBanVfd1E)

### Аннотация видео
7_1_HW6  
- Рефакторинг:
  - метод `saveOverflow()` должен исполняться только для массивов

0617 IDEA Ctrl F6 Change Signature  
0830 Прекондишны  

1846 IDEA Ctrl I Implement Method  

2145 Arrays.toList  
Не можем добавлять, удалять из такого, но можем изменять.  
Нам подходит, т.к. это уровень представления.  

2514 Остановился
ошибка uuid  

**Коммиты:**
- [`Lesson07_HW06 test refactoring`](https://github.com/JavaWebinar/basejava/tree/b47cadba8f2fb2da61ef6b9f6b245f5c358ea5d8/test/ru/javawebinar/basejava/storage)
- [`Lesson07_HW06 add fullName`](https://github.com/JavaWebinar/basejava/tree/fb608dd824abda1f15bbc437e4d0d5e094fc1680)
- [`Lesson07_HW06 getAllSorted`](https://github.com/JavaWebinar/basejava/tree/bd8e5f4f4582c9f65e1d6a82da1311d6b0efe294)
- [`Lesson07_HW06 mapStorage`](https://github.com/JavaWebinar/basejava/tree/6d0dbdc64e257452662d65f76edf6d9d07328a79)

### Аннотация видео
#### stackOverflow
Паттерн Шаблонный метод (Template Method)  
0130 AbstractArrayStorageTest extend AbstractStorageTest  
оставляем 
- конструктор
  - супер
- stackOverflow  

AbstractStorageTest  
удаляем  
- stackOverflow

0248 JUnit группируем тесты AllStorageTest  
~~?: Откуда взялся MapUuidStorage?~~

0500 Диаграммы  

## Параметризация. Стирание типов
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Параметризация. Стирание типов](https://drive.google.com/open?id=0B_4NpoQW1xfpbXotWEFrYVVGUWc)

**Коммиты:**
- [`Lesson07 generic`](https://github.com/JavaWebinar/basejava/tree/1cb2a6bc0bbbb43285b8ca6b297588e9984fa84b/src/ru/javawebinar/basejava/storage)

**Ресурсы:**
- [Дженерики (Java, обучающая статья)](http://www.quizful.net/post/java-generics-tutorial)
- [Обобщения (Generic)](http://developer.alexanderklimov.ru/android/java/generic.php)
- [Ограничения](http://docs.oracle.com/javase/tutorial/java/generics/restrictions.html)
- **Дополнительно**
  - [Java Generics Example Tutorial](https://www.journaldev.com/1663/java-generics-example-method-class-interface)


### Аннотация видео
Работает на этапе компиляции  
Затем, в байт-коде стирается  
0642 Можно ввоодить  
Значения с типом хранить    
Аргументы типа принимать  
Когда мы объявляем экземпляр этого типа  
или  
делаем наследника (как в нашей программе,  
тогда вводим конкретный тип  
В конструкторе мы кроме заданного типа уже не сможем ничего передать  
Будем ошибка времени компиляции  
Метод проверки типов на уровне компиляции  
Стирание типов. В рантайме мы не знаем какого типа был  
(Можно через отражения посмотреть)
- Не могут быть примитивными  
- Нельзя использовать как инстанс  

1245 Параметризация метода  

В 7 версии появился <> diamond - алмаз

1505 Ключевые слова super, extend  
Collections  

```java
1523 unmodifiableSet  
public static <T> Set<T> unmodifiableSet (Set<? extends T> s) {
}
```

что это
Set<? extend T> s
значит
? - можем подавать любой тип, который  
экстендит  
параметризованный тип T  
Т - яблоки
? extends T - конкретный тип, который наследуется от яблока, например,  
Антоновка  

как аргумент можем подать происводные от Яблок и на выходе метода  
получим именно Сет с яблоками.  

когда мы как параметр передаем какой-то Сет,  
а на выходе получаем какой-то другой сет, который нельзя изменить  

```java
public static <T> void sort (List<T> list, Compatator<? super T> c) {
} 
super
```
super обозначает, что наоборот мы имеем родительским классом этот T  
любой, кто перекрывает T  
Пример с Фрукты/Яблоки  
Фрукты - родитель от Яблока  
Фрукты super Яблоки  
Соответственно,  
Comporator, котоырй умеет сравнивать Фрукты (Фукты super Яблоки )  

## Логирование
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Логирование](https://drive.google.com/open?id=0B_4NpoQW1xfpM1J5NkVqNHd1MlU)

### Аннотация видео
Стандартная библиотека  Java util logging - Java 1.4
Ротирование  
Log4j - до Java 1.4
Стандартный проект - 60 Jar-ников. У каждого есть своя система логирования. 
Нужно подключать около 5 зависимостей, чтобы в Java настроить красиво логирование. 
Синтаксис  
Tomcat используем Java util logging внутри себя  

0540 Logger - фактори-метод, котоый возвращает Logger, которым мы  
можем логировать  
в него передается имя класса  
0658 Более распространеный случай - статический, в наследниках не будет, т.е. подходит.  
В каждом методе добавили логирование.  

0800 уровни логирования  
Вывод в лог операция.  
0900 Можно ставить лог к конкретному пакету.  
Дебажить или логировать можно - 2 варианта разбора.  
1011 60% - заказчики - иностранцы  
По умолчанию у Java Util Logging вывод идет на консоль  

**Коммиты:**
- [`Lesson07 logging`](https://github.com/JavaWebinar/basejava/blob/63674b7f246bf6bc4e509cc1241c7b6340477d18/src/ru/javawebinar/basejava/storage/AbstractStorage.java)

**Ресурсы:**
- [Log4J (Apache logging)](https://logging.apache.org/)
- [Java Logging API - Tutorial](http://www.vogella.com/tutorials/Logging/article.html)
- [Логирование в Java / quick start](https://habrahabr.ru/post/130195/)
- [Ведение лога приложения](http://skipy.ru/useful/logging.html)
- [Java Logging: история кошмара](http://habrahabr.ru/post/113145/)

## Синглтон. Enum
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[3. Синглтон. Enum](https://drive.google.com/open?id=0B_4NpoQW1xfpZ3lmWVhUSXprQXc)

**Коммиты:**
- [`Lesson07 enum`](https://github.com/JavaWebinar/basejava/tree/a1fe80b00444b6c8d8af149c5e82137c312fee22/src/ru/javawebinar/basejava)

**Ресурсы:**
- [Одиночка (шаблон проектирования)](https://ru.wikipedia.org/wiki/Одиночка_(шаблон_проектирования))
- [Перечисляемые типы (enum) в Java](http://easy-code.ru/lesson/enum-types-java)

### Аннотация видео
Есть выбор в Java
0230 Синглтон разбираем  
0315 Ленивый и не ленивый  
0342 Пишем ленивый в.1
Ленивый - по требованию, если объет тяжелый  
Обычный -   конструируется при запуске  
Ленивый в многопоточности работать уже не будет - как у нас. Нужен специальный.  

0530 Перечислимые типы enum-ы  
Появились в Java 5  
```java
public enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, 
    THURSDAY, FRIDAY, SATURDAY 
}
```
Других экземпляров класса Day больше нет.  
Можно использовать как параметр, как член классов.  
Можем передавать объекты, которые являются объектами Enum  

0704 Синглетон на enum  
Средство конструирования и загрузки классов в JVM  

0950 Конструирование объекта резюме на примере  
Есть секции, у которых имеется схожая структура  

Строго типизированные развания есть. Это типы этих секций.  

Переложение из бизнес-модель и нашу доменную модель.  
Такие вещи будут Enum-ами.  

Строго заданный порядок как идут секции  
Дриугие не будем позволять создавать и редактировать.  

Порядок общепринятый. Вверху - самое важное.  

Можно в портфолио указать приложение.  

В каждой секции есть свой заголовок.  

Можно класс наследовать от Enum-а

1620 Делаем работу с секциями в цикле  
Полиморфизм можно использовать (круги, квадраты, др.).

## Домашнее задание
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Домашнее задание:](https://drive.google.com/open?id=0B_4NpoQW1xfpVjhZTzhqemlYZUU)
[Доменный объект](https://ru.wikipedia.org/wiki/Доменный_объект)

- [x] Начните выполнение ДЗ с рисования UML-диаграммы классов модели, описывающих резюме. Покажите ее наставнику
- [x] Сделать объектную модель резюме (диаграмма и классы). [**Образец резюме**](https://javawebinar.github.io)
  - [x] Resume - главный класс. Делать только классы, включаемые в Resume (тип [отношения](https://github.com/ichimax/Java-Interview-Questions/blob/master/Questions/1.%20OOP.md#Типы-отношений-между-классами) - композиция)
  - [x] Схожие по структуре и функциональности сущности делаем одним классом
  - [x] Модель максимально упрощаем, и храним в ней только необходимые данные, а также функционал для вывода и редактирования резюме
  - [x] В модели резюме должны быть представлены контакты и следующие секции:
    - PERSONAL("Личные качества")
    - OBJECTIVE("Позиция")
    - ACHIEVEMENT("Достижения")
    - QUALIFICATIONS("Квалификация")
    - EXPERIENCE("Опыт работы")
    - EDUCATION("Образование")
  - [x] В секциях Достижения и Квалификация хранить список строк
  - [x] Учесть в классах модели, что обработка резюме (вывод в html, сохранение, чтение) будет 
  происходить следующим образом:
обработка `fullName`, цикл обработки по контактам, цикл обработки по секциям (для секций использовать 
полиморфизм, как для фигур: круг, квадрат...)
  - [x] При добавлении / удалении новых видов контактов (например домашний телефон) или разделов 
- изменения в коде (и БД) должны быть минимальны
- [x] **ПРОВЕРЬТЕ свою модель: создайте класс ResumeTestData с методом main, а в нем объект `Resume` 
  и заполните все его разделы данными, взятыми из [**Образца резюме**](https://javawebinar.github.io)**  
- [x] **Не размещайте в AbstractStorageTest код, связанный с заполнением резюме данными. 
  Делайте это в ResumeTestData**

### Аннотация видео
Из чего состоит наше Resume  
Минимально необходимое - правило программирования. Чтобы нечего было убирать лишнего.  

Будут храниться секции  
- Подумать как их лучше хранить так, чтобы можно было быстро достать, например, Личные качества.  
Быстро - O1  
Мы можем хранить списки секций  
Можно получить через get, которую мы проходили в Collection  

0250 Если контакты и секции будут отдельно, то в базе это будут отдельные колонки  
Модель будет очень плохой. Не приспособлена к изменениям  

Как дополнять поля?

Секция имеет тип  

Близнес-логика - отображение и редактирование. С этой точки зрения и проектируем приложение.  

TextSection  

Работа с контактами в цикле тоже  

Сделать наполнение резюме

Картинка резюме
Диаграммы  
Другие классы и соотношения - палочка.  
Упорядочить Layout - ортогональная  

#### Инструменты для рисования UML-диаграмм:

- [Generate class diagram in IntelliJ IDEA](http://stackoverflow.com/questions/8942751/use-intellij-to-generate-class-diagram#26926334) 
  ([Help: working with Diagrams](https://www.jetbrains.com/help/idea/2016.1/working-with-diagrams.html?origin=old_help))
- Нарисовать и сфотографировать
- [Online: www.draw.io](http://www.draw.io)
- [yEd - Graph Editor](https://www.yworks.com/)

### Ревью 1
+ SectionType
- [x] title - сделай поле приватным
- [x] abstract public class Section  - первым принято писать модификатор доступа 
  public abstract class Section
+ Organization
- [x] description != null ? description.equals(that.description) : that.description == null 
  идея предлагает заменить на
 Objects.equals(description, that.description); - соглашайся
- [x] hashCode - можно переписать при помощи Objects.hashCode
+ Link
- [x] url != null ? url.equals(link.url) : link.url == null
можно заменить на
Objects.equals(url, link.url)
- [x] hashCode - можно переписать при помощи Objects.hashCode
+ ResumeTestData
- [x] LocalDate.of(2016, 01, 01) - ноль не нужно писать перед числом
LocalDate.of(2016, 1, 1)
- [x] List<Organization> listOrganizationsExperience;
        listOrganizationsExperience = new ArrayList<>();
в таком разделении нет смысла
- [x] желательно заполнить все резюме с примера, т.к. потом не будет с чем работать на UI

Занятие 8
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Восьмое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson08.md)

- Разбор домашнего задания
- Классы работы с датами: Date, Calendar, TimeZone
- Дата и время в Java 8
- Внешние библиотеки: Joda Time library
- Работа с файловой системой: класс File
- try-with-resources
- Домашнее задание

***

## Разбор Домашнего Задания-7
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-7](https://drive.google.com/open?id=0B_4NpoQW1xfpSXBDR3NndlFXSFE)
[см. коммит Lesson08 HW07 model implementation](https://github.com/JavaWebinar/basejava/tree/8ba1997667b33253df132eb5aef1fc618298687b/src/ru/javawebinar/basejava/model)

- <a href="https://drive.google.com/open?id=1P2qn_bW7hNclKr-J9Yb5LJmbZEwM3IyK">Объектная модель резюме</a>

### Аннотация видео
https://javawebinar.github.io/

0159 Разбор начинаем;
0420 Разбираем модель  
Наше Резюме  
имеет  

        Поле
            ФИО (fullName)
                Имеет ссылку
                H2

        Группа полей - объединяем
            Контакты
                Список полей
                    Требуется удобно работать - add, get
                    Элемент
                        Map-а
                    У каждого контакта есть свой тип и значение
                        Аналогично структуре Секции
            Используем полиморфизм для работы с конечными объектами, абстрагируясь от реализаций.

        Наша модель ориентирована на функциональность просмотр и редактирование резюме - ничего лишнего.

        Позиция  
        Личные качества  
            Секция  
                Текстовая Секция  
                    В ней хранится текст  

        Достижения  
        Квалификация  
            Секция
                Список строк Секция
                    В ней хранится список строк

        Можем легко добавить в enum еще 1 тип секции, которая хранит список строк

        Опыт работы  
        Образование  
            Секция
                Организация

0620 
У нас есть  
    Структура с контактами  
    С секциями  
Почему не List  
    Придется перебирать весь лист контакты с проверкой на тип

Вместо этого, мы можем создать  
Ассоциативный массив (Map), в котором определенному типу (Секции) будет асооцииатировать - Map тип со значением

0702 ContactType
https://github.com/JavaWebinar/basejava/blob/150e15f99c/src/ru/javawebinar/basejava/model/ContactType.java
https://javawebinar.github.io/

0812 Можем сделать в Резюме метод для вывода контактов contacts - getContacts  

0850 Выбор реализации Map
Почему не HashMap  
Есть hashcode, backets, туда попадает по hashcode

У нас в contacts
Ключом Map является ContactType, который является enum-ом - перечислимым типом данных, 
у которого есть объекты, которые Singleton-ы, они заранее заданы, 
поэтому нам не нужны бакеты и можно реализовать проще этот ассоциативный массив.  
EnumMap - делает мапу, ключами которой являются объекты enum.

1056 Создаем класс Section  

Map

Секции  

ListSection  
0630 Выбор реализации - не List для Секции  
0615 Рассмотр Resume  
1357 ListSection  
1600 Программирование по контракту  
2340 Почему final - обязательное поле?
?:  
2445 Не понял про глубокое сравнивание
2635 Глубокое сравнение - ?  
?:  

## Работа с датами и временем
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Работа с датами и временем.](https://drive.google.com/open?id=0B_4NpoQW1xfpV3hZMk85djRfeVk)
[см. коммит Lesson08 DateTime api ](https://github.com/JavaWebinar/basejava/tree/f4844c291cf82387a14088ab3eed112b3102a607/src/ru/javawebinar/basejava)

- <a href="http://www.intuit.ru/studies/courses/16/16/lecture/27131?page=1">Класс Date, Calendar, TimeZone</a>
- <a href="https://www.mkyong.com/java/java-convert-date-and-time-between-timezone/">Java – Convert date and time between timezone</a>
- <a href="http://www.joda.org/joda-time">Joda Time library</a>
- <a href="https://github.com/winterbe/java8-tutorial#date-api">Java 8 Date API</a>

### Аннотация видео
8_2_DateAPI.mp4

    Tue Mar 03 11:24:53 MSK 2020

    1583224226589

Можно в базе хранить лонги start currentTimeMillis

Если нужно отдавать число - время пользователю, то лонги не оптимальны

Григорианский календарь  
Java 1.1  
Calendar  
- год < 1970  
- операции с временем  
- Можно задавать TimeZone  
Возвращает Date текущей зоны, а не той, которую мы задали в setTimeZone  
с передачей в этот метод строкового параметра  
Есть форматер для преобразований TimeZone  
Java Time API  
Имеет недостатки  
- Она мутабельная - можно изменить  

Calendar - Обертка над лонгом

Joda Time
    Решает проблемы
    Range между датами

В LocalDate нет TimeZone  

Время  

    Аблосютное  
    Относительное  

В Java 8 LocalDate Time API  
Сделали похожим на Joda  

SimpleDateFormat

    Не работает с многопоточностью
      
      Веб-приложение

1605 Создаем DateUtil  

    Для Util обычно приватный конструктор не создается

## Работа с файлами и ресурсами
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Работа с файлами и ресурсами.](https://drive.google.com/open?id=0B_4NpoQW1xfpWjJFazJQT0Y2SHc)
[см. коммит Lesson08 File and Resources ](https://github.com/JavaWebinar/basejava/blob/c4011b8d0a07aa0cbc07731809b6b0de61cd767b/src/ru/javawebinar/basejava/MainFile.java)

 - <a href="http://www.intuit.ru/studies/courses/16/16/lecture/27133?page=4#sect23">File. Работа с файловой системой.</a>
 - Работа с ресурсами. <a href="https://habrahabr.ru/post/178405/">Правильно освобождаем ресурсы в Java</a>
 - <a href="http://info.javarush.ru/translation/2013/08/19/Java-7-try-with-resources.html">Java 7 try-with-resources</a>

### Аннотация видео
8_3_file_resource.mp4  

Пакет io

    Дальше будем рассматривать nio,  
      Работает через Path  

    File - абстракция, которая по пути связана с
      файлом,  
      которого может не быть в начале.  

    Очень многие File 
      бросают IOException  
        который checked
          старый класс
            Java 1.1

    Пока просто пробросим
      throw 
        на psvm  

    Не возвращать null, а  
        возвращать пустой
          или
        бросать NPE или др.  
    В nio это лучше реализовано

      Чтобы было красиво, мы можем проверять на null

    Основу пакетов io составляют не файлы, а  
    классы, которые работают с потоками
    входной поток

        байты
        чарактеры

    считываем или записываем

    потоком может быть что угодно

        файл
        сеть 
        память
        строка

    Stream API ничего общего с 
      
      потоками не имеет

    Основные классы для чтения байтов
      InStr
      OutStr

    Ресурсы
      Входной поток
      Выходной поток
        Их нужно закрывать

      Пользователи становятся в очередь за ресурсом

    До 1.7 было сложно работать
      Обработка Exception-ы
        Как при работе Так и при закрытии
      
    checked Exception мы оборачиваем в Runtime
      Не захламляем интерфейс и др. деталями реализации
    
    Мы его можем обернуть try-catch, внутри 
      залогировать 
       или
      пробросить через unchecked Exception
        через параметр e нужно обязательно
          передавать исходный Exception
            его называют 
              root-Exception
              cause-Exception

      Stacktrace - самый нижний нужно смотреть
        нужно смотреть причину cause

1723

    try-with-resources
    В блоке try создаем ресурс, который наследует
    AutoClosable (должны наследовать)

## Домашнее задание
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Домашнее задание:](https://drive.google.com/open?id=0B_4NpoQW1xfpRV8xMnpDV0VBUGc)
[см. коммит Lesson08 HW08 ](https://github.com/JavaWebinar/basejava/tree/126be641f9cf8202956817d26279a7af0cdf6845/src/ru/javawebinar/basejava)

- [x] 1) Переделать модель резюме: учесть, что на одной работе (в одном учебном заведении) 
  можно работать/ учиться в разные периоды и при этом имя организации не дублируется
- [x] 2) Сделать рекурсивный обход и вывод имени файлов в каталогах и подкаталогах 
  (корневой каталог- ваш проект)
- [x] 3) Для создания и заполнения данными резюме из класса `AbstractStorageTest` 
  используйте `ResumeTestData`. Не делайте это в  `AbstractStorageTest`!
- [x] 4) Реализовать `AbstractFileStorage`, базовый класс для хранения резюме в файлах.

### Аннотация видео
    Не нужно дублировать Имя орг

Занятие 9
=========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Девятое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson09.md)

- Разбор домашнего задания
- Обзор пакета java.io
- Классы чтения/записи потоков: InputStream/OutputStream
- Паттерн проектирования Декоратор
- Работа с классами чтения/записи символов: Reader и Writer
- Сериализация
- Обзор пакета java.nio
- Введение в Java 8 Stream API
- Домашнее задание

***

## Разбор Домашнего Задания
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания](https://drive.google.com/open?id=0B_4NpoQW1xfpeENDOVdQbUpIWEU)
>Для создания и заполнения данными резюме из класса AbstractStorageTest используйте ResumeTestData. 
Не делайте это в AbstractStorageTest!

**Коммиты:**
- [`Lesson09 HW08`](https://github.com/JavaWebinar/basejava/tree/150e15f99c35d53e0c43c9f64d7833b5e7184768)

### Аннотация видео
8_5_HW8.mp4 - Shortcut

0655

    Person делаем статическим

0700

    Делаем конструкторы 

0725

    Паттерн Special Case (Особый Случай)
      Заменяется инстансом объекта, чтобы 
      с ним было удобно работать
        Константа в DateUtil
          LocalDate NOW
      
0943

1119 

    Для сериализации в Java придется делать конструкторы по умолчанию

1142

    IDEA
      Как разворачивать скобки
      Expand All
      Shift Ctrl NumPad +

1203

    Добавление методов 
      addContact
      addSection

1323

    Инициализация
    Заполнение тестовыми данными в 
      AbstractStorageTest

1324



1725

    Рекурсивный обход - начало решения

1942

    printDirectoryDeeply

2537

    Параметры в методе - оба одинаковые - стринги
      В проекте ID-ки таска и пользователя чтобы не путать
        Оборачивали в отдельные классы - типы
          UserId
          TaskId

      Введение новых типов - UserId примитивный int, но 
      в программе есть проверка на тип.
        Ожидается в 
          Java 9
          Kotlin
        Есть в 
          Scala

      Сложность с работой с врапперами в коллекциях и др.

3355

3226

3306

    IDEA - Alt и стрелки - пролистывание по методам

?:

    Можно ли свернуть группу коммитов и оставить историю коммитов?

## Ввод/вывод
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Ввод/вывод](https://drive.google.com/open?id=0B_4NpoQW1xfpZHk3TnYyaDRjY3M)

**Ресурсы:**
- <a href="http://www.intuit.ru/studies/courses/16/16/lecture/27133">Пакет java.io</a>
- <a href="http://ru.wikipedia.org/wiki/Декоратор_(шаблон_проектирования)">Паттерн Декоратор</a>.
- <a href="http://www.intuit.ru/studies/courses/16/16/lecture/27133?page=4">Классы Reader и Writer.</a>

### Аннотация видео
2_IO.mp4

0031
    
    Открыли ссылку на Интуите

    Классы основые пакета io
      байтовые потоки
        InputStream
        OutputStream
        чтение вывод 1 байта или массива байтов
      
      символьные потоки
        Reader
        Writer

    Поток байтов и чарактеров (char)
      Входной
      Выходной

    Есть классы оболочки
      Для доп. функциональности
        BufferedInputStream
          Можем применить его к любому 
          InStr
          Не важно, какой вид операции и по какому каналу

          InStr есть для архива, массивов, сети, др.
            Для любого

0520

    Иерархия бесконечная получилась бы
    Реализация сделана на основе паттерна
      Декоратор
      Враппер Wrapper
        Он Реализует тот же интерфейс 
        Добавляет свою функц-сть
        Делегирует вызов в метод класса, который 
        он обертывает

      Есть еще паттерн Адаптер

0640

      Книга GoF
        Стратегия
        Компоратор
        Шаблонный метод
        Декоратор
          BufferedInputStream оборачивает FileInputStream (ниже уровнем иерархии)
            Получается InputStream, который читает из файла и буферизированный 
              
java.io.InputStream (implements java.io.Closeable)
  java.io.ByteArrayInputStream
  java.io.FileInputStream
  java.io.FilterInputStream
    java.io.BufferedInputStream
    java.io.DataInputStream (implements java.io.

0645

    https://docs.oracle.com/javase/8/docs/api/java/io/BufferedInputStream.html

https://docs.oracle.com/javase/8/docs/api/java/io/FileInputStream.html

0710

    Мы будем работать с буферизированным потоком
      Для любой работы с нашими сериализациями
    
    Это лучше, чем с побайтовым потоком - с обычным файлом

IDEA

    Keyboard shortcut for Ctrl+LeftClick?

        https://intellij-support.jetbrains.com/hc/en-us/community/posts/206379269-Keyboard-shortcut-for-Ctrl-LeftClick-

          The shortcut is Goto | Declaration (Ctrl+B)
          After using it you might be interested in Goto | Back (Alt+Back) and Search | Find Usages Popup (Ctrl+Alt+F7) 

    Alt Left Right - переключение между вкладками

0824

    FileOutputStream

0846

    Сделаем OutputStream буферизированным прямо в методе класса AbstractFileStorage
      Не в каждом наследнике

0858

    Делаем обертку BufferOutputStream
    и в нее подаем то, что будем обертывать - поток FiOuStr

1253

    InStr
      Работаем как с двоичными данными
        Из файла
        По сети

    Есть классы, которые работают с символами
      Можно задать кодировку

    Пример с браузером и строками в Java - будут кривые, если работать через двоичное представление

    Функц-ть перекодирования потока char, которые мы принимаем во внутр-ю код-ку Java и обратно. 
    HTTP по сети

    Профилирование
    
    Основная нагрузка на процессор сервера. 
      Посмотреть может, можно как-то подготовить данные.

    Кусок вхождения в большом файле.

    Текстовые файлы в UTF-8. Есть смысл перевести строку в Java в 2-е данные в UTF-8 и 
    работать с файлом не как с набором символов, а как с двоичными данными.

    Табличка для 
      байтового потока
      символьного потока
      
      https://www.intuit.ru/studies/courses/16/16/lecture/27133?page=4

## Сериализация
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Сериализация](https://drive.google.com/open?id=0B_4NpoQW1xfpb0dRNjI1S2tOUjA)

**Коммиты:**
- [`Lesson09 ObjectStreamStorage`](https://github.com/JavaWebinar/basejava/tree/7a80d1d7feba08d433e55417bfd26ac0b3fa5298)

**Ресурсы:**
- <a href="http://www.intuit.ru/studies/courses/16/16/lecture/27133?page=3">Сериализация объектов (serialization)</a>
- Реализация Storage используя <a href="https://habrahabr.ru/post/60317/">сериализацию</a>.
- Сериализация: [1](https://www.youtube.com/watch?v=dBcqizwOWLg), [2](https://www.youtube.com/watch?v=nr4_JRKCGBU) (youtube)

### Аннотация видео
3_ObjectStreamStorage.mp4

    Файл
      Сериализовать
      Десереализовать

    При закрытии делается Flush
      Если не закроем close
      то, что в буфере не запишется - конц файла

IDEA

    Alt F1 Структура

0549 

1019

    Serializable
      Интерфейс-маркер

1307

    Мы
    Резюме
      Сериализуем как набор байтов 2-ые данные
      
      Меняем Резюме
      
      Если не сделать строчку самостоятельно  serialVersionUID 1L
        Тогда Java автосгенерит

        Будет несовместимость версий 
          С той, которую мы записали на диск, например

      Как происходит Сер-ция
        Берем инстанс класса - объект
          Его представление в 2-м виде

          У него есть версия

        Когда мы читаем после изменения (добавления) поля в класс
          На уровне 2-х данных будет ошибка
            Данные будут различаться
          
      Мы вводим serialVersionUID вручную
        Для ручного управления версиями
          Не меняем номер
            если
              Изменился метод
          Меняем
            если изменение на уровне данных
              поле
                может быть
                  данные
                  тип
      
1923
  
    Почему в doRead есть ClassNotFoundException
      Класс загружается в PergemSpace или в > 7 - MetaSpace

    Undeploy в Tomcat, тогда выгружается

    В класспасе у нас нет этого класса нет
      Например, Резюме

    2 программы - выгружает и принимает

    Пример с проводами

    ORM Hibernate
      Читаем из базы объект при помощи него

      Передаем 
        по сети
          по RMI 
            EJB (под собой имеет RMI)
              Serialization используют внутри

      Читаем
        на клиенте
          классов обёрток нет, но есть Resume
            возникнет ошибка, т.к.
              придется притягивать Hibernate
              В класспас клиента

2409

    Дебажим

      IDEA
          Поставить точку останова
          Выделить (Resume) ois.readObject();
            Alt F8
          F9
          
2610

    Почему приложение может падать после настройки логирования веб-приложения
      Потому, что уже вычитано прошлым потоком
        Создавать копию потока
          Веб-сервис
            XML

## NIO
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[3. NIO](https://drive.google.com/open?id=0B_4NpoQW1xfpMzBqSWI3eEI2RGs)
**Коммиты:**
- [`Lesson09 AbstractPathStorage`](https://github.com/JavaWebinar/basejava/commit/4b37c38fb980e315c5ec5f1b2b868fbb5935fe6d)

**Ресурсы:**
- <a href="http://www.quizful.net/post/java-nio-tutorial">NIO Java 7</a>
- <a href="https://habrahabr.ru/post/269667/">Чтения строк из файла</a>

### Аннотация видео

IDEA

    Что возвращает
    Ctrl Задержать над методом
    Ctrl Shift P
    Ctrl Q
    Ctrl Space
    Ctrl Shift I

    Преобразования
    F6

    Extract variable
    Ctrl Alt V

    Diagram
    Ctrl Alt Shift U

    Развернуть
    Shift Ctrl +/-

0637

    Разбор clear
    Lambda

0700

    Для на Stream<> - это как Collection

## Основы Java 8 Stream API
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[4. Основы Java 8 Stream API](https://drive.google.com/open?id=0B_4NpoQW1xfpMHd6VDJjS28tRmM)

**Ресурсы:**
- <a href="https://annimon.com/article/2778">Потоки</a>

### Аннотация видео

## Домашнее задание
- [x] Сделать рекурсивный вывод каталогов и файлов с отступами
- [x] Реализовать `ObjectStreamPathStorage` (через `java.nio.file.Path`) 
и добавить `ObjectStreamPathStorageTest`
- [x] Сделать реализации `Storage` сохранения в файл через `File` и `Path` с 
возможностью выбора стратегии 
- [x] сериализации (посмотрите на [паттерн стратегия](https://refactoring.guru/ru/design-patterns/strategy)). 
Кроме сохранения через `ObjectOutputStream/ObjectInputStream` у нас будут еще 
несколько вариантов сериализации. Сделать тесты для тестирования сохранения через 
`ObjectOutputStream/ObjectInputStream` для `File` и `Path`.

Занятие 10
==========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Десятое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson10.md)

- Разбор домашнего задания
- Паттерн проектирования Стратегия
- Работа с XML
- Работа с JSON: Google GSON и Jackson
- Введение в REST
- DataInputStream/DataOutputStream
- Домашнее задание

***

## Разбор домашнего задания
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор домашнего задания](https://drive.google.com/open?id=0B_4NpoQW1xfpZDVJdGlDRlBlUEU)

**Коммиты:**
- [`Lesson10 HW09`](https://github.com/JavaWebinar/basejava/tree/cf532714164239d7d99909f92ba52cb79cb0694a)

**Ресурсы:**
- [Паттерн - Стратегия](https://www.youtube.com/watch?v=rsB2exGsR4I)

### Аннотация видео
0044 

    Делаем обход файлов

0205

    Реализация AbstractPathStorage

      0240 size()

      0524 StorageException constructor
      2118

      0552 getSeaKey

      0624 doUpd

      0738 isExist

      0755 doSave

      0935 doGet

      1124 dpDelete

      1152 copyAll
      1715

      1126 Refactor try

1925

    ObjectStreamStorage

      2118 StorageException constructor

      2214 Тест создаем копированием

      2301 Смотрим Local History

      2335 Избавиться от дублирования  
        3 доп. сериализации  

      2403 

          Реализация Storage
            AbFiSto
            AbPaSto
          У нас есть работа с 
            ObjStreStor
              C File
            ObjStrePathStor
              C Path
          У нас есть 4 сериализации 
            В бинарном виде - Java
            Json
            XML
            DataStreamStorage
          Для каждого Storage получается по 4 файла

          Stor
            AbStor
              AbFiSto
                ObjStreStor
                  4 сериализации 
              AbPaSto
                ObjStrePathStor
                  4 сериализации 
        
        2514 
        
            в классах (файах) ObjSt
              для сериалайзеров
                есть _поведение_, которое будет меняться в их реализациях - методы
                  doRea
                  doWri

            классы (файлы) должны 
            _параметризоваться_ этим _поведением_
              AbStor
              AbPaSto

              _параметризоваться_ - передать реализациям
                AbStor
                AbPaSto
                поведение как
                параметр

                т.е. стратегию для 
                  сериализации и
                  десериализации

                далее, они работают каждый по свойму с этой стратегией
                  паттерн Стратегия

        2615 Стратегия
          Использовали в Comporator
            Когда делали сортировку мы предавали стратегию
            которой нужно сравнивать элементы 

        3827 

      IDEA  

        Alt Ins - создать.. пакет  

## Формат XML. Работа с XML в Java
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Формат XML. Работа с XML в Java](https://drive.google.com/open?id=0B_4NpoQW1xfpUEtzQjhtQ0c3cFU)

**Коммиты:**
- [`Lesson10 xml`](https://github.com/JavaWebinar/basejava/tree/c36b41e468df8a82bb1e8ba668f3d00e76989fd9)

**Ресурсы:**
- <a href="http://www.duct-tape-architect.ru/?p=315">XML формат и технологии</a>
- Wiki: 
  <a href="https://ru.wikipedia.org/wiki/XML">XML</a>, 
  <a href="https://ru.wikipedia.org/wiki/XSL">XSL</a> , 
  <a href="https://ru.wikipedia.org/wiki/Document_Object_Model">DOM</a>, 
  <a href="https://ru.wikipedia.org/wiki/SAX">SAX</a>, 
  <a href="https://en.wikipedia.org/wiki/StAX">StAX</a>, 
  <a href="https://ru.wikipedia.org/wiki/Java_Architecture_for_XML_Binding">JAXB</a>
- <a href="http://www.vogella.com/tutorials/JavaXML/article.html">Работа с XML в Java</a>. 
  Реализация хранения в XML. 
 
### Аннотация видео

## JSON
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. JSON](https://drive.google.com/open?id=0B_4NpoQW1xfpRUlvMU54a2hMR3c)

**Коммиты:**
- [`Lesson10 json`](https://github.com/JavaWebinar/basejava/tree/ba409e3666f1a5086182a736784c4362a1979b7f)

**Ресурсы:**
- <a href="https://ru.wikipedia.org/wiki/JSON">JSON</a>. <a href="https://learn.javascript.ru/json">JSON в JavaScript</a>
- Работа с JSON в Java: 
  <a href="https://code.google.com/p/google-gson/">Google GSON</a> и 
  <a href="https://github.com/FasterXML/jackson">Jackson</a>. 
  Реализация хранения в JSON
- [Введение в JSON](https://www.youtube.com/watch?v=syuIHCMHQgc) (youtube)

### Аннотация видео

0133 

    Конфиг в XML
      Tomcat 
      Logger
      Spting

    Структура, разметка
      Типы
        Проверка - файл-расширение XML - xsd
          xsd описывает структуру документа
            что и где должно лежать в документе
        Автодополнение
    
    XML
      Теги
        Могут быть атрибуты
        
        Если внутри тела нечего нет, то можно закрывать в открывающем
        Внутри тела есть entity (элемент)
          Могут быть атрибуты

      Элементы - существительные
      Атрибуты - прилагательные
        Дополняющие данные к элементу. Метаданные - ?
      
      Как матрешка
        Дочерние элементы
      Внутри бина 
        объявляем проперти
          в нем - сет

      В файле валидации xsd
        прописана структура
        IDEA ПКМ позвлоляет на основе этого файла провести валидацию

      В Spring схема p (неймспейс) задана программно

      Неймспейс
        Собственная схема валидации 

      BASE64 - двоичные данные, хэши

      XHTML
      Строгая валидация
        Теги закрыты и др.
          Well-formed

      Форматы валидации
        DTD
          Старый, сам не является XML
        XSD
          Современный
        
      Есть технологии
      Стандарт
        Xpath
          Как к базе
      IDEA 
        Show Unic Path

      ESB - Enterprise System Bus

      XSL - язык XML, который
        Задает правила трансформации
      XSLT - применяет правила XSL к XML документу

      XML часто трансформируют в HTML
        для отображения в браузере
      
      1520 Браузеры могут исполнять преобразования XSLT
        Если на вход подать XML, в 
        шапке которого стоит XSLT, то 
        он будет выдавать преобразованный документ

      В Java
        Преобразования
          Объект в XML
            Маршаллинг и
              Сохранение или
              Передача по сети между клиентом и сервером
                SOAP
                  XML
          Разбор XML и извлечение нужной информации  
            Парсинг
            Анмаршаллинг
              DOM-парсер
                JAXB - стандартный
                Будем работать с этим
              SAX
                Работает с документом по частям
                Основана на модели Push
                  Мы ему API даем обработчики событий, а он сам уже
                  дергает за них при наступлении события в XML
                    Программа похожа на колбэки
                      ступеньки как в JS
              StAX
                Java 6
                Может и писать, в отл-е от SAX
                Основана на модели Pull
                  Мы сами запрашиваем - линейный код
                Если большой документ и не все нужно из него, то нужно использвать его

## DataInputStream / DataOutputStream
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[3. DataInputStream / DataOutputStream](https://drive.google.com/open?id=0B_4NpoQW1xfpczVtenBCSDlKWU0)

**Коммиты:**
- [`Lesson10 DataStream`](https://github.com/JavaWebinar/basejava/tree/6f699cb5d804b3d033a06cc1173cd1076b0553f9)

### Аннотация видео

## Домашнее задание
- [x] Сделать и протестировать реализацию `DataStreamSerializer`

Занятие 11
==========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Одиннадцатое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson11.md)

- Процессы и потоки
- Синхронизация методов и блоков
- Закон Мура
- Закон Амдала
- Обзор методов класса Object
- Ленивая инициализация
- Java Memory Model
- Взаимная блокировка
- Домашнее задание

***

## Разбор Домашнего Задания-10 будет на следующем уроке

## Многопоточность. Параллельное выполнение
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Многопоточность. Параллельное выполнение.](https://drive.google.com/open?id=0B_4NpoQW1xfpSmVjRzl6c3ctTTA)
[см. коммит Lesson11](https://github.com/JavaWebinar/basejava/blob/6a626f61722af844663860d1af284c53a9adf423/src/ru/javawebinar/basejava/MainConcurrency.java)

### Аннотация
1_multithread.mp4

0302

    Concurrent
      1 Кофе-машина
      Синхронизация
      Разграничение доступа
    Parallel
      2 Кофе-машины

    Закон Амдала

    2 JVM - 2 процесса в системе
      Внутри JVM можно делать 
        1000-ти потоков Thread-ов
          Можно делать внутри них можно делать
          с точки зрения пользователя
          параллельные вычисления

    Многопоточная архитектура
      time-slicing - квантование времени
        переключение процессора между потоками на заданные отрезки времени
          эмуляция многопоточности

        управляется ОС
          планировщик процессов 
        
        операция переключения между потоками - переключение контекста

    0859 
        
    В 1 процессе запускать множество потоков гораздо дешевле, чем запускать
    множество процессов

    У каждого потока своя память стека, в которой хранится весь контекст
      локальные переменные
      адреса возврата

?: 

    0815 
    
    У потока/нити/thread -а у каждого в приложении своя область выделенной памяти или общая Stack?

    0933

    Потоки могут быть
      Демоны
        Работают в фоне и, например, при завершении главного потока тоже завершается
        ВМ работает, если работает хоть 1 демон-поток
        Утильные, которые исполняются в фоне - библиотеки
          Когда запущена ЖВМ, то запускается порядка
          10-ти демон-потоков
            GC
      Не демоны

      1051

      Создаем MainConcurrency
      new Thread()
        в пакете package java.lang;
          можно не импортировать
        с помощью него можно запускать параллельный процесс

        переопределяем метод run()
          IDEA

              Ctrl O Override

          super.run();
            Нулевой по умолчанию - target не задан

          IDEA 
          
              surround with sout
                https://blog.jetbrains.com/idea/2006/07/surround-with/
                https://stackoverflow.com/questions/14112623/is-there-a-shortcut-for-wrapping-a-statement-with-system-out-println-in-intellij
          
        Параметризируем Thread и в конструктор передаем Runnable
          Thread implements Runnable

2050 

    Порядок выполнения между thread не определен - по усмотрению ОС. Это проблема для тестирования 
и написания многопоточного кода в Java. (Решается Конечными автоматами?)  
https://ru.wikipedia.org/wiki/%D0%9F%D0%BE%D1%82%D0%BE%D0%BA_%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F

    2107

    Через Runnable считается более правильно
      параметризация предпочительнее переопределения
        Можно преедавать как интерфейс
        он ведет себя как параметр
          более предпочтительно, чем переопределение метода
            можем использовать множественное наследование

2237 

    Синхронизация
    Когда у нас есть зашаренный объект
    Concurrency

    Count -ер у Servlet-ов
    Веб-контейнер Tomcat
    150 пользователей-потоков по умолчанию, далее - ждут
    Сервлеты - многопоточные приложения

    2428

    Задача

    Есть счетчик
    Каждый поток += к потоку

    VSCode

        Ctrl Up Down - прокрутка

        Ctrl Shift V - превью markdown

        Ctrl Alt R - Refresh Git
        Ctrl Alt C - Commit
        Ctrl Alt Shift C - Push Remote Repo

    IDEA

        fori

        sout

        psvm

        psf

        Ctrl Alt T Surround With

2920 

    Ставим syncronized на метод inc
      До void - возвращаемого значения в сингнатуре метода
    
    2957 

    Вывелся не 1e+6, т.к.

    3222 

    Чем меньше время блокировки потока выполнения, тем быстрее работает приложение
      синхронизированный код должен быть как можно короче 

    ed (v)
      v - объект, по которому мы будем синхронизироваться

    В Java любой объект имеет wain set - очередь ожиданий, т.е. 
      на него можно ставить синхронизацию и все потоки, которые будут доходить до блока
      syncronized с объектом - будут вставать в очередь к этому объекту

    3535

    Когда синхронизируем между собой потоки - они должны быть в одной очереди

    IDEA

        Shift Ctrl U

    3845

    На какой объект мы лочимся
      В чей wait set мы попадаем?

    Если в сингатуре статического метода ставим, то JVM лочится на объект MainConcurrency.class
      в MetaSpace

      Запись, когда не в сингатуре, а с передачей класса более оптимизирована на низком уровне, но нам
      это не важно

    Если в сингатуре _не_ статического метода ставим, JVM лочится на экземпляр объекта (инстанс)
      syncronized (this)
    
4352 

    IDEA 

        final поля помечать по умолчанию

    4434

    В Java есть механизм - Монитор, который обеспечивает синхронизацию
    Создали объект, 
    вызвали у него синхронизированный метод
    все потоки встанут к нему в очередь и будут выполняться последовательно
  
    4752

    Оговорка - переопределяем метод run не у Thread, а у Runnable

    4815

    Итого по syncronized

    Смотреть куда мы встаем в очередь
      Если к одному объекту, в одну очередь - всё Ок,
      если каждый к своему (к разным), то - НЕ Ок.

    4950

    Другие методы

    С 1.5 появилось много высокоуровневых методов

    Object

5159 

    wait()
      только внутри syncronized, т.е. Монитора
      передает управление другим потокам

      Пока мы не отпустили Монитор (блок), все потоки будут стоять в очереди

      По этому методу мы передаем блокировку и выходим из syncronized метода
        снимаем для другого потока блокировку, чтобы тот мог войти в блок

    другой поток может сказать в блоке 

    notify - пробудить любой другой поток из этой очереди
    или
    notifyAll - ... все потоки ...
    происходит выполнение далее всех инструкций
    и
    блокировка снимается

    5530

    не сразу передается управление другому потоку, а продолжается пока не вышли из
    syncronized блока

    5833

    Параллелизм в Java

    iterrupt() - прерывание потока

    010000

    Сделаем join
    присоединение к потоку

    Нужно подконектиться к этим потокам

    thread.join();
      текущий поток будет ждать пока не исполнится данный поток

    thread.join();
      многопоточности нет
        исполнение в 2 потоках

    Нужно запустить все потоки, чтобы они выполнялись в фоне
    После этого сказать, что теперь мы вас будем ждать

    IDEA

        Ctrl Alt C - Extract const

    Если счетчик не нужен, можно воспользоваться forEach  

    010700
    
    Не обработанное исключение ведет к завершению потока
      завершение JVM процесса не произойдет

    010800

    Deadlock взаимная блокировка

    1 процесс встал в 1 очередь, захватил Лог
    с другой стороны - наоборот.

    Все висим и никаких вычислений не происходит

    Циклическая зависимость - ожидание друг-друга

    Банковский счет - снять с одного и перечислить на другой

      Синхронизация по аккаунтам

      Со второго на первый аккаунт, то противоположно получится

      Нужно их упорядочить - обязательно
        например, ID
        можно с меньшим сначала лочить

![Закон Мура](https://www.karlrupp.net/wp-content/uploads/2015/06/40-years-processor-trend.png)
- <a href="https://ru.wikipedia.org/wiki/Закон_Мура">Закон Мура</a>
- <a href="https://ru.wikipedia.org/wiki/Закон_Амдала">Закон Амдала</a>
- [Фундаментальный поворот к параллелизму в программировании](https://habrahabr.ru/post/145432/)

![Concurrent vs Parallel](https://joearms.github.io/images/con_and_par.jpg)

## Потоки. Синхронизация
- <a href="http://www.intuit.ru/studies/courses/16/16/lecture/27127">Потоки выполнения. 
  Синхронизация.</a>
- <a href="http://www.intuit.ru/studies/courses/16/16/lecture/27127?page=4">
  Методы wait(), notify(), notifyAll() класса Object</a>

## Ленивая инициализация, JMM
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Ленивая инициализация, JMM.](https://drive.google.com/file/d/1kAoLlGhsHAyl_Vtak5R_VuNiQp5cYUx3)
[см. коммит Lesson11](https://github.com/JavaWebinar/basejava/blob/6a626f61722af844663860d1af284c53a9adf423/src/ru/javawebinar/basejava/LazySingleton.java)

- <a href="https://ru.wikipedia.org/wiki/Параллелизм_в_Java">Параллелизм в Java</a>
- <a href="https://habrahabr.ru/post/27108/">Реализация Singleton в JAVA</a>
- <a href="https://ru.wikipedia.org/wiki/Double_checked_locking">Double checked locking</a>
-  <a href="http://www.javaspecialist.ru/2011/06/java-memory-model.html">Java Memory Model</a>. final, volatile
- <a href="https://en.wikipedia.org/wiki/Initialization-on-demand_holder_idiom">Initialization-on-demand holder idiom</a>

### Ресурсы
- Алексей Владыкин, <a href="https://www.youtube.com/watch?v=zxZ0BXlTys0&list=PLlb7e2G7aSpRSBWi5jbGjIe-v_CjRO_Ug">Основы многопоточность в Java</a>
- Виталий Чибриков, <a href="https://www.youtube.com/watch?v=dLDhB6SRXzw&list=PLrCZzMib1e9qkzxEuU_huxtSAxrW1t9NZ">Java. Многопоточность</a>
- Computer Science Center, курс <a href="https://compscicenter.ru/courses/hp-course/2016-spring">Параллельное программирование</a>
- Юрий Ткач, курс <a href="https://www.youtube.com/playlist?list=PL6jg6AGdCNaXo06LjCBmRao-qJdf38oKp">Advanced Java - Concurrency</a>
- Головач, курс <a href="https://www.youtube.com/playlist?list=PLoij6udfBncgVRq487Me6yQa1kqtxobZS">Java Multithreading</a>

### Аннотация видео
2_singleton_jmm.mp4

0100

    Создает единственный объект в куче в контексте 1-го ClassLoader-а

    Как паттерн часто используется
      ЕЕ есть аннотация 
      В контексте Spring как Singleton появляется


    psf объект
    private конструктор
    public getInstance

    Он 1 на вcю JVM

    Будем ClassLoader смотреть на последнем занятии

    Приватный конструктор JVM 
      В каждом ClassLoader может быть свой Singleton

    0325

    Ленивый 
      Инстанциируется по требованию
        Тяжелый объект
      
      Проверяем на null
        Инстанциируем
      Возвращаем

      Если многопоточное (Сервлеты), то 
      несколько потоков могут создать несколько Singleton, 
      причем, сохранили только последний

      syncronized можно написать
        Минус - время ожидания, 
          очередь
        так с каждым последовательно

      syncronized не дешевая операция

      делаем
      паттерн
      Double Checked Locking
        https://ru.wikipedia.org/wiki/%D0%91%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D0%BE%D0%B2%D0%BA%D0%B0_%D1%81_%D0%B4%D0%B2%D0%BE%D0%B9%D0%BD%D0%BE%D0%B9_%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%BE%D0%B9
        Проверяем если не равен нулл, то в очередь не встаем - 
          не блокирующая
        Проверяем внутри, в синхронизированном по инстансу класса 
          Singleton второй раз - не успел ли кто инстанциировать
        До J 1.5 это не работало, т.к. JMM

      JMM
        JVM может внутри производить reordering - переставлять 
          инструкции для оптимизации
          внутри 1 потока это всегда будет корректно выполняться
        В результате, программа может быть выполненна не по порядку 
          сверну-вниз
          и мы можем получить в каком-то потоке
            не инициализированный инстанс объекта полем в его классе
        Для решения проблемы произвели пересмотр JMM
        JMM статья
          JMM спецификация регламентирует доступ к зашаренным объектам
            многопоточность
          Видимость
            Процессор - быстрый
            Память - медленная
              Ввели кэш
        Если общий счетчик для потоков, то для сброса в общую память (не кэш процессора)
        его надо сделать volatile

        1405

        Happans-before
        volatile
          Читаем переменную return
            Мы переменную volatile не можем брать из локального кэша процессора
            Должны сбросить кэш
            Заново всё прочитать из памяти, в т.ч. int (не volatile)
              Ускорение
              Состояние  
                Снапшот
        
        syncronized работает как volatile

        1810
        
        Картинка - между тредами

        interract не работает при вычислениях
          делается volatile переменную - флаг

        2540

        volatile не строит потоки в очередь, а обеспечивает шаринг значения переменной между ними

2612

    Статья

    2943

    final

    Публикация объектов

    1.5 JMM
    Ссылка на объект класса не будет видна ни одному из потоков, 
      пока не будут проинициализированны все final поля
    
    LazySingleton
      может не ставить volatile, если мы уверенны, что все его поля
        final-ые
      не сможет произойти reordeing

    syncronized было до 1.5 JMM

    3247

    Initialization-on-demand holder idiom

    Создаем Hold-ер
      внутренний статический класс (вложенный)

    Проще конструкция

    Работает в многопоточном

    Загрузка по требованию - в MetaSpace
      new
    
    LazSingHol не будет загружен ClassLoader-ом, пока он не встретится в коде

    final поле
      Пока он не будет проинстанциировано - объект класса LazSingHol не будет виден 

    У Java есть внутрений механизм загрузки одного ресурса

     Initialization-on-demand holder idiom
     лучшая замена 
     DCL

## Домашнее задание
- [x] Реализовать deadlock
- <a href="https://ru.wikipedia.org/wiki/%D0%92%D0%B7%D0%B0%D0%B8%D0%BC%D0%BD%D0%B0%D1%8F_%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D0%BE%D0%B2%D0%BA%D0%B0">
  Взаимная блокировка</a>

Занятие 12
==========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Двенадцатое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson12.md)

- Разбор домашнего задания
- Обзор java.util.concurrent
- Синхронизаторы
- ThreadLocal переменные
- Сравнение с обменом (Compare-and-swap)
- Домашнее задание

***

## Разбор Домашнего Задания-11 
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-11](https://drive.google.com/open?id=0B_4NpoQW1xfpcWNMeHQ1Y0JoaUU)

[см. коммит Lesson12 HW11](https://github.com/JavaWebinar/basejava/blob/50388920c5e29e70208df572dc34208b46bcdd1a/src/ru/javawebinar/basejava/MainConcurrency.java)

### Аннотация видео
1_HW11.mp4

0000

    Взаимная блокировка - deadlock

    Несколько потоком заняли ресурсы
      они ждут друг-друга
        каждому нужен ресурс, который занят другим потоком
          циклическая занятость ресурсов

    Простейшая реализация 2 ресурса и 2 потока
      Ресурсы делаем стринги
        лочиться можно на любой объект
    
    С syncronized быть осторожным,
      помогают
        Ожидания с таймаутами


## Concurrency
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Concurrency](https://drive.google.com/open?id=0B_4NpoQW1xfpRkdBLW81a1AtWDg)

[см. коммит Lesson12 Concurrency](https://github.com/JavaWebinar/basejava/blob/a34c2eec5a4b96d7ef7cd1fce140b0398e00a197/src/ru/javawebinar/basejava/MainConcurrency.java)

- <a href="http://habrahabr.ru/company/luxoft/blog/157273/">Обзор java.util.concurrent.*</a></li>
- <a href="https://en.wikipedia.org/wiki/Compare-and-swap">Compare-and-swap</a>
- <a href="https://habrahabr.ru/post/277669/"> Справочник по синхронизаторам java.util.concurrent.*</a>
- <a href="http://articles.javatalks.ru/articles/17">Использование ThreadLocal переменных</a>

>  Замечания по видео:

    ThreadLocal<SimpleDateFormat> DATE_FORMAT = new ThreadLocal<SimpleDateFormat>() {
       @Override
       protected SimpleDateFormat initialValue() {
            return new SimpleDateFormat("dd.MM.yyyy HH:mm:ss");
       };
    };

можно написать через лямбду:

    ThreadLocal.withInitial(() -> new SimpleDateFormat("dd.MM.yyyy HH:mm:ss"));

А лучше использовать потокобезопасный `DateTimeFormatter` Java 8 Time API:

    DateTimeFormatter.ofPattern("dd.MM.yyyy HH:mm:ss");

### Аннотация видео
2_concurrency2.mp4

0120

    С Java 1.5

    Статься на хабре
      https://www.google.com/search?q=Java+Concurrent+Animated&rlz=1C1GCEU_enRU844RU844&oq=Java+Concurrent+Animated&aqs=chrome..69i57j69i60&sourceid=chrome&ie=UTF-8

      Nominal vs Structural Type System
        Go, TS vs Java
    
    Doug Lea

    java.util.concurrent
      Concurrent Collections
      Queues
      Synchronizers
      Executors
      Locks
      Atomics

    CopyOnWrite
      Write операции редки
        Listeners механизм

    ConcurrentMap
      Перенесено в Map многое 1.8
      Атомарное действие между потоками

0630

    0700 Vector

    Collections
      оберточки
        syncro...
      если нет в пакете conc
      
      Блок по 1-му объекту - не эффективно
        1 очередь для изменения

    ConcurrentHashMap
      Добавляет 16 мониторов
        очередей
      
    0928 

    Разные очереди на чтение и запись
      разные блоки - гибко

    1002
    
    Queue
    Очереди
      Это коллекции
      Многопоточные очереди
        Блокирующие
          Много потоков
            1 поток - кладет в нее
            1 поток - берет из нее
              get
              pull
              может подождать
                поток встает в состояние wait
                  до момента, пока продюсер (поставщик)
                  не положит туда что-то и не скажет notify

                  1142
                  
                  BlockingQueue
                    можно с таймаутом
                    poll
                  
            не часто попадаются - есть более высокоуровневые конструкции

        Неблокирующие

    1250
    
    Synchronizers
    Синхронайзеры
      countDownLatch
        Отсчитывает до нуля

      Семафор
        Один уходит, 1 заходит

    2035

    Executions
    Экзекюторы
      чаще других используются

    Вместо создания Thread-ов попробуем сделать это через Execution-ы

    Factory Фабрика класс Executors
    статические медоды
    newSingle...
      Выполнение действия в 1 потоке
    newFixex...
      В фиксированном кол-ве потоков
    newCached
      Автоматически настраивает
    ...

    Можно в стримах parallels
      Executors поменьше стало

    Есть очередь из 1000 писем
      Сервер почтовый по 8 принимает
        newFixed 
          8 потоков
            в него бросал письма

    2301

    Делаем пример

    IDEA

        Shift Ctrl P - выделяем
        Ctrl Alt V

    executorService

    Callable - если нужно возвращать результат, иначе - Runnable

    2830

    Смотрим, что есть в пакете 
    Executors

    Если Collable
      Например, отправка Email
        Отправился или нет
      
    3013

    Future

    Собеседование

    Будущее

    Интерфейс
      отоженный результат
        выполнился или нет - не известно в момент возврата Future

    из нее можно сказать
      ... методы
        get
          тайм-аут
          возьмет результат этой Future

    3306

    Механизм работы потока 

    get
      усыпляет поток по wait
        уходит в режим ожидания
          процессор переключит на него свой контекст когда 
          Future будет готова

    juc хорош тем, что происходит блокировка потока
      время процессора не используется

    3430

    Книжка

    Есть примеры с синхронизаторами
    Есть сайт с картинками
    Хотим сделать подгрузку картинок в фоне
      подгрузилась - отображаем сразу
    
    Через Execution будем все картинки подгружать
    Мы должны знать, что она подгрузилась и ее можно отобразить
    CompletionService
      ExecutorCompletionService - реализация

    ExecutorCompletionService - обертка
      блокирующая очередь
      позволяет брать первую законченную таску

3949

    Fork Join
    MapReduce
      Map - таски бъются на куски
        параллельно
      Reduce - сливаются
        и общий результат дает
      
    Наша задача
      Map
        Все каунтеры отдельно посчитали
          все они вернули свои значения
            по 100 на поток
      Reduce
        В 1 потоке
        Все их сложили и получили результат
          1e+6
      
      4045

      Locks
      Локи
        1.5
        ReentrantLock
          RW есть
            для блокировки
              Map
                запись
        
      4439

      Atomics
      Атомики
        atomicInteger.incrementAndGet
          Самое быстрое решение
            внутри нет синхронизаторов
        
        compareAndSwapInt
          CAS
            процессорная инструкция

    4900

            Конструкция Skip
              В цикле пытаемся добавить 1
    
    Шипилёв

    5125

    ThreadLocal

    Ищем
      thread safe

    SimpleDataFormator для всех потоков мы не можем
      у него есть свое состояние
      будут коллизии
        внутри вычисляется что-то
        второй поток собъет
          не thread-safe - называется
      
      thread-safe
        у него есть свое состояние
        immutable классы

      в многопоточном SimpleDataFormator можем использовать
        через ThreadLocal
          для каждого Thread-а
            он использует свой экземпляр
              типизированный
        
## Разбор Домашнего Задания-10 
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-10](https://drive.google.com/open?id=0B_4NpoQW1xfpY3d6R204ZXplb00)

[см. коммит Lesson12 HW10](https://github.com/JavaWebinar/basejava/tree/4e75634fa4670a71a60f5643fa995295c4fb959d/src/ru/javawebinar/basejava)

## Домашнее задание:
- [x] <a href="http://java-course.ru/begin/postgresql">Установить PostgreSQL</a>
- [ ] Посмотреть на реляционные базы данных и SQL:
  - [x] <a href="http://www.codenet.ru/progr/vbasic/vb_db/1.php">Введение в базы данных</a>

### Аннотация материала

        В отличие от плоских, реляционные базы данных состоят из нескольких таблиц, связь между которыми устанавливается с помощью совпадающих значений одноименных полей.

        Каждая из таблиц содержит информацию об объектах одного типа. Из названий таблиц становиться понятно, что данные в каждой таблице принадлежат одной и той же группе объектов. Каждая строка в этих таблицах однозначно определяет один объект из соответствующей группы. Вообще, база данных может состоять из одной или нескольких таблиц. Запись, в свою очередь, состоит из нескольких полей, каждое из которых содержит элемент данных об объекте.

        Рис.1.3. Структура таблицы PUBLISHERS
        Рис.1.4. Содержимое таблицы PUBLISHERS

        Для удобства работы с таблицами, имеющими отношение много-ко-многим, обычно в базу данных добавляют еще одну таблицу, которая находится в отношении один-ко-многим и много-к-одному к соответствующим таблицам. В случае базы данных BIBLIO.MDB такой таблицей является TITLE AUTHOR.

        надо стремиться максимально уменьшить количество повторяющейся информации. Процесс уменьшения избыточности информации в базе данных посредством разделения ее на несколько связанных друг с другом таблиц и называется нормализацией данных

        Для того, чтобы построить достаточно эффективную структуру данных, достаточно придерживаться нескольких простых правил:

          1. Определите таблицы таким образом, чтобы записи в каждой таблице описывали объекты одного и того же типа. В нашем случае библиографические данные можно разместить в трех таблицах:

          PUBLISHERS - содержит информацию об издательствах;
          AUTHORS - содержит информацию об авторах книг;
          TITLES - содержит информацию об изданных книгах.
          1. Если в вашей таблице появляются поля, содержащие аналогичные данные, разделите таблицу.

          2. Не запоминайте в таблице данных, которые могут быть вычислены при помощи данных из других таблиц.

          3. Используйте вспомогательные таблицы. Например, если в вашей таблице есть поле Страна, то может быть стоит ввести вспомогательную таблицу Country, которая будет содержать соответствующие записи (Россия, Украина, США и т.п.). Этот прием также поможет уменьшить количество ошибок при вводе данных, допускаемых пользователями.

      Ключевым полем может быть практически любое поле в таблице. Ключ может быть первичным (primary) или внешним (foreign).

      Индекс представляет собой таблицу, которая содержит ключевые значения для каждой записи в таблице данных и записанные в порядке, требуемом для пользователя. 

      Каждая таблица может иметь несколько различных индексов, каждый из которых определяет свой собственный порядок следования записей

      Примером простого индекса в базе данных BIBLIO.MDB может служить код ISBN

      Составной индекс строится на основе значений двух или более полей таблицы
        составного индекса, основанного, например, на следующих полях таблицы: имя, фамилия, отчество, город и номер телефона.

  - [x] * <a href="http://www.intuit.ru/studies/courses/5/5/info">Основы SQL</a>

### Аннотация материала
- [x] Лекция 1
53 минуты
Введение в структурированный язык запросов SQL
    SQL:1999
    Каждая таблица БД представляется как совокупность строк и столбцов, где строки (записи) соответствуют экземпляру объекта, конкретному событию или явлению, а столбцы (поля) – атрибутам (признакам, характеристикам, параметрам) объекта, события, явления.

    Между двумя или более таблицами базы данных могут существовать отношения подчиненности, которые определяют, что для каждой записи главной таблицы (называемой еще родительской) возможно наличие одной или нескольких записей в подчиненной таблице (называемой еще дочерней).

    Связь "один–ко–многим" является самой распространенной для реляционных баз данных. Она позволяет моделировать также иерархические структуры данных.

    для чтения связанной информации в нескольких таблицах приходится производить ряд операций чтения вместо одной, когда данные хранятся в одной таблице.

    Всякую связь "многие–ко–многим" в реляционной базе данных необходимо заменить на связь "один–ко–многим" (одну или более) с помощью введения дополнительных таблиц.

    Стандарт на язык SQL был выпущен Американским национальным институтом стандартов (ANSI) в 1986 г., а в 1987 г. Международная организация стандартов (ISO) приняла его в качестве международного. Нынешний стандарт SQL известен под названием SQL/92

    Дальнейшее расширение двухуровневой архитектуры клиент-сервер предполагает разделение функциональной части прежнего, "толстого" (интеллектуального) клиента на две части. В трехуровневой архитектуре клиент-сервер "тонкий" (неинтеллектуальный) клиент на рабочей станции управляет только пользовательским интерфейсом, тогда как средний уровень обработки данных управляет всей остальной логикой приложения. Третий уровень – сервер базы данных. Эта трехуровневая архитектура оказалась более подходящей для некоторых сред – например, для сетей Internet и intranet, где в качестве клиента может выступать обычный Web-браузер.

    Основные категории команд языка SQL:
      DDL – язык определения данных; Data Definition Language
        CREATE TABLE, ALTER TABLE, DROP TABLE, CREATE INDEX, ALTER INDEX, DROP INDEX
      DML – язык манипулирования данными; Data Manipulation Language
        INSERT, UPDATE, DELETE
      DQL – язык запросов
        SELECT
      DCL – язык управления данными; Data Control Language
        GRANT, REVOKE
      команды администрирования данных;
      команды управления транзакциями
        COMMIT, ROLLBACK, SAVEPOINT, SET TRANSACTION

    С помощью типов данных устанавливаются основные правила для данных, содержащихся в конкретном столбце таблицы, в том числе размер выделяемой для них памяти.

    Идентификаторы
      ( A-Z, a-z ), цифры ( 0-9 ) и символ подчеркивания ( _ ).
      до 128 символов
      начинаться с буквы
      не может содержать пробелы
    
    не чувствительны к регистру

    Бэкуса-Науэра формами (БНФ)

    Прописные буквы используются для записи зарезервированных слов

    БНФ 
    Символ	Обозначение
    ::=	Равно по определению
    |	Необходимость выбора одного из нескольких приведенных значений
    <…>	Описанная с помощью метаязыка структура языка
    {…}	Обязательный выбор некоторой конструкции из списка
    […]	Необязательный выбор некоторой конструкции из списка
    [,…n]	Необязательная возможность повторения конструкции от нуля до нескольких раз

    ТОВАР и КЛИЕНТ
    СДЕЛКА

    Определим атрибуты и свяжем их с сущностями и связями

    ТОВАР относятся такие характеристики, как 
      название, тип, цена, сорт

    КЛИЕНТ – 
      имя, отчество, фамилия, фирма, город, телефон

    СДЕЛКА может быть охарактеризован такими признаками, как 
      дата и количество проданного товара
    
    Важным этапом в создании базы данных является 
      определение атрибутов, которые однозначно определяют каждый экземпляр сущности, т.е. 
        выявление первичных ключей.

    ТОВАР
      КодТовара
        артикул 

    КЛИЕНТ
      КодКлиента
    
    СДЕЛКА 
      КодСделки

    В качестве первичного ключа можно было бы выбрать не одно поле, а некоторую совокупность полей

    связи между таблицами
      установим
        между таблицами КЛИЕНТ и СДЕЛКА 
          имеется связь "один–ко–многим" 
            по полю КодКлиента

        между таблицами ТОВАР и СДЕЛКА 
          имеется связь "один–ко–многим" 
            по полю КодТовара

        созданим
          Для таблицы СДЕЛКА поля КодКлиента и КодТовара являются внешними (чужими) ключами

![alt](https://www.intuit.ru/EDI/08_01_19_2/1546899581-11707/tutorial/22/objects/1/files/1.gif)

- [ ] Java 8 Streams:
    - [ ] 1) реализовать метод через стрим `int minValue(int[] values)`.  
Метод принимает массив цифр от 1 до 9, надо выбрать уникальные и вернуть минимально возможное число, 
составленное из этих уникальных цифр. Не использовать преобразование в строку и обратно. 
Например {1,2,3,3,2,3} вернет 123, а {9,8} вернет 89

    - [ ] 2)  реализовать метод `List<Integer> oddOrEven(List<Integer> integers)`
если сумма всех чисел нечетная - удалить все нечетные, если четная - удалить все четные. 
Сложность алгоритма должна быть O(N). 
Optional - решение в один стрим.

Занятие 13
==========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Тринадцатое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson13.md)

- Разбор домашнего задания
- Введение в реляционные базы данных
- Язык SQL
- Обзор NoSQL баз данных
- Установка и настройка СУБД PostgreSQL
- Работа с базами данных из IDEA
- Конфигурирование базы данных и каталога хранения
- Подключение базы данных к проекту
- Обзор JDBC-архитектуры
- Домашнее задание

***

## Базы данных. Реляционные СУБД. PostgreSQL
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Базы данных. Реляционные СУБД. PostgreSQL](https://drive.google.com/open?id=0B_4NpoQW1xfpOHFGQTUydzdKaFE)

**Коммиты:**

- [`Lesson13 Init DB`](https://github.com/JavaWebinar/basejava/blob/79f4e1d3ecc9ce306504a991fcca00c81c992f8c/config/init_db.sql)

**Ресурсы:**
- [DB-Engines Ranking](http://db-engines.com/en/ranking)
- [Реляционная СУБД](https://ru.wikipedia.org/wiki/Реляционная_СУБД) (wiki)
- [Введение в базы данных](http://www.codenet.ru/progr/vbasic/vb_db/1.php)
- [Реляционные базы vs NoSQL](http://habrahabr.ru/post/103021). SQL. Денормализация. PK, FK, Cascade
- [PostgreSQL: надёжность](https://ru.wikipedia.org/wiki/PostgreSQL#Качество_исходного_кода)
- [Работа с базами данных из IDEA](https://habrahabr.ru/company/JetBrains/blog/204064)
- [IDEA Database tools](https://www.jetbrains.com/datagrip/features)
- [Как работает реляционная БД](https://habrahabr.ru/company/mailru/blog/266811)
- [SQL ключи во всех подробностях](https://habrahabr.ru/company/oleg-bunin/blog/348172)
- [Книги по postgreSQL](https://postgrespro.ru/education/books)
- [Интерактивная обучалка по postgreSQL](https://www.pgexercises.com/)

### Аннотация видео
13_1_RDBMS.mp4

    Рассматриваем популярность

    MySQL PHP - LAMP
      CGI Common Gateway Interface
        ENV
        Скрипты - в отдельных процессах, от серверного
          Overhead в сравнении с потоками Java
          PHP
            https://en.wikipedia.org/wiki/LAMP_(software_bundle)
          Perl
      https://en.wikipedia.org/wiki/Netscape_Server_Application_Programming_Interface
      https://en.wikipedia.org/wiki/Generator_(computer_programming)
          https://en.wikipedia.org/wiki/FastCGI
          Nginx
      
    https://db-engines.com/en/ranking
      
    0636 
    
    Рекомендация по Книжке

    Кортеж - запись

    Между таблицами - отношения

    Приложение на базе данных
      5 таблиц

    Pg
      Расширения
        Py
        Гео
      Мало ошибок
      На большой нагрузке - ок
      В банках - Оракл
        Миграция идет
    
    1120

    pgAdmin

1326

    IDEA 
      Options
        Схемы
          public
            в ней наши создаются

    1737

    Создаем таблицу

    1742

    Именование таблицы
      Без s
        кроме users
          user - системой занята
    
    resume
      uuid - primary key
      fullName

    Придерживаемся нормализации

    Строки pg
      Длины
        переменной
        фиксированной
          CHAR(36)
      
    Генерится команда SQL

    DDL есть

    camelCase не пишем в названии полей
      underscore вмето

    ```sql
    create table resume
    (
      uuid char(36)
        constraint resume_pk
          primary key,
      full_name text
    );

    comment on table resume is 'Resume Table';

    alter table resume
      owner to postgres;
    ```
    
2342

    Таблица 
    contact

    Просмотрел все видео по этому уроку

    fk - связка

    Создал init_db.sql
      проверил работу

    Index
      Seq scan

    Pg
      2-ый поиск
        TreeMap
    
    Нужно создавать индексы - приучаться делать правильно

    По pk pg автоматически строит индексы

    Индекс - структура ключ-значение
    ключ - uuid наш, а указатель на запись на диске

    type - должен быть уникальным, т.к. это ключ в нашей Map-е

    Для данного резюме
      resume_uuid
        type - уникальный
          строится индекс, который является уникальным

3911

    ускорение всех sql команд
      при использовании
        resume_uuid
        type
    обеспечит целостность бд
      не позволит вставить вторую запись с совпадающими
        type
        резюме

    3946

    Создаем индекс IDEA
      от порядка полей в индексе многое зависит

    4159

## Конфигурирование данных в Java проекте
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Конфигурирование данных в Java проекте](https://drive.google.com/open?id=0B_4NpoQW1xfpQUpkVTJiQnpBNnM)

**Коммиты:**

[`Lesson13 properties`](https://github.com/JavaWebinar/basejava/tree/25f4dd3b23790cc74c30d3703b16fa6af09c3905)

**Ресурсы:**

- [Properties sample](https://www.mkyong.com/java/java-properties-file-examples)
- Конфигурирование DB и каталога хранения  

### Аннотация видео
13_2_config.mp4

    Credention

    Пароли

    resume.properties

    Параметры
      Каталог ./storage

    Создали синглтон
      приватный конструктор, чтобы не вызвать извне
        в нем нужно зачитать все пропы
      
0712

    Config.java

    Можем сделать, чтобы приложение падало на старте
      при невалидном конфиге

    Ошибка is

## Подключение DB в проект
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[3.Подключение DB в проект](https://drive.google.com/open?id=0B_4NpoQW1xfpWVVSOURIeDNEMUk)

**Коммиты:**

[`Lesson13 SqlStorage`](https://github.com/JavaWebinar/basejava/tree/62705ea7e24dda66647b47971f83f1507dd80016)

**Ресурсы:**

- [JDBC](http://ru.wikipedia.org/wiki/Java_Database_Connectivity)
- [JDBC Architecture](http://www.developersbook.com/jdbc/interview-questions/jdbc-interview-questions-faqs.php)
- [Книга: Семь баз данных за семь недель. Введение в современные базы данных и идеологию NoSQL](http://www.ozon.ru/context/detail/id/19383907)
- [Работа с базами данных с помощью JDBC драйвера](https://devcolibri.com/работа-с-бд-mysql-postgresql-с-помощью-jdbc-драйвера)
- [Уроки по JDBC](https://www.youtube.com/playlist?list=PLIU76b8Cjem5qdMQLXiIwGLTLyUHkTqi2)

### Аннотация видео
13_3_jdbc.mp4

    JDBC Arch
      Java App
        JDBC API
          Driver Manager
            JDBC Driver написаны на Java
            Driver
              PostgreSQL
            Driver
              MySQL
            Driver
              MSSQL
            Driver
              ODBC Data Source
    
    Получить коннект

    IDEA

        Настроил keymap для Local History на 
          Shift Alt H

0416

    Как работает JDBC API с БД
      Основное - Получаем Connection к БД, далее можем 
        отдавать sql комманду
        получать данные
        т.д.

      Для получения Connection к БД
        создаем интерфейс
          connectionFactory
            получает conn к БД
              пакеты sql
                checked

      С этим conn будет работать
        SqlStorage

0612

    SqlStorage реализуем
      сonnectionFactory нам нужно для 
        получения conn к БД
      нам нужно через конструктор 
        передать параметры подклчюения к БД

        реализуем через аннонимный класс
          DriverManager

0614

    Реализация интерфейса Storage

    SqlStorage

    DriverManager 
      Подходит для тестовых приложений

    Для реальных - делается пул коннектов

    Дорогая операция
      На каждого пользователя свой коннект - плохо

    Очередь коннектов

    Пул - можем переиспользовать коннекты

    Пул - в Enterprise

    1000

    1033

    Connection нужно как и любой другой ресурс закрывать
      с Java 1.7 делаем это в ARM

1056

    clear

    ORM коннекшн нужно закрывать 

    prepareStatement
      выполнение команды

1211

    Логирование дублируем

    Взять коннекшн
    ps

    Нужно зарефакторить - ДЗ

1434
    
    ? - подставляемый параметр 

    Склеивать нельзя - уязвимость SQL Injection
      делать через параметр подставляемый
        ps.setString ...
          идет проверка через Driver
        
    алиасы
      r
        работа с несколькими таблицами в запросе

1450

    1750 
    
    результат - rs
      executeQuery возвращает результат - rs
      
      тоже ресурс
        в каждой СУБД по своему - pg сам зактывает при закрытии ps

    next() спрашивает и передвигает
      возвратит булево

    2015

    save()

    2030

    ДЗ

## Домашнее задание HW13
- [x] Пройдено

![hw](https://cloud.githubusercontent.com/assets/13649199/13672719/09593080-e6e7-11e5-81d1-5cb629c438ca.png) 
Домашнее задание HW13

- [x] Доделать `SqlStorage` без контактов и секций
- [x] Для работы с DB надо в lib и проект добавить 
  [драйвер базы данных](http://repo1.maven.org/maven2/org/postgresql/postgresql/42.2.1)
- [x] Запустить `SqlStorageTest` (в `AbstractStorageTest` контакты и секции закоменченны), 
  креденшелы к базе взять из `Config`
- [x] Вынести общий код (`getConnection(), prepareStatement, catch SQLException`) в класс `SqlHelper`
(https://dzone.com/articles/removing-duplicate-code-with-lambda-expressions)

Занятие 14
==========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Четырнадцатое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson14.md)

- Разбор домашнего задания
- Операции соединения таблиц. JOIN
- Транзакции
- Требования к транзакциям. ACID
- Уровни изоляции транзакций в SQL
- Установка и настройка контейнера сервлетов Tomcat
- Домашнее задание

***

## Разбор Домашнего Задания-13
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-13](https://drive.google.com/open?id=0B_4NpoQW1xfpREpRYm5ZLWN2RWc)

[см. коммит Lesson14 HW13](https://github.com/JavaWebinar/basejava/tree/aa4dd3537275cc3be0d68aeb902d28c0ef94e747)

### Аннотация видео
14_1_HW13.mp4 - Shortcut

    Утильный класс
      SqlHelper
    
    0435 
    
    stackoverflow

    0528

    Т.е. договорились, что склеивать не будем, то
    нам нужен параметр в sqlHelper.execute

    Делаем универсально - паттерн Стратегия

    Есть интерфейс, в нутри которого 
      мы можем в ps засетить параметры
        он будет выполняться
    
    Добавить интерфейс и через него реализовать метод get
      SqlExecutor
        все, что в нем есть - PreparedStatement statement

      где-то в sqlHelper-е мы создаем ps, потом мы его 
        передаем в интерфейс sqlExecutor
          в нем действие, которое мы задаем в нашем анон классе
          исполняется
          
          и делаем execute

    0646

    Создаем интерфейс SqlExecutor
      паттерн Стратегия

0746

    1020

    sqlHelper устраняем дублирующий код
      делегируем конструктор более частный случай 
        в более общий

      делегирование - вызов в какими-то параметрами

1140

2240

    Наполнение БД

## JOIN
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. JOIN](https://drive.google.com/open?id=0B_4NpoQW1xfpT3R6WFBBbmVGXzA)

[см. коммит Lesson14 JOIN](https://github.com/JavaWebinar/basejava/blob/57c5687e276d4fb3bfcf8d7b0c7b301db1a0095b/src/ru/javawebinar/basejava/storage/SqlStorage.java)
- <a href="http://www.skillz.ru/dev/php/article-Obyasnenie_SQL_obedinenii_JOIN_INNER_OUTER.html">LEFT, RIGHT, INNER JOIN</a>
- [SQL Join](https://www.youtube.com/watch?v=EHvzvwAv7RU&index=1&list=PLY7PmJJFH5nT-lbFKxfbp3rw5BBuq5Azo) (youtube)
- Добавляем в `SqlStorage` контакты

### Аннотация видео
14_2_JOIN.mp4

    Чаще всего встречаются
      INNER JOIN - default JOIN

      LEFT 

      OUTER 

    Склеивание таблиц по общему полю

    0226

    К талице резюме приконнекчиваем таблицу контактов
      по полю алиасы используем
        r.uuid = c.resume.uuid
    
0445

    SQL нужно знать на среднем уровне
      большие запросы - на экран
        выравнивать с отступами

    Разбирался с вызовами и интерфейсами

    Разобрался с connnectionFactory и SqlHelper

0508

0526

    Заполнение контактов

        select *
        from resume r
                left join contact c
                          on r.uuid = c.resume_uuid
        where r.uuid = '22054d98-e6ab-4c46-a99a-c68a6ffcd3e5'

0932

    В общем, я понял, что мне не понятно как реализован CRUD в решении Григория. Конкретно - я не могу найти конец, на котором замыкается цепочка execute-ов. Lesson13.

    Ок, попробую по-другому. Зачем нам интерфейс?

1533

    getAll
    
    подходы
      достать все резюме
        поджойнить туда контакты
      
      можем достать сначала
        все из таблицы резюме, потом 
        все из таблицы контактов  

          объединить вручную где-то на уровне кода

      если у нас много резюме и контактов, у каждого резюме по 
      нескольку контактов
        получается дублирование строк

      много лишних данных - накладные расходы

        сначала достать все из таблицы 
          резюме
        затем из таблицы
          контакты
        
        склеивать их на уровне кода

## Транзакции
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Транзакции](https://drive.google.com/open?id=0B_4NpoQW1xfpTm43Z2hnZkV4c2M)

[см. коммит Lesson14 Transaction_Batch](https://github.com/JavaWebinar/basejava/tree/0901c3a80ce8150524f2513c7ba148fdd03e49b2/src/ru/javawebinar/basejava)
- <a href="http://ru.wikipedia.org/wiki/Транзакция_(информатика)">Транзакция. ACID.</a> 
  <a href="https://ru.wikipedia.org/wiki/Уровень_изолированности_транзакций">Уровни изоляции транзакций.</a>
- <a href="http://www.osp.ru/pcworld/2009/07/9708191/">Уровни изоляции транзакций в SQL</a>
- Добавляем в `SqlStorage` транзакции
- Batch execute.

### Аннотация видео
14_3_Transaction.mp4

    Атомарная группа последовательных операций
      либо полностью выполняется
      либо откатывается
        rollback
      
      пример с аккаунтами

    Большинство операций на модификацию делается через транзакции

    Если мы используем ORM инструменты - реализуют JPA
      все операции происходят через транзакции

    Свойство ACID
      Атомарность
      Согласованность
      Изолированность
      Долговечность

    Уровни изоляции транзакции

    Чем выше уровень (таблица), тем дольше выполняется

    0430

    делаем в транзакции

    Добавляем интерфейс SqlTransaction, с которым будем 
    работать из SqlHelper
      SqlTransaction работает с conn
        берем из него ps, 
        выполняем,
        делаем commit
          или rollback

    0511
    
    добавляем transactionalExecute в SqlHelper

    setAutoCommit false
    по умолч true - маленькие операции
      нам нужно сделать транзакционно несколько операций в одном connection 

    0817

    существует аннотация 
    @Transacional

    по бизнес транзакциям операцию rollback не делает, а по

    exception-ам происходит rollback

    это поведение можно тоже менять

    0852

    попробуем составные операции проводить в транзакции

    0939 

    save

## Установка/запуск Tomcat
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[3. Установка/запуск Tomcat](https://drive.google.com/open?id=0B_4NpoQW1xfpZU9QQ25VTkRmSjg)

- Скачать и установить <a href="http://tomcat.apache.org/download-80.cgi">Tomcat 8</a>. 
  Устанавливать лучше простым копированием из архива в каталог (в том числе и для unix). 
  Следите чтобы в пути не было пробелов и национальных букв.
- Для доступа к <a href="http://localhost:8080/manager">Tomсat Manager</a> 
  добавьте в конфигурацию Tomcat `TOMCAT_HOME\conf\tomcat-users.xml` права:
```
<user username="tomcat" password="tomcat" roles="tomcat,manager-gui,admin-gui"/>
```
- Запуск из `TOMCAT_HOME\bin\`: `catalina.bat start`
 
### Аннотация видео
14_4_Tomcat.mp4

    работает

## Домашнее задание HW14
- [x] Закончить реализацию `SqlStorage` с контактами
- [x] Выделить общие части <a href="https://ru.wikipedia.org/wiki/Don%E2%80%99t_repeat_yourself">( DRY )</a>

Занятие 15
==========
- [x] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Пятнадцатое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson15.md)

- Разбор домашнего задания
- Введение в HTML
- Основы протокола HTTP
- Настройка web.xml
- Развертывание (деплой) web-приложения в Tomcat
- Сервлеты
- Домашнее задание

***

## Разбор Домашнего Задания-14
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-14](https://drive.google.com/open?id=0B_4NpoQW1xfpY1hTY282dzhuOFU)

[см. коммит Lesson15 HW14](https://github.com/JavaWebinar/basejava/tree/02aee9744d7512dfa9ffbebe00ad415ffe5f71ea)

### Аннотация видео
1_HW14_SqlStorage.mp4 - Shortcut

    DRY

    update

    контакты
      сохраненные
      которые пришли к нам

    мапа контактов
      тип значение

      могли 
        удалить
        добавить
        обновить

      нужно сравнивать

      если был
        обновлять
      не стало
        удалять
      не было
        появился
          инсертить - сохранять
      
      сложна логика

      делают (мы) по простому
        удалим контакты, которые были в резюме и 
          добавим по новой

        contacts
          delete
          insert

    0811

    save

    переносим ins contact в отд. метод

    1115 

    вынесли общую часть кода - утильные методы

    1148

    getAllSorted

    варианты
      join
        1 запрос к базе
          получаем все резюме со всеми контактами
            начинаем их разделять
          не нужно делать через транзакцию, т.к. всего 1 зарпос
          не большой оверхед
      2 запроса запрашиваем 
        все резюме
        все контакты 
      начинаем их склеивать

    делаем по 1 варианту - через left join

    1326

    order by - если full_name совпали, по по uuid

1406

    2421

    Подкручиваем тесты

    Дебажим
      addContact

IDEA

    F7
    выделяем 
    Alt F8

2644

    getAllSorted смотрим

    2708

    ставим BP getAllSorted

    3032

    секции

    через разделитель (перенос строки)

    кроме OrganizationSection

## HTML, Tomcat
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. HTML, Tomcat](https://drive.google.com/open?id=0B_4NpoQW1xfpZk1pQ1h4dEJBVEE)

[см. коммит Lesson15 web](https://github.com/JavaWebinar/basejava/tree/2fe01af02b7ba82c3f0c8fa29dc3effb5b575531/src/ru/javawebinar/basejava)

- <a href="http://java-course.ru/student/book1/servlet/">Протокол HTTP</a>. 
  Смотрим <a href="http://topjava.herokuapp.com/">демо приложение<a/> в Chrome -> Инструменты разработчика</a>
- Добавление в проект Web Facet. web.xml. Постороение/cтруктура WAR. Статические ресурсы.
- Настройка и деплой в Tomcat. Tomcat manager.
- Запуск Tomcat из IDEA. Динамическое обновление без передеплоя.

### Аннотация видео
2_web_tomcat.mp4

    объясняется почему клиентское приложение - веб-браузер

    0604

    инструменты разработчика в хроме

0703

    json передается
    массив объектов js

    0900 
    
    есть запрос
    тело запроса, где спрятаны параметры
    
    методы 
      основные 
        get
          ?lang=en
          параметр=значение

        post
          при добавлении еды
          в URL параметром 
            все они находятся в 
            view source
            в теле запроса
              в них передаются параметры в форме, которые мы ввели

            имя значение & (амперсанд) 

            URL Encode
              Специальные символы энкодятся
                Класс UrlEncoder и декодер

            Браузер производит те же преобразования
              Символ не ASCI код - кодами, т.к. русские символы

          
    в теле запроса что угодно может быть
      Response - возвращается в тебе запроса

    заголовки помогают общаться браузеру и серверу

    1628

    код 302 - редирект на логин (авторизацию)

    1757

    пробуем сделать из нашего проекта - веб-проект

    web.xml Добавился, который обрабатывается Tomcat-ом

2020

    добавили файлы статические 

    закончил это видео, перешел к сл.

3100

    Проблема интеграции с IDEA

      HTTP Status 404 – Not Found
        Type Status Report

## Сервлеты
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Сервлеты](https://drive.google.com/open?id=0B_4NpoQW1xfpUWw3NWo0SVFBRjg)

[см. коммит Lesson15 static_content](https://github.com/JavaWebinar/basejava/tree/e9a4a68e8e360f9cbcd3ff12d27876cee1b9f8cd/src/ru/javawebinar/basejava/web)

[см. коммит Lesson15 servlets](https://github.com/JavaWebinar/basejava/tree/4d1043a3a45d27eda11fdc9c68ac46aa68fdd563)

- <a href="http://devcolibri.com/как-создать-servlet-полное-руководство/">Создаем Servlet</a>. Параметры. Кодировка. 
- Дополнительно:
    - <a href="http://stackoverflow.com/questions/3106452/how-do-servlets-work-instantiation-shared-variables-and-multithreading">How do servlets work?</a>
    - <a href="http://www.intuit.ru/studies/courses/569/425/lecture/9683">Язык программирования Java: введение в сетевое программирование</a>
    - <a href="http://www.intuit.ru/studies/courses/1102/134/info">Основы работы с HTML</a>
    - <a href="http://ru.html.net/tutorials/html/">Учебник HTML</a>
    - [Ссылки по HTML, JavaScript, CSS](https://github.com/JavaOPs/topjava#html-javascript-css)

### Аннотация видео
3_servlet.mp4

    0250

    web.xml 
    входная точка для контейнера
    куда направляет все запросы 
      не статические
        смотрит соответствие запроса
    конфигурация роутинга

    парами идёт
      связаны по имени servlet-name
      класс в первом
      по какому пути будет связывание - вторым
      
    динамика - маппинг, связывание

    application context 
      /resumes

    url 
      /resume/...
    
      тогда перенаправлять в ResumeServlet

    В ResumeServlet отнаследован от HttpServlet

    servlet не входит в JavaSE

    подтягивает - библиотека

    https://search.maven.org/search?q=servlet-api

    добавил 3 библиотеки через подтягивание через IDEA

    1250

    write

    http://localhost:8080/resumes/resume?name=Denis

    закончил

## Домашнее задание HW15
- [x] Сделать реализацию `SqlStorage.getAllSorted` через 2 отдельных запроса: 
  отдельно резюме и отдельно контакты.
- [x] Добавить в реализацию `SqlStorage` и в базу секции (кроме `OrganizationSection`). 
  Для `ListSection` склеиваем строки через `\n`.
- [x] Сделать отображение таблицы резюме в сервлете (табл resume, т.е. только uuid и fullName).
  - <a href="http://www.webremeslo.ru/html/glava4.html">HTML таблицы</a>

Занятие 16
==========
- [ ] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Шестнадцатое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson16.md)

- Разбор домашнего задания
- Жизненный цикл сервлета
- Создание динамических страниц. JSP
- Расширенные возможности JSP: JSTL
- Redirect и Forward
- CRUD
- Домашнее задание

***

## Разбор Домашнего Задания-15. DB
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-15. DB](https://drive.google.com/open?id=0B9Ye2auQ_NsFS0J4TEN2cjdtWjQ)

[см. коммит Lesson16 HW16 DB](https://github.com/JavaWebinar/basejava/tree/39775ee817be0da26ce111db9ba475bfd97b5a4c)

### Аннотация видео
1_HW15_db.mp4 - Shortcut

    ускоренно просмотрел до донца

    0723

    достали все резюме и сохранили в мапу в том порядке
    как было в базе

    0853

    addSection

    1030

    секцию сериализовать в строку и десерилизовать из нее
     вместо join-ов

    mongodb как pg по популярности
      все документы в json хранятся
    есть индексы, ссылки, не просто кусок текста

    доставать целиком нужно, чтобы с ним работать

    переиспользуем наш код по сер/десер json
      делить на таблицы не обязательно

    преимущества по таблице
      позиций 
        будем хранить по полям

      сможем делать выборку запросом

      фильтры

      сложные запросы

    если одной строкой, то такой запрос уже не сможем сделать

    у нас гибкие вещи не запланированы

    если отчеты, то не получится
      завязаны на структуру, которую мы выбрали

    сразу нужно понимать ограничения
      нашего решения

    1439

    почему выбрали именно json

    привычный формат

    более короткий, читаемый (не бинарный как DataStringSeri)

    в pg ввели json хранение в последних версий

    1606

    нужно немного доработать json парсер

    мы должны уметь читать и писать строки JsonParser
    
    1853

    getAll готов

    1900

    добавляем секции в остальные методы

    1930

    delete - у нас cascade

    1928 

    save

    2014

    insertSections

    2205

    добаротка write JsonParser

    с одним параметром не работало

    2240 

    создали JUnit тест JsonParserTest

    тест как резюме работает

    не идет в прод

    используется в maven при сборке

    регрессионное тестирование

    3025

    прошел тест

    нужно подавать .class в метод

    write - сериализация
    read - десериализация

    3131

    update

    можно было бы удалить резюме и создать снова
    в одной тразакции

    save в своей транзакции

    получается вложенность

    в фреймворках

    есть артибуты если одна в другой транзакции

    3309

    deleteSections добавляем

    3330

    не в том же коннекте делали

    3525

    update

    все делается через 1 connect, через назные ps

    3554

    get

    делаем не join а как getAll

    завершил

## Разбор Домашнего Задания-15. Servlet
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-15. Servlet](https://drive.google.com/open?id=0B_4NpoQW1xfpZWVSX0tCTjRiU28)

[см. коммит Lesson16 HW16 servlet](https://github.com/JavaWebinar/basejava/tree/46a5500bc1060ca7ab90ceb4de7979d0cefa3824)

- <a href="https://habrahabr.ru/post/231213/">Почему вы никогда не должны использовать MongoDB</a>
- <a href="https://ru.wikipedia.org/wiki/%D0%A1%D0%B5%D1%80%D0%B2%D0%BB%D0%B5%D1%82_(Java)#.D0.96.D0.B8.D0.B7.D0.BD.D0.B5.D0.BD.D0.BD.D1.8B.D0.B9_.D1.86.D0.B8.D0.BA.D0.BB_.D0.A1.D0.B5.D1.80.D0.B2.D0.BB.D0.B5.D1.82.D0.B0">Жизненный цикл сервлета</a>
- <a href="http://tomcat-configure.blogspot.ru/2009/01/tomcat-maxthreads-configuration.html">Tomcat maxThreads configuration</a>
- [Веб-приложение с Java Servlets](https://tproger.ru/translations/building-a-web-app-with-java-servlets/)

### Аннотация видео
2_HW15_servlet.mp4

0248

    жизненный цикл сервлета

    инстанциирует сервлет томкат

    до сервлетов 2.3
    томкат создавал пул сервлетов

    веб-контейнер - многопоточное приложение

    томкат по умолч 200 потоков
    200 пользователей

    сейчас создается всего 1 инстанс этого сервлета

    все запросы будут работать с этим одним инстансом

    0540

    Нельзя создавать член класса uuid или др. в классе Servlet

    сервлеты доложны быть thread safe

    VM options

## 1. JSP
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. JSP](https://drive.google.com/open?id=0B_4NpoQW1xfpQ2hYRWJ2TWd2QjA)

[см. коммит Lesson16 jsp](https://github.com/JavaWebinar/basejava/tree/b29ed85e8a99432de317dcae0780ecedc37981ac)

### Аннотация видео
3_jsp.mp4


    Компилятор JSP-страниц
      Jasper

    В половине проектов есть JSP

    Он встроен в Tomcat
      не нужно подтягивать

    Простые вещи можно делать на нем

    Apache Velocity

    Thymeleaf движок
      Spring
        Boot
      
      Есть в MasterJava

    0334

    Внутри WEB-INF не видно по URL клиенту

    0452

    создался шаблон

    инструкции <% %>

    Jasper ищет в web/ jsp-файлы и компилит их в сервлеты

    можно динамически изменять контент

    использование java-вставок <% %> плохой тон - 
      переход на jstl

## 2. include
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. include](https://drive.google.com/open?id=0B_4NpoQW1xfpRy1DbWhRVXhTbHc)

[см. коммит Lesson16 include](https://github.com/JavaWebinar/basejava/tree/28f305b52abb96f237b4e30447b102f9b67d12a5/web/WEB-INF/jsp)

- <a href="http://java-course.ru/student/book1/jsp/">Что такое JSP</a>. <a href="https://ru.wikipedia.org/wiki/JSP">Wiki JSP</a>
- <a href="https://www.hscripts.com/tutorials/jsp/variables.php">Predefined Variables in JSP</a>
- <a href="http://www.javaportal.ru/java/articles/Java_Server_Pages.html">Стандартные элементы action</a>
- <a href="http://stackoverflow.com/questions/4764405/how-to-use-relative-paths-without-including-the-context-root-name">How to use relative paths in JSP</a>
- Отличие Redirect от Forward

### Аннотация видео
4_jsp_fragment.mp4

    вставки против дублирования

    jstl директивы находятся в jsp в шапке

    хедер футер - один фрагмент

## 3. JSTL
- [x] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[3. JSTL](https://drive.google.com/open?id=0B_4NpoQW1xfpSHdUNE9TZWNJV1k)

[см. коммит Lesson16 jstl](https://github.com/JavaWebinar/basejava/blob/a909d0854c47753d8f278a9d6e930411992762ac/web/WEB-INF/jsp/list.jsp)

- <a href="https://ru.wikipedia.org/wiki/JSTL">JSTL</a>
- <a href="https://devcolibri.com/jstl-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B0%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D1%8F-jsp-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86">
  JSTL для написания JSP страниц</a>

### Аннотация видео
5_jstl.mp4

    0110

    tablib подключаем директиву

    появляется новый функционал

    for

    ${  }

    0254

    интеграция useBean 

    библиотеку jstl-1.2 поставил, импортнул в WEB-INF

## 4. CRUD
- [ ] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[4. CRUD](https://drive.google.com/open?id=0B_4NpoQW1xfpak9nZS1BXzBTbEU)

[см. коммит Lesson16 crud](https://github.com/JavaWebinar/basejava/tree/3e07257a33d1ba51508e315d6021aa1b78849fca)

### Аннотация видео

## Домашнее задание HW16
- [ ] Доделать логику сервлета
- [ ] Дополнить отображение и редактирование JSP секциями

Занятие 17
==========
- [ ] Пройдено

[Общий список занятий](https://github.com/JavaWebinar/basejava)

[Семнадцатое занятие](https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson17.md)

- [ ] Разбор домашнего задания
- [ ] Деплой приложения в облачный сервис Heroku
- [ ] Загрузка классов в Java. Classloader
- [ ] Домашнее задание

***

## Разбор Домашнего Задания-16
- [ ] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-16](https://drive.google.com/open?id=0B_4NpoQW1xfpR2U1OUJEM0hzc1k)

[см. коммит Lesson17 HW16](https://github.com/JavaWebinar/basejava/tree/dc678d613ecdf18d9973e7464ddc997ad316c22f)

### Аннотация видео

## Разбор Домашнего Задания-16 добавление резюме
- [ ] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[Разбор Домашнего Задания-16 добавление резюме](https://drive.google.com/open?id=0B_4NpoQW1xfpQ1d3VmN1RHA1Q1k)

[см. коммит Lesson17 HW16_add_resume](https://github.com/JavaWebinar/basejava/tree/10c521a8d412b3a4b3256d3044504fb269e16a26)

### Аннотация видео

## 1. Деплой в Heroku
- [ ] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[1. Деплой в Heroku](https://drive.google.com/open?id=0B_4NpoQW1xfpS2JSSDByQ2xGWm8)

[см. коммит Lesson17 DB_credentials_as_resources](https://github.com/JavaWebinar/basejava/tree/9b8552f6957ae48440685cba5a24afd592e60fba)
- <a href="https://devcenter.heroku.com/articles/war-deployment#deployment-with-the-heroku-cli">Deployment with the Heroku CLI</a>
- для доступа к удаленной БД используйте следующие настройки SSL `ssl=true&sslmode=verify-ca&sslfactory=org.postgresql.ssl.NonValidatingFactory`

### Аннотация видео

## 2. Classloader
- [ ] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[2. Classloader](https://drive.google.com/open?id=0B_4NpoQW1xfpQnJQZ0d2ajJNWlU)

- <a href="https://habrahabr.ru/post/103830/">Загрузка классов в Java</a>
- <a href="https://tomcat.apache.org/tomcat-8.0-doc/class-loader-howto.html">Apache Tomcat Class Loader</a>

### Аннотация видео

## 3. Вебинар "Осваиваем Java String/JPA Enterprise"
- [ ] Пройдено

![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 
[3. Вебинар "Осваиваем Java String/JPA Enterprise"](https://drive.google.com/file/d/0B9Ye2auQ_NsFY1ZDNXRCd1NCTG8)

- [Слайды вебинара](https://goo.gl/XNVOj4)
- <a href="https://habrahabr.ru/post/308104/">Из юниоров в разработчики: получаем первую работу</a>
- <a href="http://zeroturnaround.com/rebellabs/java-tools-and-technologies-landscape-2016/">Java Tools and Technologies Landscape Report 2016</a>

### Аннотация видео

#### Java Enterprise project Topjava
- <a href="http://javaops.ru/reg/topjava">Стажировка Spring/JPA Enterprise (Topjava)</a>
- <a href="http://javaops.ru/view/test">Ссылки по темам интервью, тестовое интервью</a>
- <a href="https://github.com/JavaOPs/topjava/blob/master/cv.md">Составление резюме, подготовка к интервью, поиск работы</a>
- [Как стать профессиональным Java разработчиком (Яков Фaйн)](https://www.youtube.com/watch?v=ft0Nj8Cm9kk)
