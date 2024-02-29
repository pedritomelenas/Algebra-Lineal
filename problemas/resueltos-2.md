---
layout: page
title: Problemas espacios vectoriales
tag: problemas
---
<style>
@media (min-width: 38em) {
  html {
    font-size: 18px;
  }
}

.container {
    max-width: 56rem;
    }
    @media (min-width: 38em) {
    .container {
        max-width: 38rem;
    }
    }
    @media (min-width: 56em) {
    .container {
        max-width: 56rem;
    }
}


body {
  counter-reset: article;
}

article:before {
  counter-increment: article;
  content: "Ejercicio " counter(article) ". ";
  font-weight: bold;
}

article {
  border-style: solid;
  border-width: 1px 1px 1px 5px;
  border-color: gray gray gray gray;
  border-radius: 5px;
  padding: 0.5em 0.5em 0em 0.5em;
  margin-bottom: 0.5em;
}
</style>

# Espacios vectoriales

Los ejercicios aquí mostrados han sido amablemente proporcionados por [Evangelina Santos](https://www.ugr.es/~esantos/) y maquetados por [Juan Rivas](https://github.com/MrRiversGit).

## Ejercicios resueltos 

<article>

En $\mathbb{R}^4$ se considera el conjunto 
$$
\{(b,0,a,b),(0,a,1+a,0),(0,1,1+a,0),(0,1+a,2+2a,1-a)\}.
$$
¿Cuál es el número máximo de vectores linealmente independientes que puede contener dicho conjunto, según los valores de a y b?

<details>
<summary>Solución</summary>

Para determinar si los vectores son linealmente independientes o linealmente dependientes construimos la matriz cuyas columnas son esos vectores, a continuación calculamos su rango y lo comparamos con el número de vectores. Se tiene que los vectores son linealmente independientes si y sólo si $\operatorname{rg}(A)$ es máximo (coincide con el número de vectores) y en otro caso son linealmente dependientes.<br>

La matriz que se forma es:

$$A=\left( \begin{array}{cccc}
b & 0 & 0 & 0\\
0 & a & 1 & 1+a\\
a & 1+a& 1+a & 2+2a\\
b & 0 & 0 & 1-a
\end{array}\right).$$

Puesto que es cuadrada de orden cuatro, entonces tendrá rango cuatro exactamente cuando el determinante sea distinto de cero. Lo calculamos:

$$|A|=\left| \begin{array}{cccc}
b & 0 & 0 & 0\\
0 & a & 1 & 1+a\\
a & 1+a& 1+a & 2+2a\\
b & 0 & 0 & 1-a
\end{array}\right|= \left| \begin{array}{cccc}
b & 0 & 0 & 0\\
0 & a-1 & 1 & 1+a\\
a & 0 & 1+a & 2+2a\\
b & 0 & 0 & 1-a
\end{array}\right|= b(a-1)(1+a)(1-a).$$

Luego si $b\not = 0$ y $a\not\in\{-1,1\}$, el rango es cuatro y los vectores son linealmente independientes.

Para estudiar todos los casos podemos representarlos en una tabla de doble entrada e iremos calculando cada uno de ellos.
El primero que completamos es el caso que acabamos de obtener, si $b\not = 0, a\not = \pm 1$ el rango es cuatro. En los demás uno o los dos parámetros toman valores concretos, por lo que es más fácil su estudio. La solución es:

<table border="1">
  <tr>
    <td></td>
    <td>$a=1$</td>
    <td>$a=-1$</td>
    <td>$a\not = \pm 1$</td>
  </tr>
  <tr>
    <td>$b=0$</td>
    <td>rango 2</td>
    <td>rango 3</td>
    <td>rango 3</td>
  </tr>
  <tr>
    <td>$b\not =0$</td>
    <td>rango 2</td>
    <td>rango 3</td>
    <td>rango 4</td>
  </tr>
</table>

Veamos por ejemplo el caso $b\not = 0, a=1$:
$$A=\left( \begin{array}{cccc}
b & 0 & 0 & 0\\
0 & 1 & 1 & 2\\
1 & 2& 2 & 4\\
b & 0 & 0 & 0
\end{array}\right)\sim_c \left( \begin{array}{cccc}
b & 0 & 0 & 0\\
0 & 1 & 0 & 0\\
1 & 2& 0 & 0\\
b & 0 & 0 & 0
\end{array}\right)$$
y es inmediato que el rango es dos. 

</details>
</article>

<article>
Estudia si los siguientes conjuntos de vectores son
linealmente independientes o linealmente dependientes (se recomienda usar coordenadas en las bases más adecuadas).

<ol type="a">
<li>En el conjunto de polinomios de $\mathbb{R}[x]$ con grado menor o igual que dos:</li>

$$\{ 1+2x+3x^{2},\; 1-x+x^{2},\; 1+x-x^{2},\; x+2x^{2} \}.$$

<li>En el conjunto de polinomios de $\mathbb{Z}_3[x]$ con grado menor o igual que tres:</li>

$$\{2x, x^3-3, 1+x -4x^3, x^3 + 18x -9\}.$$

<li>En $\mathcal{M}_{2}(\mathbb{Z}_7)$: </li>

$$\left\{ \begin{pmatrix} 1 & -1 \\ 0 & 6
\end{pmatrix}, \begin{pmatrix} -1 & 0 \\ 3 & 1 \end{pmatrix},
\begin{pmatrix} 1 & 1 \\ -1 & 2 \end{pmatrix}, \begin{pmatrix}
0 & 1 \\ 1 & 0 \end{pmatrix}\right\}.$$
</ol>

<details>
<summary>Solución</summary>

En cada caso utilizaremos la base más sencilla que conozcamos del espacio vectorial para obtener coordenadas de los vectores y aplicar el criterio conocido.

<ol type="a">

<li>Podemos utilizar la base $B=\{1,x,x^2\}$ en la que resulta muy sencillo escribir las coordenadas de los vectores:</li>

$$\begin{array}{rl}
1+2x+3x^{2}&=(1,2,3)_B,\\
1-x+x^{2}&=(1,-1,1)_B,\\
1+x-x^{2}&=(1,1,-1)_B,\\
x+2x^{2}&=(0,1,2)_B.
\end{array}$$

Ahora escribimos las coordenadas por columnas en una matriz y calculamos el rango:

$$\left(\begin{array}{rrrr}
1 & 1 & 1 & 0\\
2 & -1 & 1 & 1\\
3 & 1 & -1 & 2
\end{array}\right)\sim_c \left(\begin{array}{rrrr}
1 & 0 & 0 & 0\\
2 & -3 & -1 & 1\\
3 & -2 & -4 & 2
\end{array}\right)\sim_c \left(\begin{array}{rrrr}
1 & 0 & 0 & 0\\
2 & 1 & 0 & -3\\
3 & 2 & -2 & -2
\end{array}\right),$$

que tiene rango tres (las tres primeras columnas forman una submatriz con determinante distinto de cero). Los cuatro vectores son linealmente dependientes.

Realmente no era necesario el cálculo del rango, puesto que no podía ser en ningún caso mayor que tres. Podíamos haber utilizado que como $\operatorname{dim} (\mathbb{R}^2[x]) = 3$, el máximo número de vectores linealmente independientes en este espacio vectorial es tres.

<li>En este caso, utilizamos la base $B=\{1,x,x^2,x^3\}$ y de nuevo escribimos los vectores por sus coordenadas:</li>

$$\begin{array}{rl}
2x&=(0,2,0,0)_B,\\
x^3-3&=(0,0,0,1)_B,\\
 1+x-4x^{3}&=(1,1,0,2)_B,\\
 x^{3}+18x-9&=(0,0,0,1)_B.
\end{array}$$

Hemos tenido en cuenta que los coeficientes están en $\mathbb{Z}_3$ y por tanto $-3=0,-4=2,18=0,9=0$. En este caso observamos que se repite el mismo vector $(0,0,0,1)_B$, si lo consideramos dos veces el conjunto sería linealmente dependientes, pero como es un conjunto observamos que en realidad lo forman de tres vectores.
Escribimos la matriz
$$\left(\begin{array}{rrr}
0 & 0 & 1 \\
2 & 0 & 1 \\
0 & 0 & 0 \\
0 & 1 & 2
\end{array}\right)\sim_c \left(\begin{array}{rrr}
0 & 0 & 1 \\
1 & 0 & 0 \\
0 & 0 & 0 \\
0 & 1 & 0
\end{array}\right)$$

que tiene rango tres y los tres vectores son linealmente independientes.

<li>En $\mathcal{M}_{2}(\mathbb{Z}_7)$ una base sencilla es</li>

$$\left\{ \begin{pmatrix}
1 & 0 \\ 0 & 0 \\
\end{pmatrix}, \begin{pmatrix}
0 & 1 \\ 0 & 0 \\
\end{pmatrix}, \begin{pmatrix}
0 & 0 \\ 1 & 0 \\
\end{pmatrix},\begin{pmatrix}
0 & 0 \\ 0 & 1 \\
\end{pmatrix}\right\}.$$

Escribimos cada una de las matrices por sus coordenadas en esta base:

$$
\begin{pmatrix} 1 & -1 \\ 0 & 6
\end{pmatrix}=(1,-1,0,6)_B,$$
$$\begin{pmatrix} -1 & 0 \\ 3 & 1 \end{pmatrix}=(-1,0,3,1)_B,$$
$$
\begin{pmatrix} 1 & 1 \\ -1 & 2 \end{pmatrix}=(1,1,-1,2)_B,$$
$$\begin{pmatrix}
0 & 1 \\ 1 & 0 \end{pmatrix}=(0,1,1,0)_B.$$

Calculamos el rango de la matriz que forman (los coeficientes están en $\mathbb{Z}_7$):

$$\left(\begin{array}{rrrr}
1 & -1 & 1 & 0\\
-1 & 0 & 1 & 1\\
0 & 3 & -1 & 1 \\
6 & 1 & 2 & 0
\end{array}\right)\sim_c \left(\begin{array}{rrrr}
1 & 0 & 0 & 0\\
-1 & -1 & 2 & 1\\
0 & 3 & -1 & 1 \\
6 & 0 & 2 & 0
\end{array}\right)\sim_c \left(\begin{array}{rrrr}
1 & 0 & 0 & 0\\
0 & 1 & 0 & 0\\
1 & 1 & 4 & 4 \\
6 & 0 & 2 & 0
\end{array}\right)$$

que tiene determinante distinto de cero y por tanto rango cuatro, así que los vectores son linealmente independientes.

</ol>
</details>
</article>

<article>
calcula las matrices de cambio de base para las bases de $\mathbb{R}^{3}$:

$$B=\{(4,0,7);\ (2,1,1);\ (3,1,3)\},\quad B'=\{(1,0,2);\ (4,1,5);\ (1,0,3)\}.$$

<details>
<summary>Solución</summary>

Este ejercicio puede realizarse por varios métodos. Explicaremos dos de ellos.

<strong>Método 1</strong>

Para calcular la matriz de cambio de base de $B$ a $B'$ necesitamos como datos los vectores que forman $B$ escritos por sus coordenadas en $B'$. Nos planteamos entonces calcular $\alpha, \beta, \gamma$ tales que:
$$(4,0,7)=\alpha (1,0,2)+\beta (4,1,5)+\gamma (1,0,3)$$
y por tanto tenemos que resolver el sistema con matriz ampliada:

$$\left( \begin{array}{rrr|r}
1 & 4 & 1 & 4\\
0 & 1 & 0 & 0\\
2 & 5 & 3 & 7
\end{array} \right).$$

Para el siguiente vector de $B$ tenemos que resolver 
$$(2,1,1)=\alpha (1,0,2)+\beta (4,1,5)+\gamma (1,0,3)$$
con matriz ampliada:

$$\left( \begin{array}{rrr|r}
1 & 4 & 1 & 2\\
0 & 1 & 0 & 1\\
2 & 5 & 3 & 1
\end{array} \right).$$

Observamos que ambos sistemas tienen la misma matriz de coeficientes, y también el tercer sistema que debemos resolver, solo cambian las columnas de términos independientes. Podemos resolver los tres sistemas simultáneamente escribiendo

$$\left( \begin{array}{rrr|rrr}
1 & 4 & 1 & 4 & 2 & 3\\
0 & 1 & 0 & 0 & 1 & 1\\
2 & 5 & 3 & 7 & 1 & 3
\end{array} \right)\sim_f \left( \begin{array}{rrr|rrr}
1 & 0 & 0 & 5 & -2 & -1\\
0 & 1 & 0 & 0 & 1 & 1\\
0 & 0 & 1 & -1 & 0 & 0
\end{array} \right).$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,4,1],[0,1,0],[2,5,3]])
B=matrix([[4,2,3],[0,1,1],[7,1,3]]) 
AB=A.augment(B,subdivide=True) #matriz aumentada
show(AB,"~",AB.rref())
</script>
</div>  

