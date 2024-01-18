## Предсказание стоимости жилья

В проекте нам предстоит обучить модель линейной регрессии на данных о жилье в Калифорнии в 1990 году. На основе данных нужно предсказать медианную стоимость дома в жилом массиве. Обучите модель и сделайте предсказания на тестовой выборке. Для оценки качества модели используйте метрики RMSE, MAE и R2.

## Использованные инструменты
- python
- numpy
- pandas
- pyspark
- pyspark.sql.SparkSession
- pyspark.sql.types.*
- pyspark.sql.functions
- pyspark.ml.feature.StringIndexer
- pyspark.ml.feature.VectorAssembler
- pyspark.ml.feature.StandardScaler
- pyspark.ml.regression.LinearRegression
- pyspark.ml.evaluation.RegressionEvaluator
- pyspark.ml.feature.OneHotEncoder
- pyspark.ml.feature.OneHotEncodeEstimator

## Анализ результатов

Метрики RMSE и MAE должны стремиться к минимальному значению, а метрика R2 напротив, должна стремится к единице.

Как видно из таблицы модель, обученная на всех данных имеет лучшие метрики качества, чем модель, обученная на только на числовых признаках.

Поэтому можно сделать вывод, что модель лучше обучается на всех доступных признаках.