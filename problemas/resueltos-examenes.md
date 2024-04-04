---
layout: page
title: Problemas de exámenes
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

# Exámenes de la asignatura

Los ejercicios aquí mostrados han sido amablemente proporcionados por [Evangelina Santos](https://www.ugr.es/~esantos/) y maquetados por [Juan Rivas](https://github.com/MrRiversGit).

## Ejercicios resueltos 

<article> 

Dada la matriz
$$A=\left(
\begin{array}{ccc}
0 & 0 & 1\\
0 & a & 0 \\
1 & 0 & 0 
\end{array}\right)
\hspace{1cm} \mbox{ con } a\not = 0$$

<ol type="a">
<li>Calcula los valores propios y sus multiplicidades algebraicas en todos los casos posibles.</li>
<li>¿Para qué valores de $a$ es diagonalizable?</li>
<li>Para el caso $a=1$ comprueba que es diagonalizable por semejanza ortogonal y calcula $D$ diagonal y $P$ ortogonal (esto es, $P^t=P^{-1}$) tal que $D=P^tAP$. </li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Calcular los valores propios y sus multiplicidades algebraicas.<br>
Calculamos los valores propios en función de $a$:
$$|A-\lambda I|=\left|
\begin{array}{ccc}
-\lambda & 0 & 1\\
0 & a-\lambda & 0 \\
1 & 0 & -\lambda 
\end{array}\right|= (a-\lambda)\left|
\begin{array}{cc}
-\lambda &  1\\
1 &  -\lambda 
\end{array}\right|=(a-\lambda)(\lambda^2-1)=(a-\lambda)(\lambda-1)(\lambda +1).$$
Así que cuando $a\not = \pm 1$ entonces hay tres valores propios distintos con multiplicidad algebraica 1. Pero si $a=1$ entonces hay dos valores propios, $\lambda=1$ con multiplicidad algebraica dos y $\lambda=-1$ con multiplicidad algebraica uno; y si $a=-1$ entonces hay dos valores propios, $\lambda=-1$ con multiplicidad algebraica dos y $\lambda=1$ con multiplicidad algebraica uno.
</li>

<li>¿Para qué valores de $a$ es diagonalizable?<br>
Siempre es diagonalizable puesto que es simétrica.</li>

<li>Comprobar que es diagonalizable por semejanza ortogonal y calcular $D$ diagonal y $P$ ortogonal.<br>
Como es simétrica es diagonalizable por semejanza ortogonal (Teorema espectral). Para $a=1$ ya tenemos los valores propios: $\lambda=1$ con multiplicidad algebraica dos y $\lambda=-1$ con multiplicidad algebraica uno, y nos queda calcular las bases ortonormales (para que $P$ sea ortogonal) de cada uno de los subespacios propios:<br>
<strong>$V_{\lambda=1}$</strong>
$$\begin{pmatrix}
-1 & 0 & 1\\
0 & 0 & 0\\
1 & 0 & -1\\
\end{pmatrix}\begin{pmatrix}
x\\ y\\ z
\end{pmatrix}=  \begin{pmatrix}
0\\ 0\\ 0 
\end{pmatrix}$$
nos da la ecuación $x-z=0$ y una base es $\{(1,0,1),(0,1,0)\}$ que es ortogonal, así que los dividimos por su norma: $\{(1/\sqrt{2},0,1/\sqrt{2}),(0,1,0)\}$.<br>
<strong>$V_{\lambda=-1}$</strong>
$$\begin{pmatrix}
1 & 0 & 1\\
0 & 2 & 0\\
1 & 0 & 1\\
\end{pmatrix}\begin{pmatrix}
x\\ y\\ z
\end{pmatrix}=  \begin{pmatrix}
0\\ 0\\ 0 
\end{pmatrix}$$
nos da las ecuaciones $x+z=0; y=0$ y una base es $\{(1,0,-1)\}$ que es ortogonal, así que lo dividimos por su norma: $\{(1/\sqrt{2},0,-1/\sqrt{2})\}$.<br>
Tenemos entonces
$$D=\begin{pmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & -1
\end{pmatrix},\hspace{2cm}  P=\begin{pmatrix}
1/\sqrt{2} & 0  & 1/\sqrt{2}\\
0 & 1 & 0 \\
1/\sqrt{2} & 0  & -1/\sqrt{2}\\
\end{pmatrix}.$$
</li>

</ol>
</details>
</article> 

<article> 

<ol type="a">
<li>Calcula la matriz de Gram del producto escalar en el espacio de las matrices simétricas de orden dos dado por la fórmula:
$$\langle A,B\rangle=\operatorname{traza}(AB)$$
respecto de la base $B= \left\{ \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}; \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix};\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}\right\}$.</li>
<li>En $\mathbb{R}^2$ conocemos la base $B=\{ (1,1),(2,-1)\}$ y que la matriz de cambio de base de $B$ a $B'$ es $P=\begin{pmatrix}
1 &  2\\
2/3  & 1/3\\
\end{pmatrix}$. Calcula $B'$. </li>
<li>Calcula la signatura de la matriz $A=\begin{pmatrix}
0 & 0 & 1  \\
0 & b& 0\\
1 & 0 & 0
\end{pmatrix}$ según los valores de $b$.</li>
<li>De una aplicación lineal $f:\mathbb{R}^{n} \longrightarrow \mathbb{R}^{m}$ se conoce que es sobreyectiva. ¿Puedes deducir algo sobre los valores de $n$ y $m$? 
</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Calcula la matriz de Gram.<br>
Para obtener la matriz de Gram calculamos el producto de cada dos matrices de la base:
$$\langle \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} ,\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}\rangle=\operatorname{traza}\left(  \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}\right)=\operatorname{traza}\left(  \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} \right)=1,$$
$$\langle \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} ,\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}\rangle=\operatorname{traza}\left(  \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}\right)=\operatorname{traza}\left(  \begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix} \right)=0,$$
del mismo modo se obtienen los productos restantes y se obtiene

