---
layout: page
title: Matrices y sistemas de ecuaciones
---

# Matrices con coeficientes en un cuerpo

*Este guión es una adaptación de los guiones de [ALEM](https://www.ugr.es/~pedro/alem/).*


## Matrices

Sean $I=\lbrace 1,2,\dots,m\rbrace$ y $J=\lbrace 1,2,\dots,n\rbrace.$ Una *matriz* de orden $m\times n$ sobre un cuerpo $K$ es una aplicación 

$$
 A:I\times J\to K,\ (i,j)\mapsto a_{ij}.
$$

Normalmente a la matriz $A$ la representaremos de la siguiente forma

$$
 A=\begin{pmatrix}
    a_{11} & a_{12} & \ldots & a_{1n}\\
    a_{21} & a_{22} & \ldots & a_{2n}\\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} & a_{m2} & \ldots & a_{mn}
   \end{pmatrix},
$$

y a veces simplemente escribiremos $A=(a_{ij})$, si queda claro dónde varían $i$ y $j.$ Diremos que $A$ es una matriz con $m$ filas y $n$ columnas.

Una submatriz de $A$ no es más que la matriz que se obtiene cuando escogemos un número de filas y columnas de $A$ (o bien cuando eliminamos algunas filas y columnas).

Denotaremos por $\mathcal M_{m\times n}(K)$ al conjunto de las matrices de orden $m\times n$ sobre $K.$ El conjunto $\mathcal M_{m\times n}(K)$ con la suma coordenada a coordenada tiene estructura de grupo, esto es, la suma es asociativa, tiene elemento neutro, toda matriz tiene inversa y es conmutativa.

$$
 \begin{pmatrix}
    a_{11} & a_{12} & \ldots & a_{1n}\\
    a_{21} & a_{22} & \ldots & a_{2n}\\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1} & a_{m2} & \ldots & a_{mn}
   \end{pmatrix} +
 \begin{pmatrix}
    b_{11} & b_{12} & \ldots & b_{1n}\\
    b_{21} & b_{22} & \ldots & b_{2n}\\
    \vdots & \vdots & \ddots & \vdots \\
    b_{m1} & b_{m2} & \ldots & b_{mn}
   \end{pmatrix} =
 \begin{pmatrix}
    a_{11}+b_{11} & a_{12}+b_{12} & \ldots & a_{1n}+b_{1n}\\
    a_{21}+b_{21} & a_{22}+b_{22} & \ldots & a_{2n}+b_{2n}\\
    \vdots & \vdots & \ddots & \vdots \\
    a_{m1}+b_{m1} & a_{m2}+b_{m2} & \ldots & a_{mn}+b_{mn}
   \end{pmatrix}.
$$

Sea $A=(a_{ij})\in \mathcal M_{m\times n}(K)$ y $B=(b_{jk})\in \mathcal M_{n\times p}(K).$ Entonces podemos definir el producto de $A$ y $B$ como $AB=C=(c_{ik})\in \mathcal M_{m\times p}(K)$ con 

$$c_{ik}=a_{i1}b_{1k}+a_{i2}b_{2k}+\cdots + a_{in}b_{nk}.$$

Una matriz de orden $n\times n$ diremos que es una *matriz cuadrada* de orden $n.$ La terna $(\mathcal M_{n\times n}(K),+,\cdot)$ es un anillo.

El elemento neutro del producto en $\mathcal M_{n\times n}(K)$ es la *matriz identidad*, que es la matriz que tiene todas sus entradas cero salvo en la diagonal que tiene unos (cero es el elemento neutro de $K$ para la suma, y uno el neutro para el producto). A dicha matriz la denotamos por $I_n$, o simplemente $I$ cuando $n$ queda claro en el contexto.

Una matriz $A\in \mathcal M_{n\times n}(K)$ es *regular* si tiene inversa para el producto, esto es, si existe $B$ tal que $AB=BA=I_n.$ En dicho caso, a la matriz $B$ se le denota por $A^{-1}.$ Si $A$ y $B$ tienen inversa,

$$
(AB)^{-1}=B^{-1}A^{-1}.
$$

## Matrices con formas especiales

Una matrix $A=(a _ {ij})\in \mathcal{M} _ {n\times n}(K)$ decimos que es *triangular superior* si $a_{ij}=0$ para $i>j$, y decimos que es *triangular inferior* si $a_{ij}=0$ para $i < j.$ Si la matriz es cuadrada, a los elementos $a_{ii}$ se les conoce como elementos de la diagonal. La matriz es diagonal si $a_{ij}=0$ siempre que $i\neq j.$

