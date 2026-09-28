# Reto 15 - Clasificación: SVM

Para los ejercicios en el campus:

Ej01: Responder las siguientes preguntas:
- Qué es un modelo de clasificación SVM y cuál es el principio fundamental en el que se basa para separar las clases de datos?
- ¿Qué función cumple la instrucción make_blobs() y por qué es útil para este tipo de prácticas de aprendizaje supervisado?
- En el modelo svm.SVC(kernel='linear', C=1000), qué representan los parámetros kernel y C, y cómo afectan al comportamiento del clasificador?
- ¿Qué información devuelve el método clf.decision_function(xy) y cómo se utiliza para representar las fronteras de decisión y los márgenes del modelo?
- ¿Qué son los “vectores soporte” (clf.support_vectors_) y qué papel juegan en la construcción de la frontera de decisión del SVM?
- ¿Por qué se utiliza una malla de puntos (np.meshgrid) para evaluar la función de decisión y cómo se relaciona esto con la visualización del modelo?
- En términos de generalización del modelo, ¿qué podría ocurrir si se usara un valor de C demasiado alto o demasiado bajo, y por qué?
- ¿Quieres que te prepare también una versión de estas preguntas con respuestas explicadas (por ejemplo, para usar como guía del profesor o para corrección)?

Ej02: Responder las siguientes preguntas:
- ¿Cuál es el objetivo del modelo SVM en esta práctica y por qué se utilizan únicamente dos especies del conjunto de datos “Iris”?
- ¿Qué representan las variables X y y después de filtrar los datos (y != 0) y seleccionar solo las dos primeras columnas (:2)?
- ¿Por qué es importante dividir el conjunto de datos en entrenamiento y test, y qué proporciones se utilizan en este código?
- El código utiliza tres tipos de ‘kernel’: linear, rbf y poly. Explica brevemente qué tipo de frontera de decisión genera cada uno y cuándo puede ser más apropiado usar cada caso.
- ¿Qué función cumple clf.decision_function() y cómo se utiliza su resultado para visualizar las regiones de clasificación en el gráfico?
- ¿Por qué se usa una malla (np.mgrid) para representar las zonas de decisión del modelo? ¿Qué ventajas tiene frente a representar solo los puntos de datos?
- ¿Qué diferencias se pueden observar al comparar los resultados visuales de los tres kernels? ¿Qué conclusiones se pueden extraer sobre la complejidad del modelo y el riesgo de sobreajuste?

Ej03: En base a lo trabajado en Ej01 y Ej02, resolver el Ej03. Clasificación de tráfico de red.
