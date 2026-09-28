# Reto 27

# Explorando Algoritmos de enjambre y cúmulos de partículas

Trabaja los 2 ejemplos del campus analizandoo su funcionamiento e infiriendo los conceptos teóricos explicados en clase.

Ejemplo 01: Inteligencia de Enjambres, el algoritmo de Colonia de Hormigas.
1. ¿Qué ocurre si modificas los valores de α y β en la función eligeCiudad()? En el código, ambos parámetros aparecen fijos (alfa=1.0, beta=0.5) Modifica los valores y observar cómo cambia el comportamiento de las hormigas y la calidad del camino encontrado.
2. En la función hormigas(), solo la mejor hormiga de cada iteración deja feromonas. ¿Qué efecto tiene esto? Cmpara este enfoque con una versión donde todas las hormigas depositan feromonas.
3. ¿Qué pasa si reduces o aumentas la tasa de evaporación? En la función evaporaFeromonas() la constante es fija: 0.9 (evaporación=0.1) Prueba con valores como 0.99, 0.5, 0.1 y observar si el algoritmo converge más rápido, más lento o se estanca.
4. ¿Cómo afecta el número de iteraciones a la calidad del resultado? El programa principal usa 100 iteraciones. Mira como varia el mejor camino encontrado con 10, 50, 200 y 500 iteraciones.
5. Cambia el número de ciudades en la matriz de distancias: ¿sigue funcionando igual de bien? Aumenta las ciudades a 15, 20, 30 ciudades y analizar si incrementa mucho el tiempo de ejecución, si sigue encontrando buenas soluciones o si se vuelve más sensible a los parámetros
6. ¿Por qué el algoritmo siempre empieza en la ciudad 0? ¿Qué pasaría si la ciudad inicial fuese aleatoria?
7. Analiza el rastro de feromonas: ¿qué relación encuentras entre la longitud del camino y la cantidad de feromona depositada? En rastroFeromonas() se añade una dosis proporcional a distMedia/longCamino . Experimenta cambiando esta fórmula y observar si aparece: convergencia más rápida, sobreexplotación prematura, caminos peores o mejores.

Ejemplo 02: Optimización basada en cúmulos de partículas – PSO
1. ¿Cómo afecta la inercia al movimiento de las partículas? En el código, la inercia comienza con valor 1.4 (atributo inercia de la clase Particula) y se reduce multiplicándola por reduccionInercia en cada iteración (línea Particula.inercia*=reduccionInercia) .Probar valores iniciales menores (0.5, 0.8) o mayores (2.0, 3.0). Observar si el enjambre converge más rápido, más lento, o si se vuelve inestable.
2. ¿Qué sucede si cambias los pesos cognitivo y social? En la práctica, cognitiva=2.0 y social=2.0 para todas las partículas . Fijar βc = 3.0 y βs = 0.5 (más pensamiento individual). Fijar βc = 0.5 y βs = 3.0 (más comportamiento de rebaño). Observar diferencias en la exploración del espacio.
3. ¿Cómo cambia el resultado si aumentas o reduces el número de partículas? En el programa principal, nParticulas = 10 .  Probar con 5, 20 y 50 partículas. Registrar tiempo, estabilidad de la convergencia y precisión del mínimo encontrado. Saca conclusiones
4. ¿Por qué algunas partículas se quedan “pegadas” en los límites del espacio de búsqueda? El código fuerza a que las posiciones se mantengan entre [-2,2] en x y [-1,1] en y mediante max/min en actualizaPosicion() . Observa cuándo ocurre este efecto y qué implicación tiene sobre la calidad del resultado. ¿Qué es la restriccion del espaciio de soluciones y para qué sirve?
5. ¿Qué sucede si eliminas la reducción progresiva de la inercia? Actualmente la inercia se reduce cada iteración por un factor redInercia = 0.9. Comentar la línea Particula.inercia*=reduccionInercia  y ejecuta el algoritmo con inercia constante. Reflexionar si hay más oscilaciones o si tarda más en estabilizarse.
6. Analiza el comportamiento inicial: ¿por qué el mínimo global no mejora durante muchas iteraciones? En la salida del programa, el valor global permanece en torno a –0.76 hasta la iteración 7. Analiza la interacción entre inercia alta + velocidad inicial pequeña. ¿por qué el enjambre tarda en explorar zonas más prometedoras?
7. Observa la convergencia final: ¿por qué el algoritmo obtiene uno de los dos mínimos globales? La función tiene dos mínimos globales similares en (0.09, –0.71) y (–0.09, 0.71) y, en el resultado final de la práctica, el enjambre converge cerca de (–0.087, 0.705) con valor –1.0311.
Repetir la ejecución varias veces. Comprueba si a veces converge al otro mínimo.  --->  identifica qué factores influencian cuál mínimo se elige: posiciones iniciales, peso social, número de partículas.
