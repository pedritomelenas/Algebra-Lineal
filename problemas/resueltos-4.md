---
layout: page
title: Problemas espacio euclídeo
tag: problemas
---
<style>
@media (min-width: 38em) {
  html {
    font-size: 18px;
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

# Espacio euclídeo

Los ejercicios aquí mostrados han sido amablemente proporcionados por [Evangelina Santos](https://www.ugr.es/~esantos/) y maquetados por [Juan Rivas](https://github.com/MrRiversGit).

## Ejercicios resueltos 

<article>
En $\mathbb{R}^4$ con el producto escalar usual se consideran los subespacios:
$$
U\equiv \left\{ \begin{aligned}
x+t&=0,\\
y+z&=0,\\
x-y-z+t&=0.
\end{aligned}\right. 
\qquad  W=\mathcal{L}((1,0,0,1),(0,0,1,-1)).$$ 

<ol type="a">
<li>Calcula una base ortogonal de cada uno de ellos.</li>
<li>Prueba que $U$ y $W$ son complementarios, pero que $U^{\perp}\not = W$.</li>
<li>Para el vector $v=(1,-1,1,1)$ calcula $p_{U}(v)$ y $p_{U^{\perp}}(v)$.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Calcular una base ortogonal.<br>
Para calcular una base ortogonal de $U$ empezamos simplificando las ecuaciones cartesianas y obteniendo una base:
$$U\equiv \left\{ \begin{array}{rl}
x+t&=0,\\
y+z&=0,\\
x-y-z+t&=0.
\end{array}\right. \sim_f U\equiv \left\{ \begin{array}{rl}
x+t&=0,\\
y+z&=0.\\
\end{array}\right.
$$ Podemos calcular una base usando como parámetros a $x$ e $y$: $\{ (1,0,0,-1),(0,1,-1,0)\}$; además esta base resulta ser ortogonal.<br>
Para $W$ ya tenemos un sistema de generadores y observamos que son linealmente independientes; pero no son ortogonales, así que utilizamos el método de Gram-Schimdt partiendo de estos vectores:
$$\begin{array}{l}
u_1=(1,0,0,1),\\
u_2=(0,0,1,-1),
\end{array}\hspace{1cm}
\begin{array}{l}
e_1=(1,0,0,1),\\
e_2=(0,0,1,-1)+\lambda_{2,1}(1,0,0,1).
\end{array}$$
Calculamos $$\lambda_{2,1}=-\frac{<(0,0,1,-1),(1,0,0,1)>}{<(1,0,0,1),(1,0,0,1)>}=-\frac{-1}{2}=\frac{1}{2}.$$
Así que la base ortogonal de $W$ que obtenemos es:
$$\{(1,0,0,1),(1/2,0,1,-1/2)\}.$$
</li>

<li>Probar que $U$ y $W$ son complementarios, pero que $U^{\perp}\not = W$.<br>
Son complementarios si $U+W=\mathbb{R}^4$ y $U\cap W=\{ 0 \}$. Calculamos $U+W$ reuniendo bases:
$$\begin{pmatrix}
1 & 0 & 1 & 0\\
0 & 1 & 0 & 0\\
0 & -1 & 0 & 1\\
-1 & 0 & 1 & -1
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0 & 0\\
0 & 1 & 0 & 0\\
0 & -1 & 0 & 1\\
-1 & 0 & 2 & -1
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0 & 0\\
0 & 1 & 0 & 0\\
0 & -1 & 0 & 1\\
0 & 0 & 1 & 0
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0 & 0\\
0 & 1 & 0 & 0\\
0 & 0 & 1 & 0\\
0 & 0 & 0 & 1
\end{pmatrix}.$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,0,1,0],[0,1,0,0],[0,-1,0,1],[-1,0,1,-1]])
show(A,"~",((A.T).rref()).T)
</script>
</div>

y obtenemos que $U+W=\mathbb{R}^4$ puesto que obtenemos la base canónica. Ahora usando la fórmula de las dimensiones 
$$\operatorname{dim}(U) + \operatorname{dim}(W) = \operatorname{dim}(U+W)+ \operatorname{dim}(U\cap W)$$
obtenemos que $\operatorname{dim}(U\cap W)=0$ y por tanto $U\cap W=\{ 0 \}$.
Sin embargo, como $<(1,0,0,-1),(0,0,1,-1)>=1$ y $(1,0,0,-1)\in U$ y $(0,0,1,-1)\in W$, entonces $W\not = U^{\perp}$.</li>

<li>Calcular $p_{U}(v)$ y $p_{U^{\perp}}(v)$.<br>
De la base de $U$ obtenemos las cartesianas de $U^{\perp}$ que son:
$$U^{\perp}\equiv \left\{ \begin{array}{rl}
x-t&=0,\\
y-z&=0.\\
\end{array}\right.$$
Escribimos ahora $v=p_{U}(v)+p_{U^{\perp}}$ usando 4 incógnitas 
$$(1,-1,1,1)=(\alpha, \beta, \gamma, \delta)+ (1-\alpha, -1-\beta,1-\gamma, 1-\delta)$$ e imponemos las condiciones de que el primero cumpla las cartesianas de $U$ y el segundo las de $U^{\perp}$ y resolvemos:
$$\begin{array}{r}
\alpha +\delta = 0,\\
-\alpha + \delta = 0,\\
\beta + \gamma = 0,\\
-1-\beta -1+ \gamma = 0,
\end{array}$$
y resulta $\alpha= 0, \beta=-1, \gamma = 1, \delta= 0$, así que:
$$p_U(1,-1,1,1)=(0,-1,1,0); \, \, p_{U^{\perp}}(1,-1,1,1)=(1,0,0,1).$$ </li>

</ol>
</details>
</article>

<article>
<ol type="a">
<li>En $\mathbb{R}^{3}$, dado el subespacio $U\equiv \left\{ \begin{array}{l}
x+y=0,\\
x+z=0.
\end{array}\right.$ y considerando el producto escalar usual, calcula $p_{U^{\perp}}(0,1,2)$. </li>
<li>En el espacio vectorial $V$, $B=\{ e_1,e_2\}$ es una base. Calcula las coordenadas respecto de la base  $B'=\{e_1+e_2, 2e_1-e_2\}$ del vector $v=(1,-1)_{B}$.</li>
<li>Consideramos en $\mathbb{R}^{2}$ el producto escalar que tiene, respecto de la base canónica, matriz de Gram (o matriz métrica)
$\begin{pmatrix}
1 & 1 \\
1 & 2
\end{pmatrix}$. Calcula una base de $\mathbb{R}^{2}$ respecto de la cual la matriz de Gram de este producto escalar sea $I_2$.</li>
<li>Determina, en función de  $b$, la signatura de la forma cuadrática $\phi:\mathbb{R}^{2} \to \mathbb{R}$ dada por 
$$\phi(x,y)= bxy.$$</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Calcular $p_{U^{\perp}}(0,1,2)$.<br>
Una base de $U$ es $\{(1,-1,-1)\}$ y por tanto $U^{\perp}\equiv x-y-z=0$, descomponemos
$$(0,1,2)=(a,b,c)+(-a,1-b,2-c),$$
e imponemos al primer vector que esté en $U$ y al segundo que esté en $W$:
$$\left\{ \begin{array}{l}
a+b=0,\\
a+c=0,\\
-a-1+b-2+c=0.
\end{array}\right. \sim_f \left\{ \begin{array}{l}
b=-a,\\
c=-a,\\
-3a-3=0.
\end{array}\right. \sim_f \left\{ \begin{array}{l}
a=-1,\\
b=1,\\
c=1.
\end{array}\right. $$
Así $p_{U^{\perp}}(0,1,2)=(1,0,1)$.
</li>

<li>Calcular las coordenadas respecto de la base  $B'$ del vector $v$.<br>
Como $B'=\{(1,1)_B, (2,-1)_B\}$, planteamos 
$$(1,-1)_B=a(1,1)_B+b(2,-1)_B$$
y resolvemos 
$$\left\{ \begin{array}{l}
a+2b=1,\\
a-b=-1.
\end{array}\right.\sim_f  \left\{ \begin{array}{l}
a=-1/3,\\
b=2/3.
\end{array}\right.$$
Luego $v=(-1/3,2/3)_{B'}$.
</li>

<li>Calcular una base de $\mathbb{R}^{2}$ respecto de la cual la matriz de Gram sea $I_2$.<br>
Que la matriz de Gram sea la identidad significa que la base sea ortonormal. En primer lugar, aplicamos Gram-Schmidt para calcular una base ortogonal. Partimos por ejemplo de la base canónica:
$$u_1=(1,0), u_2=(0,1).$$
Entonces $e_1=(1,0)$ y $e_2=(0,1)+\lambda_{21}(1,0)$ donde 
$$\lambda_{21}=-\frac{\langle u_2,e_1\rangle }{\langle e_1,e_1\rangle }=-\frac{1}{1}=-1,$$
donde los datos se han recogido de la matriz de Gram respecto de $B_c$. 
Por tanto una base ortogonal es $\{(1,0),(-1,1)\}$, el primero tiene norma 1, calculamos la del segundo:
$$\begin{pmatrix}
1 & 1
\end{pmatrix}\begin{pmatrix}
1 & 1 \\
1 & 2
\end{pmatrix}\begin{pmatrix}
-1\\
1
\end{pmatrix}=\begin{pmatrix}
0 & 1
\end{pmatrix} \begin{pmatrix}
-1\\
1
\end{pmatrix}=1$$
Así que esta base es ortonormal. 
</li>

<li>Determinar, en función de  $b$, la signatura de la forma cuadrática $\phi$.<br>
La matriz asociada a la forma cuadrática es 
$$\begin{pmatrix}
0 & b/2\\
b/2 & 0
\end{pmatrix}$$
que podemos diagonalizar por congruencia
$$\begin{pmatrix}
0 & b/2\\
b/2 & 0
\end{pmatrix}\sim_f \begin{pmatrix}
b/2 & b/2\\
b/2 & 0
\end{pmatrix}\sim_c\begin{pmatrix}
b & b/2\\
b/2 & 0
\end{pmatrix}\sim_f \begin{pmatrix}
b & b/2\\
0 & -b/4
\end{pmatrix}\sim_c\begin{pmatrix}
b & 0\\
0 & -b/4
\end{pmatrix}$$
Si $b=0$ la signatura es $(0,0)$; si $b\not = 0$ la signatura es $(1,1)$.<br>
También pueden calcularse los valores propios que son 
$$\lambda= \pm (b/4)$$ y queda el mismo resultado, por supuesto.</li>
</ol>

</details>
</article>

<article>

En el espacio vectorial $\mathcal{P}_3(\mathbb{R})$ de los polinomios de grado menor o igual que tres se considera  el subespacio $U$ generado por $x$ y $x^3$ y el producto escalar dado por:
$$
<p(x),q(x)>= \int_{-1}^1 p(x)\cdot q(x) dx.
$$

<ol type="a">
<li>Determinar una base ortogonal de $U$.</li>
<li>Determinar una base de su complementario, $U^{\perp}$.</li>
<li>Determinar la proyección sobre $U$ del vector  $1+x$.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Determinar una base ortogonal de $U$.<br>
Como $\{ x, x^3\}$ es base, y $<x,x^3>=\int_{-1}^1 x^4dx= \left. x^5\right]_{-1}^1=2/5$
por lo que no es ortogonal. Usamos el algoritmo de Gram-Schmidt para calcular una:

$$\begin{array}{lr}
e_1=x, & \\
e_2=x^3+\lambda_{21}x,& \lambda_{21}= \frac{-<x,x^3>}{<x,x>}.\\
\end{array}$$
Calculamos $<x,x>=\int_{-1}^1 x^2dx= \left. x^3\right]_{-1}^1=2/3$ luego
una base ortogonal de $U$ es $\{x,x^3-3/5x\}$.</li>

<li>Determinar una base de su complementario, $U^{\perp}$.<br>
Podemos observar que $<1,x>=<1,x^3>=0$ y $<x^2,x>=<x^2,x^3>=0$ por lo que $\{1,x^2\}$ es una base de $U^{\perp}$, ya que este subespacio debe tener dimensión dos.</li>

<li>Determinar la proyección sobre $U$ del vector  $1+x$.<br>
Puesto que tenemos bases sencillas de $U$ y de $U^{\perp}$ podemos expresar el polinomio dado como combinación lineal de todos ellos:
$$1+x=\alpha_1\cdot x +  \alpha_2\cdot x^3 + \alpha_3\cdot 1 +\alpha_4\cdot x^2$$
donde los dos primeros sumandos nos dan la proyección sobre $U$ y los dos últimos la proyección sobre $U^{\perp}$. Es inmediato que $\alpha_1=1$, $\alpha_2=0$, $\alpha_3=1$ y $\alpha_4=0$. Por tanto 
$$p_U (1+x)=x.$$</li>
</ol>

</details>
</article>