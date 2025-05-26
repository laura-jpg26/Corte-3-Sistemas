# Clase: Análisis de Sistemas en Lazo y Diagrama de Flujo de Señales
En esta clase se abordó el análisis de sistemas representados por diagramas de bloques y diagramas de flujo de señales. Se analizaron diferentes trayectorias en diagramas complejos, se calcularon funciones de transferencia aplicando la regla de Mason y se redujeron estructuras en lazos. Este tema es fundamental en el estudio de sistemas de control, donde se busca determinar la relación entrada-salida de sistemas lineales.
## 1. Subtítulos

1.1 Definición y utilidad del diagrama de flujo de señales

1.2 Caminos hacia adelante (Paths)

1.3 Lazos individuales y lazos no tocados

1.4 Aplicación de la regla de Mason

1.5 Reducción de sistemas con retroalimentación

## 2. Definiciones
🔑 Camino hacia adelante: Es una ruta desde la entrada a la salida sin pasar dos veces por el mismo nodo.

🔑 Lazo: Cualquier ruta cerrada en el grafo donde se regresa al mismo nodo inicial sin repetir nodos.

🔑 Lazos no tocados: Lazos que no comparten nodos entre sí.

🔑 Determinante de Mason ($\Delta$): Valor que se usa para calcular la función de transferencia total del sistema.

## 9. Ejercicios
📚Ejemplo 1: Cálculo de la función de transferencia con Mason: haga este sistema:

![solucion1](solucionclase1.png)

📌 Paso 1: Identificar trayectorias hacia adelante
Analizamos los caminos desde la entrada hasta la salida:

$P_1$: $1 \to 2 \to 3 \to \text{Salida}$

Ganancia: $1 \cdot 1 \cdot (-1) = -1$

$P_2$: $1 \to 3 \to \text{Salida}$

Ganancia: $-14 \cdot (-1) = 14$

📌 Paso 2: Identificar los lazos individuales
Los lazos (loops) cerrados son:

$L_1$: $3 \to 3$ con ganancia: $-1/4$

$L_2$: $1 \to 3 \to 1$ con ganancia: $(-14) \cdot (-0.2) = 2.8$

$L_3$: $1 \to 3 \to 1$ (vía otro camino) con ganancia: $(-0.25)(-0.2) = 0.05$

📌 Paso 3: Identificar lazos no tocantes
No hay lazos que no se crucen entre sí (todos comparten nodos). Entonces:

$\Delta = 1 - (\text{suma de las ganancias de lazos})$

$$ \Delta =1-\left [ (-\frac{1}{4})+2.8+0.05 \right ]=1-2.6=-1.85$$

📌 Paso 4: Calcular $\Delta_k$ para cada trayectoria
Ya que cada trayectoria toca al menos un lazo, entonces:

$\Delta_1 = \Delta_2 = 1$

📌 Paso 5: Aplicar la fórmula de Mason
La fórmula es:

$$H(s)=\frac{\sum _{k}P_{k}\Delta _{k}}{\Delta }$$

Sustituyendo:

$$H(s)=\frac{(-1)(1)+(14)(1)}{-1.85}=\frac{13}{-1.85}=-7.03$$

Resultado final:

$$H(s)=−7.03$$


💡 Simulación con Python:
```
from sympy import symbols, simplify

# Variables
P1 = -1
P2 = 14

# Determinantes
Delta = 1 - ((-1/4) + 2.8 + 0.05)  # L1 + L2 + L3
Delta1 = 1
Delta2 = 1

# Mason's Formula
H = (P1*Delta1 + P2*Delta2) / Delta

# Resultado
print("H(s) =", simplify(H))
```

📚 Ejercicio 2

Calcular la función de transferencia del siguiente sistema en lazo cerrado:

![solucion2](solucionclase2.png)

Objetivo:
Obtener la función de transferencia del sistema:

$$T(s) = \frac{Y(s)}{R(s)}$$

Paso 1: Identificar los bloques del sistema
Bloques en serie (adelante):

Primer bloque:

$G_1(s) = \frac{10}{s+1}$

Segundo bloque:

$G_2(s) = \frac{30s}{s^2 + 2s + 3}$

Entonces:

$G(s) = G_1(s) \cdot G_2(s) = \frac{10}{s+1} \cdot \frac{30s}{s^2 + 2s + 3} = \frac{300s}{(s+1)(s^2 + 2s + 3)}$

Camino de retroalimentación (feedback):

$H(s) = \frac{1}{\frac{s+1}{s^2 + 2s + 3}} = \frac{s^2 + 2s + 3}{s+1}$

Paso 2: Aplicar fórmula de sistema en lazo cerrado
La fórmula general para retroalimentación negativa es:

$T(s) = \frac{G(s)}{1 + G(s)H(s)}$

Sustituimos $G(s)$ y $H(s)$:

Paso 2.1: Calcular $G(s)H(s)$

$G(s)H(s) = \left(\frac{300s}{(s+1)(s^2 + 2s + 3)}\right) \cdot \left(\frac{s^2 + 2s + 3}{s+1}\right) = \frac{300s}{(s+1)^2}$

Paso 3: Sustituir en la ecuación

$T(s) = \frac{\frac{300s}{(s+1)(s^2 + 2s + 3)}}{1 + \frac{300s}{(s+1)^2}}$

Multiplicamos numerador y denominador por $(s+1)^2$:

Numerador:

$\frac{300s(s+1)}{(s+1)^2 (s^2 + 2s + 3)}$

Denominador:

$1 + \frac{300s}{(s+1)^2} = \frac{(s+1)^2 + 300s}{(s+1)^2}$

Resultado final

$$T(s) = \frac{300s(s+1)}{[(s+1)^2 (s^2 + 2s + 3)] + 300s(s^2 + 2s + 3)}$$

## 10. Conclusiones

La regla de Mason es una herramienta poderosa para calcular la función de transferencia sin necesidad de reducir manualmente los diagramas.

Los lazos no tocados afectan el determinante $\Delta$, permitiendo mejorar la precisión del resultado.

En sistemas de bloques, conocer las configuraciones básicas como serie, paralelo y retroalimentación simplifica los cálculos.

## 11. Referencias

Apuntes de clase: Diagramas de flujo de señales y bloque

Ogata, K. Ingeniería de control moderna

Dorf, R. & Bishop, R. Modern Control Systems




