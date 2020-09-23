# Лабораторная работа №1. Управление файлами и каталогами

## Задачи: ##
1. Освоить основные команды для работы с файлами и каталогами (директориями).
2. Научиться использовать справочную информацию по командам.
## Подсказки: ##
1. При выполнении работы могут использоваться следующие команды:
cat; cd; chmod, cmp; cp; diff; find; head; less; ln; ls; man; mkdir; mv; nano; patch; rm; split; vi; wc.
2. Для получения подробного справочного руководства по любой команде можно набрать в консоли
«man название команды», для кратной справки – название_команды --help.
3. По умолчанию, команды выводят результаты работы в консоль. Для перенаправления
стандартного вывода с консоли в файл можно использовать операторы «>» или «>>».
4. Команды могут быть собраны в конвейеры с помощью оператора «|».
5. Для удобства работы можно пользоваться одновременно несколькими консолями. На одной
консоли читать справочное руководство, на другой редактировать скрипт и т.п. Переключаться между
ними можно нажатием комбинации клавиш Alt+Fn, где Fn — функциональная клавиша (F1 — для
первой консоли, F2- для второй и т.д.).
6. Для того чтобы было удобнее смотреть результаты выполнения тех команд, которые что-то
выводят на экран можно после них вставлять в скрипт паузу (с помощью команды sleep) или ожидать
нажатия Enter с помощью команды read.
## Назначение команд: ##

+ ### cat
  Читает данные из файла и выводит их на экран  

      $ cat [файл]
+ ### cd
    Перемещение между дерикториями  

      $ cd [целевая директория]
+ ### chmod
    Читает данные из файла и выводит их на экран  

      $ chmod [опции] [права] [путь к файлу]
      Настройка прав: <группа пользователей><действие><вид прав>
  #### Виды прав:
  + **r** - чтение
  + **w** - запись
  + **x** - выполнение
  + **s** - выполнение от имени суперпользователя
  #### Категории пользователей:
  + **u** - владелец файла
  + **g** - группа файла
  + **o** - все остальные пользователи
  #### действия:
  + **\+** - включить права
  + **\-** - отключить права
+ ### cmp
    Позволяет осуществить побайтовое сравнение содержимого двух файлов  

      $ cmp [имя-файла-1] [имя-файла-2]
+ ### cp
    Копирование файлов  

      $ cp опции [файл-источник] [файл-приемник]
    #### Флаги:
    + --backup - режим копирование с созданием резервной копии
+ ### diff
    Cравнения двух или нескольких файлов или каталогов  

      $ diff [файлы или директории]
    #### Флаги:
    + u - различии в документах для создания патча
    + s - выводит информацию о том, что файлы идентичны
+ ### find
    Команда для поиска файлов и каталогов на основе специальных условий.  

      $ find [папка] [параметры] критерий шаблон [действие]
   + Папка - каталог в котором будем искать
   + Параметр - дополнительные параметры поиска
   + Критерий - критерий поиска (имя, дата создание, владелец и т.д.)
   + Шаблон - непосредственно значение по которому будем отбирать файлы
    #### Флаги:
    + type - тип файла для поиска f - файл, d - каталог
    + name - имя для поиска
    + maxdepth - максимальная глубина поиска по подкаталогам
+ ### head
    Выводит начальные строки (по умолчанию — 10)  из одного или нескольких документов.  

      $ head [опции] [файл]
+ ### less
    Позволяет перематывать текст не только вперёд, но и назад, осуществлять поиск в обоих направлениях, переходить сразу в конец или в начало файла.  

      $ less [опции] [файл]
+ ### ln
    Создание ссылок  

      $ ln [файл для создания ссылки] [ссылка]
    #### Флаги:
    + s - создание мягкой ссылки
    + r - путь для создания мягкой ссылки
+ ### ls
    Просмотр содержимого папки  

      $ ls
    #### Флаги:
    + a - отображать все файлы, включая скрытые, это те, перед именем которых стоит точка
    + p - добавлять символ, показывающий тип файла, к каждому имени файла.
    + l - выводить подробный список, в котором будет отображаться владелец, группа, дата создания, размер и другие параметры
    + R - рекурсивный вывод содержимого всех каталогов

+ ### man
    Форматирует и отображает страницы электронного справочника  

      $ man [имя утилиты]