$$G=\begin{pmatrix}
1 & 0 & 0\\
0 & 2 & 0\\
0 & 0 & 1\end{pmatrix}.$$
</li>

<li>Calcula $B'$.<br>
Los vectores de $B'$ escritos en la base canónica forman la matriz de cambio de base de $B'$ a $Bc$, así que calcularemos esta matriz para obtenerlos.
Como la matriz de cambio de base de $B'$ a $B$ es la inversa de $P$ y la de $B$ a $B_c$ es $Q=\begin{pmatrix}
1 & 2\\ 1 &-1\\
\end{pmatrix}$, entonces la matriz que buscamos es 
$Q\cdot P^{-1}$. Calculamos $P^{-1}$:
$$\left(\begin{array}{cc|cc}
1 & 2 & 1 & 0\\
2/3 & 1/3 & 0 & 1
\end{array}\right)\sim_f \left(\begin{array}{cc|cc}
1 & 2 & 1 & 0\\
0 & -1 & -2/3 & 1
\end{array}\right)\sim_f \left(\begin{array}{cc|cc}
1 &0 & -1/3 & 2\\
0 & 1 & -2/3 & 1
\end{array}\right),$$

$$Q\cdot P{-1}=\begin{pmatrix}
1 & 2\\ 1 & -1 
\end{pmatrix}\begin{pmatrix}
-1/3 & 2\\
2/3 & -1
\end{pmatrix}=\begin{pmatrix}
1 & 0\\ -1 & 3
\end{pmatrix},$$
luego $B'=\{ (1,-1), (0,3)\}$.
</li>

<li>Calcular la signatura de la matriz $A$.<br>
Para obtener su signatura debemos diagonalizarla, bien por congruencia o por semejanza ortogonal. Como es idéntica a la del problema 4 tenemos que sus valores propios son $1,-1$ y $b$, así que la signatura será:
$$\begin{array}{lr}
\operatorname{sig}(A)=(2,1) & \mbox{ si }b>0,\\
\operatorname{sig}(A)=(1,1) & \mbox{ si }b=0,\\
\operatorname{sig}(A)=(1,2) & \mbox{ si }b<0.\\
\end{array}$$
</li>

<li>¿Puedes deducir algo sobre los valores de $n$ y $m$?<br>
Como es sobreyectiva $\operatorname{dim}(\operatorname{Im}(f))=m$ y por la fórmula de las dimensiones 
$$\operatorname{dim}(\operatorname{ker}(f))+ \operatorname{dim}(\operatorname{Im}(f))=\operatorname{dim}(\mathbb{R}^{n})=n.$$
Así que $n=a+m$ siendo $a=\operatorname{dim}(\operatorname{ker}(f))$. Por tanto $$n\geq m.$$
</li>

</ol>
</details>
</article> 

<article> 
Dada la matriz
$$A=\left(
\begin{array}{cccc}
-1 & -2 & 3 & 2\\
0 & 1 & 0 & 1\\
-2 & -2 & 4 & 2\\
0 & 0 & 0 & 2
\end{array}\right)
$$