La matriz de cambio de base de $B$ a $B'$ es entonces 

$$M_{BB'}=\left( \begin{array}{rrr}
 5 & -2 & -1\\
 0 & 1 & 1\\
 -1 & 0 & 0
\end{array} \right).$$

<strong>Método 2</strong>

Considerando la base canónica en $\mathbb{R}^3$: $B_c=\{(1,0,0),(0,1,0),(0,0,1)\}$ es muy fácil calcular

$$M_{BB_c}=P=\left( \begin{array}{rrr}
4 & 2 & 3 \\
0 & 1 & 1 \\
7 & 1 & 3 
\end{array} \right)$$

y 

$$M_{B'B_c}=Q=\left( \begin{array}{rrr}
1 & 4 & 1 \\
0 & 1 & 0 \\
2 & 5 & 3 
\end{array} \right).$$

Entonces, $X_c=PX$, $X_c=QX'$ donde $X,X',X_c$ representan a las coordenadas de $\overrightarrow{x}$ en las bases $B,B'$ y $B_c$, respectivamente.
Igualando las dos fórmulas

$$QX'=PX$$

y despejando $X'=Q^{-1}PX$, por lo que la matriz $M_{BB'}=Q^{-1}P$.<br>

Si observamos el método anterior, hemos calculado precisamente $Q^{-1}P$ utilizando operaciones elementales.<br>
La matriz $M_{B'B}=(Q^{-1}P)^{-1}=P^{-1}Q$.

</details>
</article>

<article>

En un espacio vectorial sobre $\mathbb{R}$, tenemos unos vectores $e_{1},e_{2},\dots ,e_{n},\, x$ cuyas coordenadas en una cierta base vienen dadas a continuación. Comprueba que $\{e_{1},e_{2},\dots,e_{n}\}$ es una base en cada uno de los casos, y halla las coordenadas del vector $x$ en dicha base. 

<ol type="a">
<li>
$
\left.
\begin{array}{c}
e_{1}=(1,0,1)\\
e_{2}=(1,2,2)\\
e_{3}=(0,1,1)
\end{array}
\right\} x=(1,0,2).
$
</li>
<li>
$
\left.
\begin{array}{l}
e_{1}=(1,1,1,1)\\
e_{2}=(0,1,1,1)\\
e_{3}=(0,0,1,1)\\
e_{4}=(0,0,0,1)
\end{array}
\right\} x=(1,0,1,0).
$
</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Para comprobar que los vectores $\{e_1,e_2,e_3\}$ forman base es suficiente probar que son linealmente independientes, puesto que son tres que es la dimensión del espacio vectorial. Calculamos el rango de la matriz que forman:</li>

