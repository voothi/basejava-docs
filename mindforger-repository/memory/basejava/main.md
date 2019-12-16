# BaseJava <!-- Metadata: type: Outline; tags: mindforger-home; created: 2019-12-16 14:39:43; reads: 223; read: 2019-12-16 23:33:36; revision: 223; modified: 2019-12-16 23:33:36; importance: 0/5; urgency: 0/5; -->

# Занятие 1 <!-- Metadata: type: Note; created: 2019-12-16 16:02:49; reads: 33; read: 2019-12-16 22:43:39; revision: 5; modified: 2019-12-16 22:43:39; -->
Вступительное

Сдал HW1
# Занятие 2 <!-- Metadata: type: Note; created: 2019-12-16 14:39:43; reads: 15; read: 2019-12-16 22:43:42; revision: 3; modified: 2019-12-16 15:36:27; -->

## Видео 1. Принципы ООП <!-- Metadata: type: Note; created: 2019-12-16 14:39:43; reads: 16; read: 2019-12-16 22:43:43; revision: 1; modified: 2019-12-16 14:39:43; -->
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

## Видео 2. Структура памяти: куча, стек, регистры, константы <!-- Metadata: type: Note; created: 2019-12-16 14:39:43; reads: 13; read: 2019-12-16 22:45:09; revision: 1; modified: 2019-12-16 14:39:43; -->
* getClass() 

## Видео 3. Типы данных. Пакеты <!-- Metadata: type: Note; created: 2019-12-16 14:39:43; reads: 13; read: 2019-12-16 22:45:10; revision: 1; modified: 2019-12-16 14:39:43; -->
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

## Видео 4. Домашнее задание HW2 <!-- Metadata: type: Note; created: 2019-12-16 14:39:43; reads: 7; read: 2019-12-16 22:43:54; revision: 1; modified: 2019-12-16 14:39:43; -->
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


## Домашнее задание HW2 <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 9; read: 2019-12-16 22:43:54; revision: 1; modified: 2019-12-16 16:07:08; -->
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

## Ревью <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 5; read: 2019-12-16 22:40:59; revision: 1; modified: 2019-12-16 16:07:08; -->
Resume
+ toStringSuper - в классах модели принято переопределять метод toString, чтобы он кастомизировал вывод объекта модели, метод toStringSuper это избыточно и неправильно, он только усложняет восприятие кода
ArrayStorage
+ начиная с Java7 числа можно писать так 10_000, так улучшается читаемость длинных чисел
+ инициализируй поле хранилища при обьявлении, удали конструктор
+ clear - обнуляй только заполненую часть хранилища
- isPresentInMemory - удали этот метод, он нигде не используется
+ save - не нужно делать вывод об успешном сохранении
+ get - не надо итерироваться по массиву дважды..
  + return null перенеси в блок else
+ delete - удаляешь элементы без проверки их наличия
  + не было требования сохранять порядок элементов при удалении, попробуй использовать более “дешевый “ способ удаления, просто поменяв резюме местами
MainArray
>протестируйте ArrayStorage.update(Resume resume)
+ добавь тест для update в этом тестовом классе
Util
+ этот класс усложнил простой вывод в консоль, в нем нет надобности, обычного sout пока достаточно, в следующих уроках мы вместо них будем бросать исключения
+ Комментарии должны использоваться, чтобы дать краткий обзор кода и предоставить дополнительную информацию, которую нельзя легко получить из кода непосредственно, удали комментарии которые описывают очевидное
+ пиши в начале коммита номер ДЗ - WH2

# Занятие 3 <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 1; read: 2019-12-16 16:07:08; revision: 1; modified: 2019-12-16 16:07:08; -->

## Видео. Разбор домашнего задания <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 6; read: 2019-12-16 16:57:27; revision: 2; modified: 2019-12-16 16:57:27; -->
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

## Видео 1. Объектная модель в Java <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 3; read: 2019-12-16 16:49:59; revision: 1; modified: 2019-12-16 16:07:08; -->
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

fix: 14 18 реализовано на уровне С... Но, JVM на С++ написана https://en.wikipedia.org/wiki/HotSpot https://github.com/sourcemirror/jdk-8-hotspot

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

## Видео 2. Сложность алгоритмов <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 1; read: 2019-12-16 16:07:08; revision: 1; modified: 2019-12-16 16:07:08; -->
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

## Видео 3. Паттерн проектирования Шаблонный метод <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 1; read: 2019-12-16 16:07:08; revision: 1; modified: 2019-12-16 16:07:08; -->
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

## Видео 4. Домашнее задание HW3 <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 1; read: 2019-12-16 16:07:08; revision: 1; modified: 2019-12-16 16:07:08; -->
+ Просмотр видео
+ Перед тем, как приступить к ДЗ, приведите свой проект в соответствии с коммитами. Обратите внимание, что packages в видео и коммитах — отличаются
- Закончите реализацию AbstractArrayStorage, ArrayStorage, SortedArrayStorage, используя паттерн Шаблонный метод
- В SortedArrayStorage храните элементы отсортированными:
    сортировать весь массив не надо
    не используйте Arrays.sort() или самописные методы для сортировки
    для сортировки воспользуйтесь Arrays.binarySearch (бинарный поиск). Разберитесь с тем, какие значения он возвращает

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

## Ошибка NPE в реализованном методе get() для массива <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 3; read: 2019-12-16 16:50:00; revision: 1; modified: 2019-12-16 16:07:08; -->

