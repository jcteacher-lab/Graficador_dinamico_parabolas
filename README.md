# 📐 Constructor de Parábolas Interactivo

Simulador educativo que construye la **gráfica y la ecuación de una parábola**
a partir de sus elementos geométricos: **Vértice**, **Foco** y **Directriz**.
Desarrollado en **HTML + CSS + JavaScript** puro con **Canvas 2D**, autocontenido
en un solo archivo y sin dependencias externas.

---

## ✨ Características

- 🎯 **Entrada flexible:** combina libremente Vértice, Foco y Directriz mediante checkboxes.
- ⚡ **Auto-graficado:** la parábola se recalcula y dibuja automáticamente al escribir cualquier valor.
- ✅ **Validación inteligente:** verifica la consistencia geométrica entre los elementos capturados.
- 📝 **Ecuación en dos formas:** estándar y general, generadas al instante.
- 📌 **Panel de elementos:** muestra vértice, foco, directriz, eje de simetría, |p|, lado recto y orientación.
- 🎨 **Canvas interactivo:** cuadrícula adaptativa, ejes etiquetados, colores diferenciados y etiquetas flotantes.
- 🌐 **Interfaz completamente en español.**

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

| Elemento | Campos | Descripción |
|---|---|---|
| 📍 Vértice | `h`, `k` | Coordenadas del vértice de la parábola |
| ⭐ Foco | `fx`, `fy` | Coordenadas del foco |
| 📏 Directriz | Tipo (`y = c` o `x = c`) + valor `c` | Recta directriz |

**Reglas:**
- Se requieren **al menos 2 elementos activos** para construir la parábola.
- Con **3 elementos**, se valida la consistencia geométrica.
- Los cambios se reflejan **en tiempo real** sin necesidad de presionar botones.

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

- [⚡ Simulador de Tiro Parabólico](https://jcteacher-lab.github.io/tiro-parabolico) —
  Simulador educativo de movimiento de proyectiles con Canvas 2D.
