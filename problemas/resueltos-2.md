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
<li>En el conjunto de polinomios de $\mathbb{R}[x]$ con grado menor o igual que dos:

$$\{ 1+2x+3x^{2},\; 1-x+x^{2},\; 1+x-x^{2},\; x+2x^{2} \}.$$</li>

<li>En el conjunto de polinomios de $\mathbb{Z}_3[x]$ con grado menor o igual que tres:

$$\{2x, x^3-3, 1+x -4x^3, x^3 + 18x -9\}.$$ </li>

<li>En $\mathcal{M}_{2}(\mathbb{Z}_7)$: 

$$\left\{ \begin{pmatrix} 1 & -1 \\ 0 & 6
\end{pmatrix}, \begin{pmatrix} -1 & 0 \\ 3 & 1 \end{pmatrix},
\begin{pmatrix} 1 & 1 \\ -1 & 2 \end{pmatrix}, \begin{pmatrix}
0 & 1 \\ 1 & 0 \end{pmatrix}\right\}.$$</li>
</ol>

<details>
<summary>Solución</summary>

En cada caso utilizaremos la base más sencilla que conozcamos del espacio vectorial para obtener coordenadas de los vectores y aplicar el criterio conocido.

<ol type="a">

<li>Podemos utilizar la base $B=\{1,x,x^2\}$ en la que resulta muy sencillo escribir las coordenadas de los vectores:

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

Realmente no era necesario el cálculo del rango, puesto que no podía ser en ningún caso mayor que tres. Podíamos haber utilizado que como la dimensión del espacio es tres, el máximo número de vectores linealmente independientes en este espacio vectorial es también tres.

Comprobemos el resultado obtenido con <code>sage</code>.</li>

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,2,3],[1,-1,1],[1,1,-1],[0,1,2]])
show(html(f"${latex(A.T)}$ tiene rango ${A.rank()}$"))
</script>
</div>  

<li>En este caso, utilizamos la base $B=\{1,x,x^2,x^3\}$ y de nuevo escribimos los vectores por sus coordenadas:

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

que tiene rango tres y los tres vectores son linealmente independientes.</li>

<li>En $\mathcal{M}_{2}(\mathbb{Z}_7)$ una base sencilla es

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

Comprobemos el resultado obtenido con <code>sage</code>.</li>

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,-1,0,6],[-1,0,3,1],[1,1,-1,2],[0,1,1,0]])
show(html(f"${latex(A.T)}$ tiene rango ${A.rank()}$"))
</script>
</div>  

</ol>
</details>
</article>

<article>
calcula las matrices de cambio de base para las bases de $\mathbb{R}^{3}$:

$$B=\{(4,0,7);\ (2,1,1);\ (3,1,3)\},\quad B'=\{(1,0,2);\ (4,1,5);\ (1,0,3)\}.$$

<details>
<summary>Solución</summary>

Este ejercicio puede realizarse por varios métodos. Explicaremos dos de ellos.<br>

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
<li>Para comprobar que los vectores $\{e_1,e_2,e_3\}$ forman base es suficiente probar que son linealmente independientes, puesto que son tres que es la dimensión del espacio vectorial. Calculamos el rango de la matriz que forman:

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

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,0,1],[1,2,2],[0,1,1]])
show(html(f"${latex(A.T)}$ tiene rango ${A.rank()}$"))
</script>
</div>  

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
</div>  </li>

<li>Procedemos del mismo modo sin repetir los razonamientos, puesto que son idénticos al apartado anterior.

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
luego son base (la matriz de coeficientes tiene rango cuatro) y $x=(1,-1,1,0)_B$.<br>

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,1,1,1],[0,1,1,1],[0,0,1,1],[0,0,0,1]])
b=vector([1,0,1,0]) 
Ab=A.augment(b,subdivide=True) 
show(Ab,"~",Ab.rref())
</script>
</div>  </li>

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
<li>Estamos en el mismo espacio vectorial y ahora sí tenemos tres vectores. Serán sistema de generadores si y solo si son base, lo que equivale a que sean linealmente independientes. Escribimos sus coordenadas en $B_s=\{1,x,x^2\}$ y calculamos el rango de la matriz que forman:

$$1+4x=(1,4,0)_{B_s},$$
$$3+4x^2=(2,0,4)_{B_s},$$
$$x=(0,1,0)_{B_S},$$

$$\begin{pmatrix}
1 & 2 & 0\\
4 & 0 & 1\\
0 & 4 & 0
\end{pmatrix}.$$

Esta matriz tiene determinante $(-1)(4)=-4$ y por tanto son sistema de generadores.</li>

<li>En este caso tenemos cuatro vectores y $\operatorname{dim}(\mathcal{M}_{2}(\mathbb{Z}_7))=4$, así que razonamos como antes, esta vez usando coordenadas en la base estándar

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

