# RFM-кластеризация покупателей

Проект по сегментации клиентов интернет-магазина с использованием RFM-анализа и различных методов кластеризации, следуя методологии CRISP-DM.

## Описание проекта

RFM-анализ - это метод сегментации клиентов на основе трех ключевых показателей:
- **Recency (R)** - давность последней покупки
- **Frequency (F)** - частота покупок
- **Monetary (M)** - денежная ценность клиента

## Структура проекта

```
RFM-кластеризация покупателей/
├── rfm_customer_segmentation.ipynb    # Основной ноутбук с анализом
├── data_preparation.py                # Модуль подготовки данных
├── rfm_analysis.py                    # Модуль RFM анализа
├── clustering_analysis.py             # Модуль кластеризации
├── visualization_utils.py             # Утилиты визуализации
├── error_handler.py                   # Обработка ошибок и совместимость
├── config.py                          # Конфигурационный файл
├── requirements.txt                   # Зависимости
└── README.md                          # Документация
```

## Установка и запуск

1. Установите зависимости:
```bash
pip install -r requirements.txt
```

2. Поместите файл данных `customer_segmentation_project.csv` в корневую папку проекта

3. Запустите Jupyter Notebook:
```bash
jupyter notebook rfm_customer_segmentation.ipynb
```

## Решение проблем (Troubleshooting)

### Ошибки multiprocessing на Windows

Если вы получаете ошибки связанные с `joblib`, `multiprocessing` или `CreateProcess`:

1. **Автоматическое исправление**: Проект включает автоматические исправления для Windows
2. **Ручное исправление**: В начале ноутбука выполните:
```python
import os
import multiprocessing
if os.name == 'nt':
    multiprocessing.set_start_method('spawn', force=True)
```

### Отсутствие файла данных

Если файл `customer_segmentation_project.csv` отсутствует:
- Проект автоматически создаст демонстрационные данные
- Или скачайте оригинальный датасет Online Retail Dataset

### Проблемы с версиями библиотек

Если возникают проблемы совместимости:
```bash
pip install --upgrade pandas numpy scikit-learn matplotlib seaborn
```

### Проблемы с Jupyter

Если Jupyter Notebook не запускается:
```bash
pip install --upgrade jupyter notebook
# или используйте JupyterLab
pip install jupyterlab
jupyter lab
```

## Методология CRISP-DM

Проект следует стандартной методологии CRISP-DM:

1. **Business Understanding** - Определение бизнес-целей
2. **Data Understanding** - Исследование данных
3. **Data Preparation** - Подготовка и очистка данных
4. **Modeling** - Применение методов кластеризации
5. **Evaluation** - Оценка результатов

## Методы кластеризации

- K-Means (с исправлениями для Windows)
- Hierarchical Clustering
- Gaussian Mixture Models (GMM)
- Spectral Clustering
- DBSCAN

## Особенности реализации

- **Windows совместимость**: Автоматические исправления для multiprocessing
- **Обработка ошибок**: Graceful fallback при проблемах с алгоритмами
- **Демонстрационные данные**: Автоматическое создание при отсутствии файла
- **Подробная диагностика**: Информация о среде выполнения и ошибках

## Результаты

Проект создает сегменты клиентов с рекомендациями по маркетинговым стратегиям для каждого сегмента.

## TODO для студентов

В коде есть комментарии `# TODO` - места, которые нужно дописать:
- Загрузка данных
- Создание признака TotalPrice
- Выбор оптимального метода кластеризации
- Интерпретация результатов

## Техническая поддержка

При возникновении проблем:
1. Проверьте версии библиотек: `pip list`
2. Убедитесь в наличии всех файлов проекта
3. Запустите диагностику: `python error_handler.py`
4. Используйте демонстрационные данные для тестирования

## Автор

Dmitry Vlasov, 2025
Лицензия: CC BY-NC-ND 4.0