El pivote de la fila $i$-ésima de A, si ésta tiene alguna entrada distinta de cero, es la primera entrada no nula de dicha fila, a saber, es $a_{ij}\neq 0$ con $j$ mínimo verificando esa condición. 

Decimos que $A$ está en *forma normal o escalonada* por filas (de forma análoga se define por columnas) si 

- todas las filas nulas (todas las entradas son ceros) están debajo de las que tienen entradas no nulas.

- si $a_{ij}$ y $a_{kl}$ son los pivotes de la fila $i$-ésima y $k$-ésima, respectivamente, con $i< k$, entonces $j< l.$

Diremos que está en *forma escalonada reducida* por filas si además todos los pivotes son uno y son los únicos elementos no nulos de las columnas que los contienen.

Si $A=(a_{ij})\in \mathcal M_{m\times n}(K)$, la matriz traspuesta de $A$ es 

$$A^t =
  \begin{pmatrix}
    a_{11} & a_{21} & \ldots & a_{n1}\\
    a_{12} & a_{22} & \ldots & a_{n2}\\
    \vdots & \vdots & \ddots & \vdots \\
    a_{1n} & a_{2n} & \ldots & a_{mn}
   \end{pmatrix}\in \mathcal M_{n\times m}(K),
$$

esto es, la matriz que se obtiene a partir de $A$ intercambiando filas por columnas. 

Claramente, $(A^t)^t=A.$

Dadas $A$ y $B$ dos matrices, $(AB)^t=B^tA^t$ (siempre que esos productos tengan sentido).

Decimos que $A$ es *simétrica* si $A^t=A$, y *antisimétrica* si $A^t=-A.$

## Equivalencia por filas

Dos matrices $A, B\in \mathcal{M} _ {m\times n}(K)$ se dice que son *equivalentes por filas*, $A\sim_f B$, si podemos llegar de $A$ a $B$ realizando una serie de transformaciones elementales por filas. Estas transformaciones son de tres tipos:

- intercambio de filas,
- multiplicar una fila por un elemento no nulo del cuerpo $K$,
- sumarle a una fila un múltiplo de otra fila.

### Resultado

Toda matriz $A$ es equivalente por filas a una matriz escalonada reducida por filas $H$, $A\sim_f H.$ Esta matriz es única.


<div class="sage">
<script type="text/x-sage">
A=matrix(3,4,range(1,13))
show(A,"~",A.rref())
</script>
</div>  


###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/1-1.html) 

Llamamos $E _ {ij}\in \mathcal{M} _ n(K)$ a la matriz que se obtiene al intercambiar la fila $i$-ésima con la $j$-ésima en la matriz identidad. Cambiar la fila $i$-ésima con la $j$-ésima en $A$ se corresponde con calcular $E_{ij}A.$ Claramente, $E_{ij}^{-1}=E_{ij}.$

Sea ahora $E_i(k)\in \mathcal{M} _ n(K)$ la matriz que se obtiene al multiplicar la fila $i$-ésima de la matriz identidad por $k\in K$, $k\neq 0.$ Multiplicar la fila $i$-ésima de $A$ por $k$ es lo mismo que calcular $E_i(k)A.$ Se tiene que $E_{i}(k)^{-1}=E_i(1/k).$

La matriz $E_{ij}(k)$ es la matriz que se obtiene sumando a la fila $i$-ésima de la identidad la fila $j$-ésima multiplicada por $k.$ Así, para sumarle a la fila $i$-ésima de $A$ la fila $j$-ésima multiplicada por $k$, calculamos $E_{ij}(k)\times A.$ Tenemos además que $E_{ij}(k)^{-1}=E_{ij}(-k).$

A las matrices de la forma $E_{ij}$, $E_i(k)$, $k\neq 0$, y $E_{ij}(k)$ se les llama *matrices elementales*. 

Por tanto, si $A\sim_f H$, entonces existe $P$ tal que $PA=H$, y además $P$ es un producto de matrices elementales. 

Podemos calcular $P$ de la siguiente forma. Partimos de la matriz $(A \mid I_m)$, la matriz cuyas primeras $n$ columnas son las de $A$, y cuyas últimas columnas son las de $I_m.$ Si $A\sim_f H$ y $H$ es la forma escalonada reducida de $A$, entonces 
$$(A \mid I_m)\sim_f (H \mid P).$$

