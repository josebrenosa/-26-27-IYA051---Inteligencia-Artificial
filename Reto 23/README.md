# Reto 23 - Visión Artificial con Deep Learning

Descripción: Enfoque de visión por computador con redes neuronales Convolucionales (CNN avanzadas)

Ej01 Digitos:
1. El ejercicio aplica dos pasos de preprocesamiento esenciales: la normalización de imágenes a un rango de 0 a 1 y la transformación categórica de las etiquetas (one-hot encoding). ¿Qué sucede al omitir la normalización de la imagen (manteniendo los valores de píxel entre 0 y 255) o la transformación categórica de las etiquetas? Infiere la razón técnica por la cual ambos pasos son cruciales para el correcto entrenamiento y convergencia de este modelo de clasificación usando la función de pérdida categorical_crossentropy.

2. La arquitectura de la CNN utiliza un tamaño de kernel de 5×5 para la convolución y un tamaño de pooling de 2×2.
Modifica la arquitectura, por ejemplo:
- Aumenta el tamaño del kernel en la primera capa a 7×7
- aumenta el tamaño de la ventana de Max Pooling a 4×4 
Analiza cómo afecta cada modificación al tamaño del Output Shape de las capas.

3. El entrenamiento se ejecuta durante 30 épocas. Observando los gráficos de pérdida y precisión , se puede notar que la pérdida de validación (val_loss) comienza a aumentar ligeramente, o al menos se estanca, alrededor de la época 15, indicando un posible sobreajuste (overfitting). Modifica el código añadiendo la técnica de Early Stopping (Parada Temprana) de Keras para monitorear la métrica val_loss. Configura un patience de 5. Vuelve a entrenar el modelo con 30 épocas. ¿En qué época se detiene el entrenamiento automáticamente? Justifica por qué la pérdida de validación (val\_loss) es una mejor métrica que la pérdida de entrenamiento (loss) para decidir cuándo detener el proceso. 

4.-El ejercicio utiliza capas convolucionales para la extracción de características; Modifica la arquitectura original (eliminando todas las capas Conv2D y MaxPooling2D ) para crear un Perceptrón Multicapa (MLP) simple. Mantén la estructura de clasificación final (capa Flatten seguida por Dense(100) y Dense(10) ). Vuelve a entrenar el nuevo modelo MLP bajo las mismas condiciones. Compara el rendimiento (precisión final en el conjunto de prueba) del MLP modificado con el rendimiento de la CNN original (0.9892 ). Infiere por qué las CNNs generalmente superan a los MLPs simples en tareas de clasificación de imágenes. 

Ejercicio02: PerrosGatos
1. El documento indica claramente que el modelo sufre de sobreajuste (la precisión de entrenamiento llega al 99.1% mientras que la de validación se estanca en ∼70%). Se sugiere la Aumentación de Datos (Data Augmentation) como solución. Modifica el código que define el generador de datos de entrenamiento (train\_datagen) en la página 4. Añade al menos tres transformaciones aleatorias (p. ej., rotation_range=40, width_shift_range=0.2, horizontal_flip=True). Vuelve a entrenar el modelo durante las 30 épocas.
Compara las curvas de Pérdida de Validación y Precisión de Validación del modelo original con las del modelo modificado. Infiere y explica el principio detrás de la Aumentación de Datos en las CNNs: ¿cómo la generación artificial de nuevas imágenes mejora la capacidad de generalización del modelo y reduce el sobreajuste?

2. La arquitectura original es con cuatro bloques de Conv2D seguidos de MaxPooling2D y una capacidad total de 3.4 millones de parámetros entrenables. Esta capacidad es excesiva para solo 2,000 imágenes de entrenamiento, lo que contribuye al sobreajuste. Modifica la arquitectura simplificándola drásticamente. Elimina las últimas dos capas de convolución (conv2d\_3 y conv2d\_4) y sus respectivas capas de pooling. La arquitectura debe terminar con la segunda capa de pooling (es decir, antes de conv2d_3). Vuelve a entrenar el modelo simplificado, manteniendo las mismas configuraciones de optimizador y épocas.
¿Cómo se reduce el número de parámetros entrenables con tu modificación? 

3. Compara las curvas de precisión del modelo con y sin Dropout. ¿Afecta Dropout al rendimiento del conjunto de entrenamiento y al de validación? Infiere el papel de la capa Dropout como técnica de regularización. ¿Por qué el Dropout previene la co-adaptación de las neuronas y cómo esto obliga a la red a encontrar características más robustas para la clasificación?

Ejercicio 03: Data augmentation

1.-  El código actual utiliza un rango de rotación (rotation_range) de 40 grados y un rango de zoom (zoom_range) de 0.2. Estos parámetros definen la "fuerza" de la Aumentación de Datos. Modifica el código aumentando drásticamente la intensidad de una de las transformaciones, por ejemplo, cambiando zoom_range de 0.2 a 0.8 o rotation_range de 40 a 90. Vuelve a entrenar el modelo con la nueva configuración durante las mismas 100 épocas.
¿Cómo afecta esta transformación excesivamente agresiva (un zoom o rotación muy grande) a la precisión final de validación? ¿por qué una transformación muy intensa puede generar imágenes irreconocibles o antinaturales que en realidad perjudican el entrenamiento y la capacidad de la red para aprender características relevantes?

2. Cuando se rotan o trasladan las imágenes, se generan píxeles vacíos en los bordes. El parámetro fill_mode='nearest'  se encarga de rellenar esos espacios. Modifica el código para cambiar el modo de relleno a fill_mode='constant' y utiliza un valor de relleno (cval) de 0. Genera y visualiza algunas imágenes aumentadas para observar el efecto (requiere un fragmento de código extra con datagen.flow(...) y plt.imshow).
Al usar fill_mode='constant' con cval=0, se introducen franjas negras en el borde de las imágenes transformadas. Analiza cómo estas franjas negras constantes podrían afectar a la extracción de características de la primera capa convolucional. Infiere por qué el fill_mode='nearest' (que copia el píxel más cercano) es generalmente más efectivo para la mayoría de las tareas de Computer Vision que el relleno con un color constante (negro o blanco).

3.-Modifica el código reduciendo la cantidad de épocas de entrenamiento (e.g., de 100 a 30) y aumentando el learning rate del optimizador (por ejemplo, cambiando lr=1e-4 a lr=1e-3 en el optimizers.RMSprop). Vuelve a entrenar el modelo.
Qué sucede con el modelo cuando intentas entrenar más rápido (mayor learning rate) con menos datos efectivos por época (menor número de épocas) en presencia de Data Augmentation? Analiza la convergencia inicial de la Pérdida de Entrenamiento. ¿por qué el Data Augmentation (que muestra una imagen ligeramente diferente en cada época) tiende a requerir un menor learning rate (o al menos uno cuidadosamente elegido) y más épocas para converger de forma estable, a diferencia del entrenamiento sin aumento?

