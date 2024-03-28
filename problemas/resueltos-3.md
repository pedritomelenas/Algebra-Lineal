---
layout: page
title: Problemas aplicaciones lineales
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

# Aplicaciones lineales

Los ejercicios aquí mostrados han sido amablemente proporcionados por [Evangelina Santos](https://www.ugr.es/~esantos/) y maquetados por [Juan Rivas](https://github.com/MrRiversGit).

## Ejercicios resueltos 

<article>
Determina cuáles de las siguientes aplicaciones son lineales:

<ol type="a">
<li>La aplicación $f:(\mathbb{Z}_3)^2 \rightarrow (\mathbb{Z}_3)^2$, $f(x,y)=(x+1,y+2)$.</li>
<li>La aplicación $f:V \rightarrow V'$, $f(v)=0$.</li>
<li>La aplicación $f:\mathbb{R} \rightarrow \mathbb{R}$, $f(r)=r^2$.</li>
<li>La aplicación $f:(\mathbb{Z}_7)^3 \rightarrow (\mathbb{Z}_7)^2$, $f(x,y,z)=(x+y+z,28x+92z)$.</li>

</ol>
<details>
<summary>Solución</summary>

<ol type="a">
<li>La aplicación $f:(\mathbb{Z}_3)^2 \rightarrow (\mathbb{Z}_3)^2$, $f(x,y)=(x+1,y+2)$.<br>

No es aplicación lineal. Basta tomar $u=(1,0)$ y $a=2$ y comprobar que no se cumple la segunda propiedad:
$$f(au)=f(2,0)=(0,2),$$
mientras que, 
$$af(u)=2(2,2)=(1,1).$$</li>

<li>La aplicación $f:V \rightarrow V'$, $f(v)=0$.<br>

Es aplicación lineal:<br>
Para cualesquiera $u,v$ se tiene $f(u+v)=0=0+0=f(u)+f(v)$.<br>
Para todo $u$ y todo $a$ se verifica $f(au)=0=a\cdot 0=af(u)$.</li>

<li>La aplicación $f:\mathbb{R} \rightarrow \mathbb{R}$, $f(r)=r^2$.<br>

No es lineal, tomamos $u=1$ y $a=2$ y comprobamos que no se cumple la segunda propiedad de aplicación lineal:
$$af(u)=2\cdot 1^2,$$
$$f(au)=f(2)=2^2.$$</li>

<li>La aplicación $f:(\mathbb{Z}_7)^3 \rightarrow (\mathbb{Z}_7)^2$, $f(x,y,z)=(x+y+z,28x+92z)$.<br>

Es aplicación lineal. Cada componente de la imagen se calcula como una combinación lineal de las componentes del vector inicial.</li>

</ol>
</details>
</article>

<article>
Prueba que la siguiente aplicación es lineal y calcula la matriz asociada considerando las bases estándar en cada espacio vectorial.
$$D:\mathbb{R}_3[x] \to \mathbb{R}_3[x] \text{ dada por } D(p(x))=p'(x).$$

<details>
<summary>Solución</summary>

Es conocido que la derivada tiene las propiedades:

<ol type="a">
<li>La derivada de una suma es la suma de las derivadas.<br>
Es decir, dadas dos funciones (derivables, y los polinomios lo son) $f$ y $g$ se verifica
$$D(f+g)=D(f)+D(g),$$
que es la primera propiedad que debe verificar una aplicación lineal. Hay que tener cuidado porque aquí $f$ y $g$ son los vectores y $D$ es la aplicación.</li>
<li>La derivada de una constante por una función es la constante por la derivada de la función.<br>
Es deir, dadas $f$ (derivable) y $a\in \mathbb{R}$ entonces
$$D(af)=aD(f),$$
que es la segunda propiedad de aplicación lineal.</li>
</ol>

Calculemos ahora la matriz asociada a $D$ utilizando la base de $\mathbb{R}_3[x]$ (el conjunto de los polinomios con coeficientes en $\mathbb{R}$ de grado menor o igual que tres), $B_s=\{1,x,x^2,x^3\}$ en el espacio inicial y en el final, puesto que son el mismo:
$$D(1)=0=(0,0,0,0)_{B_s},$$
donde el primer cero representa a la derivada del polinomio constante igual a uno, que es el polinomio constante igual a cero, cuyas coordenadas en la base $B_s$ son $(0,0,0,0)$.
Procedemos de la misma forma con los otros tres vectores de la base:
$$\begin{array}{l}
D(x)=1=(1,0,0,0)_{B_s},\\
D(x^2)=2x=(0,2,0,0)_{B_s},\\
D(x^3)=3x^2=(0,0,3,0)_{B_s}.
\end{array}
$$
Así que la matriz asociada resulta de poner estas coordenadas por columnas:
$$M_{B_sB_s}(D)=\begin{pmatrix}
0 & 1 & 0 & 0\\
0 & 0 & 2 & 0\\
0 & 0 & 0 & 3\\
0 & 0 & 0 & 0 
\end{pmatrix}.$$

</details>
</article>

<article>

Se considera la matriz sobre $\mathbb{Z}_5$: 
$$A=\begin{pmatrix}
1 & 2 & 0\\
2 & 1 & 0\\
1 & 4 & 2
\end{pmatrix}.$$

<ol type="a">
<li>Diagonaliza la matriz $A$.</li>
<li>Calcula la matriz $A^{123}$.</li>
<li>Diagonaliza la matriz $A^{-1}$.</li>

</ol>
<details>
<summary>Solución</summary>
<ol type="a">

<li>Diagonalizar la matriz $A$.<br>
En primer lugar calculamos el polinomio característico para determinar los valores propios y sus multiplicidades algebraicas:
$$|A-\lambda I|=\begin{vmatrix}
1-\lambda & 2 & 0\\
2 & 1-\lambda & 0\\
1 & 4 & 2-\lambda
\end{vmatrix}=(2-\lambda)\begin{vmatrix}
1-\lambda & 2 \\
2 & 1-\lambda \\
\end{vmatrix}= (2- \lambda)[(1-\lambda)^2-4]=(2-\lambda)(\lambda^2+3\lambda+2).$$
Las raíces de $\lambda^2+3\lambda+2$ en $\mathbb{Z}_5$ son $3$ y $4$, que son simples, luego los valores propios son $2$, $3$, $4$ con multiplicidades algebraicas $1$ para cada uno.<br>


Ahora debemos calcular cada uno de los subespacios propios:<br>

<strong>$V_{\lambda=2}$</strong> 
 
$$A-2I=\begin{pmatrix}
4 & 2 & 0\\
2 & 4 & 0\\
1 & 4 & 0
\end{pmatrix}.$$
Para calcular unas ecuaciones cartesianas más sencillas de $V_{\lambda=2}$ a partir de $(A-2I)X=0$ hacemos operaciones elementales por filas en la matriz anterior:
$$A-2I=\begin{pmatrix}
4 & 2 & 0\\
2 & 4 & 0\\
1 & 4 & 0
\end{pmatrix}\sim_{f} \begin{pmatrix}
1 & 4 & 0\\
4 & 2 & 0\\
2 & 4 & 0\\
\end{pmatrix}\sim_{f} \begin{pmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 0\\
\end{pmatrix}.$$
Entonces nos quedan las cartesianas
$$\boxed{\begin{array}{l} x=0,\\ y=0. \end{array} }$$
Como el espacio $(\mathbb{Z}_{5})^3$ tiene dimensión tres y el subespacio tiene dos ecuaciones cartesianas, entonces 
la multiplicidad geométrica (esto es, la dimensión de $V_{\lambda=2}$) es 1 y una base es $\{(0,0,1)\}$.<br>

<strong>$V_{\lambda=3}$</strong> 
 
$$A-3I=\begin{pmatrix}
3 & 2 & 0\\
2 & 3 & 0\\
1 & 4 & 4
\end{pmatrix}.$$
Para calcular unas ecuaciones cartesianas más sencillas de $V_{\lambda=3}$ a partir de $(A-3I)X=0$ hacemos operaciones elementales por filas en la matriz anterior:
$$A-3I=\begin{pmatrix}
3 & 2 & 0\\
2 & 3 & 0\\
1 & 4 & 4
\end{pmatrix}\sim_{f} \begin{pmatrix}
1 & 4 & 0\\
0 & 0 & 1\\
0 & 0 & 0\\
\end{pmatrix}.$$
Entonces nos quedan las cartesianas
$$\boxed{\begin{array}{l} x+4y=0,\\ z=0. \end{array} }$$
Como el espacio $(\mathbb{Z}_{5})^3$ tiene dimensión tres y el subespacio tiene dos ecuaciones cartesianas, entonces 
la multiplicidad geométrica (esto es, la dimensión de $V_{\lambda=3}$) es 1 y una base es $\{(1,1,0)\}$.<br>

<strong>$V_{\lambda=4}$</strong> 
 
$$A-4I=\begin{pmatrix}
2 & 2 & 0\\
2 & 2 & 0\\
1 & 4 & 3
\end{pmatrix}.$$
Para calcular unas ecuaciones cartesianas más sencillas de $V_{\lambda=3}$ a partir de $(A-4I)X=0$ hacemos operaciones elementales por filas en la matriz anterior:
$$A-3I=\begin{pmatrix}
3 & 2 & 0\\
2 & 3 & 0\\
1 & 4 & 4
\end{pmatrix}\sim_{f} \begin{pmatrix}
1 & 0 & 4\\
0 & 1 & 1\\
0 & 0 & 0\\
\end{pmatrix}.$$
Entonces nos quedan las cartesianas
$$\boxed{\begin{array}{l} x+4z=0,\\ y=0. \end{array} }$$
Como el espacio $(\mathbb{Z}_{5})^3$ tiene dimensión tres y el subespacio tiene dos ecuaciones cartesianas, entonces 
la multiplicidad geométrica (esto es, la dimensión de $V_{\lambda=3}$) es 1 y una base es $\{(1,4,1)\}$.<br>

Por último, una vez comprobada que la multiplicidad algebraica y geométrica coinciden para cada valor propio escribimos las matriz diagonal $D$ (con los valores propios en la diagonal) y la matriz $P$ (con los vectores propios por columnas) cuidando de que el orden en el que se escriben los valores propios en $D$ corresponda con el orden de los vectores propios asociados en $P$:
$$D=\begin{pmatrix}
2 & 0 & 0\\
0 & 3 & 0\\
0 & 0 & 4
\end{pmatrix}, \hspace{2cm}  P=\begin{pmatrix}
0 & 1 & 1\\
0 & 1 & 4\\
1 & 0 & 1
\end{pmatrix}.$$
</li>

<li>Calcular la matriz $A^{123}$.<br>

Para calcular $A^{123}$ utilizamos la diagonalización que acabamos de realizar para la que se cumple $D=P^{-1}AP$.
Despejando $A$ tendremos $$A=PDP^{-1},$$ y podemos observar que en el producto
$$A^{123}= (PDP^{-1})(PDP^{-1})\cdots (PDP^{-1})$$
los productos $P^{-1}P=I$, y por tanto queda
$$A^{123}=PD^{123}P^{-1}.$$
Además el cálculo de las potencias de una matriz diagonal es muy sencillo, puesto que consiste en elevar a dicha potencia cada uno de los elementos de la diagonal, es decir:
$$D^{123}=\begin{pmatrix}
2^{123} & 0 & 0\\
0 & 3^{123} & 0\\
0 & 0 & 4^{123}
\end{pmatrix}.$$
Se trata entonces de calcular dichas potencias en $\mathbb{Z}_5$, para lo que utilizaremos el Teorema pequeño de Fermat: $a^4=1$ en $\mathbb{Z}_5$.<br>
Como $123=30\cdot 4+3$, entonces $2^{123}=(2^4)^30\cdot 2^3=2^3=3$. Por otro lado, $3^{123}=(3^4)^30\cdot 3^3=3^3=2$ y $4^{123}=(4^4)^30\cdot 4^3=4^3=4$.<br>
Así que 

$$D^{123}=\begin{pmatrix}
3 & 0 & 0\\
0 & 2 & 0\\
0 & 0 & 4
\end{pmatrix}.$$
Solo queda calcular $P^{-1}$ y realizar el producto $PD^{123}P^{-1}$.
$$\begin{align*}
(P|I) & =\left(\begin{array}{ccc|ccc}
0 & 1 & 1 & 1 & 0 & 0\\
0 & 1 & 4 & 0 & 1 & 0\\
1 & 0 & 1 & 0 & 0 & 1
\end{array}\right)\sim_f \left(\begin{array}{ccc|ccc}
1 & 0 & 1 & 0 & 0 & 1\\
0 & 1 & 1 & 1 & 0 & 0\\
0 & 1 & 4 & 0 & 1 & 0\\
\end{array}\right)\sim_f  \left(\begin{array}{ccc|ccc}
1 & 0 & 1 & 0 & 0 & 1\\
0 & 1 & 1 & 1 & 0 & 0\\
0 & 0 & 3 & 4 & 1 & 0\\
\end{array}\right) \\ &
\sim_f  \left(\begin{array}{ccc|ccc}
1 & 0 & 1 & 0 & 0 & 1\\
0 & 1 & 1 & 1 & 0 & 0\\
0 & 0 & 1 & 3 & 2 & 0\\
\end{array}\right)\sim_f \left(\begin{array}{ccc|ccc}
1 & 0 & 0 & 2 & 3 & 1\\
0 & 1 & 0 & 3 & 3 & 0\\
0 & 0 & 1 & 3 & 2 & 0\\
\end{array}\right)=(I|P^{-1}).
\end{align*}$$
Por último:
$$A^{123}=\begin{pmatrix}
0 & 1 & 1\\
0 & 1 & 4\\
1 & 0 & 1
\end{pmatrix}\begin{pmatrix}
3 & 0 & 0\\
0 & 2 & 0\\
0 & 0 & 4
\end{pmatrix}\begin{pmatrix}
2 & 3 & 1\\
3 & 3 & 0\\
3 & 2 & 0
\end{pmatrix}=\begin{pmatrix}
3 & 4 & 0\\
4 & 3 & 0\\
3 & 2 & 3
\end{pmatrix}.$$</li>

<li>Diagonalizar la matriz $A^{-1}$.<br>

Para diagonalizar $A^{-1}$ basta observar que como $D=P^{-1}AP$ entonces $D^{-1}=P^{-1}A^{-1}P$, luego la matriz diagonal será $D^{-1}$:
$$D^{-1}=\begin{pmatrix}
2^{-1} & 0 & 0\\
0 & 3^{-1} & 0\\
0 & 0 & 4^{-1}
\end{pmatrix}=\begin{pmatrix}
3 & 0 & 0\\
0 & 2 & 0\\
0 & 0 & 4
\end{pmatrix},$$ 
y la matriz de paso es la misma, $P$.</li>

</ol>
</details>
</article>

<article>
Sea la matriz 
$$
A=\left(\begin{array}{cccc}
 1 & a & 2 & -1\\
0 & 1 & 3 & 4\\
 0 & 0 & 2 & b\\
 0 & 0 & 0 & 2\\
\end{array}
\right)
.$$
Estudiar para qué valores de los parámetros $a$ y $b$ es
diagonalizable.

<details>
<summary>Solución</summary>

Necesitamos calcular los valores propios y sus multiplicidades algebraica y geométrica.
Los valores propios son fáciles:
$$
|A-\lambda I|=\left|\begin{array}{cccc}
 1-\lambda & a & 2 & -1\\
0 & 1-\lambda & 3 & 4\\
 0 & 0 & 2-\lambda & b\\
 0 & 0 & 0 & 2-\lambda\\
\end{array}
\right|=(1-\lambda)^2(2-\lambda)^2.$$
Los valores propios son $1$ y $2$ con multiplicidades algebraicas $2$ para cada uno.<br>

<strong>$V_{\lambda=1}$</strong> 
$$
A-I=\left(\begin{array}{cccc}
 0 & a & 2 & -1\\
0 & 0 & 3 & 4\\
 0 & 0 & 1 & b\\
 0 & 0 & 0 & 1\\
\end{array}
\right).
$$
Para que tenga rango dos (y por tanto la dimensión de $V_{\lambda=1}$ sea también dos) debe ser $a=0$.<br>

<strong>$V_{\lambda=2}$</strong> 
$$
A-2I=\left(\begin{array}{cccc}
 -1 & a & 2 & -1\\
0 & -1 & 3 & 4\\
 0 & 0 & 0 & b\\
 0 & 0 & 0 & 0\\
\end{array}
\right).
$$
Para que tenga rango dos (y por tanto la dimensión de $V_{\lambda=2}$ sea también dos) debe ser $b=0$.<br>

Concluimos que solo es diagonalizable en el caso $a=b=0$.

</details>
</article>

<article>
Sea $f:(\mathbb{Z}_{13})^3 \longrightarrow  (\mathbb{Z}_{13})^3 $ la aplicación lineal dada
por:
$$f(x,y,z)=(7x+12y+4z, x+6y+3z, 5x+6y+12z).$$
<ol type="a">
<li>Halla la matriz de $f$ en la base canónica (llamémosla $A$).</li>
<li>Estudia si $f$ es diagonalizable, y en caso afirmativo halla una base de vectores propios.</li>
<li>Calcula $A^{2431}$.</li>
<li>Calcula $f^{2432}(1,2,3)$.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Hallar la matriz de $f$ en la base canónica.<br>

Para calcular la matriz asociada calculamos las imágenes de los vectores de la base canónica:
$$\begin{array}{l}
f(1,0,0)=(7,1,5),\\
f(0,1,0)=(12,6,6),\\
f(0,0,1)=(4,3,12).
\end{array}$$
Podemos, por simplificar cálculos posteriores, sustituir que $12=-1$ en $\mathbb{Z}_{13}$, y nos queda la matriz
$$A=M_{B_c}(f)=\begin{pmatrix}
7 & -1 & 4\\
1 & 6 & 3\\
5 & 6 &-1
\end{pmatrix}.$$</li>

<li>Estudiar si $f$ es diagonalizable, y hallar una base de vectores propios.<br>

Calculamos los valores propios, mediante la ecuación característica:
$$\begin{align*}
\left| \begin{array}{ccc}
7-\lambda & -1 & 4\\
1 & 6-\lambda & 3\\
5 & 6 &-1-\lambda
\end{array}\right| & 
=(7-\lambda)(6-\lambda)(-1-\lambda)-2-2-7(6-\lambda)-5(7-\lambda)+(-1-\lambda)\\ &
=-\lambda^3-\lambda^2+8\lambda -7.
\end{align*}$$
Calculamos las raíces de este polinomio (lo cual es laborioso) y  obtenemos que son $\lambda=5$ con multiplicidad algebraica 1 y $\lambda=-3(=10)$ con multiplicidad algebraica 2.<br>

Debemos calcular la multiplicidad geométrica de $\lambda=-3$ para poder decidir si es o no diagonalizable. Para ello calculamos el subespacio propio correspondiente:
$$(A+3I)=\begin{pmatrix}
10 & -1 & 4\\
1 & 9 & 3\\
5 & 6 & 2
\end{pmatrix}\sim_f \begin{pmatrix}
1 & 9 & 3\\
0 & 0 & 0\\
0 & 0 & 0\\
\end{pmatrix}.$$
Luego nos queda una única ecuación cartesiana que es $x+9y+3z=0$ y por tanto la multiplicidad geométrica (esto es, la dimensión de $V_{\lambda=2}$) es 2, así que la matriz es diagonalizable.<br>
Calculamos una base de  $V_{\lambda=-3}$:
$$\{ (4,1,0),(10,0,1) \}.$$

Necesitamos también una base de $V_{\lambda=5}$:
 $$(A-5I)=\begin{pmatrix}
2 & -1 & 4\\
1 & 1 & 3\\
5 & 6 & -6
\end{pmatrix}\sim_f 
\begin{pmatrix}
1 & 0 & -2\\
0 & 1 & 5\\
0 & 0 & 0\\
\end{pmatrix}.$$
Nos quedan las ecuaciones $V_{\lambda=5}\equiv \boxed{\begin{array}{l}
x-2z=0,\\
y+5z=0.\end{array} }$ y una base es $\{(2,-5,1)\}$.<br>
Luego la solución al problema de diagonalización es:
$$ D=\left(\begin{array}{ccc}
5 & 0 & 0\\
0 & 10 & 0\\
0 & 0 &  10
\end{array}\right)=\left(\begin{array}{ccc}
5 & 0 & 0\\
0 & -3 & 0\\
0 & 0 & -3
\end{array}\right), \hspace{1cm}  P=\left(\begin{array}{ccc}
2 & 4 & 10\\
-5 & 1 & 0\\
1 & 0 &  1
\end{array}\right).$$</li>

<li>Calcular $A^{2431}$.<br>
Para calcular la potencia pedida utilizamos la diagonalización:
$$D=P^{-1}AP \text{ o bien }  A=PDP^{-1},$$
que nos permite deducir que
$$A^{2431}=PD^{2431}P^{-1}.$$
Calculamos 
$$D^{2431}=\left(\begin{array}{ccc}
5^{2431} & 0 & 0\\
0 & 10^{2431} & 0\\
0 & 0 &  10^{2431}
\end{array}\right),$$
para lo que hemos realizado los cálculos $5^{703}, 10^{703}$ en $\mathbb{Z}_{13}$ mediante el Teorema pequeño de Fermat: $a^{12}=1$ en $\mathbb{Z}_{13}$. Obtenemos así $5^{2431}=5^{202\cdot 12+7}=5^7=8$ y además $10^{2431}=10^{202\cdot 12+7}=10^7= 10$. Y obtenemos
$$D^{2431}=\left(\begin{array}{ccc}
8 & 0 & 0\\
0 & 10 & 0\\
0 & 0 &  10
\end{array}\right).$$
Necesitamos también $P^{-1}$:
$$\begin{align*}
(P|I) & =\left(\begin{array}{ccc|ccc}
2 & 4 & 10 & 1 & 0 & 0\\
-5 & 1 & 0 & 0 & 1 & 0\\
1 & 0 &  1 & 0 & 0 & 1
\end{array}\right)\sim_f\left(\begin{array}{ccc|ccc}
1 & 0 &  1 & 0 & 0 & 1\\
0 & 4 & 8 & 1 & 0 & -2\\
0 & 1 & 5 & 0 & 1 & 5\\
\end{array}\right) \\ &
\sim_f \left(\begin{array}{ccc|ccc}
1 & 0 &  1 & 0 & 0 & 1\\
0 & 1 & 5 & 0 & 1 & 5\\
0 & 0 & 1 & 1 & -4 & 4\\
\end{array}\right)\sim_f
\left(\begin{array}{ccc|ccc}
1 & 0 &  0 & -1 & 4 & -3\\
0 & 1 & 0 & -5 & -5 & -2\\
0 & 0 & 1 & 1 & -4 & 4\\
\end{array}\right).\end{align*}
$$
Luego 
$$A^{2431}=PD^{2431}P^{-1}=\left(\begin{array}{ccc}
2 & 4 & 10\\
-5 & 1 & 0\\
1 & 0 &  1
\end{array}\right)\left(\begin{array}{ccc}
8 & 0 & 0\\
0 & 10 & 0\\
0 & 0 &  10
\end{array}\right)\left(\begin{array}{ccc}
 -1 & 4 & -3\\
-5 & -5 & -2\\
 1 & -4 & 4\\
\end{array}\right).$$</li>

<li>Calcula $f^{2432}(1,2,3)$.<br>

Basta realizar la operación $f^{2432}(1,2,3)=A^{2431}(1,2,3)^T$.</li>

</ol>
</details>
</article>

<article>
Sea $f:(\mathbb{Z}_{5})^3\longrightarrow (\mathbb{Z}_{5})^3$ la
aplicación lineal dada por:
$$
f(x,y,z)=(4z,2x+2y+z,x)
$$

<ol type="a">
<li>Halla la matriz de $f$ en la base canónica (llamémosla $A$).</li>
<li>Estudia si $f$ es diagonalizable, y en caso afirmativo halla una base de vectores propios.</li>
<li>Calcula $A^{703}$.</li>
<li>Halla $f^{704}(1,2,3)$.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Hallar la matriz de $f$ en la base canónica.<br>
Calculamos las imágenes de los vectores de la base canónica:
$$\begin{array}{l}
f(1,0,0)=(0,2,1),\\
f(0,1,0)=(0,2,0),\\
f(0,0,1)=(4,1,0).
\end{array}$$
Así la matriz es 
$$A=M_{B_c}(f)=
\left(\begin{array}{ccc}
0 & 0 & 4\\
2 & 2 & 1\\
 1 & 0 & 0\\
\end{array}\right).$$</li>

<li>Estudiar si $f$ es diagonalizable y hallar una base de vectores propios.<br>
Calculamos los valores propios y sus multiplicidades algebraica y geométrica:
$$|A-\lambda I|=\left| \begin{array}{ccc}
-\lambda & 0 & 4\\
2 & 2-\lambda & 1\\
 1 & 0 & -\lambda\\
\end{array}\right|=(2-\lambda)[(-\lambda)^2-4)]=(2-\lambda)(\lambda^2-4).$$
Las raíces de $\lambda^2-4=0$ son $\lambda=2$ y $\lambda=3(=-2)$ en $\mathbb{Z}_5$. Así el valor propio $\lambda=2$ tiene multiplicidad algebraica 2 y $\lambda=3$ tiene multiplicidad algebraica 1.<br>
Calculamos $V_{\lambda=2}$:
$$
A-2I =
\left(\begin{array}{ccc}
-2 & 0 & 4\\
2 & 0 & 1\\
 1 & 0 & -2\\
\end{array}\right)\sim_f \left(\begin{array}{ccc}
 1 & 0 & -2\\
0 & 0 & 0\\
0 & 0 & 0\\
\end{array}\right).$$
Luego nos queda una única ecuación cartesiana que es $x-2z=0$ y por tanto la multiplicidad geométrica (esto es, la dimensión de $V_{\lambda=2}$) es 2, así que la matriz es diagonalizable.<br>
Calculamos una base de  $V_{\lambda=2}$:
$\{ (0,1,0),(2,0,1) \}$.<br>
Nos queda calcular una base de $V_{\lambda=3}$:
$$A-3I=
\left(\begin{array}{rrr}
-3 & 0 & 4\\
2 & -1 & 1\\
 1 & 0 & -3\\
\end{array}\right)\sim_f 
\left(\begin{array}{rrr}
 1 & 0 & -3\\
 0 & 1 & 3\\
0 & 0 & 0\\
\end{array}\right).$$
Nos quedan las ecuaciones$V_{\lambda=3}\equiv \boxed{\begin{array}{l}
x-3z=0,\\
y+3z=0.\end{array} }$. Además una base es $\{(3,2,1)\}$.<br>
Luego la solución al problema de diagonalización es:
$$D=\left(\begin{array}{rrr}
2 & 0 & 0\\
0 & 2 & 0\\
 0 & 0 & 3\\
\end{array}\right), \hspace{1cm}
 P= \left(\begin{array}{rrr}
0 & 2 & 3\\
1 & 0 & 2\\
 0 & 1 & 1\\
\end{array}\right).$$</li>

<li>Calcular $A^{703}$.<br>
Para calcular la potencia pedida utilizamos la diagonalización:
$$D=P^{-1}AP \text{ o bien }  A=PDP^{-1},$$
que nos permite deducir que
$$A^{703}=PD^{703}P^{-1}.$$
Calculamos 
$$D^{703}=\left(\begin{array}{ccc}
2^{703} & 0 & 0\\
0 & 2^{703} & 0\\
0 & 0 &  3^{703}
\end{array}\right),$$
para lo que realizamos los cálculos en $\mathbb{Z}_5$, mediante el uso del Teorema pequeño de Fermat: $2^{703}=2^{175\cdot 4+3}=2^3= 3$, y también $3^{703}=3^{175\cdot 4+3}=3^3= 2$. Obtenemos así:
$$D^{703}=\left(\begin{array}{ccc}
3 & 0 & 0\\
0 & 3 & 0\\
0 & 0 &  2
\end{array}\right).$$
También necesitamos calcular $P^{-1}$:
$$(P|I)= \left(\begin{array}{ccc|ccc}
0 & 2 & 3 & 1 & 0 & 0\\
1 & 0 & 2 & 0 & 1 & 0\\
 0 & 1 & 1 & 0 & 0 & 1\\
\end{array}\right)\sim_f \left(\begin{array}{ccc|ccc}
1 & 0 & 0 & 3 & 1 & 4\\
0 & 1 & 0 & 4 & 0 & 3\\
 0 & 0 & 1 & 1 & 0 & 3\\
\end{array}\right)=(I|P^{-1}).$$
Luego 
$$A^{703}=PD^{703}P^{-1}=\left(\begin{array}{rrr}
0 & 2 & 3\\
1 & 0 & 2\\
 0 & 1 & 1\\
\end{array}\right)\left(\begin{array}{ccc}
3 & 0 & 0\\
0 & 3 & 0\\
0 & 0 &  2
\end{array}\right)\left(\begin{array}{ccc}
 3 & 1 & 4\\
 4 & 0 & 3\\
1 & 0 & 3\\
\end{array}\right)=\left(\begin{array}{rrr}
0 & 0 & 1\\
0 & 3 & 4\\
 4 & 0 & 0\\
\end{array}\right).$$</li>

<li>Hallar $f^{703}(1,2,3)$.<br>
Basta realizar la operación 
$$f^{703}(1,2,3)=A^{703}(1,2,3)^T=
\left(\begin{array}{rrr}
0 & 0 & 1\\
0 & 3 & 4\\
 4 & 0 & 0\\
\end{array}\right)
\left(\begin{array}{rrr}
1\\
2\\
3\\
\end{array}\right)=
\left(\begin{array}{rrr}
3\\
18\\
4\\
\end{array}\right).$$</li>

</ol>
</details>
</article>

<article>
Sea $f:U+W=\mathbb{R}^3 \to U+W=\mathbb{R}^4$ la aplicación lineal que, respecto de las bases canónicas, viene dada por la matriz
$$A=\begin{pmatrix}
1 & -1 & 0\\
1 & 2 & 1 \\
0 & 1 & 1 \\
1 & 1 & 1
\end{pmatrix}
$$

<ol type="a">
<li>Determina la base más sencilla de $\operatorname{Im}(f)$ y unas ecuaciones cartesianas del $\operatorname{ker}(f)$.</li>
<li>Determina para qué valores de $a$ el vector $(a,1,a,a)$ pertenece a $\operatorname{Im}(f)$.</li>
<li>Calcula la matriz asociada a $f$ respecto de las bases $\overline{B}$ de $\mathbb{R}^3$ y $B_c$ de $\mathbb{R}^4$, siendo
$$\overline{B}=\{ (1,-1,-1),(0,1,1),(0,0,1)\}.$$</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Determinar la base más sencilla de $\operatorname{Im}(f)$ y unas ecuaciones cartesianas del $\operatorname{ker}(f)$.<br>
Para calcular la base más sencilla de la Imagen realizamos operaciones elementales por columnas hasta obtener la forma de Hermite por columnas:
$$ \begin{pmatrix}
1 & -1 & 0\\
1 & 2 & 1 \\
0 & 1 & 1 \\
1 & 1 & 1
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0\\
1 & 3 & 1 \\
0 & 1 & 1 \\
1 & 2 & 1
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0\\
0 & 1& 0 \\
-1 & 1 & -2 \\
0 & 1 & -1
\end{pmatrix}\sim_c \begin{pmatrix}
1 & 0 & 0\\
0 & 1& 0 \\
0 & 0 & 1 \\
1/2 & 1/2 & 1/2
\end{pmatrix}.
$$
Luego la base más sencilla de $\operatorname{Im}(f) $ es $\{(1,0,0,1/2),(0,1,0,1/2),(0,0,1,1/2)\}$.<br>
Para obtener las cartesianas del núcleo imponemos $AX=0$:
$$\operatorname{ker}(f)\equiv \left\{ \begin{array}{rl}
x-y&=0,\\
x+2y+z&=0,\\
y+z&=0,\\
x+y+z&=0.
\end{array}\right. \sim_f \left\{ \begin{array}{rl}
x-y&=0,\\
y+z&=0,\\
x&=0.
\end{array}\right. \sim_f \left\{ \begin{array}{rl}
x&=0,\\
y&=0,\\
z&=0.
\end{array}\right. $$ 
</li>

<li>Determinar para qué valores de $a$ el vector $(a,1,a,a)$ pertenece a $\operatorname{Im}(f)$.<br>
Para que $(a,1,a,a)\in \operatorname{Im}(f)$ tiene que ser combinación lineal de los vectores de una base, por ejemplo la más sencilla que hemos calculado, luego el rango de la matriz que forman los cuatro vectores debe ser tres, y por tanto el determinante siguiente debe ser cero:
$$\left|\begin{array}{cccc}
1 & 0 & 0 & a \\
0 & 1 & 0 & 1\\
0 & 0 & 1 & a\\
1/2 & 1/2 & 1/2 & a
\end{array}\right|=\left|\begin{array}{cccc}
1 & 0 & 0 & a \\
0 & 1 & 0 & 0\\
0 & 0 & 1 & a\\
1/2 & 1/2 & 1/2 & a-1/2
\end{array}\right|= \left|\begin{array}{ccc}
1 &  0 & a \\
0 &  1 & a\\
1/2  & 1/2 & a-1/2
\end{array}\right|=\frac{1}{2}(a-1)-\frac{1}{2}a=-\frac{1}{2}.$$
Como siempre es distinto de cero, este vector no está en la imagen de $f$ para ningún valor de $a$.
</li>

<li>Calcular la matriz asociada a $f$ respecto de las bases $\overline{B}$ de $\mathbb{R}^3$ y $B_c$ de $\mathbb{R}^4$.<br>
Usamos el "método de los cuatro pasos", comenzando calculando la imagen de los vectores de la base $\overline{B}$ multiplicando por la matriz $A$ cada uno de los vectores:
$$ \begin{pmatrix}
1 & -1 & 0\\
1 & 2 & 1\\
0 & 1 & 1\\
1 & 1 & 1
\end{pmatrix}\begin{pmatrix}
1\\ -1\\ -1
\end{pmatrix}=  \begin{pmatrix}
2\\ -2\\ -2 \\ -1
\end{pmatrix}$$
con lo que $f(1,-1,-1)=(2,-2,-2,-1)$, del mismo modo $f(0,1,1)=(-1,3,2,2)$, $f(0,0,1)=(0,1,1,1)$; como se obtienen las coordenadas en la base canónica solo queda escribirlos por columnas:
$$M(f,\overline{B}, B_c)=\begin{pmatrix}
2 & -1 & 0\\
-2 & 3 & 1\\
-2 & 2 & 1\\
-1 & 2 & 1
\end{pmatrix}.$$
</li>

</ol>
</details>
</article>

