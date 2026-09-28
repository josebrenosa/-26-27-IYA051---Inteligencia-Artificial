# Reto 20 - Clustering: kMeans

[a completar]

Responder estas preguntas para el ejemplo disponible:
- ¿Qué tipo de aprendizaje automático se utiliza en este ejemplo y por qué?
- ¿Cuál es el objetivo del algoritmo K-Means aplicado a la base de datos IRIS?
- ¿Qué representan las variables X e y dentro del código?
- ¿Qué diferencia hay entre los tres modelos definidos en estimators (k_means_iris_8, k_means_iris_3 y k_means_iris_bad_init)?
- ¿Por qué se generan tres gráficos distintos con diferentes valores de k y diferentes inicializaciones?
- ¿Qué función tiene la línea est.fit(X) dentro del bucle que construye los gráficos?
- ¿Qué efecto tiene la variable labels = est.labels_ en la visualización 3D?
- ¿Por qué se utiliza ax.text3D() en el último gráfico y qué información proporciona al observador?
- ¿Qué significa la instrucción y = np.choose(y, [1, 2, 0]).astype(np.float) y por qué se realiza este reordenamiento?
- ¿Cómo podrías evaluar de forma cuantitativa la calidad de los clusters obtenidos con K-Means en este ejemplo?
