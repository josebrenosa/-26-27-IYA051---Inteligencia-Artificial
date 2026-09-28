# Reto 11 - Regresión polinómica

En "Materiales de la asignatura" > "Machine Learning" > "Regresión"
Ahí hay 5 carpetas con ejercicios a trabajar con sus códigos. Además de hacer que funcionen en un cuaderno de Google Colab, con los correspondientes comentarios de haber entendido el código, hay que responder las siguientes cuestiones:


Para el Ej01:  
1.1 ¿Cuál es el objetivo principal de la regresión lineal en este ejercicio?  
1.2 ¿Qué representan las variables X e y en el código y cómo se formalizan (tipo de estructura de datos)?  
1.3 ¿Qué hace el siguiente código?  
regr = LinearRegression()  
regr.fit(X_train, y_train)  
1.4 ¿Qué significan los parámetros coef_ e intercept_ del modelo?  
1.5 Ecuación matemática del modelo de regresión obtenida. Si vuelvo a ejecutar el código, ¿varían los coeficientes de la ecuación? ¿por qué?  
1.6 ¿Qué hace el siguiente bloque de código y qué representa la gráfica resultante? ¿qué diferencia hay entre y_train e y_test, y por qué se separan estos dos tipos de datos?  
plt.scatter(X_train, y_train, color="red")  
plt.scatter(X_test, y_test, color="blue")  
plt.plot(X_train, regr.predict(X_train), color="black")  
1.7 ¿Qué miden las métricas MSE y R^2 que aparecen en el código?  
1.8 Explica los resultados de R^2 en entrenamiento y de test.  
1.9 ¿Cómo se haría una predicción nueva con el modelo entrenado? Formalízalo en código con un ejemplo.  
1.10 ¿Qué parámetros o configuraciones se podrían cambiar para mejorar el modelo?  
  
Para el ejercicio 02:  
2.1 ¿Qué propósito tiene la función generador_datos_simple()?  
2.2 ¿Por qué se introduce un término de error aleatorio en la generación de datos?  
2.3 ¿Qué papel tien el parámetro beta en la simulación?  
2.4 ¿Por qué se realiza la división de los datos 70% / 30% en entrenamiento y test? ¿harías otra división? ¿en función de qué se cogen esos porcentajes?  
2.5 ¿Qué información proporcionan los atributos coef_ e intercept_ después del entrenamiento? Semejanzas y diferencias respecto del código del ej01.  
2.6 Cuánto vale R^2. Interprétalo y compáralo con el ej01.  
2.7 ¿Por qué son diferentes los valores de R^2 del test y del entrenamiento? ¿Qué valores desearíamos tener en ellos?  
2.8 ¿Qué pasaría si aumentamos el parámetro desviacion en el generador de datos? ¿para qué querríamos hacer esto?  
2.9 ¿Por qué el código hace reshape((muestras,1)) al generar X e y?  
2.10 Si yo hago X=50, ¿qué significaría respecto al ejemplo y al modelo calculado?  

Para el Ejercicio 03:  
3.1 Diferencia entre regresión lineal simple de ejercicios anteriores y la múltiple de este.  
3.2 Ecuación del modelo obtenido. ¿Qué significa el término independiente de la ecuación? (a nivel físico del caso de uso y a nivel matemático)  
3.3 ¿De cuántas variables de entrada depende la salida? ¿Podríamos hacerlo de una sola? ¿de qué depende?  
3.4 ¿Qué significa que el coeficiente de la masa glaciar sea negativo en este ejercicio?  
3.5 Interpreta los valores obtenidos de R^2 en entrenamiento y test  
3.6 Al aumentar el número de variables de entrada, ¿qué ventajas e inconvenientes tendría? Por ejemplo, si incluyésemos la deforestación.  
3.7 ¿Crees que es adecuada la regresión lineal múltiple para predecir CO2 en este caso? Explica por qué.  

Para el Ejercicio 04:   
4.1 Diferencias entre regresión lineal y polinómica  
4.2 ¿Para qué se usa la función np.poly() en el código?  
4.3 Explica la métrica utilizada para evaluar la calidad de ajuste de cada modelo polinómico  
4.4 Por qué el modelo de grado 5 tiene menos error que los de grado 3 y 4  
4.5 Explica el overfitting o sobreajuste en el contexto del ejemplo.  
4.6 ¿Para qué se usa la función np.polyval() en el código? Diferencias con np.poly() ¿Por qué empiezan por np. ambas?  
4.7 Si siguiésemos aumentando el grado del polinomio del modelo que efectos podrían observarse. ¿Con qué grado te quedarías tú y por qué?  

Para el Ejercicio 05: Resolverlo según lo inferido y aprendido en los ejemplos anteriores.


