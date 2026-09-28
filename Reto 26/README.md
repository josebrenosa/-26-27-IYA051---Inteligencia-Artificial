# Reto 26 - Retos de Computación Evolutiva

Ejercicio 01:
1. ¿Por qué en esta práctica los individuos se representan con cromosomas binarios de 4 bits?
Explica qué limita y qué posibilita esta longitud del cromosoma según el intervalo [0–15] definido en la función fitness.
2. La Función Fitness f(x)=∣ x−52+sin(x) ∣ ¿Qué rol cumple esta función dentro del algoritmo genético y por qué afecta directamente a la probabilidad de selección de cada individuo?
Utiliza como referencia el cálculo de fitness mostrado para las generaciones iniciales.
3. se calcula la probabilidad de selección de cada individuo como: pi=fif1+f2 ¿Qué interpretas cuando un individuo tiene probabilidad 1 o probabilidad 0, como ocurre en la Generación 1?
Explica cómo esto influye en las siguientes etapas del algoritmo.
4. Usando el procedimiento explicado en la página donde se muestra el punto de corte y su selección aleatoria: ¿Qué efecto tiene elegir un punto de corte más cercano al inicio o al final del cromosoma?
5. Mutación: La probabilidad de mutación es 0.3 y en el código se revisa bit por bit. ¿Por qué es importante incluir mutación en un algoritmo genético y qué consecuencias se observan cuando esta probabilidad es alta, como se ve en las primeras generaciones del ejemplo?
6. Según el resultado obtenido, el mejor valor aparece en la Generación 2, donde se alcanza x = 11 con fitness ≈ 5.9999. ¿Por qué el algoritmo encuentra tan rápido el mejor individuo en esta práctica?
Comenta sobre el tamaño de población (2 individuos), longitud del cromosoma y forma de la función fitness.
7. Experimenta con parámetros modificand: la probabilidad de emparejamiento, la probabilidad de mutación, número de individuos... ¿Qué predicen que ocurrirá con la velocidad de convergencia y la diversidad genética?


Ejercicio 02
1. En este código, cada individuo (cromosoma) está representado por una lista donde cada posición indica una columna y el número en esa posición indica la fila de la reina. ¿Qué ventajas tiene usar esta representación (permuta de 0 a n-1) en comparación con usar una matriz 8×8 con ceros y unos? Explica cómo esta representación reduce automáticamente ciertos tipos de conflictos.
2. La función fidoneidad() incrementa el fitness cada vez que una reina NO está en conflicto con otra (ni en la misma fila ni en diagonal). ¿Por qué el valor máximo de fitness para un tablero de n casillas es: n^2−n  ? Relaciona esta fórmula con la cantidad de pares de reinas que pueden evaluarse.
3.El método seleccion() simplemente escoge un individuo al azar: return rnd.choice(poblacion) Qué efectos puede tener este tipo de selección aleatoria sobre la velocidad de convergencia y la diversidad genética, en comparación con métodos como torneo o ruleta?  Pon un ejemplo para un tablero de 8×8.  
4. La mutación sustituye una posición del genoma por un valor aleatorio que no esté duplicado: genes[n] = genX if genX in genes else genY ¿Por qué el algoritmo evita repetir números en el cromosoma, y qué problema generaría permitir duplicados en la solución? 
5. Escalabilidad del algoritmo. El documento indica que para 9 casillas el tiempo de ejecución "se dispara" en comparación con tableros de 4 a 8 casillas. ¿Qué aspectos del algoritmo (representación, fitness, selección o mutación) contribuyen a que el tiempo crezca tanto al aumentar el tamaño del tablero?


Ejercicio 03:
1.  ¿Cómo se relaciona la función distancia() del código con el concepto de función de fitness y por qué minimizar la distancia equivale a maximizar la aptitud del individuo?
2. Selección determinista vs. selección evolutiva: ¿Qué consecuencias tiene usar un método de selección completamente determinista sobre la diversidad de la población y el riesgo de convergencia prematura?
Relaciona tu respuesta con el comportamiento observado en las primeras generaciones del ejemplo.
3.  La función mutacion() genera nuevos valores en un intervalo: [numero_seleccionado−rango, numero_seleccionado+rango]
¿Cómo afecta el valor elegido por el usuario para rango_mutacion al equilibrio entre exploración (buscar lejos) y explotación (afinar búsqueda)? Da ejemplos de valores pequeños y grandes.
4. Comportamiento del algoritmo con diferentes parámetros, el usuario puede elegir: número de individuos, número de generaciones, rango de mutación, y límites inferior y superior de búsqueda. DEducir el número de individuos o el rango de búsqueda inicial a la probabilidad de encontrar el número objetivo antes del límite de generaciones?
Explica qué parámetro es más crítico y por qué.
5.  la metáfora evolutiva depende de población, entorno, competición ,adaptación. ¿Cómo se refleja esta metáfora en este código, considerando que solo un individuo (el más apto) “lidera” y los demás se mueven alrededor de él en cada generación? Comenta si este modelo representa una “evolución realista” o más bien una búsqueda guiada por explotación intensa.


DCA2_Ej02
1.- En este DCA, las señales “benign”, “danger” y “context” se construyen a partir del rango normal (20–25).
¿Qué efecto tendría estrechar o ampliar el rango normal (por ejemplo, cambiarlo a 21–24 o 18–27) sobre el potencial de activación y, en consecuencia, sobre la tasa de falsos positivos y falsos negativos?
2.- El umbral (threshold) determina qué valores de activación se consideran anomalías. Aquí se usa un valor fijo de 0.5.  ¿Qué consecuencias tendría modificar este umbral a valores más altos (por ejemplo, 0.8) o más bajos (por ejemplo, 0.2) en la sensibilidad del sistema?
