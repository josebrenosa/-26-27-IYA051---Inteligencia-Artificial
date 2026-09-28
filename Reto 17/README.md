# Reto 17 - Clasificación: Perceptron

Descripción: Modelo perceptrón simple como fundamento de redes neuronales: convergencia, limitaciones y casos linealmente separables.
	
Para el ejercicio del perceptron (Ejercicio 01 de Redes Neuronales):
- ¿Qué representa un perceptrón dentro de una red neuronal y qué tipo de problemas puede resolver?
- ¿Cuál es el papel de los pesos  w1,w2,w3  en el perceptrón y cómo influyen en la salida final?
- Cambia los valores de los pesos w1,w2,w3 y analiza cómo varía el resultado de la salida y. ¿Qué interpretación tiene este cambio?
- Por qué se utiliza una función de activación (como tanh) y qué ventajas tiene frente a una función lineal
- Representa gráficamente la función tanh(s) y explica cómo se comporta para valores grandes y pequeños de s
- ¿Qué diferencias existen entre la función tanh, sigmoide y ReLU en cuanto a rango y comportamiento?
- Sustituye la función de activación tanh por una función sigmoide o ReLU y compara los resultados.
- ¿Cómo podría extenderse este modelo de una sola neurona a una red con varias capas (perceptrón multicapa, MLP)?
- Añade un término de sesgo (bias) al modelo y explica cómo afecta al cálculo de la salida.
- Modifica el código para que el perceptrón procese varios conjuntos de entradas (X) en forma de matriz y obtenga varios outputs a la vez.