$$\begin{pmatrix}
1 & 1 & 0\\
0 & 2 & 1\\
1 & 2 & 1
\end{pmatrix}\sim_f \begin{pmatrix}
1 & 1 & 0\\
0 & 2 & 1\\
0 & 1 & 1
\end{pmatrix}\sim_f \begin{pmatrix}
1 & 0 & -1\\
0 & 1 & 1\\
0 & 0 & -1
\end{pmatrix}.$$

Como tiene rango tres, son linealmente independientes y por tanto base.
Para calcular las coordenadas de $x$ en esta base planteamos
$$(1,0,2)=\alpha (1,0,1)+\beta (1,2,2)+\gamma (0,1,1)$$
que nos da el sistema

$$\left\{\begin{aligned}
\alpha+\beta &= 1,\\
2\beta+\gamma &= 0,\\
\alpha+2\beta+\gamma&=2.
\end{aligned}\right.$$

Observamos la matriz ampliada y las columnas de la matriz de coeficientes son los vectores de la base, mientras que la de términos independientes es el vector que queremos escribir por coordenadas en esta base:

$$\left( \begin{array}{rrr|r}
1 & 1 & 0 & 1\\
0 & 2 & 1 & 0\\
1 & 2 & 1 & 2
\end{array} \right).$$

Recordaremos esta relación para la próxima vez que realicemos este tipo de cálculos. Resolvemos:

$$\left( \begin{array}{rrr|r}
1 & 1 & 0 & 1\\
0 & 2 & 1 & 0\\
1 & 2 & 1 & 2
\end{array} \right)\sim_f  \left( \begin{array}{rrr|r}
1 & 1 & 0 & 1\\
0 & 2 & 1 & 0\\
0 & 1 & 1 & 1
\end{array} \right)\sim_f \left( \begin{array}{rrr|r}
1 & 0 & -1 & 0\\
0 & 1 & 1 & 1\\
0 & 0 & -1 & -2
\end{array} \right)\sim_f \left( \begin{array}{rrr|r}
1 & 0 & 0 & 2\\
0 & 1 & 0 & -1\\
0 & 0 & 1 & 2
\end{array} \right).$$

Luego $x=(2,-1,2)_B$.<br>

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,1,0],[0,2,1],[1,2,1]])
b=vector([1,0,2]) 
Ab=A.augment(b,subdivide=True) 
show(Ab,"~",Ab.rref())
</script>
</div>  

