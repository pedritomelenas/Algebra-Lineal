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
0 & 1 & 2/3 & -1
\end{array}\right)$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
P=matrix([[1,2],[2/3,1/3]])
I=matrix([[1,0],[0,1]]) 
PI=P.augment(I,subdivide=True) 
show(PI,"~",PI.rref())
</script>
</div>

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

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[-2,-2,3,2],[0,0,0,1],[-2,-2,3,2],[0,0,0,1]])
show(A,"~",A.rref())
</script>
</div>

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

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix([[-3,-2,3,2],[0,-1,0,1],[-2,-2,2,2],[0,0,0,0]])
show(A,"~",A.rref())
</script>
</div>

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

<article> 

<ol type="a">
<li>Dadas las matrices $A=\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$ y 
$B=\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$, dar matrices regulares $P$ y $Q$ de forma que $Q\cdot A \cdot P = B$.</li>
<li>Determinar las coordenadas del vector $p(x)=1+x+x^2$ de $\mathcal{P}_2(\mathbb{R})$ respecto de la base $B'=\{1, 1-x, 1-x^2  \}$.</li>
<li>Razonar que la aplicación $G: \mathcal{M}_2(\mathbb{R})  \longrightarrow \mathcal{M}_2(\mathbb{R})$ definida por: 
$$G\left(\begin{pmatrix} a & b \\ c & d \end{pmatrix}\right)=\begin{pmatrix} a\cdot b & 0 \\ c & d \end{pmatrix}$$
no es lineal.</li>
<li>Calcular la signatura de la matriz simétrica 
$$
C=\begin{pmatrix}
5 & 2 \\ 2 & \frac{1}{2}
\end{pmatrix}.
$$
</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Dar matrices regulares $P$ y $Q$ de forma que $Q\cdot A \cdot P = B$.<br>
$$\left(\begin{array}{rcl}
A&|&I\\
\hline
I &| \\ \end{array} \right)=\left(\begin{array}{ll|ll}
 1 & 0 & 1 & 0\\ 
 0 & 0 & 0 & 1\\
 \hline
 1 & 0 & & \\
 0 & 1 & & \\
 \end{array}\right)\sim_f \left(\begin{array}{ll|ll}
 1 & 0 & 1 & 0\\ 
 1 & 0 & 1 & 1\\
 \hline
 1 & 0 & & \\
 0 & 1 & & \\
 \end{array}\right)\sim_c \left(\begin{array}{ll|ll}
 1 & 1 & 1 & 0\\ 
 1 & 1 & 1 & 1\\
 \hline
 1 & 1 & & \\
 0 & 1 & & \\
 \end{array}\right),$$
luego 
$$Q=\begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix} \mbox{ y } P=\begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}.$$</li>

<li>Determinar las coordenadas del vector $p(x)$ respecto de la base $B'$.<br>
Si denotamos $1+x+x^2=(\alpha_1, \alpha_2,\alpha_3)_{B'}$, tenemos:
$$1+x+x^2=\alpha_1 \cdot  1 + \alpha_2 \cdot  (1-x)+\alpha_3 \cdot  (1-x^2)
=
(\alpha_1+\alpha_2+\alpha_3) \cdot 1 - \alpha_2 \cdot x - \alpha_ 3 \cdot x^2,
$$
y resolviendo $\alpha_1+\alpha_2+\alpha_3=1$, $-\alpha_2=1$, $-\alpha_3=1$, nos queda que
$$1+x+x^2=(3,-1,-1)_{B'}.$$

Alternativamente, la matriz del cambio de $B'$ a $B_s$ es 
$
P=\begin{pmatrix} 1 & 1 & 1 \\ 0 & -1 & 0 \\ 0 & 0 &-1 \end{pmatrix}
$
, luego la matriz del cambio de $B_s$ a $B'$ es 
$$
P^{-1}=\begin{pmatrix} 1 & 1 & 1 \\ 0 & -1 & 0 \\ 0 & 0 &-1 \end{pmatrix}.
$$
Puesto que $1+x+x^2=(1,1,1)_{B_s}$ obtenemos:
$$
\begin{pmatrix} 1 & 1 & 1 \\ 0 & -1 & 0 \\ 0 & 0 &-1 \end{pmatrix}\cdot
\begin{pmatrix}
1 \\ 1 \\ 1
\end{pmatrix}
=
\begin{pmatrix}
3 \\ -1 \\ -1
\end{pmatrix}.
$$</li>

<li>Razonar que la aplicación $G$ no es lineal.<br>
Calculamos
$$G\left(\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}\right)=\begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}, G\left(\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}\right)=\begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$$
Sin embargo la imagen de la suma de estas matrices es
$$G\left(\begin{pmatrix} 1 & 1 \\ 0 & 0 \end{pmatrix}\right)=\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}\not = G\left(\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}\right)+G\left(\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}\right).$$</li>

