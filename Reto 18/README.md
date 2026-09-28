# Reto 18 - Clasificación: Convolutional Neuronal Networks

Clasificación: CNN

Ejemplo 1 – Clasificación de dígitos escritos a mano (MNIST)
1.  ¿Por qué es necesario normalizar las imágenes entre 0 y 1 antes de entrenar la red? ¿Qué ventaja aporta transformar las etiquetas numéricas (y_train, y_test) en formato categórico (one-hot encoding)?
2. Explica cuál es la dimensión de entrada que espera una capa Conv2D, ¿Por qué, en este caso, la forma de entrada es (28, 28, 1) y no (28, 28)?
3. En la primera capa convolucional se define:
layers.Conv2D(10, (5, 5), activation='relu', input_shape=(28, 28, 1))
Explica qué significa cada parámetro (número de filtros, tamaño del kernel, activación e input_shape).
¿Cómo cambia el tamaño de la imagen tras aplicar esta convolución y la posterior capa de pooling (2, 2)?
4. En la xtracción de características: ¿Qué diferencia hay entre una capa densa (Dense) y una capa convolucional (Conv2D)? ¿Por qué se dice que las capas convolucionales buscan “patrones locales” en lugar de globales?
5. Función de pérdida y optimizador
a) ¿Qué representa la función de pérdida 'categorical_crossentropy' en este contexto?
b) ¿Por qué se utiliza el optimizador rmsprop y qué papel cumple durante el entrenamiento?
6. Al observar las curvas de pérdida y precisión, ¿cómo puedes detectar sobreajuste (overfitting) o subajuste (underfitting)? 
7.Compara el rendimiento de esta CNN con el obtenido previamente con una red densa (MLP). ¿Qué mejoras observas y a qué se deben? (considera el número de parámetros, tipo de capas y capacidad de generalización).
8. [opcional, pensadla por lo menos] La arquitectura actual tiene 2 capas convolucionales y 2 de pooling. ¿Cómo cambiaría el comportamiento del modelo si aumentas el número de filtros (por ejemplo, de 10 a 32 en la primera capa) o si cambias el tamaño del kernel de (5,5) a (3,3)?


Ejemplo 2 – Red Neuronal Convolucional para Clasificación de Gatos y Perros
1. En la preparación del conjunto de datos: ¿Por qué en este ejemplo se requiere crear manualmente las carpetas de entrenamiento, validación y test? ¿Qué ventajas ofrece esta estructura frente a cargar directamente todos los datos en memoria?
2. Explica qué hace el parámetro rescale=1./255 en el ImageDataGenerator. ¿Por qué es importante reescalar las imágenes y mantener un mismo tamaño (target_size=(150,150)) para todas?
3. La primera capa se define como: 
layers.Conv2D(32, (3, 3), activation='relu', input_shape=(150, 150, 3))
Explica el significado de cada argumento: número de filtros, tamaño del kernel, activación y forma de entrada.
¿Por qué en este caso la forma de entrada es (150, 150, 3) y no (150, 150, 1) como en el ejemplo de los dígitos?
4. ¿Cómo evoluciona la profundidad (número de canales) y el tamaño espacial (ancho y alto) de las imágenes a medida que avanzan las capas convolucionales y de pooling? Para quu crees que es esta reducción progresiva del tamaño de las imágenes?
5. ¿Por qué la última capa tiene una única neurona (Dense(1)) con activación sigmoide? Qué diferencia habría si en lugar de sigmoid se utilizara softmax con dos salidas? Prueba.
6. Al observar las curvas de precisión y pérdida, ¿qué evidencias muestran que el modelo está sobreajustando? ¿Qué causas técnicas piensas que influir en el sobreajuste en este caso (considera tamaño del dataset, número de parámetros, profundidad de la red, etc.)?
7. Menciona al menos tres estrategias que podrían ayudar a reducir el sobreajuste en este modelo (relaciónalas con técnicas vistas o futuras, como regularización, dropout o data augmentation).

Ejemplo 3 – Clasificación de Imágenes con CNN y Aumento de Datos (CIFAR-10)
1. El modelo CNN definido con la función createModel() incluye varias capas Conv2D, MaxPooling2D, Dropout y Dense: define lo que hacen, ¿Qué función cumple cada uno de estos tipos de capas dentro de la red? ¿Por qué se utilizan varias capas de convolución seguidas antes de aplicar una de pooling?
2. ¿Qué hace la capa Dropout() durante el entrenamiento de la red? ¿Cómo contribuye a reducir el sobreajuste y qué efecto tiene en la precisión del modelo durante el entrenamiento y la validación?
3. Observa las curvas de pérdida y precisión antes de aplicar data augmentation. ¿Qué evidencias muestran que el modelo estaba sobreajustando? ¿Por qué piesnas que ocurre este fenómeno en conjuntos como CIFAR-10?
4. Explica el propósito de los parámetros rotation_range, zoom_range, width_shift_range, height_shift_range y horizontal_flip del ImageDataGenerator. ¿Por qué el data augmentation mejora la capacidad de generalización del modelo aunque las nuevas imágenes sean “artificiales”?
5. Tras aplicar el data augmentation, las curvas de entrenamiento y validación se acercan mucho más entre sí. ¿Qué indica este comportamiento sobre el modelo y su capacidad de generalización?

"Jugar" e intentar mejorar el Ejemplo 4 o el Ejemplo 5
