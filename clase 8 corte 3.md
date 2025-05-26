# Sistemas de segundo orden

Los sistemas de segundo orden son fundamentales en la ingeniería de control, ya que modelan una amplia gama de sistemas físicos como oscilaciones mecánicas, circuitos eléctricos RLC, estructuras con amortiguamiento, y sistemas de temperatura o presión. La dinámica de estos sistemas está gobernada por ecuaciones diferenciales de segundo orden, que pueden analizarse eficientemente mediante su representación en el dominio de Laplace. Esta clase busca explorar detalladamente el comportamiento de estos sistemas, sus características temporales, sus respuestas típicas y cómo se interpretan en el plano complejo.


## 1. Subtítulos

1.1 Introducción a los sistemas de segundo orden

1.2 Función de transferencia estándar

1.3 Parámetros dinámicos: frecuencia natural y factor de amortiguamiento

1.4 Respuesta al escalón unitario

1.5 Clasificación según el amortiguamiento

1.6 Análisis en el planos

1.7 Cálculo del tiempo pico, sobre impulso, y tiempo de establecimiento

1.8 Sistemas con retardo (tiempo muerto)

## 2. Definiciones
🔑 Sistema de segundo orden: sistema cuya ecuación diferencial característica contiene una derivada de segundo orden, y su comportamiento se describe mediante una función de transferencia cuadrática.

🔑 Frecuencia natural ($\omega_n$): frecuencia en radianes por segundo a la que un sistema oscilaría si no existiera amortiguamiento.

🔑 Factor de amortiguamiento ($\zeta$): número adimensional que representa la cantidad de disipación de energía en el sistema.

🔑 Sobreimpulso ($M_p$): máxima desviación porcentual del valor final, causada por la oscilación de la respuesta.

🔑 Tiempo de establecimiento ($T_s$): tiempo requerido para que la respuesta permanezca dentro de un margen (generalmente 2%) alrededor del valor final.

🔑 Tiempo pico ($T_p$): instante en que la respuesta alcanza su valor máximo.

🔑 Tiempo muerto ($T_d$): retardo temporal entre la aplicación de la entrada y el inicio visible de la respuesta del sistema.

## 3. Subsecciones

### 3.1. Función de transferencia estándar
La forma canónica de un sistema de segundo orden es:

$$G(s)=\frac{w_{n}^{2}}{s^{2}+2\zeta w_{n}+w_{n}^{2}}$$

Esta expresión representa el cociente entre la salida y la entrada en el dominio de Laplace, bajo condiciones iniciales nulas.

### 3.2. Clasificación según $\zeta$
$\zeta > 1$: Sobreamortiguado (respuesta lenta, sin oscilaciones)

$\zeta = 1$: Críticamente amortiguado (tiempo mínimo sin oscilaciones)

$0 < \zeta < 1$: Subamortiguado (oscilación con atenuación)

$\zeta = 0$: No amortiguado (oscilación pura, sin atenuación)

### 3.3. Parámetros característicos de desempeño
Frecuencia natural ($\omega_n$): determina la rapidez del sistema.

Frecuencia amortiguada ($\omega_d$): $\omega_d = \omega_n \sqrt{1 - \zeta^2}$

Tiempo pico ($T_p$): $\frac{\pi}{\omega_d}$

Sobreimpulso ($M_p$): $100\cdot e^{\left(-\frac{\pi \zeta}{\sqrt{1 - \zeta^2}}\right)}%$

Tiempo de establecimiento ($T_s$): $\frac{4}{\zeta \omega_n}$

### 3.4. Tiempo muerto (retardo)
Un sistema con retardo se representa como:

$$G(s)=G_{0}(s).e^{-T\Delta s}$$

Donde $G_0(s)$ es la función de transferencia sin retardo y $T_d$ es el tiempo muerto.

## 4. Ejemplos
💡 Ejemplo 1: Determinar parámetros del sistema

Dada la función de transferencia:

$$G(s)=\frac{25}{s^{2}+6s+25}$$

Comparando con la forma estándar:

$2\xi w_{n}=6$ y $w_{n}^{2}=25$

Se obtiene:

$w_{n}=5$, $\zeta =\frac{6}{2.5}=0.6$

Cálculo de otros parámetros:

$\omega_d = 5\sqrt{1 - 0.36} = 4$

$T_p = \frac{\pi}{\omega_d} = 0.785$ s

