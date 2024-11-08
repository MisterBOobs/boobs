# Калькулятор времени в пути между городами России

Программа на Python для расчета времени в пути между двумя городами на основе расстояний и средней скорости. Программа использует словарь city_distances, в котором хранится информация о расстояниях между различными городами России. Пользователь вводит два города и среднюю скорость транспорта, а программа рассчитывает время в пути.

## Описание

Программа запрашивает у пользователя названия двух городов и среднюю скорость транспортного средства. Используя заданные расстояния между городами, программа вычисляет и выводит время в пути. Если введенные города отсутствуют в базе данных расстояний, программа выводит сообщение об ошибке.

## Структура данных

Расстояния между городами хранятся в словаре city_distances, где каждый ключ — это кортеж из двух городов, а значение — расстояние между ними в километрах. Пример данных:

* city_distances = {
    ("Москва", "Санкт-Петербург"): 635,
    ("Москва", "Новосибирск"): 3300,
    ("Москва", "Екатеринбург"): 1660,
     ...другие города
}

## Код программы

#### Функция calculate_travel_time

Эта функция принимает названия двух городов (city1, city2) и среднюю скорость транспорта (speed). Функция проверяет наличие расстояния между городами в словаре city_distances, вычисляет время в пути и возвращает его.

* def calculate_travel_time(city1, city2, speed):
  key = (city1, city2) if (city1, city2) in city_distances else (city2, city1)
    
    if key in city_distances:
        distance = city_distances[key]
        time = distance / speed 
        return time
    else:
        return None

#### Функция main

Функция main запускает интерфейс для пользователя. Она запрашивает у пользователя входные данные: два города и среднюю скорость. Затем вызывает calculate_travel_time и выводит результат.

* def main():
    print("Калькулятор времени в пути между городами России")
    city1 = input("Введите первый город: ")
    city2 = input("Введите второй город: ")
    speed = float(input("Введите среднюю скорость вашего транспорта (км/ч): "))

    travel_time = calculate_travel_time(city1, city2, speed)

    if travel_time is not None:
        print(f"Время в пути между {city1} и {city2} при скорости {speed} км/ч составит {travel_time:.2f} часов.")
    else:
        print("Извините, расстояние между этими городами не найдено в базе данных.")

## Использование

 1. Запустите программу.
 2. Введите названия двух городов.
 3. Введите среднюю скорость транспорта в км/ч.

## Пример работы программы:

Калькулятор времени в пути между городами России
Введите первый город: Москва
Введите второй город: Санкт-Петербург
Введите среднюю скорость вашего транспорта (км/ч): 80
Время в пути между Москва и Санкт-Петербург при скорости 80 км/ч составит 7.94 часов.

## Примечание

Если расстояние между введенными городами не найдено в базе данных, программа выводит сообщение:

Извините, расстояние между этими городами не найдено в базе данных.

## Установка и запуск

 1. Сохраните файл с кодом.
 2. Запустите файл в терминале или в Python IDE, например:

* python travel_time_calculator.py