Nótese que $P$ es un producto de matrices elementales, y, por tanto, tiene inversa y su inversa también es un producto de matrices elementales.

<div class="sage">
<script type="text/x-sage">
A=matrix(3,4,range(1,13))
AI=block_matrix([[A,matrix.identity(3)]])
AIr=AI.rref()
show(AI,"~",AIr)
#comprobamos, primero extraemos P
P=AIr[:,4:]
show(P,A,"=",P*A)
</script>
</div>  


###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/1-4.html) 

Si $A\sim_f B$, entonces tanto $A$ como $B$ tienen la misma forma escalonada reducida; llamémosla $H.$ De esta forma, existen $P$ y $Q$ regulares tales que $H=PA=QB$, y por tanto $A=P^{-1}QB.$ 

###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/1-6.html) 


## Cálculo de inversas usando operaciones elementales

Si $A\in\mathcal{M} _ n(K)$ es una matriz cuadrada y $H$ es su forma escalonada por filas, entonces $PA=H$ con $P$ un producto de matrices elementales. 

La matriz $A$ tiene inversa si y sólo si $H$ es la matriz identidad, y por tanto, $A$ es un producto de matrices elementales. Para calcular la inversa de $A$, podemos usar las operaciones elementales por filas que llevan de $A$ a $H=I_n$, 
$$(A\mid I_n)\sim_f (I_n\mid A^{-1}).$$


<div class="sage">
<script type="text/x-sage">
A=matrix([[1,0,1],[0,1,-1],[1,-1,0]])
AI=block_matrix([[A,matrix.identity(3)]])
AIr=AI.rref()
show(AI,"~",AIr)
#comprobamos, primero extraemos P
P=AIr[:,3:]
show(P,A,"=",P*A)
#en sage podemos calcular así la inversa
show(A.inverse())
</script>
</div>  


###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/1-5.html) 


## Rango de una matriz

Se define el *rango* de una matriz $A\in\mathcal{M}_{m\times n}(K)$, $\operatorname{rg}(A)$, como el número de filas no nulas de su forma escalonada reducida por filas. 

Claramente, $\operatorname{rg}(A)\le \min(m,n).$ 

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,0,1],[0,1,-1],[1,-1,0]])
show(A," ~ ",A.rref()," de rango ",A.rank())
A=matrix(3,4,range(1,13))
show(A," ~ ",A.rref()," de rango ",A.rank())
</script>

</div>

Dadas $A,B\in \mathcal{M} _ {m\times n}(K)$,  

$$
\operatorname{rg}(A+B)
=\operatorname{rg}
\begin{pmatrix} 
A+B \\
\hline
0 
\end{pmatrix}
\le \operatorname{rg}
\begin{pmatrix} 
A+B \\ 
\hline 
B 
\end{pmatrix} 
= \operatorname{rg}
\begin{pmatrix}
A \\ 
\hline 
B 
\end{pmatrix}
\le \operatorname{rg}(A)+\operatorname{rg}(B).
$$ 

Si $A\in \mathcal{M}_n(K)$, entonces $A$ tiene inversa sí y sólo si su rango es $n.$


## Matrices equivalentes

Dadas $A,B\in \mathcal{M}_{m\times n}(K)$, decimos que $A$ y $B$ son equivalentes, $A\sim B$, si podemos llegar de $A$ a $B$ efectuando operaciones elementales por filas y por columnas. Por tanto, $A$ y $B$ son equivalentes si y sólo si existen dos matrices regulares $P$ y $Q$ tales que $PAQ=B.$

Una matriz de rango $r$ es siempre equivalente a una matriz de la forma

$$
\left(\begin{array}{c | c}
I_r & 0 \\ 
\hline
0 & 0
\end{array}\right).
$$

Por tanto, dos matrices son equivalentes si y sólo si tienen el mismo rango.

Además, $\operatorname{rg}(A)=\operatorname{rg}(A^t).$

Dadas dos matrices $A$ y $B$, consideramos $H$ y $C$ las formas escalonadas reducidas por filas y columnas de $A$ y de $B$, respectivamente. Tenemos así que existen $P$ y $Q$ regulares tales que $PA=H$ y $BQ=C.$ La matriz $H$ tiene $\operatorname{rg}(A)$ filas no nulas, y $C$ tiene $\operatorname{rg}(B)$ columnas no nulas. Así $PABQ=HC$, y por tanto $AB$ y $HC$ son equivalentes, por lo que $\operatorname{rg}(AB)=\operatorname{rg}(HC).$ De esta forma se prueba que 