que como tiene una fila entera de ceros tiene rango menor que cuatro, luego no son sistema de generadores.</li>

</ol>
</details>
</article>

<article>

Sea $V = \mathbb{Z}_3^4$ y sean los subespacios vectoriales

$$
U = \left\{(x,y,z,t) \in V ~\left|~
\begin{aligned}
x-y-z &= 0 \\
t &= 0
\end{aligned} \right. \right\}, \qquad W = \langle
(1,1,1,1), (0,1,0,1) \rangle.
$$

<ol type="a">
<li>¿Cuántos elementos hay en $W$?</li>
<li>Calcula unas ecuaciones paramétricas de $U$ y unas ecuaciones cartesianas (o implícitas) de $W$.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>$W = \langle (1,1,1,1), (0,1,0,1) \rangle$.
En primer lugar calculamos la base más sencilla y con ella escribimos las paramétricas:
$$\begin{pmatrix}
1 & 0\\
1 & 1 \\
1 & 0\\
1 & 1
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0\\
0 & 1 \\
1 & 0\\
0 & 1
\end{pmatrix},
$$
luego
$$
W \equiv \left\{ \begin{array}{l}
x=1\cdot \lambda_1 + 0\cdot \lambda_2, \\
y=0\cdot \lambda_1 + 1\cdot \lambda_2,\\
z=1\cdot \lambda_1 + 0\cdot \lambda_2,\\
t=0\cdot \lambda_1 + 1\cdot \lambda_2,\\
\end{array}\right.  \lambda_1,\lambda_2\in \mathbb{Z}_3.
$$
Como aparecen 2 parámetros que pueden tomar valores en $\mathbb{Z}_3$, en total hay $3\cdot 3=9$ vectores distintos en $W$.

También se puede razonar sin necesidad de calcular las paramétricas, comprobando que la dimensión de $W$ es dos, simplemente probando que los dos generadores son linealmente independientes.</li>

<li>Paramétricas de $U$.
Para ello resolvemos el sistema que forman las ecuaciones cartesianas, que en este caso ya es escalonado reducido; depende de dos parámetros (las incógnitas $y$ y $z$ son libres):

$$ U\equiv  \left\{ \begin{array}{l}
x=\lambda_1 + \lambda_2, \\
y=\lambda_1, \\
z=\lambda_2,\\
t=0.\\
\end{array}\right.$$
O también,
$$
\left\{ \begin{array}{l}
x=1\cdot \lambda_1 +1\cdot \lambda_2,\\
y=1\cdot \lambda_1 + 0\cdot \lambda_2,\\
z=0\cdot \lambda_1 + 1\cdot \lambda_2,\\
t=0\cdot \lambda_1 + 0\cdot \lambda_2.\\
\end{array}\right. $$
Además obtenemos que  una base es:
$$\{ (1,1,0,0), (1,0,1,0) \}.$$</li>

<li>Cartesianas de $W$.
Puesto que ya tenemos las ecuaciones paramétricas de $W$ podemos calcular unas ecuaciones cartesianas eliminando parámetros:
despejamos los dos parámetros $\lambda_1=x$ (en la primera ecuación), $\lambda_2= y$ (en la segunda ecuación), uno en una ecuación paramétrica en la que aparece y sustituimos en las otras dos ecuaciones:
$$W\equiv \left\{ \begin{array}{r}
x-z=0,\\
y-t=0.
\end{array}\right.$$
Ha sido tan sencillo porque las ecuaciones paramétricas de las que partimos son las más sencillas (hemos usado la base más sencilla).
También podría procederse formando la matriz
$$\begin{pmatrix}
x & 1 & 0\\
y & 0 & 1\\
z & 1 & 0\\
t & 0 & 1
\end{pmatrix}$$ e imponiendo que su rango debe ser dos, con lo que hay que elegir dos menores de orden tres que al igualarlos a cero nos den dos ecuaciones que no sean múltiplo una de la otra. Este procedimiento es en general mucho más laborioso.</li>

</ol>
</details>
</article>

<article>

Para cada uno de los siguientes subespacios de $\mathbb{R}^{4}$ calcula unas ecuaciones paramétricas y unas cartesianas.

<ol type="a">

<li>$U=\{(a,b,-b,a) : a,b\in \mathbb{R} \}$, $W=\{(a,b,0,c) : a,b,c\in \mathbb{R}\}$.</li>

<li>$U\equiv \left\{
\begin{array}{lcrrr}
x_{1} &=& \lambda,\\
x_{2} &=& 0,\\
x_{3} &=& \lambda & +\mu,\\
x_{4} &=& \lambda & +\mu & +\gamma,\\
\end{array}
\right.$
$W\equiv \left\{
\begin{array}{lcrrr}
x_{1} &=& \lambda & +\mu &+\gamma,\\
x_{2} &=& \lambda & +\mu,\\
x_{3} &=& 0,\\
x_{4} &=& \lambda.\\
\end{array}
\right.$</li>

<li>$U=\langle(1,1,0,0), (0,1,1,0), (0,0,1,1)\rangle$, $W\equiv \left\{
\begin{array}{lcrrr}
x_{1} &+x_{2}& & -x_{4} &=0,\\
      & x_{2}&+x_{3}&   &=0,\\
x_{1}&-x_{2}&-x_{3}&-x_{4}&=0.\\
\end{array}
\right.
$</li>

</ol>
<details>
<summary>Solución</summary>

<ol type="a">

<li>Observemos la información que tenemos sobre los vectores que están en $U$: llamamos $(x_1,x_2,x_3,x_4)$ a las coordenadas de un vector de $\mathbb{R}^4$ y para que pertenezca a $U$ se tiene que cumplir:
$$U\equiv \left\{
\begin{array}{lcrr}
x_{1} &=& a,\\
x_{2} &=& b,\\
x_{3} &=& -b,\\
x_{4} &=& a.\\
\end{array}
\right.
$$
Donde $a$, $b$ son parámetros. Así tenemos unas ecuaciones paramétricas de $U$. Para calcular cartesianas podemos eliminar parámetros, que en este caso es muy sencillo:
$$ U\equiv  \left\{ \begin{array}{l}
x_1-x_4=0,\\
x_2+x_3=0.
\end{array}\right. $$
También estas ecuaciones podían deducirse de la descripción del conjunto $U$.<br>

De la misma forma, en el caso de $W$ podemos escribir unas paramétricas directamente:
$$W\equiv \left\{
\begin{array}{lcrr}
x_{1} &=& a,\\
x_{2} &=& b,\\
x_{3} &=& 0,\\
x_{4} &=& c.\\
\end{array}
\right.
$$
Donde $a$, $b$ son parámetros. Como los vectores que acompañan a cada parámetro son linealmente independientes (esos vectores son  $\{(1,0,0,0),(0,1,0,0),(0,0,0,1)\}$) 
entonces la dimensión de $W$ es tres y debe tener una ecuación cartesiana (puesto que la dimensión de $W$ es la dimensión del total menos el número de ecuaciones cartesianas), así que con encontrar una hemos terminado. Observando las paramétricas descubrimos que la tercera ecuación ($x_3=0$) ya es una cartesiana puesto que en ella no aparece ningún parámetro, así que 
$$W\equiv x_3=0.$$ </li>

<li>Para el caso de $U$, puesto que nos dan unas ecuaciones paramétricas,  podemos usar un argumento idéntico al anterior: los vectores del sistema de generadores que aparecen en las paramétricas que nos dan son linealmente independientes (hay que comprobarlo, claro). En este caso esos vectores son $\{(1,0,1,1),(0,0,1,1),(0,0,0,1)\}$.
Utilizando de nuevo el argumento de antes, necesitamos solo una ecuación cartesiana y la segunda, $x_2=0$, ya lo es, luego 
$$U\equiv x_2=0.$$
 
Para $W$ el mismo razonamiento nos da que $$W\equiv x_3=0.$$ </li>

<li>Para $U$ en primer lugar calculamos la base más sencilla:
$$\begin{pmatrix}
1 & 0 & 0 \\
1 & 1 & 0\\
0 & 1 & 1\\
0 & 0 & 1
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0\\
0 & 0 & 1\\
1 & -1 & 1
\end{pmatrix}$$ y con ellas escribimos unas paramétricas:
$$U\equiv \left\{
\begin{array}{lclr}
x_{1} &=& \lambda_1,\\
x_{2} &=& \lambda_2,\\
x_{3} &=& \lambda_3,\\
x_{4} &=& \lambda_1 -\lambda_2 +\lambda_3.\\
\end{array}
\right.
$$
usando las tres primeras para eliminar parámetros nos queda 
$$U\equiv x_4=x_1-x_2+x_3,$$
o bien, 
$$U\equiv x_1-x_2+x_3-x_4=0.$$

De $W$ nos dan unas ecuanciones cartesianas y para encontrar unas paramétricas solo hay que resolver el sistema:
$$\left(\begin{array}{rrrr}
1 & 1 & 0 & -1\\
0 & 1 & 1 & 0\\
1 & -1 & -1 & -1
\end{array}\right)\sim_f \left(\begin{array}{rrrr}
1 & 0 & 0 & -1\\
0 & 1 & 0 & 0\\
0 & 0 & 1 & 0
\end{array}\right)$$
y obtenemos que $x_4$ actúa como parámetro mientras que las otras tres incógnitas están despejadas:
$$W\equiv \left\{
\begin{array}{lcrrr}
x_{1} &=& \lambda,\\
x_{2} &=& 0,\\
x_{3} &=& 0,\\
x_{4} &=& 0.\\
\end{array}
\right.
$$
son unas ecuaciones paramétricas de $W$.</li>

</ol>
</details>
</article>

<article>
<ol type="a">

<li>Calcula las coordenadas del vector $v=(1,1)_B$ respecto de $B'$ siendo
$B=\{(1,1),(1,2)\}$ y $B'=\{(2,1),(0,1)\}$, en el espacio vectorial $\mathbb{Z}_3^2$.</li>
<li>En el espacio vectorial $\mathbb{Z}_3^3$ se considera el plano generado por los vectores $u=(1,2,1)$ y $v=(1,1,2)$. Calcula una ecuación cartesiana de dicho plano.</li>

</ol>
<details>
<summary>Solución</summary>

<ol type="a">
<li>Debemos calcular en primer lugar las coordenadas de $v$ en la base canónica:
$$v=(1,1)_B=1\cdot (1,1)+1\cdot (1,2)=(2,0)$$
y ahora planteamos el sistema:
$$v=(2,0)=\alpha (2,1)+\beta (0,1)=(\alpha,\beta)_{B'}$$
que resolvemos:
$$\left(\begin{array}{cc|c}
2 & 0 & 2\\
1 & 1 & 0
\end{array}\right)\sim_f \left(\begin{array}{cc|c}
1 & 0 & 1\\
0 & 1 & 2
\end{array}\right),$$
luego $v=(1,2)_{B'}$.</li>

<li>Como nos dan un sistema de generadores del subespacio podemos buscar la base más sencilla
$$\begin{pmatrix}
 1 & 1 \\
 2 & 1 \\
 1 & 2 \\
  \end{pmatrix}\sim_c \begin{pmatrix}
 1 & 0 \\
 0 & 1 \\
 0 & 2 \\
  \end{pmatrix}
$$
y con esta base escribimos las ecuaciones paramétricas más sencillas:

$$\pi\equiv \left\{
\begin{array}{lcrrr}
x &=& \lambda_1,\\
y &=& \lambda_2,\\
z &=& 2\lambda_2.\\
\end{array}
\right.
$$
Eliminando los dos parámetros nos queda 
$$\pi \equiv 2y-z=0.$$</li>

</ol>
</details>
</article>

<article>
En $\mathbb{R}^4$ consideramos los subespacios

$$U\equiv \left\{ \begin{array}{l}
x+y+z=0,\\
t=0.\\
\end{array}\right.  \hspace{.5cm} W=\mathcal{L}\{(0,1,1,1),(0,1,-1,1),(-2,1,1,0)\}.$$

Calcula la base más sencilla de $U$ y unas cartesianas de $W$.

<details>
<summary>Solución</summary>

Para calcular la base más sencilla de $U$, de las ecuaciones cartesianas obtendremos unas paramétricas resolviendo el sistema. De estas paramétricas obtenemos una base desde la que calcular la base más sencilla.<br>

Resolver las cartesianas es inmediato puesto que ya es un sistema escalonado reducido, $y$, $z$ actúan como parámetros, luego nos queda:

$$U\equiv \left\{
\begin{array}{lcrrr}
x &=& -\lambda_1-\lambda_2,\\
y &=& \lambda_1,\\
z &=& \lambda_2,\\
t &=& 0.\\
\end{array}
\right.
$$
Con lo que obtenemos la base de $U$, $\{ (-1,1,0,0),(-1,0,1,0)\}$. Ahora calculamos la base más sencilla a partir de la forma de Hermite por columnas:
$$\begin{pmatrix}
 -1 & -1  \\
 1 & 0 \\
 0 & -1  \\
 0 & 0 
  \end{pmatrix}\sim_c \begin{pmatrix}
 1 & 0  \\
 0 & 1 \\
 -1 & -1  \\
 0 & 0 
  \end{pmatrix},$$
luego la base más sencilla de $U$ es 
$$ \{(1,0,-1,0),(0,1,-1,0)\}.$$

Para calcular las cartesianas de $W$ procedemos en primer lugar a calcular la base más sencilla:
$$\begin{pmatrix}
0 & 0 & -2  \\
1 & 1 & 1\\
1 & -1 & 1 \\
1 & 1 & 0 
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0  \\
0 & 1 & 0\\
0 & 0 & 1 \\
1/2 & 1 & 0 
\end{pmatrix}$$
y escribimos las paramétricas:

$$W\equiv \left\{
\begin{array}{lclrr}
x &=& \lambda_1,\\
y &=& \lambda_2,\\
z &=& \lambda_3,\\
t &=& \frac{1}{2}\lambda_1+\lambda_2.\\
\end{array}
\right.
$$

Eliminando los tres parámetros y reordenando la ecuación restante nos queda
$$W\equiv x+2y-2t=0.$$ 
