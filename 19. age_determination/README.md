# Определение возраста покупателей

## Описание проекта
Сетевой супермаркет «Хлеб-Соль» внедряет систему компьютерного зрения для обработки фотографий покупателей. Фотофиксация в прикассовой зоне поможет определять возраст клиентов, чтобы:
- Анализировать покупки и предлагать товары, которые могут заинтересовать покупателей этой возрастной группы;
- Контролировать добросовестность кассиров при продаже алкоголя.
Постройте модель, которая по фотографии определит приблизительный возраст человека. В вашем распоряжении набор фотографий людей с указанием возраста.

Инструкция по выполнению проекта:
- Провести исследовательский анализ набора фотографий.
- Подготовить данные к обучению.
- Обучить нейронную сеть и рассчитать её качество.
- Получить значения MAE на тестовой выборке не больше 8.

## Описание данных
Данные взяты с сайта "ChaLearn Looking at People". Они находятся в папке `/datasets/faces/`. 

В вашем распоряжении одна папка со всеми изображениями (`/final_files`) и CSV-файл `labels.csv` с двумя колонками: `file_name` и `real_age`. 

Извлечь данные из папки вам поможет новый метод "ImageDataGenerator" —`flow_from_dataframe(dataframe, directory, ...)`.

## Библиотеки и инструменты

- *os*
- *python*
- *numpy*
- *pandas*
- *matplotlib.pyplot*
- *PIL.Image*
- *tensorflow.keras*
- *tensorflow.keras.Sequential*
- *tensorflow.keras.applications.resnet.ResNet50*
- *tensorflow.keras.layers.Conv2D*
- *tensorflow.keras.layers.Flatten*
- *tensorflow.keras.layers.Dense*
- *tensorflow.keras.layers.AvgPool2D*
- *tensorflow.keras.layers.MaxPool2D*
- *tensorflow.keras.layers.GlobalAveragePooling2D*
- *tensorflow.keras.optimizers.Adam*
- *tensorflow.keras.preprocessing.image.ImageDataGenerator*

## Общий вывод

Для улучшения качества модели с помощью ImageDataGenerator применили аугментацию - горизонтальное отражение, сдвиг и увеличение (зум) изображения. Разделили фрейм на тренировочный и тестовый. Так как все изображения у нас разного размера, привели их к одному размеру- 224х224, а количество изображений в батче установили 16.

Для обучения использовали модель ResNet50 из библиотеки Keras с весами, предобученными на датасете ImageNet. Для подбора шага обучения применили алгоритм Adam с подобранным гиперпараметром lr=0.0002.

Обучили модель на пяти эпохах.

По результатам тестирования модели получили MAE равное 7.3190, что меньше минимально допустимой MAE = 8.

Поставленная задача выполнена.