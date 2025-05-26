# FUNCION DE TRANSFERENCIA

> La función de transferencia es una herramienta matemática que describe cómo un sistema lineal e invariante en el tiempo responde a una entrada, en el dominio de Laplace.

$$G(S)=\frac{Y(S)}{U(S)}$$

## 1. ALGEBRA DE BLOQUES 

> La álgebra de bloques es un conjunto de reglas usadas para simplificar y manipular diagramas de bloques en sistemas de control o modelado de sistemas dinámicos. Los diagramas de bloques representan visualmente cómo se conectan las funciones de transferencia entre entradas y salidas mediante bloques funcionales.

## 2. QUE ES UN BLOQUE

Un bloque representa una función de transferencia 𝐺(𝑠), que relaciona una señal de entrada 𝑈(𝑠) con una de salida 𝑌(𝑠):

$$Y(S)=G(S)*U(S)$$

Donde:

* 𝑌(𝑠): Transformada de Laplace de la salida

* 𝑈(𝑠): Transformada de Laplace de la entrada

* 𝑠: Variable de Laplace (𝑠=𝜎+𝑗𝜔)

Condiciones iniciales nulas (se asume que todo empieza desde reposo)

## 3. PARA QUE SIRVE:

* Analizar el comportamiento dinámico del sistema

* Calcular la respuesta a entradas estándar (escalón, impulso, seno)

* Estudiar la estabilidad, amortiguamiento y resonancia

* Diseñar controladores automáticos

* Facilitar el uso de diagramas de bloques

## 4. ELEMENTOS BASICOS DE ALGEBRA DE BLOQUES

## 4.1 AGRUPACION SERIE O EN CASCADA

