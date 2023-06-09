---
layout: page
title: Espacios vectoriales
---

# Espacios vectoriales

*Este guión está basado en los apuntes de [ALEM](https://www.ugr.es/~pedro/alem/).*

## Espacios vectoriales

Sea $K$ un cuerpo. Diremos que un conjunto $V$ tiene estructura de
*espacio vectorial* sobre $K$ si

1. en $V$ hay una operación $+$ de forma que $(V,+)$ es un grupo
    abeliano,

2. existe una aplicación $K\times V\to V$,
    $(a,\mathbf{v})\mapsto a\mathbf{v}$ verificando
    1. $a(\mathbf{u}+\mathbf{v})=a\mathbf{u}+ a\mathbf{v}$,
    2. $(a+b)\mathbf{u}=a\mathbf{u}+b\mathbf{u}$,
    3. $a(b\mathbf{u})=(ab)\mathbf{u}$,
    4. $1\mathbf{u}=\mathbf{u}$.

A los elementos de $V$ los llamamos vectores y a los de $K$ escalares.
La aplicación descrita arriba se conoce como producto por escalares.

### Ejemplo

Si $K$ es un cuerpo, entonces para cualesquiera enteros
positivos $n$ y $m$,

1. $K^n$,
2. $\lbrace a(x)\in K[x]  : {\rm gr}(a(x))\le n\rbrace$,
3. $\mathcal{M}_{m\times n}(K)$,

son espacios vectoriales sobre $K$.

### Propiedades que se deducen de la definición 

1. $0\mathbf{u}=\mathbf{0}$ (el elemento neutro de $+$ en
    $V$).
2. $a\mathbf{0}=\mathbf{0}$.
3. Si $a\mathbf{u}=\mathbf{0}$, entonces $a=0$ o $\mathbf{u}=\mathbf{0}$.
4. $-(a\mathbf{u})=(-a)\mathbf{u}= a(-\mathbf{u})$.
5. $a(\mathbf{u}-\mathbf{v})=a\mathbf{u}-a\mathbf{v}$.
6. $(a-b)\mathbf{u}=a\mathbf{u}-a\mathbf{u}$.
7. Si $a\mathbf{u}=a\mathbf{v}$ y $a\neq 0$, entonces $\mathbf{u}=\mathbf{v}$.
8. Si $a\mathbf{u}=b\mathbf{u}$ y $\mathbf{u}\neq\mathbf{0}$, entonces $a=b$.

## Subespacios vectoriales

Un subconjunto $U$ no vacío de un espacio vectorial $V$ (sobre un cuerpo $K$) es un *subespacio vectorial* de $V$ si
1. si $\mathbf{u},\mathbf{v}\in U$, entonces $\mathbf{u}-\mathbf{v}\in U$ ($U$ es un subgrupo del grupo $V$),
2. si $a\in K$ y $\mathbf{u}\in U$, entonces $a\mathbf{u}\in U$.

Estas dos propiedades se pueden substituir por

1. si $\mathbf{u},\mathbf{v}\in U$ y $a, b\in K$, entonces $a\mathbf{u} + b\mathbf{v}\in U$ ($U$ es cerrado para combinaciones lineales de sus elementos).

### Ejemplo
El conjunto $\lbrace(x,y,z)\in \mathbb{Q}^3  : x+y+z=0\rbrace$ es un subespacio vectorial de $\mathbb{Q}^3$.

### Propiedad

Sea $V$ un espacio vectorial sobre el cuerpo $K$. Un subespacio vectorial de $V$ es un espacio vectorial sobre $K$, con la misma suma y producto por escalares.

Sea $S$ un subconjunto no vacío de un espacio vectorial $V$. El subespacio vectorial de $V$ *generado* por $S$ es la intersección de todos los subespacios vectoriales de $V$ que contienen a $S$. A dicho subespacio lo denotaremos por $\langle S\rangle$, y diremos que $S$ es un *sistema de generadores* de $\langle S\rangle$.

### Caracterización
Sea $V$ un espacio vectorial sobre el cuerpo $K$. Si $S=\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_n\rbrace$, entonces

$$
\langle S\rangle=\lbrace a_1\mathbf{u}_1+\cdots +a_n\mathbf{u}_n  : a_1,\ldots,a_n\in K\rbrace.
$$

## Bases

Dado un espacio vectorial $V$ sobre el cuerpo $K$, un conjunto de vectores $S\subseteq V$ es *linealmente dependiente* si existen $n$ un entero positivo, $\lbrace\mathbf{v}_1,\dots,\mathbf{v}_n\rbrace\subseteq S$, con $\mathbf{v}_i\neq \mathbf{v}_j$ para todo $i\neq j$, y $(a_1,\ldots,a_n)\in K^n\setminus\lbrace(0,\dots,0)\rbrace$ tales que $a_1\mathbf{v}_1+\dots +a_n\mathbf{v}_n=\mathbf{0}$. En caso contrario, decimos que $S$ es un conjunto de vectores
linealmente independientes.

### Ejemplo

El conjunto $\lbrace(1,1,0),(0,1,1),(1,0,1)\rbrace\subset\mathbb{R}^3$ es un conjunto de vectores linealmente independientes.

### Propiedades

- $S$ es un conjunto de vectores linealmente dependientes si y sólo si existe $\mathbf{v}\in S$ tal que $\mathbf{v}\in \langle S\setminus \lbrace\mathbf{v}\rbrace\rangle$.

- Si $\mathbf{0}\in S$, entonces $S$ es un conjunto de vectores linealmente dependientes.

- Si $S$ es un conjunto de vectores linealmente dependientes, entonces para todo $\mathbf{v}\in V$, $S\cup\lbrace\mathbf{v}\rbrace$ también es un conjunto de vectores linealmente dependientes.

- Si $S$, con $\sharp S\geq 2$, es un conjunto de vectores linealmente    independientes, entonces para todo $v\in S$, el conjunto  $S\setminus \lbrace\mathbf{v}\rbrace$ también es un conjunto de vectores linealmente independientes.

Una *base* de $V$ es un subconjunto $S$ de vectores linealmente independientes de $V$ tal que $V=\langle S\rangle$.

### Propiedad

Si $B=\lbrace\mathbf{v}_1,\ldots,\mathbf{v}_n\rbrace$ es una base de $V$, entonces para todo vector $\mathbf{v}\in V$, existen $a_1,\ldots,a_n\in K$ únicos tales que $\mathbf{v}=a_1\mathbf{v}_1+\cdots +a_n\mathbf{v}_n$.

A la $n$-upla $(a_1,\ldots,a_n)$ se le llama *coordenadas* del vector $\mathbf{v}$ respecto de la base $B$. Escribiremos $\mathbf{v}\equiv (a_1,\dots,a_n)_B$ para denotar que $(a_1,\dots,a_n)$ son las coordenadas de $\mathbf{v}$ respecto de $B$.

### Observación

Si $B$ es una base de un espacio vectorial $V$, y $\mathbf{u}\equiv (a_1,\dots,a_n)_B$ y $\mathbf{v}\equiv (b_1,\dots,a_n)_B$, entonces para todo $\lambda,\mu\in K$, 

$$
\lambda \mathbf{u}+\mu\mathbf{v}\equiv (\lambda a_1+\mu b_1,\dots, \lambda a_n+\mu a_n)_B, 
$$

es decir, las coordenadas de una combinación lineal de un par de vectores son la combinación lineal de las coordenadas de esos vectores. Por tanto, una vez fijamos una base $B$, trabajar en $V$ es equivalente a trabajar con las coordenadas de los vectores de $V$ y por tanto en $K^n$.

### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/2-1.html)

### Teorema de la base

Todo espacio vectorial distinto de $\lbrace\mathbf{0}\rbrace$ tiene al menos una base. Además todas sus bases tienen el mismo cardinal.

Al cardinal de una base de $V$ lo denotamos por $\dim(V)$, y nos referiremos a él como la *dimensión* de $V$.

### Ejemplo
Si $K$ es un cuerpo, $\dim(K^n)=n$, $\dim(\mathcal M_{m\times n}(K))=nm$ y
$\dim(\lbrace a(x)\in K[x] : {\rm gr}(a(x))\le n\rbrace)=n+1$.

### Teorema de ampliación a base

Si $\dim(V)=n$ y $\lbrace\mathbf{v} _1,\ldots,\mathbf{v} _m\rbrace$ es un conjunto de vectores linealmente independientes de $V$, entonces $m\le n$. Además existen $\mathbf{v} _{m+1},\ldots,\mathbf{v} _n\in V$, de forma que $\lbrace\mathbf{v} _1,\ldots,\mathbf{v} _m,\mathbf{v} _{m+1},\ldots,\mathbf{v} _n\rbrace$ es una base de $V$.

### Teorema de reducción a base

Si $\dim(V)=n$ y $S=\lbrace\mathbf{v} _1,\ldots,\mathbf{v} _m\rbrace$ es un sistema de generadores de $V$, entonces $m\ge n$. Además existen $\mathbf{v} _{i_1},\ldots,\mathbf{v} _{i_n}\in S$, de forma que $\lbrace\mathbf{v} _{i_1},\ldots,\mathbf{v} _{i_n}\rbrace$ es una base de $V$.

### Consecuencia

Si $\dim(V)=n$, entonces cualquier conjunto de vectores de $V$ linealmente independientes de cardinal $n$ es una base de $V$.

### Ejemplo

Los vectores $(0,1)$, $(1,-1)$ son linealmente independientes en $\mathbb{R}^2$, y por tanto $\lbrace(0,1),(1,-1)\rbrace$ es una base de $\mathbb{R}^2$.

## Ecuaciones del cambio de base

Sean $B=\lbrace\mathbf{v}_1,\ldots,\mathbf{v}_n\rbrace$ y $B'=\lbrace\mathbf{v}_1',\ldots,\mathbf{v}_n'\rbrace$ dos bases de $V$. Sea $\mathbf{x}\in V$. Entonces existen $x_1,\ldots,x_n,x_1',\ldots,x_n'\in K$ tales que $\mathbf{x}=x_1\mathbf{v}_1+\cdots +x_n\mathbf{v}_n$
y $\mathbf{x}=x_1'\mathbf{v}_1'+\cdots +x_n'\mathbf{v}_n'$. 

Queremos ver qué relación hay entre las coordenadas de $\mathbf{x}$ respecto de $B$ y de $B'$. Para ello utilizaremos las coordenadas de los vectores de $B$ respecto de $B'$. Supongamos que

$$
\begin{matrix}
\mathbf{v} _1& = &a _{11}\mathbf{v} _1'+\cdots +a _{n1}\mathbf{v} _n',\\
&\vdots& \\
\mathbf{v} _n&=&a _{1n}\mathbf{v} _1'+\cdots+ a _{nn}\mathbf{v} _n'.
\end{matrix}
$$

Entonces,

$$
\begin{matrix}
\mathbf{x} & = x_1\mathbf{v}_1+\cdots +x_n\mathbf{v}_n = x_1(a_{11}\mathbf{v}_1'+\cdots +a_{n1}\mathbf{v}_n')+\cdots +x_n(a_{1n}\mathbf{v}_1'+\cdots+ a_{nn}\mathbf{v}_n')\\
& =(x_1a_{11}+\cdots+ x_n a_{1n})\mathbf{v}_1'+\cdots+ (x_1a_{nn}+\cdots+x_na_{nn})\mathbf{v}_n'= x_1'\mathbf{v}_1'+\cdots+ x_n'\mathbf{v}_n'.
\end{matrix}
$$

Como las coordenadas son únicas,

$$
\left\lbrace
 \begin{matrix}
  x_1'= x_1a_{11}+\cdots+ x_n a_{1n},\\
  \vdots \\
  x_n'= x_1a_{n1}+\cdots+x_na_{nn},
 \end{matrix}
 \right.
 $$

que se conocen como las *ecuaciones de cambio* de base de $B$ a $B'$. Éstas se pueden también expresar en forma matricial 

$$
\begin{pmatrix}
    x_1'\\ 
    \vdots\\ 
    x_n'
\end{pmatrix} = 
\begin{pmatrix}
 a_{11} & \ldots & a_{1n}\\
 \vdots & \ddots & \vdots \\
 a_{n1} & \ldots & a_{nn}
\end{pmatrix} 
\begin{pmatrix} 
    x_1\\ 
    \vdots \\
    x_n
\end{pmatrix}.
$$ 

A la matriz 

$$
A=\begin{pmatrix}
 a_{11} & \ldots & a_{1n}\\
 \vdots & \ddots & \vdots \\
 a_{n1} & \ldots & a_{nn}
\end{pmatrix}
$$

se le llama *matriz de cambio de base* de $B$ a $B'$. Esta matriz es siempre regular y su inversa, $A^{-1}$ es justamente la matriz de cambio de base de $B'$ a $B$.

### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/2-2.html)

## Ecuaciones paramétricas de un subespacio vectorial

Supongamos que $\dim(V)=n$ y que $U$ es un subespacio vectorial de $V$ de dimensión $r$. Sea $B=\lbrace\mathbf{v}_1,\ldots,\mathbf{v}_n\rbrace$ una base de $V$, y $B_U=\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_r\rbrace$ una base de $U$. Supongamos que

$$
\begin{matrix}
\mathbf{u}_1=a_{11}\mathbf{v}_1+\cdots +a_{1n}\mathbf{v}_n,\\
\vdots \\
\mathbf{u}_r=a_{r1}\mathbf{v}_1+\cdots+ a_{rn}\mathbf{v}_n.
\end{matrix}
$$

Sea $\mathbf{x}=x_1\mathbf{v}_1+\cdots+x_n\mathbf{v}_n$ un vector de $V$. Veamos qué tienen que verificar las coordenadas $(x_1,\ldots,x_n)$ para que $\mathbf{x}\in U$.

El vector $\mathbf{x}\in U$ si y sólo si existen $\lambda_1,\ldots,\lambda_r\in K$ tales que $\mathbf{x}= \lambda_1\mathbf{u}_1+ \cdots +\lambda_r\mathbf{u}_r$, y esto equivale a que 

$$
\begin{matrix}
\mathbf{x}&=&\lambda_1(a_{11}\mathbf{v}_1+\cdots +a_{1n}\mathbf{v}_n)+ \cdots + \lambda_r (a_{r1}\mathbf{v}_1+\cdots+ a_{rn}\mathbf{v}_n) \\
&=& (\lambda_1a_{11}+\cdots+\lambda_ra_{r1})\mathbf{v}_1+\cdots+ (\lambda_1 a_{1n}+\cdots+\lambda_r a_{rn})\mathbf{v}_n.
\end{matrix}
$$ 

Como las coordenadas son únicas, 

$$
\left\lbrace
\begin{matrix}
x_1= \lambda_1 a_{11}+\cdots+ \lambda_r a_{r1},\\
\vdots\\
x_n= \lambda_1 a_{1n}+\cdots+ \lambda_r a_{rn}.
\end{matrix}
\right.
$$ 

Estas ecuaciones son las *ecuaciones paramétricas* de $U$ respecto de la base $B$.

## Ecuaciones cartesianas o implícitas de un subespacio vectorial

Sea $U$ un subespacio vectorial de $V$. Sea $B=\lbrace\mathbf{v}_1,\ldots,\mathbf{v}_n\rbrace$ una base de $V$, y $B_U=\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_r\rbrace$ una base de $U$. Supongamos que

$$
\begin{matrix}
\mathbf{u}_1=a_{11}\mathbf{v}_1+\cdots +a_{1n}\mathbf{v}_n,\\
\vdots \\
\mathbf{u}_r=a_{r1}\mathbf{v}_1+\cdots+ a_{rn}\mathbf{v}_n.        
\end{matrix}
$$

Sea $\mathbf{x}=x_1\mathbf{v}_1+\cdots+x_n\mathbf{v}_n$ un vector de $V$. Recordemos que el vector $\mathbf{x}\in U$ si y sólo si existen $\lambda_1,\ldots,\lambda r\in K$ tales que 

$$
\left\lbrace
\begin{matrix}
x_1= \lambda_1 a_{11}+\cdots+ \lambda_r a_{r1},\\
\vdots\\
x_n= \lambda_1 a_{1n}+\cdots+ \lambda_r a_{rn},
\end{matrix}
\right.
$$ 

Luego $\mathbf{x}\in U$ si y sólo si el sistema con incógnitas $\lambda_1,\ldots \lambda_r$ 

$$
\begin{pmatrix}
a_{11} & \ldots & a_{r1}\\
\vdots & \ddots & \vdots\\
a_{1n} & \ldots & a_{rn}
\end{pmatrix}
\begin{pmatrix}
\lambda_1 \\
\vdots\\
\lambda_r
\end{pmatrix}=
\begin{pmatrix}
x_1 \\
\vdots\\
x_n
\end{pmatrix}
$$

tiene solución. Y sabemos que esto equivale a que

$$
\operatorname{rg}\begin{pmatrix}
a_{11} & \ldots & a_{r1}\\
\vdots & \ddots & \vdots\\
a_{1n} & \ldots & a_{rn}
\end{pmatrix} = 
\operatorname{rg}\begin{pmatrix}
a_{11} & \ldots & a_{r1} & x_1\\
\vdots & \ddots & & \vdots\\
a_{1n} & \ldots & a_{rn} & x_n
\end{pmatrix}.
$$ 

Esto ocurre cuando unos cuantos determinantes valen
cero, proporcionándonos así una sistema de ecuaciones de la forma

$$
\left.
\begin{matrix}
b_{11}x_1+\cdots+b_{1n}x_n=0\\
\vdots \\
b_{k1}x_1+\cdots+b_{kn}x_n=0
\end{matrix}
\right\rbrace,
$$ 

a las que llamaremos ecuaciones cartesianas de $U$ respecto de la base $B$ de $V$.

### Propiedad

Si $k$ es el número de ecuaciones cartesianas independientes que describen a $U$, entonces $k+\dim(U)=\dim(V)$.

Una forma alternativa de calcular la ecuaciones cartesianas de $U$ es considerar $x_1,\dots,x_n$ como las componentes del término independiente del sistema

$$
\left\lbrace
\begin{matrix}
\lambda_1 a_{11}+\cdots+ \lambda_r a_{r1}=x_1,\\
\vdots\\
\lambda_1 a_{1n}+\cdots+ \lambda_r a_{rn}=x_n,
\end{matrix}
\right.
$$ 

y transformar el sistema en otro equivalente que esté en forma escalonada. El número de ecuaciones en las que no aparecerán $\lambda_1,\dots,\lambda_r$ será la dimensión de $U$, mientras que el resto serán ecuaciones de la forma $0$ igual a una expresión lineal en $x_1,\dots,x_n$, que son las que imponen que el sistema original sea compatible, y por tanto las ecuaciones de $U$.

### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/2-3.html)

## Suma e intersección de subespacios

La intersección de subespacios vectoriales de $V$ es de nuevo un subespacio vectorial de $V$. Si conocemos las ecuaciones cartesianas de cada uno de los subespacios, las ecuaciones cartesianas de la intersección serán la unión de todas las ecuaciones de cada uno de los subespacios.

Sean $U_1,\dots,U_n$ subespacios vectoriales de $V$. El subespacio vectorial suma de $U_1,\ldots, U_n$ es

$$
U_1+\dots+ U_n=\lbrace\mathbf{u}_1+\dots +\mathbf{u}_n :\mathbf{u}_1\in U_1,\dots,\mathbf{u}_n\in U_n\rbrace.
$$

### Propiedades

- $U_1+\dots+U_n=\langle U_1\cup \cdots \cup U_n\rangle$.

- Si $U_1=\langle S_1\rangle,\ldots, U_n=\langle S_n\rangle$, entonces $U_1+\cdots+U_n= \langle S_1\cup \cdots \cup S_n\rangle$.

## Resultado

Sean $U$ y $W$ dos subespacios del espacio vectorial $V$. Entonces 

$$
\dim(U\cap W)+\dim(U+W)=\dim(U)+\dim(W).
$$

### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/2-4.html)

Sean $U$ y $W$ subespacios vectoriales del espacio vectorial $V$. Decimos que $V$ es *suma directa* de $U$ y $W$, y lo denotamos por $V=U\oplus W$, si todo vector $\mathbf{v}\in V$ se puede expresar de forma única como $\mathbf{v}=\mathbf{u}+\mathbf{w}$, con $\mathbf{u}\in U$ and $\mathbf{w}\in W$. En dicho caso, diremos que los subespacios vectoriales $U$ y $W$ son *complementarios*.

### Caracterización
Sea $V$ un espacio vectorial, y sean $U$y $W$ dos subespacios suyos. Entonces,
$V=U\oplus W$ si, y sólo si, $V=U+W$ y $U\cap W=\lbrace\mathbf{0}\rbrace$.

### Ejemplo
Sean $U=\lbrace(x,y)\in \mathbb{R}^2  : x+y =0\rbrace$ y $W=\lbrace(x,y)\in \mathbb\lbrace R\rbrace^2  : x-y=0\rbrace$. Entonces $\mathbb{R}^2=U\oplus W$.

### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/2-5.html)


## Autoevaluacion

<iframe src="{{ site.baseurl }}{% link /assets/autoevaluacion/espacios-vectoriales.html %}" style="border:none;" height="600" width="100%" title="autoevaluación"></iframe>