$$
\operatorname{rg}(AB)\le \min(\operatorname{rg}(A),\operatorname{rg}(B)).
$$

## Sistemas de ecuaciones y matrices

Un *sistema de ecuaciones lineales* con $n$ incógnitas sobre un cuerpo $K$ es una expresión de la forma 

$$\left\lbrace
\begin{matrix}
a_{11}x_1+\cdots+a_{1n}x_n=b_1,\\
\vdots \\
a_{m1}x_1+\cdots+a_{mn}x_n=b_m.
\end{matrix}
\right.
$$

Los elementos $a_{ij}\in K$ son los *coeficientes del sistema*, los $b_i\in K$ son los *términos independientes*, y las $x_i$ son las incógnitas. Una *solución* es una $n$-upla $(s_1,\ldots,s_n)\in K^n$ tal que $x_1=s_1,\ldots, x_n=s_n$ verifica las igualdades del sistema.

Las $m$ igualdades del sistema anterior se pueden expresar como una única igualdad entre matrices,

$$
\begin{pmatrix}
 a_{11} & \ldots & a_{1n}\\
\vdots & \ddots & \vdots \\
a_{m1} & \ldots & a_{mn}
\end{pmatrix} 
\begin{pmatrix}
x_1\\ 
\vdots \\ 
x_n
\end{pmatrix}=
\begin{pmatrix}
b_1\\ 
\vdots \\ 
b_m
\end{pmatrix},
$$

a la que llamaremos *expresión matricial del sistema*. A dichas matrices se les llama *matriz de coeficientes*,  *matriz incógnita* y *matriz de términos independientes*, respectivamente.

La *matriz ampliada del sistema* es 

$$
\begin{pmatrix}
 a_{11} & \ldots & a_{1n} & b_1\\
\vdots & \ddots & & \vdots  \\
a_{m1} & \ldots & a_{mn} & b_m
\end{pmatrix}.
$$

Normalmente denotaremos a esta matriz por $(A \mid b).$

Si un sistema tiene solución diremos que es *compatible*, y en caso contrario *incompatible*. Si tiene una única solución, es un sistema *compatible determinado*, y si tiene más de una solución decimos que es un sistema *compatible indeterminado*. 

Dos sistemas de ecuaciones lineales sobre un cuerpo y con igual número de incógnitas son *equivalentes* si tienen las mismas soluciones.

### Operaciones elementales

- Si intercambiamos de posición dos ecuaciones de un sistema, obtenemos un sistema equivalente.

- Si multiplicamos una ecuación por un escalar no nulo, obtenemos un sistema equivalente.

- Si a una ecuación le sumamos otra multiplicada por un escalar, también obtenemos un sistema equivalente al original.

###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/1-2.html) 


### Teorema de Rouché-Frobenius

Sea $AX=b$ la expresión matricial de un sistema de ecuaciones lineales con $n$ incógnitas. 

- El sistema es compatible si y sólo si $\operatorname{rg}(A)=\operatorname{rg}(A \mid b).$

- El sistema es compatible determinado si y sólo si $\operatorname{rg}(A)=\operatorname{rg}(A \mid b)=n.$

###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/1-8.html) 


## Determinantes

Dada $A=(a_{ij})\in \mathcal M_{n\times n}(K)$, definimos $\vert A\vert$, el determinante de $A$, recursivamente de la siguiente forma.

Para $n=1$, $\vert (a_{11})\vert =a_{11}$ (el determinante de una matriz de orden $1\times 1$ es su único coeficiente).

Supuesto que sabemos calcular el determinante de matrices de orden $n-1$, dado $i\in\lbrace 1,\ldots,n\rbrace$, 

$$
\vert A\vert =a_{i1}\alpha_{i1}+\dots+a_{in}\alpha_{in},
$$

donde $\alpha_{ij}=(-1)^{i+j}\vert A_{ij}\vert$ se conoce como el adjunto de la entrada $a_{ij}$, con $A_{ij}\in \mathcal M_{(n-1)\times(n-1)}(K)$ la matriz que se obtiene al eliminar la fila $i$-ésima y la columna $j$-ésima de $A.$ Esta fórmula se conoce como Desarrollo de Laplace por la fila $i$ del determinante de $A$, y el resultado no depende de $i.$ Es más, también se puede desarrollar por cualquier columna. Dado $j$ el Desarrollo de Laplace por la columna $j$ es 

$$
\vert A\vert =a_{1j}\alpha_{1j}+\dots+a_{nj}\alpha_{nj}.
$$

