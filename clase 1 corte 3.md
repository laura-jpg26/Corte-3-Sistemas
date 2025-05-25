# SISTEMAS DINAMICOS HIDRAULICO

> Los sistemas dinámicos son modelos matemáticos que describen cómo cambian las variables de un sistema a lo largo del tiempo. Estos sistemas pueden representarse mediante ecuaciones diferenciales o en forma discreta, y se utilizan para analizar el comportamiento de fenómenos en disciplinas como la física, la ingeniería, la biología y la economía. Un sistema dinámico puede ser lineal o no lineal, y su estudio permite predecir la evolución del sistema, analizar su estabilidad y entender su respuesta ante diferentes condiciones iniciales o entradas externas.

## 1. QUE ES UN SISTEMA HIDRAULICO DINAMICO:

Un sistema dinámico hidráulico es un sistema físico en el que el comportamiento dinámico del fluido (como agua o aceite) se describe mediante variables que cambian en el tiempo, como la presión, el caudal y el volumen. Estos sistemas suelen modelarse con ecuaciones diferenciales que representan la relación entre las entradas (como una válvula que se abre) y las salidas (como el caudal o la presión en una tubería).

Ejemplos comunes incluyen tanques conectados por tuberías, sistemas de frenos hidráulicos y servomecanismos hidráulicos. Al igual que en sistemas eléctricos o mecánicos, se pueden analizar propiedades como la estabilidad, la respuesta transitoria y el régimen permanente.

## 2 SISTEMA DE TANQUES:

En los sistemas industriales que utilizan tanques, como los procesos de almacenamiento, mezcla o transporte de líquidos, es fundamental mantener constante el nivel del fluido o el flujo de salida. Esto se debe a que variaciones en estos parámetros pueden afectar la calidad del producto, la eficiencia del proceso o incluso la seguridad de la operación. Por esta razón, se implementan sistemas de control automático que regulan el nivel o flujo mediante el ajuste de válvulas, bombas u otras variables de entrada.

## 2.1 GRAFICO DE TANQUES:

