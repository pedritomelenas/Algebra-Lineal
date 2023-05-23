---
layout: page
title: Descomposición y diagonalización de matrices
---

# Descomposición y diagonalización de matrices

Este guión se basa en los libros [L. Merino, E. Santos, [Álgebra Lineal con Métodos Elementales](https://www.amazon.es/%C3%81lgebra-lineal-m%C3%A9todos-elementales-GONZALEZ/dp/8497324811)] y [I. Ojeda, J. Gago, [Métodos matemáticos para la Estadística](https://publicauex.unex.es/libro/metodos-matematicos-para-estadistica_135467/)].

# Diagonalización por semejanza ortogonal de matrices simétricas


Sea $(V,\langle,\rangle)$ un espacio vectorial euclídeo. Un endomorfismo $f:V\to V$ se dice *simétrico* (o *autoadjunto*) si para todo $\mathbf{u},\mathbf{v}\in V$ se tiene que 

$$
\langle f(\mathbf{u}),\mathbf{v}\rangle =\langle \mathbf{u},f(\mathbf{v})\rangle.
$$

Si $B=\lbrace \mathbf{e} _1,\dots,\mathbf{e} _n\rbrace$ es una base ortonormal de $V$, y $A=\mathcal{M}(f;B)$, entonces $a _{ij}=\langle f(\mathbf{e} _j),\mathbf{e}_i\rangle=\langle \mathbf{e} _j,f(\mathbf{e} _i) \rangle=a _{ji}$, y por tanto $A$ es simétrica.

El recíproco también es cierto pues si $A$ es simétrica, entonces si $x$ y $y$ son las coordenadas de $\mathbf{u}$ y $\mathbf{v}$, respectivamente, tenemos que $\langle f(\mathbf{u}),\mathbf{v}\rangle = (Ax)^ty=x^tA^ty=x^t(Ay)=\langle \mathbf{u},f(\mathbf{v})\rangle$.

### Resultado

El endomorfismo $f$ es autoadjunto si y sólo si su matriz respecto de una base ortonormal es simétrica.

Sea $A\in \mathcal{M}_n(\mathbb{R})$ simétrica. Supongamos que $\lambda=a+i b$ es un valor propio complejo de $A$. Existen $x,y\in \mathbb{R}^n$ tales que $A(x+iy)=(a+ib)(x+iy)$. Por tanto,

$$
Ax+iAy=A(x+iy)=(a+ib)(x+iy)=(ax-yb)+i(bx+ay).
$$

Igualando parte real con parte imaginaria, obtenemos $Ax=ax-yb$ y $Ay=bx+ay$. Usamos ahora que $A$ es simétrica (y por tanto su endomorfismo asociado es autoadjunto)

$$
\begin{aligned}
\langle Ax ,y\rangle & =\langle ax-yb,y\rangle =a\langle x,y\rangle - y \langle y,y\rangle,\\
\langle x, Ay\rangle &= \langle x, bx+ay\rangle =b\langle x,x\rangle + a \langle x,y\rangle.
\end{aligned}
$$

Como $\langle Ax,y\rangle =\langle x,Ay\rangle$, tenemos que 

$$
0=b(\langle x,x\rangle +\langle y,y\rangle),
$$

y como $\langle x,x\rangle + \langle y,y\rangle >0$, deducimos que $b=0$. Tenemos así el siguiente resultado.

### Resultado

Todos los valores propios de una matriz simétrica con entradas reales son reales.

Supongamos ahora que $\lambda_1,\dots,\lambda_m$ son todos los valores propios (reales) de $A$. Como $\lambda_i\neq \lambda_j$ con $i\neq j$, si $\mathbf{v}\in V_{\lambda_i}\cap V_{\lambda_j}$ y $x$ son las coordenadas de $\mathbf{v}$, tenemos que $Ax=\lambda_ix=\lambda_jx$, por lo que $x=0$ y $\mathbf{v}=0$. Esto quiere decir que $V_{\lambda_i}\cap V_{\lambda_j}=\lbrace\mathbf{0}\rbrace$. De esta forma la suma $V_{\lambda_1}+\dots+V_{\lambda_m}$ es directa. Sea $U=V_{\lambda_1}\oplus \dots \oplus V_{\lambda_m}$. 

Si $f$ es el endomorfismo que viene determinado por $A$, entonces $f(U)\subseteq U$. Es más, por ser $f$ autoadjunto, si $\mathbf{u}\in U$ y $\mathbf{v}\in U^\perp$, por ser $f(\mathbf{u})\in U$, se tiene que $0=\langle \mathbf{v},f(\mathbf{u})\rangle= \langle f(\mathbf{v}),\mathbf{u}\rangle$, por lo que $f(\mathbf{v})\in U^\perp$, esto es, $f(U^\perp)\subseteq U^\perp$. Si $U^\perp\neq \lbrace \mathbf{0}\rbrace$, entonces $f$ restringido a $U^\perp$ tendrá al menos una valor propio $\lambda$. Si $\mathbf{v}$ es un vector propio asociado a $\lambda$, $f(\mathbf{v})=\lambda\mathbf{v}$, por lo que $\lambda\in \lbrace\lambda_1,\dots,\lambda_m\rbrace$, lo que lleva a $\mathbf{v}\in U\cap U^\perp=\lbrace\mathbf{0}\rbrace$, lo que es absurdo. Por tanto $U^\perp=\lbrace \mathbf{0}\rbrace$ y $U=\mathbb{R}^n$. Acabamos de probar el siguiente resultado.

### Teorema espectral para matrices simétricas reales

Toda matriz simétrica con entradas reales es diagonalizable.

Veamos ahora que los subespacios propios son además ortogonales entre sí. Si $\lambda$ y $\mu$ son dos valores distintos de $A$ (simétrica con entradas reales), y $\mathbf{u}$ y $\mathbf{v}$ son vectores propios asociados a $\lambda$ y $\mu$ respectivamente, entonces 

$$
\begin{aligned}
\langle f(\mathbf{u}),\mathbf{v}\rangle &=\lambda \langle \mathbf{u},\mathbf{v}\rangle,\\
\langle \mathbf{u},f(\mathbf{v})\rangle &= \mu\langle \mathbf{u},\mathbf{v}\rangle,
\end{aligned}
$$

con $f$ el endomorfismo determinado por $A$. Como $f$ es autoadjunto, $(\lambda-\mu)\langle \mathbf{u},\mathbf{v}\rangle=0$, y al ser $\lambda\neq \mu$, concluimos que $\langle \mathbf{u},\mathbf{v}\rangle=0$. 

Esto nos permite escoger dentro de cada subespacio asociado a cada valor propio de $A$ una base ortonormal. Al juntarlas todas obtenemos una base ortonormal de $V$, y tenemos que la expresión de $f$ en esa base ortonormal es diagonal. Si llamamos $P$ a la matriz de paso (sus columnas son las coordenadas de los vectores de nuestra base ortonormal), entonces $P P^t=I_n$, por lo que $P^{-1}=P^t$. Estas matrices se denominan *ortogonales*. 

### Resultado

Si $A$ es una matriz simétrica con entradas reales, entonces existen $P$ ortogonal y una matriz diagonal $D$ tales que $D=P^tAP$.

### Ejemplo

Sea 

$$
A=\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}.
$$ 

Entonces, $D=Q^{-1}AQ$, con 

$$
Q=\begin{pmatrix}1 - \sqrt{2} & 1 + \sqrt{2}\\1 & 1\end{pmatrix},\quad D=\begin{pmatrix}- \sqrt{2} & 0\\0 & \sqrt{2}\end{pmatrix}.
$$

Nótese que $Q$ no es ortogonal. Si tomamos $\mathbf{u}=(1-\sqrt{2},1)$ y $\mathbf{v}=(1+\sqrt{2},1)$, entonces la matriz $P$ cuyas columnas son $\frac{1}{\Vert \mathbf{u}\Vert }\mathbf{u}$ y $\frac{1}{\Vert\mathbf{v}\Vert}\mathbf{v}$ verifica que $D=P^tAP$.

# Inversas generalizadas. Mínimos cuadrados

## Motivación

Supongamos que el sistema $Ax=b$ no tiene solución (sistema incompatible). Pretendemos buscar un $y$ de forma que $Ax=y$ si tenga solución y de forma que $y$ sea lo más "cercano" posible a $b$.

Si la matriz $A\in \mathcal{M}_{m\times n}(K)$, el conjunto $U=\lbrace Ax : x \in K^n\rbrace$ es un subespacio vectorial de $K^m$ generado por las columnas de $A$. Por el teorema de mejor aproximación, $p_U(b)$ (la proyección ortogonal de $b$ en $U$) es el elemento de $U$ más cercano a $b$. Por tanto, existe un $z\in K^n$ tal que $Az=p_U(b)$.

Llamemos $y=p_U(b)$. Sabemos que $b-y=b-Az\in U^\perp$. Por lo que $\langle b-Az,Ax\rangle=0$ para todo $x\in K^n$. Así, 

$$
\begin{aligned}
0 & =\langle Ax, b-Az\rangle = \langle Ax ,b \rangle - \langle Ax, Az \rangle \\ &= (Ax)^tb -(Ax)^t(Az)= x^tA^tb -x^tA^tAz=x^t(A^tb-A^tAz).
\end{aligned}
$$

Por tanto, $A^tb-A^tAz=0$, por lo que $z$ es solución de

$$
A^tA z= A^t b.
$$

### Ejemplo

Supongamos que queremos calcular la recta de $\mathbb{R}^2$ que pasa por $(0,1)$ y $(1,3)$. Supongamos que la recta tiene ecuación implícita $ax+by+c=0$. Si $b=0$, tendríamos que $x$ es igual a una constante, lo cual no es cierto con los datos que nos están proporcionando. Por tanto, $b\neq 0$ y nuestra ecuación se puede escribir como $y=\alpha+\beta x$. Esto es, estamos buscando un polinomio de grado uno que valga $1$ en $0$, y $3$ en $1$. Si consideramos $\alpha$ y $\beta$ como incógnitas, esto equivale a resolver el sistema

$$
\left\lbrace
\begin{aligned}
\alpha & & = 1,\\
\alpha &+\beta & =3,
\end{aligned}
\right.
$$

que es un sistema compatible determinado, con solución $\alpha=1$ y $\beta=2$. Así nuestra recta es $y=1+2x$.

Supongamos ahora que queremos calcular una recta que pase por los puntos $(0,1)$, $(1,3)$ y $(2,2)$. Eso nos lleva a resolver el sistema 

$$
\left\lbrace
\begin{aligned}
\alpha  & = 1,\\
\alpha +\beta & =3,\\
\alpha +2\beta & = 2.
\end{aligned}
\right.
$$

Este sistema no tiene solución. Tomamos 

$$
A=\begin{pmatrix}1 & 0\\1 & 1\\1 & 2\end{pmatrix}.
$$

Tenemos que 

$$
A^tA=\begin{pmatrix}
3 & 3\\ 
3 & 5
\end{pmatrix},
$$

y que el sistema 

$$
A^tA\begin{pmatrix} \alpha\\ \beta\end{pmatrix} = A^t \begin{pmatrix} 1\\ 3\\ 2\end{pmatrix},
$$

$$
\begin{pmatrix}3 & 3\\3 & 5\end{pmatrix} \begin{pmatrix} \alpha\\ \beta\end{pmatrix} = \begin{pmatrix} 6 \\ 7 \end{pmatrix},
$$

tiene solución (única) $\alpha=3/2$, $\beta=1/2$. Así, la recta $y=\frac{3}2+\frac{1}2 x$ es la que verifica que al evaluar $x$ en $0$, $1$ y $2$ proporciona los valores más cercanos a $1$, $3$ y $2$ (y son $3/2$, $2$ y $5/2$). 

## Espacios de filas y columnas de $A^tA$

Sea $A\in\mathcal{M}_{m\times n}(K)$. Si $x\in \operatorname{N}(A)$, entonces $Ax=0$, y $A^tAx=0$, por lo que $x\in \operatorname{N}(A^tA)$. Supongamos ahora que $x\in \operatorname{N}(A^tA)$, y veamos que $x\in \operatorname{N}(A)$. Sabemos que $Ax=0$ si y sólo si $\Vert Ax\Vert=0$. Ahora bien, si tomamos la norma asociada al producto escalar usual,

$$
\Vert Ax\Vert^2= \langle Ax,Ax\rangle = (Ax)^t(Ax)=x^tA^tAx=x^t0=0.
$$

Tenemos así el siguiente resultado.

### Resultado

Para una matriz $A$, $\operatorname{N}(A)=\operatorname{N}(A^tA)$.

Sea $\operatorname{C}(A)$ el subespacio generado por las columnas de $A$, y sea $\operatorname{F}(A)$ el subespacio generado por las filas de $A$. Por la definición de núcleo, respecto al producto escalar usual, tenemos que $\operatorname{N}(A)=\operatorname{F}(A)^\perp$, y por el resultado anterior $\operatorname{F}(A^tA)=\operatorname{F}(A)$. Como $\operatorname{F}(A)=\operatorname{C}(A^t)$, tenemos que $\operatorname{C}(A^tA)=\operatorname{C}(A^t)$. 

### Resultado

Dada una matriz $A$.

1. $\operatorname{F}(A^tA)=\operatorname{F}(A)$.
1. $\operatorname{C}(A^tA)=\operatorname{C}(A^t)$.
3. $\operatorname{rg}(A^tA)=\operatorname{rg}(AA^t)=\operatorname{rg}(A)$.

## Inversas a izquierda y a derecha de una matriz

Dada una matriz $A\in \mathcal{M}_{m\times n}(K)$, decimos que es de *rango pleno por filas* si $\dim(\operatorname{F}(A))=m$, y es de *rango pleno por columnas* si $\dim(\operatorname{C}(A))=n$.

Nótese que $AA^t\in \mathcal{M}_m(K)$, y $\operatorname{rg}(AA^t)=\operatorname{rg}(A)$. Por tanto, $AA^t$ es invertible si y sólo si $\operatorname{rg}(A)=m$, lo que equivale a que $A$ sea de rango pleno por filas. En este caso

$$
A(A^t(AA^t)^{-1})=(AA^t)(AA^t)^{-1}=I_m,
$$

por lo que $A^D=A^t(AA^t)^{-1}$ es una inversa a la derecha de $A$: $AA^D=I_m$.

Por otro lado, $A^tA\in\mathcal{M}_n(K)$, y de nuevo $\operatorname{rg}(AA^t)=\operatorname{rg}(A)$. Así, $A^tA$ tendrá inversa si y sólo si $\operatorname{rg}(A)=n$, y esto sólo ocurre si $A$ es de rango pleno por columnas. En esta situación

$$
((A^tA)^{-1}A^t)A=(A^tA)^{-1}(A^tA)=I_n,
$$

y de esta forma $A^I=(A^tA)^{-1}A^t$ es una inversa a la izquierda de A: $A^IA=I_n$.

### Teorema de existencia de inversas a izquierda y a derecha

Sea $A\in \mathcal{M}_{m\times n}(K)$.

1. La matriz $A$ tiene inversa a la derecha si y sólo si es de rango pleno por filas, y en ese caso $A^D=A^t(AA^t)^{-1}$ es una inversa a la derecha de $A$.

1. La matriz $A$ tiene inversa a la izquierda si y sólo si es de rango pleno for columnas, y en ese caso $A^I=(A^tA)^{-1}A^t$ es una inversa a la izquierda de $A$.

### Ejemplo

En nuestro ejemplo sobre calcular una recta que pasaba por una serie de puntos, la matriz 

$$
A=\begin{pmatrix}1 & 0\\1 & 1\\1 & 2\end{pmatrix}
$$

es de rango pleno por columnas, por lo que $A^tA$ es invertible cuya inversa es

$$
(A^tA)^{-1}=\begin{pmatrix}\frac{5}{6} & - \frac{1}{2}\\- \frac{1}{2} & \frac{1}{2}\end{pmatrix}.
$$

Tomando 

$$
A^I=(A^tA)^{-1}A^t=\begin{pmatrix}\frac{5}{6} & \frac{1}{3} & - \frac{1}{6}\\- \frac{1}{2} & 0 & \frac{1}{2}\end{pmatrix},
$$

tenemos que $A^IA=I_2$.

### Observación

Sea $f: V\to V'$ una aplicación lineal con matriz asociada $A$ respecto de unas bases dadas en $V$ y $V'$. 

- Sabemos que $f$ es sobreyectiva si y sólo si $\operatorname{Im}(f)=V'$. Esto ocurre si y sólo si $A$ es de rango pleno por filas. Por tanto, $f$ es sobreyectiva si y sólo si $A$ tiene una inversa a la derecha.

- Para que $f$ sea inyectiva, su núcleo tiene que ser trivial. Sabemos que $\dim(V)=n=\dim(\operatorname{N}(f))+\dim(\operatorname{Im}(f))$. Así $f$ es inyectiva si y sólo si $n=\dim(\operatorname{Im}(f))=\dim(\operatorname{C}(A))$, por lo que esto equivale a que $A$ sea de rango pleno por columnas. Así, $f$ es inyectiva si y sólo si $A$ tiene una inversa por la izquierda.

## Factorizaciones de rango pleno

Sea $A\in \mathcal{M}_{m\times n}(K)$. Una *factorización de rango pleno* de $A$ es una expresión de $A$ como producto de dos matrices, $A=CF$, la primera de rango pleno por columnas y la segunda de rango pleno por filas.

Sea $r=\operatorname{rg}(A)$, sea $H$ la matriz escalonada reducida por filas de $A$ y sea $P$ tal que $PA=H$, y por tanto $A=P^{-1}H$. Podemos escribir 

$$
H=\begin{pmatrix} 
F \\ \hline
0
\end{pmatrix},\quad P^{-1}=\left( C \mid  B \right),
$$

con $F$ las primeras $r$ filas de $H$ (sus filas no nulas), y $C$ las primeras $r$ columnas de $P^{-1}$. De esta forma 

$$
A=P^{-1}H=\left( C \mid  B \right) \begin{pmatrix} 
F \\ \hline
0
\end{pmatrix}= C F + B 0= CF. 
$$

Claramente, $C$ es de rango pleno por columnas y $F$ es de rango pleno por filas.

### Ejemplo 

Retomemos nuestra matriz 

$$
A=\begin{pmatrix}1 & 0\\1 & 1\\1 & 2\end{pmatrix}
$$

Entonces 

$$
PA= \begin{pmatrix} 
1 & 0 \\
0 & 1 \\
0 & 0
\end{pmatrix},
$$

con 

$$
P=\begin{pmatrix}0 & 2 & -1\\0 & -1 & 1\\1 & -2 & 1\end{pmatrix}; P^{-1}=  \begin{pmatrix}
  1 & 0 & 1\\
  1 & 1 & 0\\
  1 & 2 & 0
  \end{pmatrix}
.
$$

Así 

$$
A= \left(
  \begin{array}{cc|c}
  1 & 0 & 1\\
  1 & 1 & 0\\
  1 & 2 & 0
  \end{array}
  \right)
\begin{pmatrix} 
1 & 0 \\
0 & 1 \\ \hline
0 & 0
\end{pmatrix},
$$

por lo que 

$$
A = \left(
  \begin{array}{cc}
  1 & 0 \\
  1 & 1 \\
  1 & 2
  \end{array}
  \right)
\begin{pmatrix} 
1 & 0 \\
0 & 1 
\end{pmatrix}.
$$

Lo cual era de esperar, pues $A$ es de rango pleno for columnas.

## Soluciones mínimo-cuadráticas

Sea $A\in \mathcal{M}_{m\times n}(K)$ y $b\in K^m$. Consideremos el sistema lineal de ecuaciones

$$
Ax=b.
$$

Un elemento $z$ de $K^m$ es una *solución mínimo-cuadrática* de $Ax=b$ si la norma $\Vert Az-b \Vert$ es mínima, esto es $\operatorname{d}(Az,b)=\operatorname{d}(b,\operatorname{C}(A))$ (estamos usando la distancia y normas asociados a un producto escalar usual en $K^m$).

Por lo que vimos antes, $z$ es una solución mínimo-cuadrática si y sólo si es solución del sistema de ecuaciones 

$$
A^tAz=A^tb.
$$

Este sistema siempre es compatible, pues $A^tb\in \operatorname{C}(A^t)=\operatorname{C}(A^tA)$. Además, el sistema será compatible determinado si $A^tA$ tiene rango máximo, y esto es equivalente a que $A$ tenga rango pleno por columnas. En ese caso, recordemos que $A^I=(A^tA)^{-1}A^t$ es una inversa a la izquierda de $A$, por lo que $z=(A^tA)^{-1}A^tb=A^Ib$.

### Resultado

Las soluciones mínimo-cuadráticas de $Ax=b$ son las soluciones de $A^tAz=A^tb$ (que siempre es un sistema compatible). Además, existe una única solución mínimo-cuadrática si $A$ es de rango pleno por columnas, y en ese caso la solución es $A^Ib$.


### Ejemplo

Volvamos al ejemplo $Ax=b$ con 

$$
A=\begin{pmatrix}1 & 0\\1 & 1\\1 & 2\end{pmatrix}
$$

y $b=(1,3,2)$ (con el que pretendíamos ajustar una recta a tres puntos dados).

La solución mínimo-cuadrática que encontramos en su momento fue $z=(3/2,1/2)$, que se obtiene como

$$
z=A^Ib,
$$

con 

$$
A^I=\begin{pmatrix}\frac{5}{6} & \frac{1}{3} & - \frac{1}{6}\\- \frac{1}{2} & 0 & \frac{1}{2}\end{pmatrix}.
$$


## Soluciones de norma mínima

Supongamos ahora que $A$ es de rango pleno por filas. Entonces para cualquier $b$, el sistema $Ax=b$ es compatible. Queremos calcular la solución con norma (asociada al producto escalar estándar) mínima. 

Al ser $A$ de rango pleno por filas, podemos calcular $A^D$, que es inversa de $A$ por la derecha. Claramente, $A(A^D)b=(AA^D)b=b$, por lo que $x=A^Db$ es una solución al sistema de ecuaciones. 

Sea ahora $x$ otra solución del sistema. Entonces $A(x-A^Db)=0$, y por tanto $x-A^Db\in \operatorname{N}(A)$. De esta forma, $x=A^Db+z$ con $Az=0$. Tenemos así que $\Vert x\Vert^2 = \Vert A^Db\Vert^2+\Vert z\Vert^2+2\langle z,A^Db\rangle$. Pero 

$$
\langle z,A^Db\rangle=z^t(A^t(AA^t)^{-1})b=(Az)^t(AA^t)^{-1}b= 0 (AA^t)^{-1}b=0,
$$

por lo que 

$$
\Vert x\Vert^2 = \Vert A^Db\Vert^2+\Vert z\Vert^2 \ge \Vert A^Db\Vert^2.
$$

### Resultado

Sea $A\in \mathcal{M}_{m\times n}(K)$ de rango pleno por filas y sea $b\in K^m$. Entonces el sistema $Ax=b$ es compatible y la solución de norma mínima es $x=A^Db$.


## Inversas generalizadas de Moore-Penrose

Vamos a intentar mezclar las dos definiciones que acabamos de dar en una: buscamos la solución mínimo-cuadrática de norma mínima. Para ello usaremos un concepto de inversa que generaliza los conceptos de inversa, inversa a derecha e inversa a izquierda.

Decimos que $A\in \mathcal{M} _{m\times n}(K)$ tiene una inversa generalizada si existe $B\in \mathcal{M} _{n\times m}(K)$ tal que

1. $ABA = A$,
1. $BAB = B$,
1. $AB$ y $BA$ son simétricas.

Por ser $AB$ y $BA$ simétricas, se tiene que $AB=(AB)^t=B^tA^t$ y $BA=(BA)^t = A^tB^t$.

Si $C$ es otra inversa generalizada de $A$, entonces 

$$
\begin{aligned}
B &= BAB = (A^t B^t) B = (A^t C^t A^t) B^t B = (C A) A^t B^t B = C A (B A) B = C A B,  \\
C &= CAC = C(C^tA^t) = CC^t(A^tB^tA^t) = C C^t A^t (A B) = C (A C) A B = C A B. 
\end{aligned}
$$

Por tanto, la inversa generalizada de $A$, de existir, es única. La denotaremos por tanto $A^+$.

### Ejemplos

1. Si $A$ es cuadrada y tiene inversa, entonces $A^+=A^{-1}$. 

1. Si $A$ es de rango pleno por filas, entonces $A^+=A^D =A^t(A A^t)^{-1}$.

1. Si $A$ es de rango pleno por columnas, entonces $A^+=A^I = (A^t A)^{-1}A^t$. 


Sea $A=CF$ una factorización de rango pleno de $A$. Sea $B=F^DC^I$ (tanto $F^D$ como $C^I$ existen por ser la $F$ de rango pleno por filas y $C$ de rango pleno por columnas).  

1. $ABA = (CF)(F^DC^I)(CF)=C(FF^D)(C^IC)F=CF=A$,
1. $BAB = (F^DC^I)(CF)(F^DC^I)=F^D(C^IC)(FF^D)C^I=F^DC^I=B$,
1. $AB = (CF)(F^DC^I)=C C^I$, que es simétrica por ser $C^I=C^+$; $BA=(F^DC^I)(CF)=F^DF$, que también es simétrica al ser $F^D=F^+$.

Por tanto, $B=A^+$.

### Resultado

Toda matriz tiene una inversa generalizada de Moore-Penrose.

### Ejemplo

Si volvemos, una vez más, a la matriz 

$$
A=\begin{pmatrix}1 & 0\\1 & 1\\1 & 2\end{pmatrix},
$$

recordemos que 

$$
A^I=(A^tA)^{-1}A^t=\begin{pmatrix}\frac{5}{6} & \frac{1}{3} & - \frac{1}{6}\\- \frac{1}{2} & 0 & \frac{1}{2}\end{pmatrix}.
$$

Y por tanto $A^+=A^I$.


Sea $Ax=b$ un sistema lineal de ecuaciones. Si el sistema es compatible, entonces existe $x_0$ tal que $Ax_0=b$. Por tanto, 

$$
A(A^+b)=AA^+Ax_0=Ax_0=b.
$$

Luego compatible implica $A(A^+b)=b$. El recíproco es claramente cierto. Tenemos así el siguiente resultado.

### Resultado

Un sistema de ecuaciones $Ax=b$ es compatible si y sólo si $A(A^+b)=b$.

Veamos ahora cómo serían, de ser el sistema $Ax=b$ compatible, todas las soluciones. Si $x$ es una solución de ese sistema, entonces $A^+Ax=A^+(Ax)=A^+b$. Luego

$$
x=x+A^+b-A^+Ax=A^+b+(I-A^+A)x.
$$

Además, para cualquier $y$,

$$
A(A^+b+(I-A^+A)y)=AA^+b+Ay-AA^+Ay=b+Ay-Ay=b.
$$

Luego todas las soluciones de $Ax=b$ son de la forma

$$
A^+b+(I-A^+A)y
$$

con $y$ arbitrario.

### Resultado (parametrización de soluciones)

Sea $A\in\mathcal{M}_{m\times n}(K)$. Si $Ax=b$ es compatible, entonces todas las soluciones son de la forma

$$
x=A^+b+(I-A^+A)y
$$

con $y\in K^n$.

## Soluciones mínimo cuadráticas de norma mínima

Sea $A\in \mathcal{M}_{m\times n}(K)$ y sea $b\in \mathbb{K}^m$. Podemos escribir $A= CF$ con $C$ de rango pleno por columnas y $F$ de rango pleno por filas. 

El sistema de ecuaciones $Ax=b$ es equivalente a 

$$
\left\lbrace
\begin{aligned}
C y = b,\\
F x = y.
\end{aligned}
\right.
$$

Por ser $C$ de rango pleno for columnas, la única solución mínimo-cuadrática de $Cy=b$ es $y=C^Ib$. Por otro lado $F$ es de rango pleno por filas, por lo que la solución de norma mínima de $Fx=C^Ib$ es $x=F^DC^Ib= A^+b$.

Veamos que efectivamente $A^+b$ es la solución mínimo cuadrática de norma mínima del sistema $Ax=b$. Para ello escribimos $Ax-b=A(x-A^+b)+(I-AA^+)(-b)$.

Comprobemos que $A(x-A^+b)$ y $(I-AA^+)(-b)$ son ortogonales (usaremos que $(A^+)^t=(A^t)^+$).

$$
\begin{aligned}
\langle A(x-A^+b),(I-AA^+)(-b)\rangle  & = - (x- A^+b)^tA^t(I-AA^+)b \\
& = -(x^t-b^t(A^+)^t)A^t(I-AA^+)b \\
& = -(x^tA^t-b^t(A^+)^tA^t)(b-AA^+b)\\
& = -x^tA^tb+b^t(A^+)^tA^tb+x^tA^tAA^+b-b^t(A^+)^tA^tAA^+b.
\end{aligned}
$$

Ahora usamos que $A A^+=(AA^+)^t=(A^+)^tA^t$:


$$
\begin{aligned}
\langle A(x-A^+b),(I-AA^+)(-b)\rangle  & =  -x^tA^tb+b^tAA^tb+x^tA^t(A^+)^tA^tb-b^tA A^+AA^+b \\
& = -x^tA^tb+b^tAA^tb +x^tA^tb-b^tAA^+b=0.
\end{aligned}
$$

Por el Teorema de Pitágoras tenemos que 

$$
\begin{aligned}
\Vert Ax-b \Vert^2 & = \Vert A(x-A^+b)\Vert^2+\Vert(I-AA^+)(-b)\Vert^2\\
& = \Vert Ax-A(A^+b)\Vert^2+\Vert A(A^+b)-b\Vert^2 \ge \Vert A(A^+b)-b\Vert^2. 
\end{aligned}
$$

Por tanto, $\Vert A(A^+b)-b\Vert \le \Vert Ax-b\Vert$ para todo $x$, con igualdad si y sólo si $\Vert Ax-A(A^+b)\Vert =0$ (lo que equivale a $Ax=A(A^+b)$). Esto demuestra que $A^+b$ es una solución mínimo-cuadrática del sistema $Ax=b$.

Veamos ahora que la $A^+b$ también es mínima en norma entre las soluciones mínimo-cuadráticas. Sea $x$ con $\Vert Ax-b\Vert  = \Vert A(A^+b)-b\Vert$. Por la discusión del párrafo anterior, eso implica que $Ax=A(A^+b)$, y por tanto $x-A^+b\in \operatorname{N}(A)$. Esto significa que $x=A^+b+z$ con $z\in \operatorname{N}(A)$. Así,

$$
\Vert x\Vert ^2 = \Vert A^+b\Vert ^2 +\Vert z\Vert ^2+2\langle A^+b,z\rangle.
$$

Veamos cuánto vale el último sumando de esta expresión:

$$
\begin{aligned}
\langle z,A^+b\rangle & = z^tA^+b=z^tA^+AA^+b=z^tA^t(A^+)^t A^+b\\
& =(Az)^t(A^+)^tA^+b=0(A^+)^tA^+b=0.
\end{aligned}
$$

En particular, hemos probado que 

$$
A^+b\in \operatorname{N}(A)^\perp.
$$

De esta forma 

$$
\Vert x\Vert ^2 = \Vert A^+b\Vert ^2 +\Vert z\Vert ^2\ge \Vert A^+b\Vert ^2,
$$

con lo que queda probado que $A^+$ es la solución mínimo-cuadrática de norma mínima.

## Descomposición por valores singulares

Sea $A\in \mathcal{M}_{m\times n}(\mathbb{R})$. La matriz $A^tA$ es simétrica, luego existe $U$ ortogonal de forma que $U^t(A^tA)U=D$ con $D$ una matriz diagonal. 

Sea $\lambda$ un autovalor de $A^tA$, por tanto existe $x\neq 0$ de forma que $(A^tA)x=\lambda x$. Entonces 

$$
0\le \Vert A x\Vert ^2 = \langle Ax,Ax\rangle = (Ax)^t(Ax)=x^t(A^tAx)= \lambda x^tx = \lambda \Vert x\Vert ^2,
$$

por lo que $\lambda \ge 0$. De esta forma, podemos reordenar las columnas de $U$ de forma que los valores de la diagonal de $D$ sean $d_1^2\ge d_2^2\ge \dots \ge d_r^2 > 0= d_{r+1}=\dots = d_n$. Hemos visto que $\operatorname{rg}(A^tA)=\operatorname{rg}(A)$, y sabemos que $U$ no es más que un producto de matrices elementales (ya que tiene inversa), deducimos que $r=\operatorname{rg}(D)=\operatorname{rg}(A)$.

Por tanto, existe una base ortonormal $\lbrace u_1,\dots,u_n\rbrace$ de $\mathbb{R}^n$ (las columnas de $U$) tal que  $A^tA u_i=d_i^2u_i$ para todo $i$. Para cada $j\in\lbrace 1,\dots,r\rbrace$, definimos $v_j=\frac1{d_j}Au_j$. Para $j,k\in \lbrace 1,\dots,r\rbrace$,

$$
\langle v_j,v_k\rangle = \frac{1}{d_jd_k} u_j^tA^tAu_k=\begin{cases}
0, \text{ si } j\neq k,\\
1, \text{ si } j=k,
\end{cases}
$$

por lo que $\lbrace v_1,\dots,v_r\rbrace\subseteq \mathbb{R}^m$ es un conjunto de vectores ortonormales. Ampliamos esta base a una base $\lbrace v_1,\dots,v_m\rbrace$ ortonormal de $\mathbb{R}^m$. 


Tomemos $j\in \lbrace 1,\dots,m\rbrace$ e $i\in\lbrace 1,\dots,n\rbrace$.

- Si $i=j \le r$, entonces $v_i^t A u_i = v_i^td_iv_i=d_i$.

- Si $i=j>r$, entonces $v_i^t Au_i=v_i^t 0=0=d_i$, ya que $u_i\in \operatorname{N}(A^tA)=\operatorname{N}(A)$.

- Si $i\neq j$, si $i>r$, al igual que antes $v_j^tAu_i=v_j0=0$; si $i\le r$, entonces $v_j^tAu_i=v_j^td_iv_i=d_i0=0$.

Con esto hemos demostrado que si consideramos la matriz $V$ que tiene por columnas $\lbrace v_1,\dots,v_m\rbrace$, entonces

$$
V^tAU=D
$$

y como $V^t=V^{-1}$ y $U^t=U^{-1}$, deducimos que 

$$
A=VDU^t,
$$

a la que llamamos *descomposición de valores singulares* de $A$. Los $d_i$ los podemos escoger no negativos, en cuyo caso se conocen como valores singulares de $A$.

Para simpificar la notación, usaremos $D=\operatorname{diag}(d_1,\dots,d_n)$ a la matriz que tiene en como entradas $d_{ii}=d_i$ y $d_{ij}=0$ si $i\neq j$. 

$$
\begin{aligned}
A & =(v_1\mid \dots \mid v_m) D (u_1\mid\dots \mid u_m)^t = (d_1v_1\mid \dots \mid d_r v_r \mid 0 \mid \dots \mid 0) (u_1 \mid \dots \mid u_m)^t \\
& = (d_1v_1\mid\dots \mid d_rv_r)(u_1\mid \dots \mid u_r)^t = (v_1\mid\dots \mid v_r) \operatorname{diag}(d_1,\dots,d_r) (u_1\mid \dots \mid u_r)^t.
\end{aligned}
$$

A la descomposición 

$$
A=(v_1\mid\dots \mid v_r) \operatorname{diag}(d_1,\dots,d_r) (u_1\mid \dots \mid u_r)^t
$$

se le conoce como *descomposición por valores singulares compacta* de $A$.

### Resultado 

Dada $A\in\mathcal{M}_{m\times n}(\mathbb R)$ de rango $r$. Si $A=(v_1\mid\dots \mid v_r) \operatorname{diag}(d_1,\dots,d_r) (u_1\mid \dots \mid u_r)^t$ es una descomposición por valores singulares compacta, entonces 

$$
A^+=(u_1\mid\dots \mid u_r) \operatorname{diag}\left(\frac{1}{d_1},\dots,\frac{1}{d_r}\right) (v_1\mid \dots \mid v_r)^t.
$$

### Ejemplo

Veamos cómo es la descomposición por valores singulares de 

$$
A=\begin{pmatrix}1 & 0\\1 & 1\\1 & 2\end{pmatrix}
$$

Para ello vamos a utilizar `sympy` (las cuentas a mano pueden resultar muy tediosas incluso con este ejemplo tan sencillo). 

Una vez definida la matriz $A$ con 
```python
A=Matrix([[1,0],[1,1],[1,2]])
``` 
podemos calcular la descomposición con 
```
V,D,U = A.singular_value_decomposition()
```
Y obtenemos $A=VDU^t$:

$$
A=\begin{pmatrix}\frac{- \sqrt{30} - \sqrt{3}}{6 \sqrt{5 - \sqrt{10}}} & \frac{- \sqrt{3} + \sqrt{30}}{6 \sqrt{\sqrt{10} + 5}}\\\frac{- \sqrt{30} + 2 \sqrt{3}}{6 \sqrt{5 - \sqrt{10}}} & \frac{2 \sqrt{3} + \sqrt{30}}{6 \sqrt{\sqrt{10} + 5}}\\\frac{\sqrt{3} \sqrt{5 - \sqrt{10}}}{6} & \frac{\sqrt{3} \sqrt{\sqrt{10} + 5}}{6}\end{pmatrix} \begin{pmatrix}\sqrt{4 - \sqrt{10}} & 0\\0 & \sqrt{\sqrt{10} + 4}\end{pmatrix} \begin{pmatrix}\frac{\sqrt{2} \left(- \sqrt{10} - 1\right)}{2 \sqrt{\sqrt{10} + 10}} & \frac{3 \sqrt{2}}{2 \sqrt{\sqrt{10} + 10}}\\\frac{\sqrt{2} \left(-1 + \sqrt{10}\right)}{2 \sqrt{10 - \sqrt{10}}} & \frac{3 \sqrt{2}}{2 \sqrt{10 - \sqrt{10}}}\end{pmatrix}.
$$

Si calculamos $UD^{-1}V^t$, obtenemos 

$$
A^+ = \begin{pmatrix}\frac{5}{6} & \frac{1}{3} & - \frac{1}{6}\\- \frac{1}{2} & 0 & \frac{1}{2}\end{pmatrix}.
$$

## Norma inducida de una matriz

Sea $A\in \mathcal{M}_{m\times n}(K)$. Tomamos en $K^n$ y $K^m$ la norma inducida por un producto escalar. Definimos

$$
\Vert A\Vert =\sup\lbrace \Vert Ax\Vert : x\in K^n, \Vert x\Vert=1\rbrace=\sup\left\lbrace \frac{\Vert Ax\Vert}{\Vert x\Vert} : x\in K^n, \Vert x\Vert\neq 0\right\rbrace.
$$

Se tiene que 

- $\Vert A\Vert \ge 0$, y $\Vert A\Vert=0$ si y sólo si $A$ es la matriz nula,
- $\Vert a A\Vert =\vert a\vert \Vert A\Vert$ para todo $a\in K$,
- $\Vert A+B\Vert \le \Vert A\Vert + \Vert B\Vert$, para cualquier $B\in \mathcal{M}_{m\times n}(K)$.

Además, si $m=n$, entonces 

- $\Vert A B\Vert \le \Vert A \Vert \Vert B\Vert$.

Llamaremos a $\Vert A\Vert$ la *norma inducida* por las normas en $K^n$ y $K^m$.

Supongamos que $K=\mathbb{R}$ y $n=m$. Si $A$ es invertible, entonces $\operatorname{rg}(A)=n$, y como $\operatorname{rg}(A^tA)=\operatorname{rg}(A)$, deducimos que $A^tA$ también es regular. Sabemos que los valores propios de $A^tA$ son no negativos y reales, y como es regular, son todos no nulos, y por tanto positivos. Sean $d_1^2\ge \dots \ge d_n^2$ los valores propios de $A^tA$ ($d_1,\dots, d_n$ son los valores singulares de $A$). Sea $A=VDU^t$ la descomposición en valores singulares de $A$, con $D=\operatorname{diag}(d_1,\dots,d_n)$. 

Al ser $U^tU=I$, se tiene que

$$
\Vert Ux\Vert^2 \langle Ux,Ux\rangle = \langle x, U^tUx\rangle = \langle x,x\rangle = \Vert x\Vert,
$$

por lo que $\Vert Ux\Vert =\Vert x\Vert$. Lo mismo ocurre con $V$, esto es, $\Vert Vx\Vert =\Vert x\Vert$. Además, todo $x\in \mathbb{R}^n$ con $\Vert x \Vert =1$ se puede escribir como $Uy$ con $\Vert y\Vert =1$ (basta tomar $y=U^tx$, pues $Uy=UU^tx=x$).

Entonces,

$$
\begin{aligned}
\Vert A \Vert  & = \sup\lbrace \Vert Ax \Vert : x\in \mathbb{R}^n, \Vert x\Vert =1\rbrace=\sup\lbrace \Vert VDU^t x \Vert : x\in \mathbb{R}^n, \Vert x\Vert =1\rbrace\\ 
& = \sup\lbrace \Vert DU^t x \Vert : x\in \mathbb{R}^n, \Vert x\Vert =1\rbrace = \sup\lbrace \Vert DU^tUy \Vert : y\in \mathbb{R}^n, \Vert y\Vert =1\rbrace\\
& = \sup\lbrace\Vert Dy\Vert : y\in \mathbb{R}^n, \Vert y\Vert =1 \rbrace= \Vert D\Vert.
\end{aligned}
$$

Sea $x=(x_1,\dots,x_n)$. Consideramos $\Vert x\Vert$ la norma inducida por el producto escalar usual. Entonces 

$$
\begin{aligned}
\Vert Dx\Vert^2 & = \langle Dx,Dx\rangle = \langle x, D^tDx\rangle= \langle x, D^2x\rangle \\ 
& =\sum_{i=1}^n x_i^2d_i^2\le d_1^2 \sum_{i=1}^n x_i^2 = d_1^2 \Vert x\Vert,
\end{aligned}
$$

por lo que $\Vert D\Vert \le d_1$. Nótese que $D\mathbf{e}_1=d_1\mathbf{e_1}$, y que $\Vert \mathbf{e}_1\Vert =1$, por lo que $\Vert D \mathbf{e_1}\Vert =d_1$, lo que lleva a $\Vert D\Vert=d_1$. De esta forma, tenemos probado el siguiente resultado.


### Resultado

Sea $A$ una matriz cuadrada invertible, y sea $d$ su mayor valor singular. Entonces


$$
\Vert A\Vert = d.
$$




## Número de condición de una matriz

Dada una matriz regular $A$, se define su *número de condición* como 

$$
\kappa(A)=\Vert A\Vert \Vert A^{-1}\Vert.
$$

Supongamos que tenemos el sistema $Ax=b$, y que se ha producido un error $e$ al leer $b$. El error en la solución que obtenemos tras esa lectura es $A^{-1}e$, pues $A(x+A^{-1}e)=Ax+e=b+e$. Si queremos medir la razón entre el error relativo de la solución obtenida respecto al error relativo cometido en la lectura de $b$ (en norma), podemos hacerlo con la cantidad

$$
\frac{\frac{\Vert A^{-1}e\Vert}{\Vert A^{-1}b\Vert}}{\frac{\Vert e\Vert}{\Vert b\Vert}}=\frac{\Vert A^{-1}e\Vert}{\Vert e\Vert}\frac{\Vert b \Vert}{\Vert A^{-1}b \Vert}.
$$

El supremo de esta razón es

$$
\begin{aligned}
\sup\left\lbrace \frac{\Vert A^{-1}e\Vert}{\Vert e\Vert} \frac{\Vert b \Vert}{\Vert A^{-1}b \Vert}: b\neq 0, e\neq 0 \right\rbrace & =  \sup\left\lbrace \frac{\Vert A^{-1}e\Vert}{\Vert e\Vert} :  e\neq 0 \right\rbrace \sup\left\lbrace \frac{\Vert b \Vert}{\Vert A^{-1}b \Vert}: b\neq 0 \right\rbrace \\
 & = 
\sup\left\lbrace \frac{\Vert A^{-1}e\Vert}{\Vert e\Vert} :  e\neq 0 \right\rbrace \sup\left\lbrace \frac{\Vert A b \Vert}{\Vert b \Vert}: b\neq 0 \right\rbrace \\
& = \Vert A^{-1}\Vert \Vert A\Vert =\kappa(A).
\end{aligned}
$$

Por tanto, el número de condición de $A$ mide cuán mal condicionado está resolver el problema $Ax=b$ (véase una motivación con `MATLAB` en este [enlace](https://blogs.mathworks.com/cleve/2017/07/17/what-is-the-condition-number-of-a-matrix/)).

Los valores singulares de $A^-1$ son los inversos de los valores singulares de $A$, por lo que si $d_1$ es el mayor valor singular de $A$ y $d_n$ es el menor valor singular, entonces usando que $\Vert A\Vert=d_1$, obtenemos

$$
\kappa(A)=\frac{d_1}{d_n}.
$$




