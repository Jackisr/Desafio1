**Informe de Desarrollo - Desafío I de Informática II**

**Profesor**: Augusto Enrique Salazar Jiménez

**Estudiante:** Jakeline Sepúlveda Ramírez

El formato BMP de 24 bits es un formato de almacenar imágenes que
conserva cada píxel utilizando 3 bytes (uno para los canales Rojo, Verde
y Azul), y es guardado fila por fila, de abajo hacia arriba, y donde
incluso puede existir \"padding\" para la alineación de los datos. Su
utilización en Windows es frecuente porque su simplicidad resulta fácil
de manipular a bajo nivel. Las operaciones a aplicar en este caso son a
nivel de bits usando XOR, rotación o desplazamientos que afectan a los
propios bits de los datos en binario. Se utilizan además máscaras de
imagen, es decir, pequeñas matrices de píxeles RGB, que alteran otra
imagen utilizando la suma por canal de manera que sea difícil su
lectura.

**ESPECIFICACIÓN DEL PROBLEMA**

En este desafío se plantea el problema de reconstruir una imagen BMP a
partir de fragmentos o transformaciones aplicadas a nivel de bits sobre
sus componentes de color. Para ello se inicia con varias imágenes que
tienen datos incompletos o dañados del archivo original. []{.mark}

[Por lo anterior, el propósito es generar un programa con Qt que revise
y maneje estas imágenes rotas, así mismo, se puede analizar el cómo se
codifica la imagen teniendo el resultado de su proceso de
construcción.]{.mark}

[Es importante comprender el funcionamiento del el formato BMP y tener
mucha precisión]{.mark}

[con el manejo de los bits para segmentar y unir los valores de cada
color de manera efectiva.]{.mark}

Este desafío sirve para poner a prueba la habilidad para manejar
archivos binarios, usar bien las estructuras y funciones, y manejar
correctamente los errores en procesos complicados de codificación
visual.

**Objetivo:**

-   Identificar qué transformaciones se aplicaron y en qué orden.

-   Comprobar con los archivos de rastreo.

-   Reconstruir la imagen original IO.

-   Cumplir con el desarrollo y los requisitos del desafío.

PROPUESTA DE SOLUCIÓN

-   Leer archivos BMP binarios modificados.

-   Aplicar operaciones bit a bit y enmascaramientos.

-   Reconstruir la imagen original.

-   Usar C++ y Qt para el desarrollo del programa.

-   Seguir una estructura modular y comprensible como funciones bien
    > separadas y uso de estructuras aprendidas en el proceso de
    > Informatica.

-   Aplicar validaciones.

-   Incluir una estructura para los parámetros de reconstrucción: ancho,
    > alto, modo, entre otros.

**ANALISIS IMPORTANTE**

-   Las transformaciones generan versiones intermedias.

-   Cada versión intermedia se enmascara y se compara con los datos
    > esperados.

-   Se guarda la transformación correcta si la suma concuerda para
    > obtener el resultado.

**Diagramas y pseudocódigo:** se pueden incluir posteriormente esquemas
de flujo del proceso general y funciones como aplicarXOR,
aplicarRotacion, verificarEnmascaramiento.

**SEGUIMIENTO DEL PROBLEMA TENIENDO EN CUENTA LA SOLUCIÓN PLANTEADA**

**Pensamiento inicial:**

-   Crear funciones separadas para cada tipo de transformación.

-   Leer y comparar archivos de rastreo.

-   Ordenar muy bien las rutas y funciones a seguir.

**Cambios durante el análisis:**

-   Se puede generar la necesidad de aplicar las transformaciones en
    > diferentes órdenes para validar la combinación correcta y llegar a
    > un mejor resultado.

-   Se probaràn como refuerzos de prueba archivos .txt para evitar
    > errores y así un mejor manejo eficaz del código.

**Elección de enfoques:**

-   Usar punteros y arreglos para mayor control.

-   No usar STL para cumplir requisitos del reto.

-   Modularizar para facilitar pruebas unitarias de transformaciones.

**PROBLEMAS TÉCNICOS PREVISTOS**

Durante el desarrollo del desafío pueden ocurrir varios problemas
comunes. Un problema es que la imagen reconstruida aparece
incorrectamente, es común que presente errores de manipulación de bits,
como la aplicación o el cambio de máscara inadecuado. En esta situación,
es mejor observar de cerca los pasos que está tomando y verificar qué
detalles son importantes. Otro problema podría ser que el software no
cargue los archivos o se apaga abruptamente. Esto generalmente surge de
rutas erróneas o una mala supervisión de errores al iniciar los
archivos. Para abordar èsto, se deben establecer verificaciones para
garantizar que los archivos se abran correctamente, y se pueden emplear
instrumentos como Qfiledialog para una selección de ruta segura. El
programa podría no poder compilar, debido a errores de sintaxis o
archivos conectados incorrectamente en el archivo .pro. Se recomienda
examinar que todos los documentos de origen se incorporan y ensamblan de
forma incremental. Por último, las inexactitudes pueden surgir en las
mediciones de la imagen, debido a asignaciones de ancho erróneas, altura
o recuento de fragmentos. Para evitar esto, tengo que asegurarme de
generar datos cruciales en el terminal durante la operación y validar
con ilustraciones menores antes de manejar instancias intrincadas.

**CRITERIOS A CODIFICAR:**

-   Eficiencia en acceso a memoria.

-   Legibilidad y pruebas de código.

-   Evitar redundancia y ampliar funciones.

-   Validación temprana de resultados parciales que me permitan avanzar.

**ALGORITMOS BASE QUE SE UTILIZARÁN**

-   **XOR:** aplicación directa entre ID e IM.

> **rotateBitsLeft/right:** se manipula cada byte para rotarlo
> circularmente.

-   **loadPixels:** usa QImage para obtener un arreglo lineal RGB.

-   **exportImage:** exporta imagen desde arreglo a BMP.

-   **loadSeedMasking:** carga offset y valores RGB del .txt en memoria.

-   **verificarEnmascaramiento:** compara la suma con los datos del
    > archivo.
