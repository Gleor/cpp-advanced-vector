# **Vector**

## **Описание**

Упрощённый аналог [вектора](https://en.cppreference.com/w/cpp/container/vector) из стандартной библиотеки. Реализованы базовые методы контейнера, а также написан вспомогательный класс RawMemory для упрощения работы с сырой памятью. Проект создан для того, чтобы на более глубоком уровне понимать внутреннее устройство контейнера из стандартной библиотеки

## **Функционал**

### **Создание экземпляра класса**

**Конструктор по-умолчанию - создаёт пустой вектор**

```cpp
Vector<int> v;
```

**Конструктор с параметром - создаёт вектор заданного размера (заполнен значениями по умолчанию)**

```cpp
Vector<int> v(5);
```

**Копирующий конструктор и перемещающий конструктор**

```cpp
Vector<int> first_vector(5);
Vector<int> second_vector(first_vector);
Vector<int> third_vector(std::move(first_vector));
```

**Операторы копирующего присваивания и перемещающего присваивания**

```cpp
Vector<int> first_vector(5);
Vector<int> second_vector = first_vector;
Vector<int> third_vector = std::move(first_vector);
```

### **Методы**

**Получение информации о ёмкости списка**

```cpp
Vector<int> v(5);
v.Size();
v.Capacity();
```

**Swap - обмен содержимого вектора с другим вектором**

```cpp
Vector<int> first_vector(10);
Vector<int> second_vector(30);
first_vector.Swap(second_vector);
```

**PushBack - добавление элемента в конец вектора**

```cpp
Vector<int> v;
v.PushBack(1);
v.PushBack(2);
```

**PopBack - удаление последнего элемента в векторе**

```cpp
Vector<int> v;
vec.PopBack();
```

**Добавление и удаление элемента в произвольном место вектора**

```cpp
Vector<int> v;
v.Insert(v.begin(), 1);
v.Insert(v.begin(), 2);
v.Erase(v.begin() + 1);
```

**Reserve - резервирование места в векторе под новые элементы**

```cpp
//Резервирование памяти помогает избегать реаллокации 
Vector<int> v;
v.Reserve(3);

a.PushBack(1);
a.PushBack(2);
a.PushBack(3); // Реаллокация памяти не произойдёт

```

**Resize - изменение размера вектора**

```cpp
Vector<int> v;
v.PushBack(1);
v.PushBack(2);
v.PushBack(3);
v.Resize(6); // {1, 2, 3, 0, 0, 0}
a.Resize(2); // {1, 2}
```

**Emplace(EmplaceBack) - создание объекта в указанном месте **

Данный метод позволяет добавить элемент в вектор без копирований и перемещений, передавая параметры сразу конструктору

```cpp
Vector<int> v;
v.Emplace(v.begin(), 1);
v.EmplaceBack(2);
```

## **Системные требования**

Компилятор С++ с поддержкой стандарта C++17 или новее

## **Использование**

Для испольования данного класса нужно скопировать файл vector.h в папку с проектом и подключить через директиву #include "vector.h"