<li>Procedemos del mismo modo sin repetir los razonamientos, puesto que son idénticos al apartado anterior.</li>

$$\left( \begin{array}{rrrr|r}
1 & 1 & 1 & 1 & 1\\
0 & 1 & 1 & 1 & 0 \\
0 & 0 & 1 & 1 & 1\\
0 & 0 & 0 & 1 & 0
\end{array} \right)\sim_f \left( \begin{array}{rrrr|r}
1 & 0 & 0 & 0 & 1\\
0 & 1 & 0 & 0 & -1 \\
0 & 0 & 1 & 0 & 1\\
0 & 0 & 0 & 1 & 0
\end{array} \right)$$
luego son base (la matriz de coeficientes tiene rango 4) y $x=(1,-1,1,0)_B$.<br>

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,1,1,1],[0,1,1,1],[0,0,1,1],[0,0,0,1]])
b=vector([1,0,1,0]) 
Ab=A.augment(b,subdivide=True) 
show(Ab,"~",Ab.rref())
</script>
</div>  

</ol>
</details>
</article>

<article>

Completa $\{(1,1,0),(2,1,1)\}$ a una base de $\mathbb{Q}^3$.

<details>
<summary>Solución</summary>

Comenzamos observando que los dos vectores son linealmente independientes (no son múltiplo uno del otro). Se trata de añadir vectores a los dados hasta obtener una base de $\mathbb{Q}^3$, como $\operatorname{dim}(\mathbb{Q}^3)=3$ en cualquier base debe haber tres vectores, con lo que en este caso habrá que añadir un vector. Se puede realizar de infinitas formas, la única condición es que los tres vectores sean linealmente independientes; se aconseja hacerlo de modo que esta condición sea fácil de comprobar.
Partimos de la matriz

