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