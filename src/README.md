# Исходный код проекта

## Структура кода

src/
├── main.py # Главный файл приложения
├── math/
│ ├── vector.py # Векторная алгебра
│ └── ray.py # Класс луча
├── geometry/
│ └── sphere.py # Класс сферы
├── rendering/
│ └── tracer.py # Основной движок
└── utils/
└── config.py # Настройки


## Зависимости
- Python 3.8+
- NumPy
- Matplotlib

## Запуск
```bash
python main.py


### src/main.py
```python
"""
Главный файл Ray Tracer
Проектная практика 2023
"""

from rendering.tracer import RayTracer
from geometry.sphere import Sphere
from math.vector import Vector3

def main():
    print("Запуск Ray Tracer...")
    
    # Создаем трассировщик
    tracer = RayTracer(800, 600)
    
    # Добавляем объекты в сцену
    tracer.add_object(Sphere(Vector3(0, 0, 0), 1.0))
    tracer.add_object(Sphere(Vector3(2, 0, -1), 0.5))
    
    # Рендерим сцену
    image = tracer.render()
    tracer.save_image("output.png")
    
    print("Рендеринг завершен!")

if __name__ == "__main__":
    main()
