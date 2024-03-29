#технологии #obsidian #плагины #заметки #базаданных #инструкция 

**Dataview** - плагин, позволяющий создавать базы данных в Obsidian

## Синтаксис


### Заметки

Для создание базы данных необходимо в заметку внести [[Список переменных Yaml|метаданные]], по которым будет происходить сортировка и формироваться выборка

**Синтаксис ввода метаданных:**

"---
Переменная 1: значение
Переменная 2: значение
---"

**Или:**

"Переменная 1:: значение
Переменная 2:: значение"

**Например:**

"---
Сон: 7 
Пульс: 43
Дата: 16.08.2022
---"


### База данных

Для удобства использования базы данных лучше создать отдельную заметку

##### Структура создания базы

**Форма показа:**

1) TABLE - таблицы
2) TASK - задачи
3) LIST - список
4) CALENDAR - календарь

**Команды**: 

- file.mtime - даты изменений заметок

**Выбор папки:** 

FROM "Имя папки"

**Сортировка:**

SORT "Переменная"
SORT file.ctime - сортировка по времени создания файла
SORT ASC - по возрастанию
SORT DESC - по убыванию 

**Фильтр:**

WHERE Переменная; "Переменная ><= значение"; !completed (выполненный чек-лист)


**Пример структуры базы данных:**

```dataviev
TABLE Переменная AS "Название", Переменная AS "Название" и т.д.
FROM "Имя папки"
WHERE Переменная = "значению" и т.д.
SORT Переменная
```


##### Информация:

https://blacksmithgu.github.io/obsidian-dataview/


https://www.makeuseof.com/obsidian-dataview-notes-guid

https://youtu.be/JTObSymEvWA



