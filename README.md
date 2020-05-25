# fugures
c++ figure printing program

Эта программа позволяет добавлять геометрические фигуры и выводить их 

Для **добавления** фигуры нужно ввести команду add, название фигуры и параметры \
Например: add circle 5

**Доступные фигуры**: \
  Circle (один параметр: радиус), \
  Rectangle (два параметра: ширина и высота), \
  Triangle (три парметра: стороны), \
  Square (один параметр: сторона). 
  
Для **вывода** фигуры нужно ввести команду print и индекс фигуры. \
Например: print 0 

Формат вывода: название_фигры параметры_фигуры

**Как запускать:** \
  make \
  ./figures (-usage)
  
 **Как все устроено:** \
  Добавленные фигуры хранятся в векторе.
  
  Есть базовый класс Figure, его наследники: Rectangle, Circle, Triangle.
  У класса Rectangle есть наследник Square.
  
  У класса Figure есть виртуальный метод Print, который переопределен в классах-наслениках.
  У класса Figure есть публичный метод GetName, в котором хранится тип фигуры.
  Метод GetName используется в методе Print наследников.
  
 Замечение:
  При выводе Square печатается 'Rectangle'. Так и должно быть, тк если представить, что есть какая-то функция
  из графической библиотеки, которая печатает фигруры, получится, что ей вообще не обязательно знать,
  выводит ли она обычный прямоугольник или частный случай прямоугольника - квадрат.
  
 **Обработка исключений:** \
  При некорректном вводе:
   - команды
   - типа фигуры
   - индекса фигуры
   
   программа сообщит об ошибке, но не прекратит работу.
   
   Значение параметров по умолчанию - 0.
   
  **Что можно улучшить:**
   - добавить методы для подсчета площади/периметра
   - подключить графичекую библиотеку и рисовать фигуры
   - добавить возможность задания координат для фигур