Para el simulador de redes (http://playground.tensorflow.org/) comenta las pruebas realizadas para ajustar a diferentes entradas y cómo se comporta en cuanto a los datos.

# Clasificación: Redes Neuronales

Ejemplo Suma de tres números:
- ¿Por qué es necesario generar los datos de entrada (X1, X2, X3) y salida (y) de forma aleatoria?
- ¿Por qué cuando sumas 3 números enteros, la salida de esta red neuronal no es un entero?
- ¿Qué podría ocurrir si los tres vectores de entrada estuvieran correlacionados (por ejemplo, X2 = X1 + 1)?
- ¿Por qué la matriz X debe tener forma (n_muestras, 3) mientras que y es un vector de una sola dimensión?
- ¿Cómo se relaciona esta estructura con la cantidad de neuronas en la capa de entrada y salida?
- ¿Cuál es el propósito de dividir los datos en X_train/y_train y X_test/y_test?
- ¿Qué podría pasar si usáramos todos los datos para entrenamiento?
- En la línea mlp = MLPRegressor(hidden_layer_sizes=(10), max_iter=500), ¿qué significa tener una capa oculta con 10 neuronas? ¿Cómo afectaría el desempeño si se aumentara o disminuyera este número
- Durante el entrenamiento se muestra el valor de loss por iteración.
- ¿Qué representa este valor y qué nos indica su evolución a lo largo de las iteraciones?
- ¿Por qué se usa la correlación entre predictions y y_test como métrica? ¿Qué otras métricas podrías usar para evaluar el rendimiento de una red neuronal en un problema de regresión?
- En el código final se predice para X_pred = [[5, 12, 6]]. ¿Qué significa el valor obtenido (y_pred) en términos del aprendizaje de la red? ¿Podría la red predecir correctamente para números fuera del rango de entrenamiento (por ejemplo, mayores que 100)?

Clasificación MLP puntos colores.
- ¿Qué representan las matrices X e y en el contexto de esta práctica? Explica qué significan las filas y columnas de X, y qué valores puede tomar y. 
- El código separa el dataset en entrenamiento y test mediante ntrain = int(3*len(y)/4). ¿Por qué es importante reservar una parte de los datos para validación (test)? ¿Qué consecuencias tendría entrenar y validar con el mismo conjunto?
- La red se define con MLPClassifier(hidden_layer_sizes=(10,10,10), activation='relu'). Explica qué significan los parámetros hidden_layer_sizes y activation. ¿Por qué podría ser útil utilizar varias capas ocultas en lugar de una sola? 
- ¿Qué nos indica la forma de la gráfica de la función de coste (loss_curve_) a lo largo de las iteraciones? Si la curva no disminuye o muestra oscilaciones grandes, ¿qué factores podrían estar afectando el aprendizaje?
- ¿En qué nos ayuda hacer la matriz de confusión? 
- El código final muestra los falsos positivos en color naranja (plt.scatter(...)). ¿Qué información aporta esta visualización sobre el comportamiento del modelo? ¿Cómo podrías usar esta gráfica para mejorar la red o entender sus limitaciones?

Clasificación Red Neuronal Secuencial Keras
- En el código se define la red con model = Sequential(). Explica qué significa crear un modelo “secuencial” en Keras y cómo se agregan las capas al modelo.
- Observa la instrucción model.add(Dense(4, input_dim=2, activation='relu')). ¿Qué representa el parámetro input_dim y por qué se indica su valor en la primera capa pero no en las siguientes?
- En la línea model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy']), ¿qué realiza internamente el optimizador Adam y por qué es adecuado para este tipo de problema?
- En el entrenamiento se utiliza model.fit(X, y, epochs=10, batch_size=128). Explica qué sucede dentro de una época y qué función cumple el tamaño de lote (batch_size) durante el proceso de ajuste.

Puerta XOR:
- Por qué el problema de la compuerta XOR no puede resolverse con un modelo lineal simple? Explica qué papel juega la capa oculta en permitir que la red neuronal lo aprenda correctamente.
- En el código se define model.add(Dense(16, input_dim=2, activation='relu')). ¿Por qué se elige una función de activación no lineal como ReLU para la capa oculta y sigmoid para la salida?
- La red se entrena con loss='mean_squared_error' y optimizer='adam'. ¿Qué hace el optimizador Adam durante el entrenamiento y cómo ajusta los pesos de la red?
- El entrenamiento usa epochs=1000. ¿Qué representa una “época” en este contexto y cómo podrías detectar si la red está sobreentrenando (overfitting)?
- En la salida final se obtiene binary_accuracy: 100.00%. ¿Qué significa este resultado en términos del aprendizaje del modelo? ¿Podría esta red generalizar si se le presentaran combinaciones distintas de entrada?

Ejemplo OCR Números:

¿Por qué es necesario transformar las imágenes de 28x28 píxeles en vectores de tamaño 784 antes de entrenar la red neuronal (X_train.reshape((60000, 28 * 28)))? Explica qué representa cada valor del vector resultante.
n el código se normalizan los datos dividiendo por 255 (X_train = X_train.astype('float32') / 255). ¿Qué efecto tiene esta normalización sobre el entrenamiento de la red y por qué es importante?
Se define una capa de salida con activation='softmax'. ¿Qué hace esta función de activación y cómo permite al modelo clasificar una imagen entre las 10 posibles clases (dígitos 0–9)?
La función de pérdida usada es 'categorical_crossentropy'. ¿Por qué se utiliza esta función en lugar de otras como 'mean_squared_error' y qué representa su valor durante el entrenamiento?
El modelo se guarda y luego se vuelve a cargar desde disco (network.save_weights("network_weights.h5")). ¿Qué ventajas tiene este proceso de guardado y carga de pesos? ¿En qué situaciones prácticas resulta útil?
¿Por qué es necesario transformar las imágenes de 28x28 píxeles en vectores de tamaño 784 antes de entrenar la red neuronal (X_train.reshape((60000, 28 * 28)))? Explica qué representa cada valor del vector resultante.
n el código se normalizan los datos dividiendo por 255 (X_train = X_train.astype('float32') / 255). ¿Qué efecto tiene esta normalización sobre el entrenamiento de la red y por qué es importante?
Se define una capa de salida con activation='softmax'. ¿Qué hace esta función de activación y cómo permite al modelo clasificar una imagen entre las 10 posibles clases (dígitos 0–9)?
La función de pérdida usada es 'categorical_crossentropy'. ¿Por qué se utiliza esta función en lugar de otras como 'mean_squared_error' y qué representa su valor durante el entrenamiento?
El modelo se guarda y luego se vuelve a cargar desde disco (network.save_weights("network_weights.h5")). ¿Qué ventajas tiene este proceso de guardado y carga de pesos? ¿En qué situaciones prácticas resulta útil?