<li>Calcular la signatura de C.<br>
Diagonalizamos por congruencia 
$$
C=\begin{pmatrix}
5 & 2 \\ 2 & \frac{1}{2}
\end{pmatrix}\sim_f \begin{pmatrix}
5 & 2 \\ 0 & -\frac{3}{10} 
\end{pmatrix}\sim_c \begin{pmatrix}
5 & 0 \\ 0 & -\frac{3}{10} \end{pmatrix},
$$
por lo que $\operatorname{sig}(C)=(1,1)$.</li>
</ol>

</details>
</article>

<article>

<ol type="a">
<li>De una aplicación lineal $f:\mathbb{R}^{3}\longrightarrow \mathbb{R}^{4}$ se sabe que $f(5,1,1)=f(1,5,1)=f(1,1,5)=(5,5,5,5)$. Determinar bases del núcleo y la imagen de $f$.</li>
<li>Dar bases $B$ de $\mathbb{R}^{3}$ y 
$B'$ de $\mathbb{R}^{4}$ de forma que $\mathcal{M}_{B B'}(f)=\begin{pmatrix}
1 & 0 & 0 \\ 0 & 0 & 0 \\  0 & 0 & 0 \\  0 & 0 & 0 \\
\end{pmatrix}$.</li>
<li>Determinar, en función de  $b$ la signatura de la forma cuadrática
$$\phi(x,y)= x^2+  y^2 + 2b x y.$$</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Determinar bases del núcleo y la imagen de $f$.<br>
La imagen de $f$ está generada por $\{(5,5,5,5)\}$ así que este vector es una base, o también $\{(1,1,1,1)\}$, que por tanto tiene dimensión uno. <br>
Como $f(5,1,1)-f(1,5,1)=f(4,-4,0)=(0,0,0,0)$ y $f(5,1,1)-f(1,1,5)=f(4,0,-4)=(0,0,0,0)$ entonces $\{(4,-4,0),(4,0,-4)\}$ es una base del núcleo (que tiene dimensión dos).
</li>

<li>Dar bases $B$ y $B'$.<br>
Hay muchas soluciones, las condiciones son: la imagen del primer vector de $B$ es el primer vector de $B'$, los otros dos vectores de $B$ deben estar en el núcleo.  
</li>

<li>Determinar, en función de  $b$ la signatura de la forma cuadrática $\phi$.<br>
La matriz asociada a la forma cuadrática es 
$$A=\begin{pmatrix}
 1 & b\\
 b & 1
\end{pmatrix}.$$
Diagonalizando por congruencia
$$\begin{pmatrix}
 1 & b\\
 b & 1
\end{pmatrix}\sim_f\begin{pmatrix}
 1 & b\\
 0 & 1-b^2
\end{pmatrix}\sim_c \begin{pmatrix}
 1 & 0\\
 0 & 1-b^2
\end{pmatrix}.$$ 
Como el segundo elemento de la diagonal se anula en $b=1$ y $b=-1$ la distinción de casos queda:<br>
Si $b=\pm 1$ entonces $\operatorname{sig}(A)=(1,0)$.<br>
Si $-1<b<1$ entonces $\operatorname{sig}(A)=(2,0)$.<br>
Si $b<-1$ o $ b>1$ entonces $\operatorname{sig}(A)=(1,1)$.<br>
</li>

</ol>
</details>
</article>

<article>

Dadas las matrices
$$A= \left(\begin{array}{rrr}
1 & 1 & 0\\
0 & 0 & 0\\
0 & 1 & 0
\end{array}\right),\hspace{2cm}  B= \left(\begin{array}{rrr}
1 & 1 & 0\\
1 & 0 & 0\\
1 & 1 & 0
\end{array}\right)$$

