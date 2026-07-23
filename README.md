# Euclides - Juego del Algoritmo de Euclides Extendido

Este es un juego educativo diseñado para dispositivos móviles y optimizado para pantallas OLED (con fondo negro puro para ahorro de batería). El objetivo del juego es practicar la resolución del **Algoritmo de Euclides** y el **Algoritmo de Euclides Extendido** para encontrar el Máximo Común Divisor (MCD) y los coeficientes de la Identidad de Bézout ($s$ y $t$).

Puedes acceder al juego directamente desde tu teléfono móvil. Está construido en un único archivo HTML para facilitar su despliegue en **GitHub Pages**.

---

## ¿Cómo se juega?

El juego consta de **25 ejercicios aleatorios** y sin repetición. Cada ejercicio se divide en **3 fases** consecutivas.

### Controles Especiales (Accesibilidad)
En la parte superior de la pantalla dispones de:
* **Selector de Tamaño de Letra:** Botones `--A`, `-A`, `A`, `A+`, `A++` para adaptar el tamaño del texto a tus necesidades.
* **Modo Contraste Extremo:** Un botón para alternar a un modo de visualización simplificado de alto contraste (blanco y negro puro sin degradados).

---

## Fases del Ejercicio

Para cada ejercicio, el enunciado te pedirá:
> **Calcula el $mcd(A, B)$ usando el algoritmo de Euclides y aprovecha el método para encontrar $s$ y $t$ enteros tal que $s \cdot A + t \cdot B = C$.**

No necesitarás hacer cálculos mentales complejos ni escribir números con el teclado: todos los números requeridos se encuentran en un **panel de botones** en la parte inferior. Simplemente selecciona una casilla vacía (se iluminará en verde) y pulsa el botón del número correspondiente para rellenarla.

### Fase 1: Algoritmo de Euclides (Divisiones Sucesivas)
El objetivo es realizar las divisiones sucesivas hasta llegar a un residuo de $0$. 
1. Rellena la primera línea de la forma $A = B \cdot q_1 + r_1$ eligiendo los valores correctos de los botones.
2. Pulsa **Comprobar**. Si es correcto, se bloqueará y se desbloqueará la segunda línea. Si es incorrecto, los valores erróneos se marcarán en rojo y perderás puntos.
3. Repite el proceso para las siguientes líneas:
   * Línea 2: $B = r_1 \cdot q_2 + r_2$
   * Línea 3: $r_1 = r_2 \cdot q_3 + r_3$
   * Línea 4: $r_2 = r_3 \cdot q_4 + 0$ (El último residuo debe ser $0$).
4. Finalmente, señala cuál es el **MCD** (que es el último residuo no nulo, $r_3$).

### Fase 2: Búsqueda de los Coeficientes $s$ y $t$ (Sustitución Hacia Atrás)
En esta fase expresaremos el MCD como combinación lineal de los residuos anteriores hasta llegar a los términos de $A$ y $B$.
* **Paso 2.1:** Expresa el MCD despejándolo de la tercera ecuación: $r_3 = r_1 - q_3 \cdot r_2$.
* **Paso 2.2:** Sustituye el residuo $r_2$ por su expresión de la segunda ecuación: $r_3 = r_1 - q_3 \cdot (B - q_2 \cdot r_1)$.
* **Paso 2.3:** Simplifica agrupando los términos de $r_1$ y $B$: $r_3 = (1 + q_2 \cdot q_3) \cdot r_1 - q_3 \cdot B$.
* **Paso 2.4:** Sustituye el residuo $r_1$ por su expresión de la primera ecuación: $r_3 = s_{temp} \cdot (A - q_1 \cdot B) - q_3 \cdot B$.
* **Paso 2.5:** Simplifica agrupando para obtener la identidad de Bézout: $r_3 = s \cdot A + t \cdot B$.

### Fase 3: Resultados Finales
Escribe directamente los valores finales de:
* Coeficiente $s$
* Coeficiente $t$
* Valor del $mcd(A, B)$

---

## Sistema de Puntuación

* **Puntuación Inicial:** Empiezas el juego con `0` puntos.
* **Aciertos:** Completar correctamente cada paso de una fase suma puntos.
* **Errores:** Si introduces un número incorrecto, la casilla se marcará en **rojo**, se restarán puntos de tu puntuación y no podrás avanzar a la siguiente línea hasta corregirlo.
* **Persistencia:** Tu progreso (ejercicios completados, puntuación y racha) se guarda automáticamente en el navegador. Si cierras la pestaña o refrescas la página, podrás continuar donde lo dejaste.

---

## Cómo alojarlo en GitHub Pages

1. Crea un repositorio en GitHub llamado `euclides`.
2. Sube el archivo `index.html` a la rama principal (`main`).
3. Ve a **Settings** (Configuración) de tu repositorio.
4. En la barra lateral izquierda, selecciona **Pages**.
5. En la sección "Build and deployment", selecciona la rama `main` y la carpeta `/ (root)`. Pulsa **Save**.
6. En unos minutos, tu juego estará disponible en `https://<tu-usuario>.github.io/euclides/`.