![image](https://github.com/user-attachments/assets/41cd7e76-7393-42c6-a70b-a6f447002427)

## 4.2 AGRUPACION EN PARALELO O EN DESVIACION

![image](https://github.com/user-attachments/assets/dda5d1cf-4cb5-40be-98e5-5a29fe48fb40)

## 4.3 BUCLE DE RETROALIMENTACION NEGATIVA

![image](https://github.com/user-attachments/assets/90290c70-0cd4-4622-8de3-55c796cc5230)

## 4.4 BUCLE RETROALIMENCACION POSITIVA

![image](https://github.com/user-attachments/assets/3ede3cd5-7dcc-4111-8596-5c54c9c1d176)

## 4.5 BUCLE RETROALIMENCACION DIRECTA NEGATIVA

![image](https://github.com/user-attachments/assets/75f5dbf9-4a94-4a2f-a73e-85081eeb32a1)

## 4.6 BUCLE RETROALIMENCACION DIRECTA POSITIVA

![image](https://github.com/user-attachments/assets/5a5e0b9c-2a34-4626-945d-c43e5b376a21)

## 4.7 SUMADOR PARALELO

![image](https://github.com/user-attachments/assets/4b33e3a9-3a42-452f-becc-d9c48271bd61)

## 4.8 RESTADOR PARALELO

![image](https://github.com/user-attachments/assets/b3a3c405-0478-4ee6-a1a5-5a2c9b8f9b48)

## 4.9 CAMBIO DE POSICION

![image](https://github.com/user-attachments/assets/6d83488b-c585-482e-b58a-1a61c172659b)

## 4.10 TRANSPOSICION DE UN SUMADOR A LA IZQUIERDA DE UN BLOQUE

![image](https://github.com/user-attachments/assets/e3d96ade-1d42-4f3e-afdd-ba345c395554)

## 4.11 TRANSPOSICION DE UN SUMADOR A LA DERECHA DE UN BLOQUE

![image](https://github.com/user-attachments/assets/e6d8956b-347d-460d-9b11-759f3adef13e)

## 4.12 TRANSPONER UNA BIRFURCACION A LA IZQUIERDA DE UN BLOQUE

![image](https://github.com/user-attachments/assets/2280d133-36cd-48c7-8b3b-0e0c7e14617a)

## 4.13 TRANSPOSICION DE UN SUMADOR A LA DERECHA DE UN BLOQUE

![image](https://github.com/user-attachments/assets/8145e5b1-421a-4eae-826f-c118f0fc5ab4)

## 5. CONSIDERACIONES:

* SISO: UNA ENTRADA UNA SALIDA
* MISO: MULTIPLE ENTRADA UNA SALIDA
* SIMO: UNA ENTRADA MULTIPLE SALIDA
* MIMO: MULTIPLE ENTRADA MULTIPLE SALIDA

## 6. EJEMPLOS DE CLASE:

# 6.1 EJEMPLOS 1

![image](https://github.com/user-attachments/assets/e6d18017-d681-42c7-abbd-45eefa8b0f43)

# 6.1 EJEMPLOS 2

![image](https://github.com/user-attachments/assets/1bb6fe89-6c1b-4e8f-a01a-63d7cb71f295)

## 7. EJEMPLOS PROPUESTOS:

# 7.1 EJEMPLO PROPUESTO 1:

![image](https://github.com/user-attachments/assets/0c339ddc-66a1-4a21-b4a4-0bd819ed2b81)

![image](https://github.com/user-attachments/assets/611b208a-8f01-476a-b4dc-66e165c69e25)

![image](https://github.com/user-attachments/assets/d500c94d-09f8-4419-b699-7636da950d7d)

![image](https://github.com/user-attachments/assets/f626d752-badc-4fed-9df9-fe0d49692566)

![image](https://github.com/user-attachments/assets/5c9f4097-4673-4389-b6b8-abc6a470e776)

# 7.2 EJEMPLO PROPUESTO 2:

![image](https://github.com/user-attachments/assets/ff889b41-e4d5-4c35-a4d7-d9c9a312a429)

![image](https://github.com/user-attachments/assets/e7b70b48-f59a-40bd-9daf-81b880ba93af)

![image](https://github.com/user-attachments/assets/cd2dd544-a359-4c23-9662-2304b91b21c7)

![image](https://github.com/user-attachments/assets/fef1bfdd-964a-4ef6-8dbb-080f567e0f09)

![image](https://github.com/user-attachments/assets/4d13d59a-8cc4-483a-ad09-1abe42f5e236)

![image](https://github.com/user-attachments/assets/0a2ad196-fbe7-4bcd-b3fe-55b0ca859645)

## 8. CONCLUSIONES:

El álgebra de bloques es fundamental en el análisis y diseño de sistemas de control. A continuación, se resumen las principales conclusiones:

## 8.1 Facilita el análisis de sistemas complejos

* Permite representar sistemas dinámicos de forma gráfica y modular.

* Cada componente del sistema se representa por su función de transferencia.

## 8.2 Permite obtener la función de transferencia total

* Usando las reglas del álgebra de bloques, podemos simplificar un sistema completo a un solo bloque equivalente.

* Esto facilita el estudio del comportamiento del sistema ante cualquier entrada.

## 8.3 Se basa en operaciones simples

* Serie → multiplicación de funciones de transferencia.

* Paralelo → suma de funciones.

* Realimentación → fórmulas específicas que dependen del tipo de lazo (positivo o negativo).

## 8.4 Aplica solo a sistemas lineales e invariantes en el tiempo

Una vez obtenida la función de transferencia total, se puede:

* Analizar la estabilidad.

* Determinar la respuesta temporal y en frecuencia.

* Diseñar controladores (como PID, lead-lag, etc.).

## 8.5 Permite usar software de simulación

Herramientas como MATLAB/Simulink se basan en diagramas de bloques para modelar y simular sistemas.

## 9. RESUMEN:

> El álgebra de bloques es una herramienta poderosa, intuitiva y sistemática que simplifica el estudio de sistemas dinámicos complejos, ayudando a representar, reducir y analizar su comportamiento mediante funciones de transferencia.

## 10. REFERENCIAS:

* CLASE PRACTICA PROFESOR JORGE COTE



