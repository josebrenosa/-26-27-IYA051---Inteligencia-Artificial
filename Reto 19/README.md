# Reto 19 - Clustering: DBScan

Ejemplo 1:
- ¿Qué sucede con el número de clusters detectados cuando modificas el parámetro eps (radio)?
Elabora una tabla con varios valores de eps (por ejemplo: 0.05, 0.1, 0.14, 0.2, 0.3) y anota el número de clusters obtenidos y la cantidad de ruido.
- Manteniendo fijo eps, ¿cómo cambia la cantidad de ruido y la forma de los clusters cuando varías min_samples? Prueba valores como 3, 5, 10, 20 y explica por qué DBSCAN cambia su comportamiento.
- ¿Por qué algunas métricas como Silhouette o Adjusted Rand Index aumentan o disminuyen cuando cambias eps? 
- Usando los resultados gráficos, identifica ejemplos de puntos núcleo, borde y ruido. ¿Cómo se diferencian en el código (core_samples_mask)? Qué condiciones debe cumplir un punto para ser núcleo y cómo DBSCAN clasifica el resto?
- Si reemplazaras DBSCAN por K-Means en este mismo dataset, ¿qué diferencias esperarías en el resultado? Razona pensando en la forma de los clusters y la presencia de ruido.
- Modifica el dataset aumentando cluster_std a valores como 0.7 o 1.0. ¿DBSCAN sigue detectando bien los clusters? ¿Qué ajustes de eps son necesarios? Identifica si es robusto DBSCAN paradatos más dispersos.
- ¿Cuál sería, según tus experimentos, una estrategia práctica para elegir un buen valor de eps para este dataset? Pista: analizar distancias y revisar cuántos puntos quedan como ruido, balancear número de clusters y métricas.

Ejemplo02:
- ¿Qué ocurre si cambias el valor de eps a uno más pequeño o más grande? Observa cuántos clusters aparecen
- ¿Aumenta o disminuye el ruido cuando subes el valor de min_samples?
- ¿Qué pasa si generas menos clusters (por ejemplo, 10 en vez de 50)? ¿DBSCAN los detecta mejor?
- Cuando cambias x_mult o y_mult, ¿cómo cambia la forma de los clusters generados?
- ¿DBSCAN detecta bien los clusters muy alargados o los fragmenta?
- Si los offsets (x_off y y_off) separan más los clusters, ¿es más fácil para DBSCAN encontrarlos?
- ¿Dónde ves más puntos de ruido: cerca de los bordes, en zonas aisladas o repartidos por todo el gráfico?


Reto 19 - Ejercicio de repaso: Examen