$$\begin{pmatrix}
1 & 2 & \_\\
1 & 1 & \_\\
0 & 1 & \_
\end{pmatrix}$$ 

y si añadimos una columna sencilla, por ejemplo

$$\begin{pmatrix}
1 & 2 & 1\\
1 & 1 & 0\\
0 & 1 & 0
\end{pmatrix}$$

comprobar que el determinante es distinto de cero es muy fácil. Entonces hemos completado con el vector $(1,0,0)$. También valdría añadir $(0,0,1)$:

$$\begin{pmatrix}
1 & 2 & 0\\
1 & 1 & 0\\
0 & 1 & 1
\end{pmatrix}.$$

</details>
</article>

<article>
Determina si los siguientes conjuntos de vectores generan al
espacio vectorial dado.

<ol type="a">
<li>En el conjunto de polinomios de $(\mathbb{Z}_5)[x]$ de grado menor o igual a dos: $\{1+4x, 3+4x^2\}$.</li>
<li>En el conjunto de polinomios de $(\mathbb{Z}_5)[x]$ de grado menor o igual a dos: $\{1+4x, 3+4x^2, x\}$.</li>
<li>En $\mathcal{M}_{2}(\mathbb{Z}_7)$: $\left\{ \begin{pmatrix} 1 & 0 \\ 1 & 0
\end{pmatrix}, \begin{pmatrix} 1 & 2 \\ 0 & 0 \end{pmatrix},
\begin{pmatrix} 4 & 6 \\ 3 & 0 \end{pmatrix}, \begin{pmatrix} 5
& 5 \\ 6 & 0 \end{pmatrix}\right\}$.</li>

