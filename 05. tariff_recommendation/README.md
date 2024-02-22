# Рекомендация тарифов клиенту компании сотовой связи.

## Описание проекта

Требуется на предобработанных данных посторить модель, которая предложит клиенту компании сотовой связи наиболее выгодный тариф. Метрика *accuracy* у модели долна быть не менее 0.75.

## Инструменты

- *python*
- *pandas*
- *numpy*
- *sklearn.metrics.accuracy_score*
- *sklearn.model_selection.train_test_split*
- *sklearn.linear_model.LogisticRegression*
- *sklearn.tree.DecisionTreeClassifier*
- *sklearn.ensemble.RandomForestClassifier*
- *sklearn.dummy.DummyClassifier*

## Общий вывод

Проведено обучение нескольких моделей, была выбрана лучшая модель, которая на тестовых данных показала *accuracy* 0.8.