Se puede comprobar fácilmente que 

$$
\left\vert \begin{matrix}
	a_{11} & a_{12} \\
	a_{21} & a_{22}
       \end{matrix}\right\vert = a_{11}a_{22}-a_{12}a_{21}.
$$

$$
\left\vert \begin{matrix}
		  a_{11} & a_{12} & a_{13} \\
		  a_{21} & a_{22} & a_{23} \\
		  a_{31} & a_{32} & a_{33} 
\end{matrix}\right\vert = a_{11}a_{22}a_{33}+a_{12}a_{23}a_{31}+a_{21}a_{32}a_{13}-a_{13}a_{22}a_{31}-a_{23}a_{32}a_{11}-a_{12}a_{21}a_{33}.
$$

<div class="sage">
<script type="text/x-sage">
A=matrix([[1,0,1],[0,1,-1],[1,-1,0]])
show(A," tiene determinante ",A.det())
</script>
</div>

### Propiedades de los determinantes 

Sea $A\in \mathcal M_{n\times n}(K).$ 
1. $\vert A\vert = \vert A^t\vert.$
1. Si se intercambian dos filas (o dos columnas) de $A$ se obtiene una nueva matriz cuyo determinante es $-\vert A\vert.$ 
1. Si multiplicamos todos los elementos de una fila (o de una columna) de $A$ por $\alpha\in K$, obtenemos una matriz con determinante $\alpha \vert A\vert.$ 
1. Si a una fila de $A$ le sumamos otra fila de $A$ multiplicada por un elemento de $K$, entonces la nueva matriz tiene el mismo determinante que $A$ (lo mismo ocurre si hacemos esta operación con columnas).
1. Si $f$ es una de las filas de $A$ y $f=f_1+f_2$, entonces $\vert A\vert  = \vert A_1\vert +\vert A_2\vert$, siendo $A_i$ la matriz resultante de cambar la fila $f$ en $A$ por $f_i$, $i\in\lbrace 1,2\rbrace.$
1. Si una de las filas de $A$ tiene todas sus entradas nulas, entonces $\vert A\vert =0.$ 
1. Si $B\in \mathcal M_{n\times n}(K)$, entonces $\vert A B\vert =\vert A\vert \vert B\vert.$

Para calcular determinantes a veces es más eficiente usar las operaciones que hemos visto anteriormente. Así efectuando operaciones elementales por filas o columnas (intercambio o suma por un factor de otra) podemos llegar a una matriz triangular superior. El determinante de una matriz de esta forma es trivial, pues sólo se multiplican los valores de la diagonal.

###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/1-7.html) 


La *matriz adjunta* de $A$ es la matriz formada por los adjuntos de las entradas de $A$, a saber, 

$$\bar{A}=
  \begin{pmatrix}
    \alpha_{11} & \alpha_{12} & \ldots & \alpha_{1n}\\
    \alpha_{21} & \alpha_{22} & \ldots & \alpha_{2n}\\
    \vdots & \vdots & \ddots & \vdots \\
    \alpha_{m1} & a_{m2} & \ldots & \alpha_{nn}
   \end{pmatrix}.
$$
 
### Resultado

Sea $A\in \mathcal M_{n\times n}(K).$ Entonces $A$ es regular si y sólo si $\vert A\vert \neq 0.$ En ese caso 

$$
A^{-1}=\vert A\vert ^{-1}\bar{A}^t.
$$

### Resultado

El rango $A$ es el mayor tamaño de una submatriz cuadrada de $A$ con determinante no nulo.

## Fórmula de Cramer

Un sistema es de Cramer si su matriz de coeficientes es cuadrada y regular. Si $AX=b$ es la expresión matricial de un sistema de Cramer, entonces el sistema es compatible determinado y su única solución es

$$
\frac{1}{\vert A\vert }(\vert M_1\vert ,\ldots,\vert M_n\vert ),
$$

donde $M_i$ es la matriz que se obtiene a partir de $A$ cambiando la columna $i$-ésima por $b.$

<!--###### $\to$ [Ejercicios resueltos]({{ site.baseurl | absolute_url }}{% link problemas/resueltos-1.md %}) -->

###### $\to$ [Ejercicios resueltos](https://sl.ugr.es/ProblemasAlgebra) 


## Autoevaluacion

<iframe src="{{ site.baseurl | absolute_url }}{% link /assets/autoevaluacion/matrices.html %}" style="border:none;" height="600" width="100%" title="autoevaluación"></iframe>
