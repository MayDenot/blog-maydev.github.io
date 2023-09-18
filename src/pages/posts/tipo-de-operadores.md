---
title: "Tipos de operadores en programación"
layout: "../../layouts/BlogPostLayout.astro"
author: "Mayra Denot"
date: "18/09/23"
---

<section class="oper-art">

# Tipos de operadores en 
# programación 🧮

18/09/23

### <a id="10"></a> Operadores aritméticos

Los operadores aritméticos a diferencia de los otros que veremos, nos devolverán 
como resultado un número. Muchos de estos operadores les resultaran obvios o conocidos,
ya que se encuentran en las calculadoras y/o los utilizan cotidianamente.

| Operador       | Símbolo | Acción                                                       |
| -------------- | :-----: | ------------------------------------------------------------ |
| Suma           |    +    | Suma dos operandos.                                          |
| Resta          |    -    | Resta el segundo operando del primero.                       |
| División       |    /    | Divide el primero operando por el segundo.                   |
| Multiplicación |    *    | Multiplica dos operandos.                                    |
| Resto (Módulo) |    %    | Calcula el resto después de dividir el primer operando por el segundo (residuo de la división).                                                                 |
| Exponenciación |   **    | Eleva el primer operando al segundo.                         |
| Negación       |    -    | Se coloca antes de un operando para indicar que es negativo. |
| Incremento     |   ++    | Incrementa al valor colocado una unidad.                     |
| Decremento     |   --    | Decrementa al valor colocado una unidad.                     |


### <a id="11"></a> Operadores relacionales

Los operadores relacionales comparan el primer operando con el segundo y si el resultado de la expresión es correcta retorna true (verdadero, 1) y en caso contrario falso (false, 0).

![Operadores relacionales](/assets/OperadoresRelacionalesGrafico.jpg)

| Operador          | Símbolo | Acción                          |
| ----------------- | :-----: | ------------------------------- |
| Mayor que         |    >    | 5 > 2 TRUE  <br> 10 > 20 FALSE  |
| Menor que         |    <    | 5 < 10 TRUE  <br> 10 < 4 FALSE  |
| Mayor o igual que |    >=   | 5 >= 5 TRUE  <br> 7 >= 8 FALSE  |
| Menor o igual que |    <=   | 9 <= 9 TRUE  <br> 9 <= 2 FALSE  |
| Distinto          |    !=   | 9 != 10 TRUE <br>  6 != 6 FALSE |
| Igual             |    ==   | 9 == 9 TRUE <br> 2 == 3 FALSE   |

### <a id="12"></a> Operadores lógicos

Los operadores lógicos comparan valores booleanos, es decir verdadero y falso, y retornan como resultado un valor booleano. 

| Operador   | Símbolo | Acción                                                         |
| ---------- | :-----: | -------------------------------------------------------------- |
| AND        |   &&    | Verdadero sólo si las dos condiciones son verdaderas.          |
| OR         |  \|\|   | Verdadero si cualquiera de las dos condiciones son verdaderas. |
| NOT        |   !     | Cambia la condición de Falso a Verdadero y viceversa.          |

<br>

Ejemplo:

![Operadores Lógicos](/assets/OperadoresLogicos.jpg)

### <a id="14"></a> Combinaciones entre sí

A los operadores lógicos y relacionales los podemos combinar entre sí, de hecho en el ejemplo de los operadores lógicos lo hicimos.

Aquí dejo algunos ejemplos más:

![Operadores combinados ejemplo 1](/assets/Ejemplo1.jpg)
![Operadores combinados ejemplo 2](/assets/Ejemplo2.jpg)
![Operadores combinados ejemplo 3](/assets/Ejemplo3.jpg)

</section>