<ol type="a">
<li>Calcula los valores propios y sus multiplicidades algebraicas.</li>
<li>Estudia si es diagonalizable y en caso afirmativo determinar su forma diagonal, $D$, y una matriz de paso, $P$, verificando que $D=P^{-1}AP$.</li>
<li>Razona si $A$ es o no diagonalizable por semejanza ortogonal.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Calcular los valores propios y sus multiplicidades algebraicas.<br>
Calculamos el polinomio característico:
$$\begin{align*}
|A-\lambda I|=& 
\left|
\begin{array}{cccc}
-1-\lambda & -2 & 3 & 2\\
0 & 1-\lambda  & 0 & 1\\
-2 & -2 & 4-\lambda & 2\\
0 & 0 & 0 & 2-\lambda
\end{array}\right|= (2-\lambda)\left|
\begin{array}{ccc}
-1-\lambda & -2 & 3 \\
0 & 1-\lambda  & 0 \\
-2 & -2 & 4-\lambda \\
\end{array}\right|=(2-\lambda)(1-\lambda)\left|
\begin{array}{cc}
-1-\lambda  & 3 \\
-2 &  4-\lambda \\
\end{array}\right| \\
=&(2-\lambda)(1-\lambda)(\lambda^2-3\lambda +2)=(2-\lambda)^2(1-\lambda)^2
\end{align*}$$
Así que hay dos valores propios $\lambda=1$ y $\lambda=2$, ambos con multiplicidad algebraica dos.
</li>

<li>Estudiar si es diagonalizable y en caso afirmativo determinar su forma diagonal, $D$, y una matriz de paso, $P$.<br>
Para comprobar que es diagonalizable debemos calcular las multiplicidades geométricas, es decir, las dimensiones de los correspondientes subespacios propios:<br>
$V_{\lambda=1}$ tiene cartesianas dadas por las filas de 
$$A-1\cdot I=\left(
\begin{array}{cccc}
-2 & -2 & 3 & 2\\
0 & 0 & 0 & 1\\
-2 & -2 & 3 & 2\\
0 & 0 & 0 & 1
\end{array}\right)\sim_f \left(
\begin{array}{cccc}
-2 & -2 & 3 & 0\\
0 & 0 & 0 & 1\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0
\end{array}\right).
$$
Como hay dos ecuaciones, $\operatorname{dim}(V_{\lambda=1})=4-2=2$, unas cartesianas son
$$V_{\lambda=1}\equiv \left\{ \begin{array}{l}
2x+2y-3z=0,\\
t=0.
\end{array}\right.$$
Y una base es por ejemplo $\{ (1,-1,0,0),(3,0,2,0)\}$.<br>
$V_{\lambda=2}$ tiene cartesianas dadas por las filas de 
$$A-2\cdot I=\left(
\begin{array}{cccc}
-3 & -2 & 3 & 2\\
0 & -1 & 0 & 1\\
-2 & -2 & 2 & 2\\
0 & 0 & 0 & 0
\end{array}\right)\sim_f \left(
\begin{array}{cccc}
1 & 1 & -1 & -1\\
0 & -1 & 0 & 1\\
0 & 1 & 0 & -1\\
0 & 0 & 0 & 0
\end{array}\right)\sim_f \left(
\begin{array}{cccc}
1 & 0 & -1 & 0\\
0 & 1 & 0 & -1\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0
\end{array}\right).
$$
Como hay dos ecuaciones, $\operatorname{dim}(V_{\lambda=2})=4-2=2$, unas cartesianas son
$$V_{\lambda=2}\equiv \left\{ \begin{array}{l}
x-z=0,\\
y-t=0.
\end{array}\right.$$
Y una base es por ejemplo $\{ (1,0,1,0),(0,1,0,1)\}$.<br>
Así concluimos que ambos valores propios tienen multiplicidad geométrica dos, y como coincide con sus multiplicidades algebraicas respectivas la matriz sí es diagonalizable.
 $$D=\begin{pmatrix}
 1 & 0 & 0 & 0\\
 0 & 1 & 0 & 0\\
 0 & 0 & 2 & 0 \\
 0 & 0 & 0 & 2
 \end{pmatrix}, \hspace{1cm} P=\begin{pmatrix}
 1 & 3 & 1 & 0\\
 -1 & 0 & 0 & 1\\
 0 & 2 & 1 & 0 \\
 0 & 0 & 0 & 1
 \end{pmatrix}.$$
</li>

<li>Razonar si $A$ es o no diagonalizable por semejanza ortogonal.<br>
La matriz no es diagonalizable por semejanza ortogonal porque no es simétrica.
</li>
</ol>

</details>
</article>