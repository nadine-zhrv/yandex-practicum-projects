# Прогнозирование заказов такси

## Описание проекта

Предоставлены исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. Требуется построить модель для такого предсказания.

Значение метрики RMSE на тестовой выборке должно быть не больше 48.

## Навыки и инструменты

- Python
- Pandas
- Numpy
- Matplotlib
- Sklearn
- Statsmodels
- TimeSeriesSplit
- GridSearchCV
- LGBMRegressor
- CatBoostRegressor
- RandomForestRegressor
- LinearRegression

## Общий вывод

- Нам предоставлены данные за полгода (с 01.03.2018 по 31.08.2018), пропусков нет, расположены в хронологическом порядке. Поменяли интервал у данных с 10 минут на 1 час.
- Данные проанализированы. Рассмотрены тренд и сезонность за весь отрезок времени, за месяц (июль), за неделю и три дня. Есть тренд увеличения количества заказов такси к концу периода практически в три раза. Выявлена суточная сезонность. Большая часть заказов происходит вечером и сходит на нет под утро, также ближе к выходным количество заказов увеличивается.
- Были созданы признаки для обучения моделей. Данные разделены на две выборки: обучающую и тестовую в соотношении 10:1.
- Обучены модели LightGBM, CatBoost, RandomForest, LinearRegression. Подобранны гипперпараметры. Найден лучший RMSE. Выбрана модель CatBoost с качеством 25.2
- Лучшая модель протестирована/ Результат проверки показал качество хуже, чем на обучающей выборке, но оно удовлетворяет условию заказчика.
