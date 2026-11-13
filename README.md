# 🐾 Clasificación de Animales Salvajes y No Salvajes mediante CNN

**Alumna:** Camila Maldonado

## Descripción

Este TP consiste en desarrollar una red neuronal convolucional (CNN) capaz de clasificar imágenes de animales en dos categorías: **salvajes y no salvajes**.

El objetivo principal es que la red pueda aprender a reconocer características visuales de los animales y determinar si una imagen corresponde a un animal salvaje o no salvaje. 
No se busca identificar exactamente la especie del animal, sino realizar una clasificación general en esas dos categorías.

Para realizar este trabajo utilicé dos conjuntos de datos (*datasets*) diferentes, con el objetivo de tener una mayor variedad de animales e imágenes y evitar trabajar con un único conjunto de datos.

La carpeta `inf` se utiliza para visualizar imágenes adicionales que no forman parte del entrenamiento ni de la evaluación.

Al finalizar, el modelo entrenado se guarda con el nombre `modelo_salvajes_cnn.keras`.

## Datasets utilizados

Se utilizaron los siguientes datasets de Kaggle:

1. [Animals Dataset - Anto Benedetti](https://www.kaggle.com/datasets/antobenedetti/animals?select=animals)
2. [Animals-10 - Alessio Corrado](https://www.kaggle.com/datasets/alessiocorrado99/animals10?resource=download)

La combinación de ambos conjuntos permite ampliar la variedad de imágenes disponibles y trabajar con diferentes especies de animales.

## Modelo utilizado

Se desarrolló una red neuronal convolucional utilizando TensorFlow y Keras.

La arquitectura cuenta con:

- Entrada de imágenes RGB de 96x96 píxeles.
- Cuatro capas convolucionales (`Conv2D`).
- Función de activación ReLU.
- `BatchNormalization`.
- Capas `MaxPooling2D`.
- `GlobalAveragePooling2D` para reducir las características extraídas.
- Una capa densa de 128 neuronas.
- `Dropout` para reducir el sobreajuste.
- Una capa de salida con activación Sigmoid para realizar la clasificación binaria.

Para el entrenamiento se utilizó el optimizador Adam y la función de pérdida Binary Crossentropy.

## Criterio de clasificación

Para el entrenamiento se estableció la siguiente división:

**Animales salvajes:**
- León
- Elefante
- Mariposa
- Ardilla
- Araña

**Animales no salvajes:**
- Caballo
- Perro
- Gato
- Gallina
- Vaca
- Oveja

Esta clasificación se realiza a partir de las especies disponibles en los datasets y del criterio definido para este trabajo.

## Preparación y entrenamiento

Antes de entrenar la red, las imágenes pasan por un proceso de preparación que incluye:

- Conversión de las imágenes al formato RGB.
- Redimensionamiento a 96x96 píxeles.
- Normalización de los valores de los píxeles.
- Eliminación de imágenes corruptas.
- Eliminación de imágenes duplicadas entre entrenamiento y validación.
- Balanceo de la cantidad de imágenes por categoría.

También se utiliza aumento de datos (*Data Augmentation*) mediante rotaciones, zoom y giros horizontales, para generar variaciones de las imágenes durante el entrenamiento.

## Evaluación

Para comprobar el funcionamiento de la red se utilizan diferentes métricas:

- Accuracy.
- Precision.
- Recall.
- F1-Score.
- AUC.
- Matriz de confusión.

También se generan gráficos de aprendizaje para observar cómo evoluciona el entrenamiento y comparar los resultados con los datos de validación.

## Tecnologías utilizadas

- Python
- Google Colab
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn
- Pillow (PIL)
