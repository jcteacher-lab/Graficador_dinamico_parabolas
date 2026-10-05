# 📐 Constructor de Parábolas Interactivo

Simulador educativo que construye la **gráfica y la ecuación de una parábola**
a partir de sus elementos geométricos: **Vértice**, **Foco** y **Directriz**.
Desarrollado en **HTML + CSS + JavaScript** puro con **Canvas 2D**, autocontenido
en un solo archivo y sin dependencias externas.

---

## ✨ Características

- 🎯 **Entrada flexible:** combina libremente Vértice, Foco y Directriz mediante checkboxes.
- ⚡ **Auto-graficado:** la parábola se recalcula y dibuja automáticamente al escribir cualquier valor.
- 🖱️ **Manipulación directa:** arrastra el vértice, el foco o la directriz **desde la gráfica**.
- ✅ **Validación inteligente:** verifica la consistencia geométrica entre los elementos capturados.
- 📝 **Ecuación en dos formas:** estándar y general, generadas al instante.
- 📌 **Panel de elementos:** muestra vértice, foco, directriz, eje de simetría, |p|, lado recto y orientación.
- 🎨 **Canvas interactivo:** cuadrícula adaptativa, ejes etiquetados, colores diferenciados y etiquetas flotantes.
- 📱 **Soporte táctil:** funciona con ratón, touchpad y pantallas táctiles.
- 🌐 **Interfaz completamente en español.**

---
## 🆕 Novedades v2.1.0

- 🖱️ **Arrastre interactivo en el canvas:** ahora puedes mover el **vértice**,
  el **foco** y la **directriz** directamente con el ratón o el dedo.
- 🎯 **Detección automática:** el cursor cambia a `grab` al pasar sobre un
  elemento arrastrable y a `grabbing` durante el arrastre.
- 🔗 **Alineación inteligente:** al arrastrar V o F, se mantiene automáticamente
  la alineación vertical u horizontal entre ambos (evita inconsistencias).
- 🔄 **Sincronización automática:** al mover V o F, la directriz se recalcula;
  al mover la directriz, el foco se ajusta si V+F están activos.
- 📱 **Soporte táctil:** funciona también en tablets y móviles.
- 🧩 **Módulo 100% aditivo:** no se modificó la lógica existente del simulador.

---
## 🆕 Novedades v2.0.0

- 🔄 **Campos siempre visibles:** Vértice, Foco y Directriz se muestran permanentemente.
  Cada uno se **activa/desactiva con un checkbox**.
- ⚡ **Auto-graficado:** se eliminó el botón "Graficar". La parábola se construye
  automáticamente al detectar **al menos 2 elementos activos**.
- 🧠 **Resolución por prioridad:**
  1. Vértice + Foco
  2. Vértice + Directriz
  3. Foco + Directriz
- 🛡️ **Validación de consistencia:** si los 3 elementos están activos, se verifica que
  la directriz coincida con el vértice y foco; si no, se avisa y se prioriza Vértice + Foco.
- 💬 **Sistema de mensajes:** informativos, avisos y errores con colores diferenciados.

---

## 🚀 Cómo usar

1. Descarga el archivo `constructor_parabolas.html`.
2. Ábrelo con cualquier navegador moderno (Chrome, Firefox, Edge, Safari).
3. Marca los **checkboxes** de los elementos que conoces:
   - 📍 Vértice V(h, k)
   - ⭐ Foco F(fx, fy)
   - 📏 Directriz (horizontal o vertical)
4. Escribe los valores numéricos. **La gráfica se actualiza al instante.**
5. Consulta la **ecuación** y el **panel de elementos** a la derecha.

---

## 🎮 Controles del simulador

## 🖱️ Arrastrar elementos (interacción con el canvas)

Además de escribir los valores en los campos, puedes **arrastrar los
elementos directamente sobre la gráfica**:

| Elemento | Acción | Comportamiento |
|---|---|---|
| 📍 **Vértice** | Arrastra el punto azul | Se mueve en tiempo real; si el foco está activo, se mantiene alineado |
| ⭐ **Foco** | Arrastra el punto rosa | Se mueve en tiempo real; si el vértice está activo, se mantiene alineado |
| 📏 **Directriz** | Arrastra la línea verde | Se desliza sobre su eje; si V+F están activos, el foco se reajusta |

### 🎨 Feedback visual

- **Cursor `grab`** 👆 al pasar sobre un elemento arrastrable.
- **Cursor `grabbing`** ✊ mientras se arrastra.
- Los valores de los campos se actualizan automáticamente al soltar.