$T_s = \frac{4}{\zeta\omega_n} = 1.33$ s

$M_p = 16.3%$

💡 Ejemplo 2: Sistema con retardo

Dado un sistema con retardo:

$$G(s)=\frac{10}{s^{2}+3s+10}e^{-2s}$$

Identificamos:

$\omega_n = \sqrt{10} \approx 3.16$

$2\zeta\omega_n = 3 \Rightarrow \zeta = 0.474$

$T_d = 2$ s

Este retardo causa un desplazamiento temporal de la respuesta sin cambiar la forma de la curva.

## 5. Ecuaciones

💡Función de transferencia estándar:

$$G(s)=\frac{w_{n}^{2}}{s^{2}+2\zeta w_{n}s+w_{n}^{2}}$$

💡Frecuencia amortiguada:

$$w_{d}=w_{n}\sqrt{1-\zeta ^{2}}$$

💡Tiempo pico:

$$T_{p}=\frac{\Pi }{w_{n}\sqrt{1-\zeta ^{2}}}$$

💡Sobre impulso:

$$M_{p}=e-(\frac{\Pi }{\sqrt{1-\zeta ^{2}}})*100%$$

💡Tiempo de establecimiento:

$$T_{s}=\frac{4}{\zeta w_{n}}$$


## 6. figuras

💡Variación del Factor de Amortiguamiento
Veamos la dinámica de sistemas de segundo orden ante la variación del factor de amortiguamiento:

![figura1](f1a.png)

💡Variación de la Frecuencia Natural No Amortiguada

![figura2](f2a.png)

## 7. Tablas
💡 Tabla 1: Efecto del factor de amortiguamiento


| **$\zeta$** | **Tipo de respuesta** |**Comportamiento** |
|-------------|-----------------------|------------------|
|      0      | Oscilatorio puro      |Oscila indefinidamente|
|       0 < $\zeta$ < 1    |  Subamortiguado  |Oscila y se estabiliza|
|      1      |     Criticamente amortiguado  |Sin oscilaciones, rápida estabilización|
|    > 1     |      sobreamortiguado   |Lenta estabilización sin oscilaciones |




## 8. Código
💡 Simulación con Python:
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import lti, step

# Parámetros
wn = 5
zeta = 0.6
sys = lti([wn**2], [1, 2*zeta*wn, wn**2])
t, y = step(sys)

# Gráfica
plt.plot(t, y, label=f'zeta = {zeta}')
plt.axhline(1, color='gray', linestyle='--')
plt.title('Respuesta al escalón - Sistema de Segundo Orden')
plt.xlabel('Tiempo (s)')
plt.ylabel('Salida')
plt.grid(True)
plt.legend()
plt.show()
```

## 9. Ejercicios:

📚 Ejercicio 1

Planteamiento: Dada la función:

$$G(s)=\frac{36}{s^{2}+12s+36}$$

Solución:

$\omega_n = 6$, $2\zeta\omega_n = 12$ $\Rightarrow \zeta = 1$

Es un sistema críticamente amortiguado

$T_s = \frac{4}{\zeta \omega_n} = \frac{4}{6} = 0.67$ s

No hay sobreimpulso

📚 Ejercicio 2

Planteamiento: Calcular $T_p$ y $M_p$ para:

$$G(s)=\frac{9}{s^{2}+3s+9}$$

Solución:

$\omega_n = 3$, $\zeta = 0.5$

$T_p = \frac{\pi}{3\sqrt{1 - 0.25}} = 1.21$ s

$M_p = e^{-\pi \cdot 0.5 / \sqrt{1 - 0.25}} \cdot 100% \approx 16.3%$


## 10. Conclusiones

Los sistemas de segundo orden se caracterizan completamente por $\zeta$ y $\omega_n$.

La posición de polos en el plano complejo permite predecir la respuesta.

Es fundamental distinguir entre amortiguamiento bajo, crítico y alto para interpretar la respuesta correctamente.

El retardo (tiempo muerto) es crucial para el control y puede afectar la estabilidad.

## 11. Referencias

Apuntes de clase: Sistemas de segundo orden.

Dorf, R. & Bishop, R. (2011). Modern Control Systems.

Ogata, K. (2010). Ingeniería de Control Moderna.

Python con SciPy y Matplotlib para simulaciones.

https://controlautomaticoeducacion.com/control-realimentado/sistemas-de-segundo-orden/