<ol type="a">
<li>¿Existen $P, Q$ matrices regulares tales que $Q^{-1}AP=B$?</li>
<li>¿Existe $P$ regular tal que $AP=B$?</li>
<li>¿Existe $P$ regular tal que $PA=B$?</li>
<li>¿Existe $P$ regular tal que $P^{-1}AP=B$?</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>¿Existen $P, Q$ matrices regulares tales que $Q^{-1}AP=B$?<br>
La pregunta es si las matrices son equivalentes, y esto ocurre si, y solo si, tienen el mismo rango. Es inmediato ver que ambas tienen rango 2, por tanto la respuesta es afirmativa.</li>

<li>¿Existe $P$ regular tal que $AP=B$?<br>
En este caso nos preguntan si son equivalentes por columnas, si, y solo si, tienen la misma forma de Hermite por columnas. Calculamos en ambos casos:
$$A= \left(\begin{array}{rrr}
1 & 1 & 0\\
0 & 0 & 0\\
0 & 1 & 0
\end{array}\right)\sim_c \left(\begin{array}{rrr}
1 & 0 & 0\\
0 & 0 & 0\\
0 & 1 & 0
\end{array}\right),$$
$$B= \left(\begin{array}{rrr}
1 & 1 & 0\\
1 & 0 & 0\\
1 & 1 & 0
\end{array}\right)\sim_c \left(\begin{array}{rrr}
1 & 0 & 0\\
0 & 1 & 0\\
1 & 0 & 0
\end{array}\right),$$
y como no son iguales la respuesta es negativa.</li>

<li>¿Existe $P$ regular tal que $PA=B$?<br>
Ahora nos preguntan si son equivalentes por filas, para lo que calculamos sus formas de Hermite por filas y las comparamos:
$$A= \left(\begin{array}{rrr}
1 & 1 & 0\\
0 & 0 & 0\\
0 & 1 & 0
\end{array}\right)\sim_f \left(\begin{array}{rrr}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 0
\end{array}\right),$$
$$B= \left(\begin{array}{rrr}
1 & 1 & 0\\
1 & 0 & 0\\
1 & 1 & 0
\end{array}\right)\sim_f \left(\begin{array}{rrr}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 0
\end{array}\right),$$
como son iguales entonces la respuesta es afirmativa.</li>

<li>¿Existe $P$ regular tal que $P^{-1}AP=B$?<br>
Si calculamos los valores propios de ambas:
$$|A-\lambda I|= \left|\begin{array}{rrr}
1- \lambda & 1 & 0\\
0 & -\lambda & 0\\
0 & 1 & -\lambda
\end{array}\right|=(1-\lambda)(-\lambda)^2.$$
Pero el valor propio $\lambda=0$ tiene multiplicidad geométrica uno, luego no es diagonalizable.
$$|B-\lambda I|= \left|\begin{array}{rrr}
1-\lambda & 1 & 0\\
1 & -\lambda & 0\\
1 & 1 & -\lambda
\end{array}\right|=(-\lambda)(\lambda^2-\lambda-1),$$
en este caso aparecen tres valores propios distintos $\{0, \frac{1+\sqrt{5}}{2}, \frac{1-\sqrt{5}}{2}\}$ y por tanto la matriz sí es diagonalizable. Entonces no puede existir una tal $P$, puesto que ello implicaría que $A$ sería también diagonalizable. También es suficiente comprobar que los valores propios son distintos y que $B$ es diagonalizable.
</li>
</ol>
</details>
</article>

<article>

Dada la matriz
$$A= \left(\begin{array}{rrr}
2 & 0 & 2\\
0 & 1 & 0\\
2 & 0 & -1
\end{array}\right).$$

<ol type="a">
<li>¿Existen $P, Q$ matrices regulares tales que $Q^{-1}AP=I_3$?</li>
<li>¿Existe $P$ regular tal que $P^{-1}AP=I_3$?</li>
<li>¿Existe $P$ regular tal que $P^{t}AP=I_3$?</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>¿Existen $P, Q$ matrices regulares tales que $Q^{-1}AP=I_3$?<br>
Existen $Q , P$ regulares si $A$ e $I$ son equivalentes, esto es, si tienen el mismo rango. Calculamos el rango de $A$.
Calculamos el determinante de $A$ desarrolando por el elemento 22,
$$det(A)=\left|
\begin{array}{ccc}
 2 & 0 & 2 \\
 0 & 1 & 0 \\
  2 & 0 & -1 \\
  \end{array}
   \right|=\left|
     \begin{array}{cc}
      2 & 2 \\
       2 & -1 \\
        \end{array}
  \right| =-6\neq 0.  $$
