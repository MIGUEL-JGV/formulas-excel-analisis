1. Clasificación por Nivel de Conocimiento (Café)
Esta fórmula realiza una búsqueda matricial para identificar el nivel de conocimiento técnico sobre café basándose en un comentario o texto específico.
Lógica: Busca una lista de términos técnicos (Palabras_clave) dentro de una celda (S2). Si encuentra una coincidencia, devuelve la categoría correspondiente desde el rango categorias_café.
Fórmula original:
```
=ÍNDICE(categorias_café,COINCIDIR(VERDADERO,ESNUMERO(HALLAR(Palabras_clave,A2)),0))
```
2. Identificación de Temas Generales
Se utiliza para categorizar comentarios abiertos en temas predefinidos (ej. servicio, precio, calidad).
Lógica: Similar a la anterior, pero aplicada a una matriz de clasificación general (Clasificacion_otros) comparando el texto de la celda A12 con el diccionario Palabras_otros.
Fórmula original:
```
=ÍNDICE(Clasificacion_otros,COINCIDIR(VERDADERO,ESNUMERO(HALLAR(Palabras_otros,A2)),0))
```
3. Concatenación Inteligente de Resultados
Esta fórmula se utiliza para agrupar múltiples resultados o etiquetas encontradas en diferentes columnas (E a J) en una sola celda, separadas por comas.
Lógica: Evalúa cada columna; si contiene un valor distinto de cero, lo agrega a la cadena. Incluye una validación interna para colocar la coma , solo si ya existe un elemento previo, evitando comas al inicio o duplicadas.
Fórmula original:
```
=SI(E2<>0,E2,"")&SI(F2<>0,SI(E2<>0,",","")&F2,"")&SI(G2<>0,SI(O(E2<>0,F2<>0),",","")&G2,"")&SI(H2<>0,SI(O(E2<>0,F2<>0,G2<>0),",","")&H2,"")&SI(I2<>0,SI(O(E2<>0,F2<>0,G2<>0,H2<>0),",","")&I2,"")&SI(J2<>0,SI(O(E2<>0,F2<>0,G2<>0,H2<>0,I2<>0),",","")&J2,"")
```
Configuración de Rangos en Excel
Para que las fórmulas de búsqueda funcionen, debes asignar nombres a tus listas:
Selecciona tu lista de palabras clave.
Ve a la pestaña Fórmulas > Asignar nombre.
En "Nombre", escribe exactamente: Palabras_clave (o el nombre que corresponda a la fórmula).
Haz lo mismo con los rangos de categorías.
