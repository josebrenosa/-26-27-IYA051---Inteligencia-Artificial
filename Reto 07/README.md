# Reto 07 - Examen parcial

Diseñamos sistemas expertos de inteligencia artificial basados en visión artificial clásica.

Todos deben cumplir la misma cadena de visión clásica: adquisición → segmentación → extracción de características → clasificación mediante árbol de decisión → interpretación de la escena → demostración cuantitativa.

## Convocatoria de trabajos — Parcial de Visión Artificial Clásica
### 1. Objetivo
El parcial consistirá en el diseño e implementación de un sistema de visión artificial clásica capaz de analizar automáticamente una escena cenital formada por objetos físicos colocados sobre un tapete.
El objetivo no es utilizar modelos entrenados de aprendizaje automático, sino resolver el problema mediante técnicas clásicas de procesamiento de imagen, extracción de características y reglas de decisión.
Cada alumno eligirá uno de los retos indicados en esta convocatoria, de tal forma que los retos se hayan distribuido equitativamente.
### 2. Montaje común obligatorio
Para garantizar que los trabajos tengan una dificultad comparable, todos utilizarán un montaje experimental equivalente.
Requisitos: 
Zona de trabajo	Tapete verde mate de Tamaño mínimo	0,50 × 0,50 m
Cámara	Una única cámara fija en Posición cenital y aproximadamente perpendicular al tapete con un Campo de visión que debe visualizarse completamente la zona útil del tapete
Resolución a elección del alaumno, aconsejable que sea lo suficiente para distinguir la característica más pequeña necesaria para resolver el reto
Iluminación a elección del alumno
Objetos lo suficientemente pequeños/medianos y manipulables sobre el tapete
Método de Visión artificial clásica: Clasificación	Características explícitas + árbol de decisión/reglas [Deep Learning o Clasificadores aprendidos tipo CNN/YOLO No están permitidos]
La distancia \(x\) entre cámara y tapete no debería fijarse igual para todos, porque depende de la óptica y del sensor. El requisito será que el campo de visión cubra como mínimo los 0,50 × 0,50 m y que la resolución espacial resultante permita resolver el elemento discriminante más pequeño del reto. El alumno deberá justificar experimentalmente que su configuración satisface esta condición.
## 3. Iluminación
La iluminación forma parte del problema. El alumno puede elegir (o no) diseñar un sistema que proporcione una iluminación razonablemente uniforme sobre el tapete y minimice sombras y reflejos. 

## 4. Pipeline mínimo obligatorio
Todos los proyectos deberán implementar conceptualmente:
Imagen RGB → preprocesamiento → segmentación → detección de objetos → extracción de características → árbol de decisión → identificación → interpretación del resultado
Entre las características permitidas se encuentran:
- área;
- perímetro;
- circularidad;
- relación de aspecto;
- orientación;
- excentricidad;
- número de componentes/regiones;
- momentos;
- centroide;
- envolvente convexa;
- descriptores geométricos;
- color en RGB, HSV, Lab u otro espacio justificable;
- análisis de regiones internas del objeto.
El alumno deberá poder explicar qué característica utiliza, cómo la calcula y por qué permite separar unas clases de otras.

## 5. Carga común de los retos
Todos los retos tengan tres niveles de dificultad obligatorios:
Nivel 1 — Detección. Localizar todos los objetos presentes en el tapete.
Nivel 2 — Identificación. Asignar a cada objeto una clase mediante características visuales y un árbol de decisión.
Nivel 3 — Interpretación. Obtener una conclusión de nivel superior: estado de una partida, suma, clasificación, pieza ausente, jugada válida, conteo, etc.
Esto evita, por ejemplo, que "reconocer un dado" sea mucho más sencillo que interpretar una partida de dominó.

## 6. Retos
| Reto | Detección | Clasificación/identificación | Interpretación obligatoria |
|---|---|---|---|
| **Tres en raya** | Detectar tablero y marcas | X, O y casilla vacía | Reconstruir matriz 3×3 e indicar ganador, empate o partida en curso |
| **Dominó** | Detectar y separar fichas | Orientación + nº de puntos de ambas mitades | Reconstruir fichas `[a\|b]`, calcular puntos e identificar al menos jugadas compatibles |
| **Baraja española** | Detectar cartas | Identificar palo y valor en un subconjunto acordado | Contar cartas por palo/valor y calcular una propiedad de la mano |
| **Dados** | Detectar dados | Determinar valor 1–6 | Sumar valores e identificar combinaciones/jugadas definidas |
| **Dados de póker** | Detectar dados | Identificar las seis caras/símbolos | Reconocer jugada: pareja, dobles parejas, trío, póker, etc. |
| **Puzle infantil de cubos** | Detectar cubos/piezas | Identificar cara/pieza por color y forma | Determinar configuración, orden correcto o piezas ausentes |
| **Monedas y billetes** | Detectar cada elemento | Identificar denominación | Calcular número de elementos y **valor monetario total** |
| **Tornillos, tuercas y arandelas** | Segmentar cada pieza | Clasificar mediante área, perímetro, circularidad/excentricidad | Conteo por clase y detección de pieza incorrecta |
| **LEGO** | Detectar piezas | Clasificar por color + tamaño/tipo | Inventario automático por tipo y color |
| **Frutas / legumbres / frutos secos / caramelos** | Detectar unidades | Clasificar mediante forma, tamaño y color | Conteo por clase y cálculo de distribución |
| **Herramientas** | Detectar herramientas | Identificar tipo mediante geometría | Inventario y detección de herramienta ausente/repetida |
| **Pilas** | Detectar unidades | Tipo/tamaño/orientación | Conteo por clase y detección de orientación incorrecta |
| **Componentes electrónicos** | Detectar componentes | Clasificar familias por geometría/color | Conteo por clase, Inventario y detección de componente incorrecto/ausente | 