Por lo tanto el rango es tres, al igual que el de $I_3$. Las matrices son equivalentes y por lo tanto \textbf{sí}  existen $P$ y $Q$ regulares tales que $Q^{-1}AP=I_3$.
</li>

<li>¿Existe $P$ regular tal que $P^{-1}AP=I_3$?<br>
Que exista la matriz $P$ regular tal que $P^{-1}AP=I_3$ equivale a decir que $A$ es diagonalizable por semejanza y su forma diagonal es $I_3$. <br>
Calculamos los valores propios de $A$:
$$\left|
  \begin{array}{ccc}
    2-\lambda & 0 & 2 \\
    0 & 1-\lambda & 0 \\
    2 & 0 & -1-\lambda \\
  \end{array}
\right|= (1-\lambda) \left|
     \begin{array}{cc}
      2 -\lambda& 2 \\
       2 & -1-\lambda \\
        \end{array}
  \right|= (1-\lambda)(-(2-\lambda)(1+\lambda)-4)=(1-\lambda)(2+\lambda)(3-\lambda).$$
Como los valores propios de $A$ son 1, -2 y 3, su forma diagonal (si fuera diagonalizable) no puede ser $I_3$, por lo tanto, no existe $P$ regular tal que  $P^{-1}AP=I_3$
</li>

<li>¿Existe $P$ regular tal que $P^{t}AP=I_3$?<br>
Si existiera una matriz $P$ cumpliendo la igualdad, estaríamos diciendo que $A$ es congruente con $I_3$ y por tanto su signatura  sería $(3,0)$, pero como los valores propios son  1, -2 y 3, su signatura es $(2,1)$, y por tanto no existe dicha matriz $P.$
</li>
</ol>
</details>
</article>

<article>

Dada la matriz:
$$
A=\begin{pmatrix}
a & 0 & 0 & 0 \\
a & 2 & 2 & a \\
a & 2 & 2 & a \\
a & 0 & 0 & 0
\end{pmatrix}.
$$

<ol type="a">
<li>Estudiar para qué valores del parámetro $a$ es $A$ diagonalizable.</li>
<li>Para el valor $a=0$ la matriz $A$ es simétrica, determinar su forma diagonal $D$ así como una matriz ortogonal $P$ de forma que $D=P^{-1}\cdot  A\cdot P=P^{t}\cdot A\cdot P$.
¿Cuál es la signatura de $A$?</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Estudiar para qué valores del parámetro $a$ es $A$ diagonalizable.<br>
Calculamos los valores propios y sus multiplicidades algebraicas:
$$
\begin{align*}
|A-\lambda I|&=\left|\begin{array}{cccc}
a-\lambda & 0 & 0 & 0 \\
a & 2-\lambda & 2 & a \\
a & 2 & 2-\lambda & a \\
a & 0 & 0 & -\lambda
\end{array}\right|=(a-\lambda)(-\lambda)\left|\begin{array}{cc}
2-\lambda & 2\\
2 & 2-\lambda
\end{array}\right|\\
&= (a-\lambda)(-\lambda)((2-\lambda)^2-4)=(a-\lambda)(-\lambda)(\lambda^2-4\lambda)=(a-\lambda)(-\lambda)^2(\lambda-4).
\end{align*}$$

<strong>Caso $a\not =0,4$</strong><br>
En este caso tenemos que para $\lambda=4$ o $\lambda=a$ ambas multiplicidades algebraicas y geométricas son 1 mientras que para $\lambda=0$
la multiplicidad algebraica es 2 y habría que estudiar la geométrica:
$$
A-0\cdot I=\begin{pmatrix}
a & 0 & 0 & 0 \\
a & 2 & 2 & a \\
a & 2 & 2 & a \\
a & 0 & 0 & 0
\end{pmatrix}\sim_f \begin{pmatrix}
a & 0 & 0 & 0 \\
0 & 2 & 2 & a \\
0 & 2 & 2 & a \\
0 & 0 & 0 & 0
\end{pmatrix}\sim_f \begin{pmatrix}
a & 0 & 0 & 0 \\
0 & 2 & 2 & a \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{pmatrix},
$$
que tiene rango 2 ($a\not = 0$) y por tanto $m_g=\operatorname{dim}(V_{\lambda=0})=4-2=2$. Así que en este caso la matriz es diagonalizable.<br>
<strong>Caso $a=0$</strong><br>
En este caso la matriz es simétrica, y por tanto diagonalizable.<br>

