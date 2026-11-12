# Clasificacion de globulos blancos con una red convolucional

Karol Alexis Alvarado Davila - A01751711

Inteligencia artificial avanzada para la ciencia de datos (TC3009C.601)

Momento de Retroalimentacion: Modulo 5 Implementacion de un modelo de deep learning. (Portafolio Implementacion)

## Problema

Se clasifica la imagen de un globulo blanco en uno de cuatro tipos: eosinofilo, linfocito, monocito o neutrofilo. Este conteo forma parte de la biometria hematica y normalmente se hace a mano en el microscopio. El modelo es una red neuronal convolucional hecha con Keras y TensorFlow.

## Contenido del repositorio

- notebooks/reporte.ipynb: reporte completo, con las secciones Introduccion, Datos, Desarrollo del modelo, Ajuste del modelo, Resultados, Conclusiones y Aplicacion. Todas las celdas estan ejecutadas.
- modelos/modelo_base.keras: modelo base (arquitectura y pesos).
- modelos/modelo_ajustado.keras: modelo final, con aumento de datos y dropout (arquitectura y pesos).
- data/dataset2-master: imagenes del dataset, separadas en TRAIN, TEST y TEST_SIMPLE.

## Datos

Se usa el dataset Blood Cell Images de Paul Mooney, disponible en Kaggle:

https://www.kaggle.com/datasets/paultimothymooney/blood-cells

El dataset esta incluido en el repositorio, en la carpeta data/dataset2-master, asi que no hace falta descargarlo para correr el notebook. La estructura es la siguiente:

    data/
      dataset2-master/
        images/
          TRAIN/
          TEST/
          TEST_SIMPLE/
        labels.csv
    modelos/
    notebooks/
      reporte.ipynb

## Resultados

Accuracy de cada modelo, en por ciento:

| Conjunto | Modelo base | Modelo final |
|---|---|---|
| Entrenamiento | 94.84 | 95.51 |
| Validacion | 86.99 | 95.23 |
| Prueba | 72.82 | 87.01 |

El conjunto de prueba tiene 2487 imagenes de celulas que no se usaron en el entrenamiento. El analisis completo esta en el reporte.

## Uso del modelo

La seccion Aplicacion del reporte define la funcion clasificar, que recibe la ruta de una imagen y regresa la clase predicha con su probabilidad, usando el modelo guardado en modelos/modelo_ajustado.keras.