### Ошибка <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 5; read: 2019-12-16 16:50:00; revision: 1; modified: 2019-12-16 16:07:08; -->
```log
Get r1: uuid1
Size: 3
Exception in thread "main" java.lang.NullPointerException
	at ru.voothi.webapp.storage.ArrayStorage.get(ru.voothi.webapp.storage.ArrayStorage.java:32)
	at ru.voothi.webapp.MainTestArrayStorage.main(ru.voothi.webapp.MainTestArrayStorage.java:21)

Process finished with exit code 1
```


### Код <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 7; read: 2019-12-16 16:50:02; revision: 1; modified: 2019-12-16 16:07:08; -->

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

### Решения <!-- Metadata: type: Note; created: 2019-12-16 16:07:08; reads: 11; read: 2019-12-16 16:54:50; revision: 1; modified: 2019-12-16 16:07:08; -->
- Хранить количество реально добавленных объектов 
    и при переборке массива через for 
        до количества вставленных объектов
- Flag "заполненности" чтобы сначала заполнить нулевые элементы
***
- Синтаксически if (uuid.equals(Optional.ofNullable(element.getUuid).orElse(null)) { ... }
- Переход на ArrayList
# Занятие 4 <!-- Metadata: type: Note; created: 2019-12-16 16:51:07; reads: 29; read: 2019-12-16 22:41:02; revision: 7; modified: 2019-12-16 16:53:45; -->
https://github.com/JavaWebinar/basejava/blob/lesson/lesson/lesson04.md

* Разбор домашнего задания
* Работа со строками: String, StringBuilder, StringBuffer
* String literal pool
* Исключения (Exceptions)
* Конструктор
* Ключевые слова: this, super
* Reflection
* Аннотации в Java 8
* Введение в модульное тестирование. JUnit
* Домашнее задание

## Разбор домашнего задания <!-- Metadata: type: Note; created: 2019-12-16 16:57:33; reads: 39; read: 2019-12-16 22:45:07; revision: 9; modified: 2019-12-16 22:44:40; progress: 100%; -->
[Разбор домашнего задания](https://drive.google.com/open?id=0B_4NpoQW1xfpQXVMb2xjRXJPdUU)

**Коммиты:**
 - [`lesson04 HW03`](https://github.com/JavaWebinar/basejava/tree/afc0cc5111434375f9da00e225ed7cbb15bbd4b7/src/ru/javawebinar/basejava/storage)

---

* [x] Задание разобрал
## Работа со строками <!-- Metadata: type: Note; created: 2019-12-16 16:57:33; reads: 72; read: 2019-12-16 23:33:36; revision: 45; modified: 2019-12-16 23:33:36; -->
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 1. [Работа со строками](https://drive.google.com/open?id=0B_4NpoQW1xfpSWVLYk51M2JpRnM)

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

***

 ## Видео
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

Так просто не получится определить позицию символа как во внутреннем представлении Java, в которой используется формат кодировки UTF-16, занимающей строго 2 байта на 1 символ.

Сколько каждый символ занимает нужно уже знать.

Загрузки процессора, который работает с вебом - 80% CPU занимает процесс конвертации на сервере в Java.

* Примеры разобрал 

https://github.com/voothi/java-my-experiments/commit/62c5410a8ba12ec41534fb02487f732d950e35f6

## Исключения <!-- Metadata: type: Note; created: 2019-12-16 16:57:33; reads: 12; read: 2019-12-16 17:15:23; revision: 2; modified: 2019-12-16 17:06:12; -->
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 2. [Исключения](https://drive.google.com/open?id=0B_4NpoQW1xfpQ1BaQjc3Y3N1MTQ)

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

## Reflection. Аннотации. Модульное тестирование <!-- Metadata: type: Note; created: 2019-12-16 16:57:33; reads: 16; read: 2019-12-16 17:15:26; revision: 2; modified: 2019-12-16 17:06:26; -->
![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 3. [Reflection. Аннотации. Модульное тестирование](https://drive.google.com/open?id=0B_4NpoQW1xfpT0dGZWlJbnN3bU0)

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

## Домашнее задание HW4 <!-- Metadata: type: Note; created: 2019-12-16 16:57:33; reads: 41; read: 2019-12-16 17:15:29; revision: 4; modified: 2019-12-16 17:10:06; -->
- Реализуйте тесты: `AbstractArrayStorageTest`, `ArrayStorageTest` и `SortedArrayStorageTest`
- В `MainReflection` сделайте вызов метода `toString` через отражение, и выведите результат

### Подсказки по HW4 <!-- Metadata: type: Note; created: 2019-12-16 17:10:06; reads: 11; read: 2019-12-16 17:15:31; revision: 2; modified: 2019-12-16 17:11:23; -->

- `SortedArrayStorageTest` должен запускаться с `SortedArrayStorage`
- `ArrayStorageTest` c `ArrayStorage`
- тестировать правильность сортировки не надо
- логика реализации теста на переполнение массива (`StorageException`):
  - заполняем массив, но не вызываем у него переполнение
  - если исключение вылетит раньше, чем массив будет заполнен, то тест должен провалиться (см. [`Assert.fail()`](https://stackoverflow.com/questions/3869954/whats-the-actual-use-of-fail-in-junit-test-case))
  - если исключение вылетает, когда пытаемся добавить в полностью заполненный массив еще одно резюме - тест пройден
- добавьте конструктор в `AbstractArrayStorageTest`, который инициализирует `Storage storage`, а в наследниках добавьте конструкторы, которые будут вызывать `super()` с нужным хранилищем

