# Field Analyzer

![C++17](https://img.shields.io/badge/C%2B%2B-17-00599C?style=flat&logo=cplusplus&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=flat&logo=opencv&logoColor=white)
![GDAL](https://img.shields.io/badge/GDAL-3.x-88C940?style=flat)
![License](https://img.shields.io/badge/license-private-red?style=flat)

Приложение на C++ для анализа мультиспектральных снимков Sentinel-2. Рассчитывает вегетационные индексы (NDVI, EVI, PRI)
и выполняет геостатистический анализ полей.

> Это репозиторий для демонстрации возможностей программы. Сам исходный код приватный.

## Демо

https://github.com/user-attachments/assets/a78ec42e-de7a-4b25-a0c4-8775d01b7a16

### Исходный снимок


![Source](https://iili.io/fQIf0qQ.md.jpg)

## Возможности

**Вегетационные индексы:**

- NDVI — оценка здоровья растительности
- EVI — усовершенствованный индекс с учетом атмосферных помех
- PRI — фотосинтетическая активность

**Геостатистика:**

- Расчет эмпирических вариограмм
- Подбор теоретических моделей (сферическая, экспоненциальная, Гаусса)
- Оптимизация через KD-Tree: O(N²) → O(N log N)

**Производительность:**

- Параллельная обработка через OpenMP
- Эффективная работа с большими растрами
- Оптимизированные структуры данных

## Результаты

Программа принимает 4 канала Sentinel-2 (B02, B03, B04, B08) и генерирует:

### NDVI

![NDVI](https://github.com/user-attachments/assets/a2ca098f-fe75-4f4b-8182-c2ae5d5e1726)

### EVI

![EVI](https://github.com/user-attachments/assets/2d6a1a12-ecc8-48ed-8fc6-f01a5a2d7cad)

### PRI

![PRI](https://github.com/user-attachments/assets/f97cdbce-9f8d-431c-bfb4-3a2c4b376076)

### Вывод

![Terminal](https://github.com/user-attachments/assets/6633ff63-ab59-484e-8d0b-70075b164940)

## Технический стек

* **Язык:** C++17
* **Обработка изображений:** OpenCV 4.x
* **Геопространственные данные:** GDAL (JP2, GeoTIFF)
* **Линейная алгебра:** Eigen3
* **Параллелизм:** OpenMP
* **Логирование:** spdlog

## Выходные файлы

```
ndvi_colored.png # Тепловая карта NDVI
ndvi_classified.png # Классификация зон NDVI
ndvi_stats.txt # Статистика (min/max/mean/stddev)
ndvi_variogram.csv # Данные вариограммы
ndvi_variogram_params.json # Параметры модели вариограммы

evi_colored.png # Тепловая карта EVI
evi_classified.png # Классификация зон EVI
evi_kriging.png # Интерполяция кригингом
evi_stats.txt # Статистика EVI

pri_colored.png # Тепловая карта PRI
pri_classified.png # Классификация зон PRI
pri_kriging.png # Интерполяция кригингом
pri_stats.txt # Статистика PRI
```

## Контакты

**Email:** uxo1612@gmail.com  
**Telegram:** @dannnnzzc

---