</ol>
<details>
<summary>Solución</summary>

<ol type="a">
<li>Como la dimensión de este espacio es tres, cualquier conjunto de generadores tiene que tener al menos tres vectores. Así que en este caso la respuesta es negativa.</li>
<li>Estamos en el mismo espacio vectorial y ahora sí tenemos tres vectores. Serán sistema de generadores si y solo si son base, lo que equivale a que sean linealmente independientes. Escribimos sus coordenadas en $B_s=\{1,x,x^2\}$ y calculamos el rango de la matriz que forman:</li>

$$1+4x=(1,4,0)_{B_s},$$
$$3+4x^2=(2,0,4)_{B_s},$$
$$x=(0,1,0)_{B_S},$$

$$\begin{pmatrix}
1 & 2 & 0\\
4 & 0 & 1\\
0 & 4 & 0
\end{pmatrix}.$$

Esta matriz tiene determinante $(-1)(4)=1$ y por tanto son sistema de generadores.

<li>En este caso tenemos cuatro vectores y $\operatorname{dim}(\mathcal{M}_{2}(\mathbb{Z}_7))=4$, así que razonamos como antes, esta vez usando coordenadas en la base estándar</li>

$$B_s=\left\{ \begin{pmatrix}
1 & 0 \\ 0 & 0 \\
\end{pmatrix}, \begin{pmatrix}
0 & 1 \\ 0 & 0 \\
\end{pmatrix}, \begin{pmatrix}
0 & 0 \\ 1 & 0 \\
\end{pmatrix},\begin{pmatrix}
0 & 0 \\ 0 & 1 \\
\end{pmatrix}\right\},$$

$$  
\begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}=(1,0,1,0)_{B_s},$$
$$\begin{pmatrix} 1 & 2 \\ 0 & 0 \end{pmatrix}=(1,2,0,0)_{B_s},$$
$$\begin{pmatrix} 4 & 6 \\ 3 & 0 \end{pmatrix}=(4,6,3,0)_{B_s},$$
$$\begin{pmatrix} 5 & 5 \\ 6 & 0 \end{pmatrix}=(5,5,6,0)_{B_s}.$$

Y ahora calculamos el rango de la matriz que forman:

$$\begin{pmatrix}
1 & 1 & 4 & 5\\
0 & 2 & 6 & 5\\
1 & 0 & 3 & 6\\
0 & 0 & 0 & 0
\end{pmatrix}$$

que como tiene una fila entera de ceros tiene rango menor que cuatro, luego no son sistema de generadores.

</ol>
</details>
</article>