+ ### mkdir
    Создание каталога

      $ mkdir [путь к каталогу]
+ ### mv
    Переместить (или переименовать) файлы или директории.  

      $ mv [исходные файлы] [куда или новые имена]
+ ### nano
    Открывает файл в редакторе nano  

      $ nano [файл]
+ ### patch
    Обновляет файл до последней версии используя файл патча 

      $ patch [оригинальный файл] [файл патча]
+ ### rm
    Удаление файлов или каталогов  

      $ rm [файл или каталогов]
+ ### split
    Разделяет файл на меньшие  

      $ split [файл]
    #### Флаги:
    + b - задаёт размер выводимых файлов
+ ### vi
    Открывает файл в редакторе vi  

      $ vi [файл]
+ ### wc
    Подсчет количества строк или слов в тексте  

      $ wc
    #### Флаги:
    + l - количество строк

## Задание: ##
Создать скрипт (создать текстовый файл с необходимыми командами (добавив в начало #!/bin/sh),
сделать его исполняемым). Создать и редактировать скрипт можно в редакторах nano или vi.
Скрипт должен выполнять следующие действия:
1. Создать каталог test в домашнем каталоге пользователя.
2. Создать в нем файл list, содержащий список всех файлов и поддиректориев каталога /etc (включая
скрытые) в таком виде, что можно однозначно определить какая из записей является именем файла, а
какая — названием директории.
3. Вывести в конец этого файла два числа. Сначала количество поддиректориев в каталоге /etc, а
затем количество скрытых файлов в каталоге /etc.
4. Создать в каталоге test каталог links.
5. Создать в каталоге links жесткую ссылку на файл list с именем list_hlink.
6. Создать в каталоге links символическую ссылку на файл list с именем list_slink.
7. Вывести на экран количество имен (жестких ссылок) файла list_hlink, количество имен (жестких
ссылок) файла list и количество имен (жестких ссылок) файла list_slink.
8. Дописать в конец файла list_hlink число строк в файле links.
9. Сравнить содержимое файлов list_hlink и list_slink. Вывести на экран YES, если файлы
идентичны.
10. Переименовать файл list в list1.
11. Сравнить содержимое файлов list_hlink и list_slink. Вывести на экран YES, если файлы
идентичны.
12. Создать в домашнем каталоге пользователя жесткую ссылку на файл list_hlink с именем list1.
13. Создать в домашнем каталоге файл list_conf, содержащий список файлов с расширением .conf, из
каталога /etc и всех его подкаталогов.
14. Создать в домашнем каталоге файл list_d, содержащий список всех подкаталогов каталога /etc,
расширение которых .d.
15. Создать файл list_conf_d, включив в него последовательно содержимое list_conf и list_d.
16. Создать в каталоге test скрытый каталог sub.
17. Скопировать в него файл list_conf_d.
18. Еще раз скопировать туда же этот же файл в режиме автоматического создания резервной копии
замещаемых файлов.
19. Вывести на экран полный список файлов (включая все подкаталоги и их содержимое) каталога
test.
20. Создать в домашнем каталоге файл man.txt, содержащий документацию на команду man.

21. Разбить файл man.txt на несколько файлов, каждый из которых будет иметь размер не более 1
килобайта.
22. Создать каталог man.dir.
23. Переместить одной командой все файлы, полученные в пункте 21 в каталог man.dir.
24. Собрать файлы в каталоге man.dir обратно в файл с именем man.txt.
25. Сравнить файлы man.txt в домашней каталоге и в каталоге man.dir и вывести YES, если файлы
идентичны.
26. Добавить в файл man.txt, находящийся в домашнем каталоге несколько строчек с произвольными
символами в начало файла и несколько строчек в конце файла.
27. Одной командой получить разницу между файлами в отдельный файл в стандартном формате для
наложения патчей.
28. Переместить файл с разницей в каталог man.dir.
29. Наложить патч из файла с разницей на man.txt в каталоге man.dir.
30. Сравнить файлы man.txt в домашней каталоге и в каталоге man.dir и вывести YES, если файлы
идентичны.
***
Предъявить скрипт преподавателю и ответить на его вопросы по любым использованным командам и
выполняющимся операциям. Перед сдачей лабораторной работы подумать, как объяснить результаты
выполнения пунктов 7, 9, 11, 25, 30