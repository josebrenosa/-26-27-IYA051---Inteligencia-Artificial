# Reto 21 - Clustering: Jerárquico

[a completar]

Para el ejemplo de clustering gerárquico: 

- Qué información aporta el dendrograma mostrado en la práctica y cómo podrías usarlo para decidir el número óptimo de clusters?
- En el dendrograma de la página 1, ¿qué indica la altura a la que se unen dos ramas y qué relación tiene con la distancia entre observaciones? 
- Observando el dendrograma, ¿cuál crees que sería un número razonable de clusters? Justifica dónde "cortarías" el dendrograma y por qué.
- ¿Por qué se utiliza el método ward en la función linkage(X, method='ward')? ¿Qué efecto tiene este método sobre la formación de clusters? 
- La práctica utiliza como variables “Ingresos” y “Puntuación” de los clientes. ¿Qué tipo de relación o patrones esperas que el clustering jerárquico identifique entre estas dos características?
- Según la gráfica “Clusters de clientes” (página 1), ¿cómo describirías las diferencias entre los cinco clusters encontrados? ¿Qué distingue visualmente a cada grupo? 
- Qué ocurriría si en lugar de usar la distancia euclidiana se empleara otra métrica (por ejemplo distancias Manhattan)? ¿Cómo afectaría eso al dendrograma y a la formación de grupos?
- En el código se establece n_clusters=5. ¿Cómo cambiaría el resultado si en su lugar se dejara que el dendrograma determine automáticamente el número de clusters? 
- ¿Por qué el clustering jerárquico no requiere especificar al principio el número de clusters como sí ocurre con k-means? ¿Qué ventaja ofrece esto al analista?
- Imagina que en el futuro se añaden muchos más clientes a la base de datos. ¿Qué limitaciones tendría el clustering jerárquico al escalar a datasets grandes? ¿Qué alternativas podrían usarse?