Se podrán proponer retos de clasificación de objetos distintos a los propuestos.

## 7. Acotación de cada reto
Aquí introduciría restricciones para evitar que algunos proyectos se disparen de dificultad.
Tres en raya. Tablero completo visible. Debe reconocer X, O y vacío independientemente de la orientación global del tablero. Como mínimo se probarán 10 configuraciones distintas, incluyendo victoria de X, victoria de O, empate y partida incompleta.
Dominó. Trabajar con un subconjunto suficiente de fichas, por ejemplo 0–0 a 6–6, pero no exigir reconocer simultáneamente las 28 clases mediante una característica distinta. El sistema debe detectar cada ficha, localizar su división central, contar los puntos de ambas mitades y generar automáticamente su identidad. La dificultad está en la descomposición jerárquica de la imagen.
Baraja española. Recomendaría acotar el problema, porque reconocer las 40 cartas completas mediante visión clásica puede resultar desproporcionado. Por ejemplo, reconocer los cuatro palos y los valores 1–7, o proporcionar un subconjunto de 16–20 cartas. Debe identificar carta, posición y orientación.
Dados. Entre 2 y 6 dados simultáneamente. Deben aparecer en posiciones y orientaciones arbitrarias. Se detectará el contorno del dado y posteriormente los puntos. Además del valor individual, se deberá reconocer una combinación definida por el profesor.
Dados de póker. Cinco dados simultáneos. Identificación de las seis caras y posterior clasificación automática de la jugada. Para igualarlo con dados convencionales, la identificación del símbolo deberá basarse en características geométricas/color, no en plantillas completas de imagen.
Puzle infantil de cubos. Entre 6 y 12 elementos. Cada pieza deberá poder distinguirse mediante combinación de color, geometría y/o patrón sencillo. No exigir reconstrucción 3D. El resultado será identificar cada pieza y determinar si la composición propuesta es correcta, o si hay alguna pieza que girar o reorientar.
Monedas y billetes. Utilizar un conjunto acotado de denominaciones. Recomendaría monedas de euro y, como máximo, 3–4 denominaciones de billetes. El sistema deberá distinguir denominación y calcular automáticamente el importe total. Debe soportar rotaciones.
Clasificador industrial. Al menos 3 familias de tornillos, tuercas y arandelas y 4 variantes dentro de alguna familia. Deberá utilizar explícitamente área, perímetro y excentricidad, pudiendo añadir circularidad, relación de aspecto u otras características. Como salida: clase, subtipo y conteo.
LEGO. Seleccionar entre 4 y 6 tipos geométricamente distinguibles, disponibles en varios colores. La clase final deberá depender de al menos dos atributos, por ejemplo pieza = tipo geométrico + color. Esto obliga a construir un árbol de decisión real.
Productos alimentarios. Elegir una sola familia: frutas pequeñas, legumbres, frutos secos o caramelos. Entre 4 y 6 clases, diferenciables mediante combinación de tamaño, forma y color. Debe incluir conteo por categoría.
Herramientas. Entre 5 y 8 tipos de herramienta claramente distinguibles por silueta: llave, destornillador, alicate, martillo, etc. Deberá funcionar con orientación arbitraria y producir un inventario.
Pilas. Utilizar 4–6 clases, por ejemplo AAA, AA, C, D y 9 V si están disponibles y varias marcas (se pueden incluir otros modelos tambien). Identificación mediante dimensiones relativas, área, relación de aspecto y geometría. Como dificultad adicional, determinar orientación/polaridad cuando visualmente sea posible, determinar precios totales.
Componentes electrónicos. Acotar a 5–8 familias visualmente diferenciables: resistencias, condensadores electrolíticos, LED, potenciómetros, circuitos integrados, etc. No exigir leer códigos impresos ni determinar el valor eléctrico. Se evaluará la clasificación morfológica.

## 8. Condiciones de prueba comunes
Esta parte es importante para que el parcial mida realmente visión artificial y no una demostración preparada.
Cada solución deberá enfrentarse a un conjunto de escenas desconocidas hasta el momento de la evaluación.
En cada prueba se modificarán:
- número de objetos;
- posición;
- orientación;
- distribución espacial;
- combinaciones de clases;

Los objetos no deberían estar siempre exactamente en las mismas coordenadas ni con la misma orientación.

## 9. Árbol de decisión obligatorio
El resultado final no deberá ser una sucesión opaca de condiciones programadas sin justificación. El alumno deberá presentar explícitamente su árbol de decisión.
Para cada nodo deberá justificarse la característica utilizada y el umbral seleccionado a partir de mediciones.

## 10. Entregables y pruebas [a completar]
Trabajo escrito:
Todos los retos deberán entregar exactamente los mismos elementos:
1. Montaje físico, con cámara, tapete e iluminacion (iluminación opcional).
2. Programa funcional de visión artificial.
3. Diagrama del pipeline completo.
4. Explicación del método de segmentación.
5. Tabla de las características extraídas.
6. Árbol de decisión utilizado.
7. Justificación experimental de los umbrales.
8. Resultados sobre un conjunto de pruebas.
9. Medida cuantitativa de aciertos y errores.
10. Demostración presencial con escenas propuestas por el profesor.
Condición: un sistema que solo funcione con las imágenes empleadas durante su desarrollo no podrá superar el aprobado, aunque su demostración preparada funcione correctamente.

Demo en video. 

Prueba - Examen parcial. [Deadline: fecha campus] Demostración en vivo.