### 🔒 Reglas de coherencia

- Con **V y F activos**, el arrastre de cualquiera de ellos se restringe
  al **eje de alineación** detectado al iniciar el arrastre.
- Al mover **V o F**, la directriz se recalcula automáticamente si está activa.
- Al mover la **directriz**, si V y F están activos, el foco se ajusta para
  mantener la relación `FV = distancia(V, directriz)`.
- Si el cursor sale del canvas durante el arrastre, se cancela limpiamente.

### 📱 Compatibilidad táctil

El arrastre funciona también con **un solo dedo** en dispositivos táctiles,
sin interferir con el desplazamiento de la página cuando no hay un elemento
seleccionado.

---

## 📤 Salidas en pantalla

### 📝 Ecuaciones generadas

- **Forma estándar** (ejemplo vertical): `(x − h)² = 4p(y − k)`
- **Forma estándar** (ejemplo horizontal): `(y − k)² = 4p(x − h)`
- **Forma general:** `Ax² + Bx + Cy + D = 0`

### 📌 Elementos mostrados

| Elemento | Ejemplo |
|---|---|
| Vértice | (0, 0) |
| Foco | (0, 1) |
| Directriz | y = −1 |
| Eje de simetría | x = 0 |
| Parámetro \|p\| | 1 |
| Lado recto (L) | 4 |
| Extremos del lado recto | (−2, 1) y (2, 1) |
| Orientación | Abre hacia arriba ↑ |

---

## 📚 Uso didáctico

Este simulador está pensado para clases de **Geometría Analítica** y **Álgebra**.
Permite al alumno:

- **Visualizar** la relación entre vértice, foco y directriz.
- **Comprobar** que la distancia de cualquier punto de la parábola al foco
  es igual a su distancia a la directriz.
- **Construir** la ecuación a partir de elementos geométricos.
- **Identificar** la orientación de la parábola según el signo de `p`.
- **Experimentar** con parábolas horizontales y verticales.

### 📖 Definición de la parábola

> Una parábola es el lugar geométrico de los puntos que **equidistan**
> de un punto fijo llamado **foco** y de una recta fija llamada **directriz**.

### 🔑 Relaciones clave

$$
\text{Vértice: } V(h, k) \qquad
\text{Foco: } F(h, k+p) \qquad
\text{Directriz: } y = k - p
$$

$$
\text{Lado recto: } L = |4p| \qquad
\text{Eje de simetría: } x = h \text{ (vertical)}
$$

---

## 🧪 Ejemplos incluidos

Puedes probar estos casos directamente en el simulador:

| Vértice | Foco | Directriz | Orientación |
|---|---|---|---|
| (0, 0) | (0, 1) | y = −1 | ↑ Arriba |
| (0, 0) | (0, −1) | y = 1 | ↓ Abajo |
| (0, 0) | (2, 0) | x = −2 | → Derecha |
| (0, 0) | (−2, 0) | x = 2 | ← Izquierda |
| (2, 3) | (2, 5) | y = 1 | ↑ Arriba |

---

## 🛠️ Tecnologías

- **HTML5**
- **CSS3** (flexbox, grid, backdrop-filter, transiciones)
- **JavaScript ES6+**
- **Canvas 2D API** (con polyfill de `roundRect`)
- Sin librerías externas

---

## 📂 Estructura del proyecto

---

## 🔬 Detalles técnicos

### Resolución de la parábola

Dependiendo de los elementos activos, el sistema aplica una de estas reglas:

1. **Vértice + Foco:**
   - Se calcula `p` como la distancia dirigida vértice → foco.
   - Se determina el eje (`vertical` u `horizontal`) según la alineación.

2. **Vértice + Directriz:**
   - `p = k − c` (directriz horizontal) o `p = h − c` (directriz vertical).

3. **Foco + Directriz:**
   - El vértice es el punto medio entre foco y directriz.
   - `p = fy − k` o `p = fx − h`.

### Validación de consistencia

Si los 3 elementos están activos, se verifica que la directriz calculada
a partir del vértice y el foco coincida con la capturada. En caso contrario:

- Se muestra un **aviso amarillo**.
- Se prioriza el par **Vértice + Foco**.

---

## 🔗 Proyectos relacionados

- [⚡ Simulador de Tiro Parabólico](https://jcteacher-lab.github.io/tiroparabolico) —
  Simulador educativo de movimiento de proyectiles con Canvas 2D.
