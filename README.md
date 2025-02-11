# 🏔 Модель машинного обучения для прогнозирования запасов газа по кривым ГИС

🔍 **Разведочный анализ данных (EDA).**  

## 🚀 О проекте  
Проект посвящен повышению качества и скорости прогнозирования фильтрационно-емкостных свойств горных пород месторождений углеводородов на основе машинного обучения.

## 📌 Задачи проекта
- Обработку и фильтрацию данных.
- Проведение разведочного анализа (EDA).
- Очистку данных от выбросов и неопределенных значений.
- Обучение и сравнение различных моделей.
- Подбор гиперпараметров с использованием `GridSearchCV`.
- Оценку качества модели и визуализацию результатов.

## 📂 Структура проекта
- `data/` – Данные (CSV-файлы, выгруженные из исходного файла).
- `notebooks/` – Jupyter Notebook с EDA и моделированием.
- `src/` – Исходный код для обработки данных и обучения моделей.
- `models/` – Сохраненные модели после обучения.

## 📊 Используемый стек технологий
- **Язык программирования:** Python 3.x
- **Библиотеки для работы с данными:**  
  - `pandas` – обработка табличных данных  
  - `numpy` – численные вычисления  
- **Визуализация:**  
  - `matplotlib`  
  - `seaborn`  
- **Машинное обучение:**  
  - `scikit-learn` (модели, метрики, GridSearchCV)  
  - `RandomForestRegressor`  
  - `GradientBoostingRegressor`  
  - `LinearRegression`  
- **Предобработка данных:**  
  - Удаление аномалий методом IQR  
  - Замена пропущенных значений  
  - Масштабирование признаков

## 📊 Данные  
Использованы реальные геофизические измерения в газовых скважин:  
- **АК (акустический каротаж)** – скорость прохождения звуковой волны через горную породу  
- **GK (гамма каротаж)** – естесвенная радиоактивность  
- **NGK (нейтронный каротаж)** – определение водородосодержания  
- **BK (боковой каротаж)** –  удельноt электрическое сопротивление горных пород 
- **PL (плотностной каротаж)** – определение плотности и эффективного атомного номера горных пород  

## 🔍 Анализ данных (EDA)
Перед обучением моделей был проведен исследовательский анализ данных:
- Проверка наличия пропущенных значений.
- Анализ распределений и выбросов.
- Корреляционный анализ между признаками.
- Проверка значимости признаков.

## 🛠 Предобработка данных
- Исключение строк, содержащих ошибочные значения `-999.25`.
- Замена выбросов методом межквартильного размаха (IQR).
- Проверка необходимости использования отдельных признаков.

## 🚀 Обучение моделей
Были протестированы три модели:
- Линейная регрессия (`LinearRegression`).
- Случайный лес (`RandomForestRegressor`).
- Градиентный бустинг (`GradientBoostingRegressor`).

Метрики оценивались с помощью:
- Коэффициента детерминации (`R²`).
- Средней абсолютной ошибки (`MAE`).
- Среднеквадратичной ошибки (`MSE`).

## 🔬 Оптимизация модели
Для подбора гиперпараметров использовался `GridSearchCV`, который позволил определить наилучшие параметры для `RandomForestRegressor`:
- Количество деревьев: `300`
- Максимальная глубина: `None`
- Использование всех доступных ядер процессора

## 📈 Итоговые результаты
После оптимизации `RandomForestRegressor` показал наилучший результат:
- `R²` ≈ 0.89
- `MAE` ≈ 3.4
- `MSE` ≈ 5.8

Были построены графики:
- Фактические значения vs предсказания.
- Гистограмма ошибок модели.
- Важность признаков.

## 🎯 Выводы
- Данные требуют очистки от выбросов и обработки пропусков.
- `RandomForestRegressor` показал наилучший баланс точности и устойчивости.
- Подбор гиперпараметров позволил повысить качество модели.
- Визуализация помогает лучше интерпретировать результаты.



