<strong>Caso $a=4$</strong><br>
Ahora tenemos que para $\lambda=0$ tanto su multiplicidad algebraica como geométrica es 2 (ha sido calculada cuando $a\not = 0$ en el primer caso) y para $\lambda=0$ la multiplicidad algebraica es 2 y debemos calcular la geométrica.
$$
A-4\cdot I=\begin{pmatrix}
0 & 0 & 0 & 0 \\
4 & -2 & 2 & 4 \\
4 & 2 & -2 & 4 \\
4 & 0 & 0 & 4
\end{pmatrix}\sim_f \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & -1 & 1 & 0 \\
0 & 1 & -1 & 0 \\
1 & 0 & 0 & 1
\end{pmatrix},
$$
tiene rango 3, así que $m_g=\operatorname{dim}(V_{\lambda=4})=4-3=1$. En este caso la matriz no es  diagonalizable.
</li>

<li>Para $a=0$ determinar su forma diagonal $D$ así como una matriz ortogonal $P$ de forma que $D=P^{-1}\cdot  A\cdot P=P^{t}\cdot A\cdot P$.
¿Cuál es la signatura de $A$?<br>
Como tenemos calculados los valores propios y en este caso son $\lambda=0$, con multiplicidad algebraica $3$ y $\lambda=4,$, con multiplicidad algebraica $1$ entonces la signatura es $(1,0)$.<br>
Para calcular la matriz ortogonal $P$ diagonalizamos por semejanza ortogonal:
$$
A-0\cdot I=\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 2 & 2 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{pmatrix},
$$
y por tanto una base de $V_{\lambda=0}$ es $\{(1,0,0,0),(0,1,-1,0),(0,0,0,1)\}$ que ya es ortogonal.
$$
A-4\cdot I=\begin{pmatrix}
-4 & 0 & 0 & 0 \\
0 & -2 & 2 & 0 \\
0 & 2 & -2 & 0 \\
0 & 0 & 0 & -4
\end{pmatrix}\sim_f \begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & -1 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix},
$$ y por tanto una base de $V_{\lambda=4}$ es $\{(0,1,1,0)\}$ que es obviamente ortogonal.<br>
Así, una base ortonormal de $\mathbb{R}^{4}$ es 
$$\{(1,0,0,0),(0,1/\sqrt{2},-1/\sqrt{2},0),(0,0,0,1),(0,1/\sqrt{2},1/\sqrt{2},0)\},$$ y por tanto 
$$P=\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1/\sqrt{2} & 0 & 1/\sqrt{2} \\
0 & -1/\sqrt{2} & 0 & 1/\sqrt{2} \\
0 & 0 & 1 & 0
\end{pmatrix}, \hspace{1cm } D=\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 4
\end{pmatrix}.
$$
</li>
</ol>
</details>
</article>

<article>

<ol type="a">
<li>En $\mathbb{R}^{8}$ consideramos dos subespacios $U$ y $W$, ambos de dimensión 5, ¿puede ser $U\cap W=0$? ¿Por qué?</li>
<li>Para la siguiente matriz determinar su signatura en función de $a$:
$$
\begin{pmatrix}
1 & 0 & 0\\
0 & 0 & a\\
0 & a & 0
\end{pmatrix}.
$$  </li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>En $\mathbb{R}^{8}$ consideramos dos subespacios $U$ y $W$, ambos de dimensión 5, ¿puede ser $U\cap W=0$? ¿Por qué?<br>
No puede ocurrir por la fórmula de las dimensiones:
$$\operatorname{dim}(U) + \operatorname{dim}(W)= \operatorname{dim}(U+W) + \operatorname{dim}(U\cap W),$$
así
$$5 + 5 = \operatorname{dim}(U+W) + 0,$$
y por tanto debería ser $\operatorname{dim}(U+W)=10$, lo que es imposible porque debe estar contenido en  $\mathbb{R}^{8}$ por lo que su dimensión es menor o igual que $8$.
</li>

<li>Determinar la signatura en función de $a$.<br>
Pueden calcularse los valores propios:
$$
\left| \begin{array}{ccc}
1-\lambda & 0 & 0\\
0 &-\lambda & a\\
0 & a & -\lambda
\end{array}\right|= (1-\lambda)(\lambda^2 -a^2)=(1-\lambda)(\lambda -a)(\lambda +a).
$$  
Así los valores propios son $1, a, -a$ y la signatura es $(1,0)$ si $a=0$ y $(2,1)$ si $a\not =0$.
</li>
</ol>
</details>
</article>