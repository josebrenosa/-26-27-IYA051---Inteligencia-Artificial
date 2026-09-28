# Reto 04 - Simuladores (II) + algoritmos

Seguimos con nuestro simulador:
Vamos a emular un robot moviéndose por nuestro mapa.
Podríamos incluir un robot tipo aspirador con odometría en las ruedas, sensores LiDAR e IR, comunicaciones WiFi, bluetooth, ZigBee, etc. ¿Recordáis que tiene que ser lo más sencillo? Pues vamos a considerar simplemente a nuestro robot como un pixel azul que se va moviendo por nuestro mapa. 

Opcional: 
- Pintar la trayectoria calculada en naranja o amarillo, para ver que la sigue correctamente.
- Pintar el objetivo en rojo y cambiar a verde cuando consigue tocarlo.

Tareas:
- Simular un robot moviendose en el mapa desde el punto inicial hasta el final, siguiendo los puntos de la trayectoria planificada.
- ¿Qué ocurre si tuviéramos niebla? Inicialmente podríamos plantearnos una trayectoria recta, pero deberíamos modificar nuestra trayectoria según se nos actualizan los obstáculos del mapa. Implementa una niebla que cubra todo el mapa a excepción de un radio de 15 o 20 pixeles respecto del robot. Mira a ver si consigues que llegue al objetivo (para un mapa de 600x800).


