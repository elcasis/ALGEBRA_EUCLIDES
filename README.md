# El Laberinto de Euler y Fermat: Juego de Aritmética Modular

Una aplicación web móvil interactiva, autocontenida en un único archivo HTML, diseñada para aprender y practicar la resolución de potencias modulares del tipo:

$$2^n \equiv x \pmod{p}$$

El juego guía al usuario a través de los conceptos de la función Fi de Euler ($\phi(p)$) y el Pequeño Teorema de Fermat, incluyendo casos "trampa" donde el módulo no es coprimo con la base.

---

## 🎮 ¿Cómo se juega?

El juego consta de **25 ejercicios matemáticos prácticos** divididos en 5 módulos de dificultad progresiva. Cada ejercicio se resuelve de forma guiada en **3 fases secuenciales** (sin tener que calcular a mano, seleccionando las respuestas correctas entre las opciones de los botones):

1.  **Fase 1: Análisis del Módulo**
    *   Determinar la naturaleza del módulo $p$.
    *   Si $p$ es primo, se aplica el **Pequeño Teorema de Fermat** (reducción modular del exponente con base $p-1$).
    *   Si $p$ es compuesto impar, se aplica el **Teorema de Euler** (reducción modular del exponente con base $\phi(p)$).
    *   Si $p$ es par (módulo trampa), se identifica que **no son coprimos** ($\gcd(2, p) \neq 1$) y no se aplica directamente ninguno de los dos teoremas.
2.  **Fase 2: Reducción del Exponente**
    *   Calcular el residuo $r = n \pmod{\text{base}}$ para simplificar el cálculo de la potencia.
    *   En el caso de módulos trampa (como mod 6, 10, 12, 20), esta fase ayuda a identificar el **ciclo recurrente** y su periodicidad.
3.  **Fase 3: Cálculo del Residuo**
    *   Elegir la respuesta final de la congruencia reducida $2^r \pmod{p}$.

---

## 📚 Estructura de Módulos (25 Ejercicios)

*   **Módulo 1: Módulos Primos Chicos (Fermat)** (Ejercicios 1-5): Aprendizaje básico del Pequeño Teorema de Fermat con módulos 3, 5, 7, 11 y 13.
*   **Módulo 2: Módulos Compuestos Impares (Euler)** (Ejercicios 6-10): Introducción a la función totiente de Euler $\phi(p)$ con módulos 9, 15, 21, 25 y 33.
*   **Módulo 3: Exponentes Grandes y Primos Medios** (Ejercicios 11-15): Reducción de exponentes de tres y cuatro cifras mod 17, 13, 19, 11 y 7.
*   **Módulo 4: Módulos Compuestos Grandes** (Ejercicios 16-20): Cálculo de $\phi(p)$ y reducciones mod 35, 45, 55, 77 y 99.
*   **Módulo 5: Casos Trampa y Especiales** (Ejercicios 21-25): Análisis de no coprimalidad y búsqueda de ciclos de recurrencia mod 6, 10, 12, 20 y un caso especial mod 17 (primo de Fermat).

---

## 🎨 Características Técnicas y Estéticas

*   **Diseño OLED Black**: Estética oscura premium (negro absoluto y gris oscuro) para reducir la fatiga visual y ahorrar batería en dispositivos móviles.
*   **Acentos de Color Didácticos**:
    *   **Cian** (`#00ffff`): Identifica los pasos gobernados por el Teorema de Euler.
    *   **Dorado** (`#ffd700`): Identifica los pasos gobernados por el Pequeño Teorema de Fermat.
*   **Accesibilidad Móvil**:
    *   **Cambio de Tamaño de Fuente**: Botón `A+` para alternar tamaños de letra base de forma global (14px, 16px, 20px, 24px) ideal para pantallas pequeñas.
    *   **Alto Contraste**: Botón `CONTRASTE` que activa una interfaz minimalista de blanco y negro puros, sin sombras ni gradientes, facilitando la legibilidad.
*   **Audio Sintetizado (Web Audio API)**: Generación dinámica offline de efectos de sonido interactivos para aciertos, errores y fanfarria de victoria final (silenciable de forma persistente con un botón).
*   **Diploma Personalizable**: Genera un diploma digital imprimible con tu nombre al superar los 25 retos matemáticos.

---

## 🚀 Despliegue en GitHub Pages

Para jugar directamente desde tu teléfono móvil utilizando GitHub Pages:

1.  Crea un repositorio público en tu perfil de GitHub (por ejemplo, `euler-fermat-quiz`).
2.  Sube el archivo `index.html` en la raíz del repositorio.
3.  Ve a **Settings** (Configuración) -> **Pages** en el menú de la izquierda del repositorio.
4.  En la sección *Build and deployment*, selecciona la rama `main` y la carpeta `/ (root)`. Presiona **Save**.
5.  GitHub generará un enlace (por ejemplo, `https://tu-usuario.github.io/euler-fermat-quiz/`) en pocos segundos. ¡Ábrelo desde tu smartphone y empieza a jugar!
