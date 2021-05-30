# Implementing a Convolutional Neural Network

Basandonos en el código de https://victorzhou.com/blog/keras-cnn-tutorial/ los primeros resultados obtenidos para el "val_accuracy" fueron entre 95% y 97%

 -- Resultados obtenidos ejecutando el notebook en dos computadoras.

### Recommended Experiments
Con los "Recommended Experiments" del tutorial, fuimos variando distintos valores, parámetros, capas, por separado en distintos experimentos:

- Varying network depth: Se agrego una capa de convolución 2D obteniendo un "val_accuracy" maximo de 0.9727 y 0.9764 en cada computadora respectivamente.
  
- Adding Dropout layers: Obtuvimos un "val_accuracy" maximo de 0.9534 y 0.9573 en cada computadora respectivamente.

- Adding Fully-connected Layers: Con la función de activación "Relu", obtuvimos un "val_accuracy" maximo de 0.9782 y 0.9774 en cada computadora respectivamente.

- Messing with convolution parameters: Añadimos varios parametros a la capa de convolución 2D, obteniendo un "val_accuracy" maximo de 0.9587 en ambas computadoras.

### Personal Experiments
Haciendo experimentos propios de la misma manera variando valores, parámetros, capas, etc, y juntando varios de estos parametros en un mismo modelo, tenemos los siguientes resultados:

- Experimento 1: Sin dropout obtuvimos un "val_accuracy" maximo de : 0.9800 y 0.9830
- Experimento 2: Con dropout y manteniendo los demas parametros, obtuvimos un "val_accuracy" maximo de : 0.9818 y 0.9821
- Experimento 3: Añadiendo un filtro (num_filters = 9) y manteniendo los anteriores parametros obtuvimos un "val_accuracy" maximo de : 0.9850 y 0.9822
- Experimento 4: Añadiendo 3 filtros más (num_filters = 12), filter_size y pool size no se modifican porque creemos que esos tamaños son perfectos ya que su objetivo es detectar características de la imagen. Obtuvimos un "val_accuracy" maximo de: 0.9859 y 0.9851

  -- Observacion: hasta este punto los mejores valores de "val_accuracy" fueron obtenidos en el 3er epoch

- Experimento 5: Con 3 capas convolucionales, cambiando el loss_function a 'binary_crossentropy' y el número de epochs a 10 y manteniendo los anteriores parametros, obtuvimos un 'val_accuracy' de: 0.9907 (Epoch 9) y 0.9908 (Epoch 10)
- Experimento 6: Con 3 capas convolucionales, cambiando el loss_function a 'categorical_crossentropy' y manteniendo los anteriores parametros, obtuvimos un 'val_accuracy' de: 0.9923 (Epoch 7) y 0.9917 (Epoch 10)


## Conclusiones
Realizando los experimentos por separado, agrengando y modificando parámetros al modelo vemos que a diferencia del modelo básico del tutorial obtenemos mejores resultados.

Juntando todos estos parámetros en un solo modelo vemos que mejoramos el accuracy. Las modificaciones hechas en los loss function, número de filtros y número de epochs, siendo los más reelevantes los dos últimos. Modificando estos parámetros al final de los distintos experimentos obtuvimos un accuracy del 99%.

- El loss fuction no fue tan reelevante ya que los cambios en los resultados no fueron tan significantes, pero si mejoraron en algunas décimas el accuracy del modelo como se ve el experimento 5 y 6.
- El número de filtros es significativo ya que el modelo se entrena reconociendo más detalles de la imagen
- El número de epochs es significativo porque nos permite ver como va mejorando o empeorando el modelo para poder definir un momento oportuno para detener el entrenamiento de la red.

Los demas parametros no se cambiaron como ser el tamaño de filtro y pool_size porque si se los hacia mas pequenos los detalles que detectaría el modelos serian tan específicos que seguramente terminarían empeorando el modelo, y si los hicieramos más grandes, los features serían tan generales que de igual manera empeorarian el modelo.
Tampoco cambiamos la estructura de la red neuronal ya que haciendo más grande la red neuronal (tamaño, número de capas, etc) vimos en otros trabajos que esto podría empeorar en los resultados de la red neuronal.
