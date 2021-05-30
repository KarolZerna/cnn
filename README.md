# Implementing a Convolutional Neural Network

Basandonos en el código de https://victorzhou.com/blog/keras-cnn-tutorial/ los primeros resultados obtenidos para el "val_accuracy" fueron entre 95% y 97%

 -- Resultados obtenidos ejecutando el notebook en dos computadoras.

Con los Recommended Experiments del tutorial, fuimos variando distintos valores, parámetros, capas.

- Varying network depth: Se cambio una capa de convolución 2D obteniendo un "val_accuracy" de 0.9727 y 0.9764
  
- Adding Dropout layers: Obtuvimos un "val_accuracy" de 0.9534 y 0.9573

- Adding Fully-connected Layers: Con la función de activación "Relu", obtuvimos un "val_accuracy" de0.9782 y 0.9774

- Messing with convolution parameters: Añadimos varios parametros a la capa de convolución obteniendo 0.9587 en ambas computadoras.

Haciendo experimentos propios de la misma manera variando valores, parámetros, capas, etc. Tenemos los siguientes resultados.

- Experimento 1: Sin dropout obtuvimos: 0.9800 y 0.9830
- Experimento 2: Con dropout obtuvimos: 0.9818 y 0.9821
- Experimento 3: Añadiendo un filtro obtuvimos: 0.9850 y 0.9822
- Experimento 4: Añadiendo 3 filtros más (num_filters = 12), filter_size y pool size no se modifican porque creemos que esos tamaños son perfectos ya que su objetivo es detectar características de la imagen. Obtuvimos: 0.9859 y 0.9851

  -- Observacion: hasta este punto los mejores valores de "val_accuracy" fueron obtenidos en el 3er epoch

- Experimento 5: Cambiando el loss_function a 'binary_crossentropy' y el número de epochs a 10, obtuvimos: 0.9907 (Epoch 9) y 0.9908 (Epoch 10)
- Experimento 6: Cambiando el loss_function a 'categorical_crossentropy' obtuvimos 0.9923 (Epoch 7) y 0.9917 (Epoch 10)