![image](https://github.com/user-attachments/assets/2ad94da7-7382-41c5-8ec9-a4a5eb197283)

Donde:
qi= flujo de entrada
qo = flujo de salida 
R1 = Resistencia del flujo
A1 = Area del tanque
h1 = altura del tanque

## 2.2 FORMULAS:

Flujo de salida de tanque

$q1=\frac{h1}{R1}$

Intercambio de masa

$A1\frac{dh1}{dt}=qi-q1$

## 3 MODELO q1 como entrada y h1 como salida:

Lo ideal aqui es relacionar las ecuaciones anteriores para buscar la ecuacion segun la solicitud del ejercicio

Lo harenos de la siguiente manera:

teniendo las siguientes ecuaciones:

$q1=\frac{h1}{R1}$................. $A1\frac{dh1}{dt}=qi-q1$

Reemplazamos 1 en 2 de la siguiente manera:

$A1\frac{dh1}{dt}=\frac{h1}{R1}-q1$

o despejamos h1 de la ecucacion 1 y reemplazamos en la ecuacion 2:

$h1=q1*R1$

$R1*A1\frac{dq1}{dt}=qi-q1$

## 4 Ejemplo 1:

![image](https://github.com/user-attachments/assets/bae75e7c-5f23-412e-979f-8cc1f46e2b07)

Teniendo en cuenta las ecuaciones de previamiente vistas, plnteamos las ecuaciones para los dos tanques:

$q1=\frac{h1}{R1}$................. $A1\frac{dh1}{dt}=qi-q1$

$q2=\frac{h2}{R2}$................. $A2\frac{dh1}{dt}=q1-q2$

para el primer tanque despejamos h1 en la ecuacion 1 y lo reemplazamos en la ecuacion 2 

$h1=q1*R1$

$R1A1\frac{dq1}{dt}=qi-q1$

para el segundo tanque reemplazamos q2 en la ecuacion 2 de la siguiente manera:

$A2\frac{dh2}{dt}=q1-\frac{h2}{R2}$

Despejamos q1 de esta ultima ecuacion de la siguiente manera:

$q1=A2\frac{dh2}{dt}+\frac{h2}{R2}$

ahora derivamos esta ecuacion para reemplazarlo en la euacion de arriba: 

$\frac{dq1}{dt}=A2\frac{d^{2}h2}{dt^{2}}&plus;\frac{dh2}{dt}\frac{1}{R2}$

La Solucion para este ejercicio es la siguiente:

esta ultima ecuacion la reemplazamos arriba:

$R1A1(A2\frac{d^{2}h2}{dt^{2}}&plus;\frac{dh2}{dt}\frac{1}{R2})=qi-A2\frac{dh2}{dt}+\frac{h2}{R2}$

## 5. EJERCICIO 2 

Tanques interconectados 

Para este tipo de ejercicios veremos dos tanques al mismo nivel 

Del siguiente ejercicio desarrollar el modelo con h2 como salida

![image](https://github.com/user-attachments/assets/ab33017f-b7a5-418f-b2a5-8c3112a609f1)

$q_{1}=\frac{h_{1}-h_{2}}{R_{1}}$

$A_{1}\frac{dh_{1}}{dt}=(qi-q_{1})$

$h_{1}=q_{1}R_{1}+h_{2}$

$h_{1}=(\frac{A_{2}dh_{2}}{dt}+\frac{h_{2}}{R_{2}})R_{1}+h_{2}$

$q_{2}=\frac{h_{2}}{R_{2}}$

$A_{2}\frac{dh_{2}}{dt}=(q_{1}-q_{2})$

$A_{2}\frac{dh_{2}}{dt}=(q_{1}-\frac{h_{2}}{R_{2}})$

$q_{1}=A_{2}\frac{dh_{2}}{dt}+\frac{h_{2}}{R_{2}}$

$h_{1}=A_{2}R_{1}\frac{dh_{2}}{dt}+\frac{R_{1}h_{2}}{R_{2}}+h_{2}$

$\frac{dh_{1}}{dt}=A_{2}R_{1}\frac{d^{2}h_{2}}{dt^{2}}+\frac{R_{1}}{R_{2}}\frac{dh_{2}}{dt}+\frac{dh_{2}}{dt}$

$A_{1}A_{2}R_{1}\frac{d^{2}h_{2}}{dt^{2}}+\frac{A_{1}R_{1}}{R_{2}}\frac{dh_{2}}{dt}+A_{1}\frac{dh_{2}}{dt}=qi-A_{2}\frac{dh_{2}}{dt}-\frac{h_{2}}{R_{2}}$



## 6. EJERCICIO 1 PROPUESTO:

Tenemos dos tanques conectados en serie. El primero recibe un caudal de entrada qi=(t) y el fluido sale por una resistencia R1 segundo tanque. Luego, el segundo tanque descarga por otra resistencia R2

Variables:

h1 y h2: altura del fluido en los tanques 
A1y A2: areas de los tanques 
R1 y R2: resistencias de las salidas de los tanques
$q1=\frac{h1}{R1}$ caudal entre los tanques
$q2=\frac{h2}{R2}$ caudal de salida

ahora: 

$q_1 = \frac{h_1}{R_1} \qquad A_1 \frac{dh_1}{dt} = q_i - q_1$

$q_2 = \frac{h_2}{R_2} \qquad A_2 \frac{dh_2}{dt} = q_1 - q_2$

despejamos h1 en la primera eecuacion:

$h_1 = q_1 \cdot R_1$

Sustituimos en la ecuación del primer tanque:

$R_1 A_1 \frac{dq_1}{dt} = q_i - q_1$

sustituimos q2 en la ecuacion del segundo tanque:

$A_2 \frac{dh_2}{dt} = q_1 - \frac{h_2}{R_2}$

despejamos q1

$q_1 = A_2 \frac{dh_2}{dt} + \frac{h_2}{R_2}$

Derivamos para obtener q1 para obtener:

$\frac{dq_1}{dt} = A_2 \frac{d^2 h_2}{dt^2} + \frac{1}{R_2} \frac{dh_2}{dt}$

Sustituimos en la ecuación del primer tanque:

$R_1 A_1 \left( A_2 \frac{d^2 h_2}{dt^2} + \frac{1}{R_2} \frac{dh_2}{dt} \right)$
$= q_i - \left( A_2 \frac{dh_2}{dt} + \frac{h_2}{R_2} \right)$

## 7. EJERCICIO 2 PROPUESTO

Supongamos que tenemos dos tanques conectados por un tubo. El flujo de entrada es constante en el primer tanque, y el flujo de salida en ambos tanques depende de la altura en cada uno de ellos. Las ecuaciones para este sistema son:

![image](https://github.com/user-attachments/assets/206853b8-9154-4315-a3bd-0b88095b467d)

$\textbf{Supongamos un sistema de dos tanques con las siguientes condiciones:}$

$\text{Flujo de entrada constante:} \quad q_{\text{in}}$

$\text{Flujos de salida:} \quad q_1 = k_1 h_1, \quad q_2 = k_2 h_2$

$\text{Ecuaciones:}$

$\text{Primer tanque:} \quad A_1 \frac{dh_1}{dt} = q_{\text{in}} - k_1 h_1$

$\text{Segundo tanque:} \quad A_2 \frac{dh_2}{dt} = k_1 h_1 - k_2 h_2$

$\textbf{Despejamos } h_1 \text{ de la primera ecuación:}$

$h_1 = \frac{q_{\text{in}}}{k_1} - \frac{1}{k_1} \cdot \frac{dh_1}{dt}$

$\textbf{Sustituimos en la ecuación del segundo tanque:}$

$A_2 \frac{dh_2}{dt} = k_1 \left( \frac{q_{\text{in}}}{k_1} - \frac{1}{k_1} \frac{dh_1}{dt} \right) - k_2 h_2$

$\text{Ecuación final:}$

$A_2 \frac{dh_2}{dt} = q_{\text{in}} - \frac{dh_1}{dt} - k_2 h_2$


## 8. RESUMEN

Un sistema hidráulico es un conjunto de elementos interconectados que manejan fluidos (generalmente agua) para realizar trabajos, como controlar el flujo, transportar o almacenar fluidos. Estos sistemas son fundamentales en ingeniería, especialmente en procesos industriales, construcción, y tratamiento de agua.

## 9. CONCLUSIONES 

Los sistemas dinámicos hidráulicos se modelan a partir de la conservación de masa en tanques conectados, asumiendo una relación lineal entre flujo y altura, lo que genera ecuaciones diferenciales acopladas que, gracias a su analogía con circuitos eléctricos, permiten predecir la respuesta transitoria y permanente del sistema y diseñar controladores eficientes en aplicaciones industriales y de tratamiento de agua.

## 10. REFERENCIAS

Clase presencia universidad ECCI
