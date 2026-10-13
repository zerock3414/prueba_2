# Laboratorio Virtual: Dinámica en el Plano Inclinado con Fricción

Aplicación web educativa, interactiva y de alta fidelidad visual para la enseñanza de la **Dinámica de la Partícula** centrada en un bloque de masa $m$ que se desliza por un plano inclinado con fricción cinética.

---

## 🚀 Cómo ejecutar la aplicación

1. **Abrir directamente en el navegador**:
   Haz doble clic sobre el archivo [`index.html`](file:///C:/Users/Dell/.gemini/antigravity/scratch/dinamica-plano-inclinado/index.html) o arrástralo a Google Chrome, Microsoft Edge, Mozilla Firefox o Safari. No requiere instalar ningún servidor ni dependencias (`node_modules`), funciona 100% de manera autónoma y local.

2. **Opcional - Servidor local HTTP**:
   Si prefieres servirlo mediante un servidor local:
   ```bash
   npx serve .
   # o con Python:
   python -m http.server 8080
   ```

---

## 🎯 Características Principales

### 1. Parámetros en Tiempo Real
- **Masa ($m$)**: de $0.5\text{ kg}$ a $30.0\text{ kg}$.
- **Ángulo de inclinación ($\theta$)**: de $0^\circ$ a $85^\circ$.
- **Coeficiente de fricción cinético ($\mu$)**: de $0.00$ (sin rozamiento) a $1.00$ (alta fricción).
- **Aceleración de gravedad ($g$)**: valor predeterminado $9.81\text{ m/s}^2$, ajustable para simular la Luna ($1.62\text{ m/s}^2$) o Marte ($3.72\text{ m/s}^2$).
- **Condiciones iniciales**: posición inicial $x_0$ y velocidad inicial $v_0$.

### 2. Escena Física y Fuerzas Reales sobre el Cuerpo
- **Bloque móvil con etiqueta** de masa $m$.
- **Fuerzas reales aplicadas directamente sobre el cuerpo**:
  - **Vector Peso Real ($\vec{P} = m\vec{g}$)** en **Rojo** (vertical hacia abajo).
  - **Fuerza Normal ($\vec{N}$)** en **Verde** (perpendicular a la superficie hacia arriba).
  - **Fuerza de Fricción ($\vec{f} = \mu N$)** en **Morado** (paralela a la superficie, opuesta al deslizamiento).
  - **Vector Aceleración ($\vec{a}$)** en **Cian eléctrico** destacado (a lo largo de la rampa).
- *Criterio pedagógico*: Las componentes del peso no se sobrecargan sobre el cuerpo físico, reservándose para el **Diagrama de Cuerpo Libre (DCL)** donde se analiza su descomposición formal.
- Flechas proporcionales con etiquetas dinámicas de magnitud en Newtons y badges de alto contraste.

### 3. Dinámica y Ecuaciones Físicas
- $N = mg \cos(\theta)$
- $f = \mu N = \mu mg \cos(\theta)$
- $\Sigma F_\parallel = mg \sin(\theta) - \mu mg \cos(\theta)$
- $a = g(\sin\theta - \mu\cos\theta)$

#### Estados del movimiento:
- **$a > 0$**: El cuerpo acelera hacia abajo ($\tan\theta > \mu$).
- **$a = 0$**: Velocidad constante / equilibrio dinámico ($\tan\theta = \mu$).
- **$a < 0$**: La fricción máxima supera el impulso gravitatorio ($\tan\theta < \mu$). El bloque permanece en reposo o desacelera hasta detenerse si partió con velocidad.

### 4. Tres Gráficas Cinemáticas Dinámicas Sincronizadas
- **Posición vs. Tiempo $x(t) = x_0 + v_0 t + \frac{1}{2} a t^2$** (verde esmeralda).
- **Velocidad vs. Tiempo $v(t) = v_0 + a t$** (azul cielo).
- **Aceleración vs. Tiempo $a(t) = \text{const}$** (ámbar).
- Incluyen escáner temporal en tiempo real, áreas coloreadas y tooltips al pasar el ratón.

### 5. Diagrama de Cuerpo Libre (DCL) y Barra Comparativa
- **Panel DCL interactivo**:
  - Partícula puntual centrada en ejes rotados ($x'$ paralelo al plano, $y'$ perpendicular).
  - Visualización aislada de las fuerzas $\vec{P}$, $\vec{N}$ y $\vec{f}$.
  - **Descomposición del peso**: interruptor para mostrar u ocultar las componentes rectangulares ($mg\sin\theta$ en naranja y $mg\cos\theta$ en azul) junto con líneas punteadas de proyección ortogonal y arco del ángulo de inclinación $\theta$.
- **Barra de balance dinámico**: comparativa visual instantánea entre la fuerza impulsora descendente $mg\sin\theta$ y la fuerza resistente de fricción $f$.

### 6. Controles de Reproducción y Atajos
- ▶️ **Iniciar** / ⏸️ **Pausar** (`Barra espaciadora`).
- ↻ **Reiniciar** animación (`Tecla R`).
- 🔄 **Restablecer parámetros** iniciales.
- Selector de velocidad de simulación: `0.25x`, `0.5x`, `1.0x`, `2.0x`.
- Selector de tema **Modo Oscuro / Modo Claro**.
- Presets inmediatos: *Sin Fricción*, *Ángulo Crítico*, *Bloqueado*, *Pendiente 60°*, *Gravedad Lunar*.
