---
layout: page
title: Espacio afín euclídeo
---

# Espacio afín euclídeo

*Estas notas se basan en las [transparencias](https://www.ugr.es/~arobles/MatApl(CivilADE)/Tema5_beamer.pdf) de [A. M. Robles Pérez](https://www.ugr.es/~arobles/).*

## Motivación

Consideremos el sistema de ecuaciones $Ax=b$ sobre un cuerpo $K$. Si $x$ e $y$ son soluciones, entonces $Ax=Ay=b$, y por tanto $A(x-y)=0$, esto es, $x-y$ está en el núcleo de la aplicación lineal asociada a la matriz $A$, que es un espacio vectorial. De hecho, si $x_0$ es una solución del sistema ($Ax_0=b$) y $x$ es cualquier otra solución, entonces $x=x_0+(x-x_0)$. Esto es, $x$ es el trasladado de $x_0$ mediante un vector del (sub)espacio vectorial con ecuaciones $Ax=0$. Así, el conjunto de soluciones $S$ de $Ax=b$ es de la forma 

$$
S=x_0+W,
$$

con $W$ el conjunto de soluciones de $Ax=0$, y para cualesquiera dos soluciones $x,y\in S$, tenemos que $y-x\in W$.

## Espacio afín

Sea $V$ un espacio vectorial real (cuyos elementos llamaremos *vectores* o *direcciones*).

Sea $\mathfrak{A}$ un conjunto no vacío cuyos elementos denominaremos *puntos*.

Decimos que $\mathfrak{A}$ es un *espacio afín sobre* $V$ si existe una aplicación 

$$
\phi: \mathfrak{A}\times\mathfrak{A} \to V
$$

tal que a cada par ordenado de puntos $(P,Q) \in \mathfrak{A}\times\mathfrak{A}$ le hace corresponder un vector $\phi(P,Q) \in V$ (denotado por $\overrightarrow{PQ}$) de forma que se satisfacen las siguientes propiedades.

1. Para cada punto $P\in\mathfrak{A}$ y cada vector $\mathbf{v}\in V$, existe un único punto $Q\in\mathfrak{A}$ tal que $\overrightarrow{PQ}=\mathbf{v}$.
2. Para cualesquiera puntos $P, Q, R \in \mathfrak{A}$, se verifica la igualdad $\overrightarrow{PQ}+\overrightarrow{QR}=\overrightarrow{PR}$.


El espacio afín se denotará por $(\mathfrak{A},V,\phi)$, aunque habitualmente se omitirá la referencia a la aplicación $\phi$ e, incluso, a $V$.

### Propiedades 

Sea $(\mathfrak{A},V,\phi)$ un espacio afín. 

1.  $\overrightarrow{PQ}=\mathbf{0}_{V}$ si y sólo si  $P=Q$.
3.  $\overrightarrow{PQ}=-$ $\overrightarrow{QP}$ para cualesquiera $P, Q\in\mathfrak{A}$.
4.  Si $\overrightarrow{PQ}=\overrightarrow{P'Q'}$, entonces   $\overrightarrow{PP'}=\overrightarrow{QQ'}$ para cualesquiera  $P, P', Q, Q'\in\mathfrak{A}$ (regla del paralelogramo).
5.  $\overrightarrow{PQ}+\overrightarrow{QR}+\overrightarrow{RP}=\mathbf{0}_{V}$    (relación de Chasles).

### Ejemplo 

Supongamos que $\mathfrak{A}=\mathbb{R}^{n}$ y que $V=\mathbb{R}^{n}$. Si $P,Q\in\mathfrak{A}$ están dados por $P=(p_{1},\ldots,p_{n})$ y $Q=(q_{1},\ldots,q_{n})$, definimos la aplicación $\phi$ por 

$$
\phi(P,Q)= (q_{1}-p_{1},\ldots,q_{n}-p_{n}).
$$

Es fácil comprobar que $(\mathfrak{A},V,\phi)$ es un espacio afín (el llamado *espacio afín usual*) y que se cumplen las propiedades de la transparencia anterior. 

## Dimensión de un espacio afín

Se define la *dimensión del espacio* afín $\mathfrak{A}$ como la dimensión del espacio vectorial $V$.

La dimensión del espacio afín del ejemplo anterior es $n$, ya que su espacio vectorial subyacente, $\mathbb{R}^{n}$, es $n$ dimensional.


## Sistemas de referencia

Sea $\mathfrak{A}$ un espacio afín sobre $V$ de dimensión $n$. Un *sistema de referencia afín* en $\mathfrak{A}$ es un conjunto de la forma $\mathfrak{R}=\lbrace O;B\rbrace$, donde $O\in\mathfrak{A}$ (denominado *origen del sistema de referencia*) y $B=\lbrace \mathbf{e} _{1},\mathbf{e} _{2},\ldots,\mathbf{e} _{n}\rbrace$ es una base de $V$.

Sea $P\in\mathfrak{A}$. Como $\overrightarrow{OP}\in V$, entonces existen escalares $x_{1},x_{2},\ldots,x_{n}\in\mathbb{R}$ tales que 

$$
\overrightarrow{OP}=x_{1}\mathbf{e}_{1}+x_{2}\mathbf{e}_{2}+\cdots+x_{n}\mathbf{e}_{n}.
$$

Diremos que $(x_{1},x_{2},\ldots,x_{n})$ son las *coordenadas* de $P$ respecto de $\mathfrak{R}$ y las denotaremos por $P=(x_{1},x_{2},\ldots,x_{n}) _{\mathfrak{R}}$.


### Ejemplo

En el espacio afín usual tridimensional, consideramos el sistema de referencia determinado por

- el origen $O=(1,1,-1)$,

- la base $B=\lbrace(1,1,1),(1,1,0),(1,0,0)\rbrace$.

Calculemos las coordenadas del punto $P=(5,4,3)$.

Como $\overrightarrow{OP}=\phi(O,P) = (5,4,3) - (1,1,-1) = (4,3,4)$, tenemos que hallar las coordenadas de este vector respecto de $B$, es decir, 
los valores $x _{1}, x _{2}, x _{3}$ tales que

$$
(4,3,4) = x _{1}(1,1,1) + x _{2}(1,1,0) + x _{3}(1,0,0).
$$

Resolviendo el sistema, obtenemos que $P=(4,-1,1) _\mathfrak{R}$


##  Variedades afines 

Sean $\mathfrak{A}$ un espacio afín sobre el espacio vectorial $V$, $P\in\mathfrak{A}$ y $W$ un subespacio vectorial de $V$.

Se denomina *variedad afín* de $\mathfrak{A}$ asociada a $W$ con base en el punto $P$ al conjunto

$$
\mathfrak{L}=\left\lbrace X\in\mathfrak{A} : \overrightarrow{PX}\in W\right\rbrace,
$$

que se denota por $\mathfrak{L}=P+W$.

### Ejemplo
En el espacio afín tridimensional usual, calculemos la variedad afín $\mathfrak{L}$ que pasa por el punto $P=(1,-1,1)$ con subespacio asociado

$$
W=\left\lbrace (w_{1},w_{2},w_{3})\in\mathbb{R}^{3}\mid w_{3}=w_{1}+w_{2} \right\rbrace.
$$

Recordemos que la aplicación $\phi$ asociada al espacio afín tridimensional usual está dada por $\phi((p_1,p_2,p_3),(q_1,q_2,q_3))=(q_{1}-p_{1},q_{2}-p_{2},q_{3}-p_{3})$.

Entonces tenemos que 

$$
\begin{aligned}
    \mathfrak{L} & = \left\lbrace X\in\mathfrak{A} \mid \overrightarrow{PX}\in W \right\rbrace  = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid (x_{1},x_{2},x_{3})-(1,-1,1) \in W \right\rbrace \\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid (x_{1}-1,x_{2}+1,x_{3}-1) \in W \right\rbrace \\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid x_{3}-1=(x_{1}-1)+(x_{2}+1) \right\rbrace  \\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid x_{3}-1=x_{1}+x_{2} \right\rbrace\\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid x_{1}+x_{2}-x_{3}=-1 \right\rbrace.
\end{aligned}
$$

### Propiedad 

Sea la variedad afín $\mathfrak{L}=\left\lbrace X\in\mathfrak{A} : \overrightarrow{PX}\in W \right\rbrace$. Si $Q\in\mathfrak{L}$, entonces se verifica que $\mathfrak{L}=\left\lbrace X\in\mathfrak{A} \mid \overrightarrow{QX}\in W\right\rbrace$.

En otras palabras, si $\mathfrak{L}=P+W$ y $Q\in\mathfrak{L}$, entonces $\mathfrak{L}=Q+W$.

Deducimos que la definición de variedad afín es independiente del punto base.

Se define la *dimensión de la variedad afín* $\mathfrak{L}=P+W$ como la dimensión de $W$.

En el ejemplo anterior, $\dim W=2$, por lo que $\dim\mathfrak{L}=2$. Por tanto, la variedad afín $\mathfrak{L}$ es un plano.


## Algunas variedades afines destacables

1.  Si $\mathfrak{L}=P+W$ con $W=\lbrace\mathbf{0}\rbrace$, entonces $\mathfrak{L}$ se reduce a un punto y $\dim\mathfrak{L}=0$. Las variedades afines de dimensión $0$ son los puntos.

2.  Si $\mathfrak{L}=P+W$ con $W=\mathcal{L}(\lbrace\mathbf{u}\rbrace)$, $\mathbf{u}\neq\mathbf{0}$,  entonces $\dim\mathfrak{L}=1$. Se trata de la *recta* que “pasa” por el punto $P$ con dirección $\mathbf{u}$.

3.  Si $\mathfrak{L}=P+W$, donde una base de $W$ es
    $B_{W}=\lbrace\mathbf{u},\mathbf{v}\rbrace$, entonces $\dim\mathfrak{L}=2$. Se trata de un *plano* que “pasa” por el punto $P$ con vectores directores $\mathbf{u}$ y $\mathbf{v}$.

4.  Si $\mathfrak{L}=P+W$ con $\dim W=n-1$ y $\dim V=n$, entonces $\dim\mathfrak{L}=n-1$. Se trata de un *hiperplano* que “pasa” por el punto $P$ con dirección dada por el subespacio vectorial definido por la base de $W$ considerada.

5.  Dado un espacio afín $\mathfrak{A}$ y $P_0,\dots,P_n$ puntos de $\mathfrak{A}$, la variedad generada por $P_0,\dots,P_n$ es la menor variedad afín que contiene a estos puntos, que es $P_0+W$, donde $W$ es el espacio vectorial generado por $\overrightarrow {P_0P_1},\dots,\overrightarrow {P_0P_n}$. Diremos que $P_0,\dots, P_n$ son afinmente independientes si los vectores $\overrightarrow {P_0P_1},\dots,\overrightarrow {P_0P_n}$ son linealmente independientes (esta definición no depende de la elección de $P_0$).

## Suma e intersección de variedades

Si $\mathfrak{L}_1=P_1+W_1$ y $\mathfrak{L}_2=P_2+W_2$ son dos variedades afines tales que existe $P\in\mathfrak{L}_1\cap \mathfrak{L}_2$, entonces 

$$
\mathfrak{L}_1\cap \mathfrak{L}_2= P+(W_1\cap W_2).
$$ 

Si $\mathfrak{L}_1$ y  $\mathfrak{L}_2$ no se cortan, entonces su intersección es vacía.

La variedad suma de $\mathfrak{L}_1$ y $\mathfrak{L}_2$ se define como la menor variedad que contiene a ambas (o como la variedad que genera la unión de ambas). En este caso, 

$$
\mathfrak{L}_1+\mathfrak{L}_2=P_1+(\mathcal{L}(\overrightarrow {P_1P_2})+W_1+W_2).
$$

## Variedades afines: ecuaciones 

Es posible asociar ecuaciones paramétricas e implícitas a las variedades afines.

Sea $(\mathfrak{A},V,\phi )$ un espacio afín de dimensión $n$.

Sea $\mathfrak{L}=P+W$ la variedad afín que “pasa” por el punto $P\in\mathfrak{A}$ con subespacio director $W$.

Sea $\mathfrak{R}=\lbrace O;B\rbrace$ un sistema de referencia para $\mathfrak{A}$ con $B=\lbrace\mathbf{e} _{1},\dots,\mathbf{e} _{n}\rbrace$.

Supongamos que $\dim W=r$, con $1\leq r < n$, y que  $\lbrace \mathbf{u} _{1},\dots,\mathbf{u} _{r} \rbrace$ es una base de $W$.

Si $X\in\mathfrak{L}$, entonces $\mathbf{w}=\overrightarrow{PX}\in W$. Para dicho vector, existirán escalares $\lambda_{1},\lambda_{2},\dots,\lambda_{r}$ tales que 

$$
\mathbf{w}=\lambda_{1}\mathbf{u} _{1}+\lambda _{2}\mathbf{u} _{2}+\cdots+\lambda _{r}\mathbf{u} _{r}.
$$

Como $B$ es base de $V$ y $W$ es un subespacio de $V$, cada vector $\mathbf{u} _{i}$ se puede expresar en la base $B$, por lo que existen escalares $\omega _{ij}$ tales que 

$$
\begin{aligned}
    \mathbf{u}_{1} & = \omega_{11}\mathbf{e}_{1}+\cdots+\omega_{n1}\mathbf{e}_{n}, \\
    &  \vdots \\
    \mathbf{u}_{r} & = \omega_{1r}\mathbf{e}_{1}+\cdots+\omega_{nr}\mathbf{e}_{n}.
\end{aligned}
$$

$$
\begin{aligned}
    \mathbf{w}  & =  \lambda_{1}(\omega_{11}\mathbf{e}_{1}+\cdots+\omega_{n1}\mathbf{e}_{n}) + \dots+ \lambda_{r}(\omega_{1r}\mathbf{e}_{1}+\cdots+\omega_{nr}\mathbf{e}_{n}) \\
     & = (\omega_{11}\lambda_{1}+\cdots+\omega_{1r}\lambda_{r})\mathbf{e}_{1} + \dots+ (\omega_{n1}\lambda_{1}+\cdots+\omega_{nr}\lambda_{r})\mathbf{e}_{n}.
\end{aligned}
$$

Por otra parte, $\overrightarrow{PX}=\overrightarrow{PO}+\overrightarrow{OX}$, por lo que $\overrightarrow{OX}=\overrightarrow{OP}+\mathbf{w}$. Supongamos que las coordenadas de $\overrightarrow{OX}$ y $\overrightarrow{OP}$, en la base $B$, son $(x_{1},x_{2},\ldots,x_{n})$ y $(p_{1},p_{2},\ldots,p_{n})$, respectivamente.

Entonces, 

$$
\left\lbrace 
\begin{aligned}
    x_{1} & = p_{1}+\omega_{11}\lambda_{1}+\omega_{12}\lambda_{2}+\cdots+\omega_{1r}\lambda_{r}, \\
    x_{2} & = p_{2}+\omega_{21}\lambda_{1}+\omega_{22}\lambda_{2}+\cdots+\omega_{2r}\lambda_{r}, \\
    &  \vdots \\
    x_{n} & = p_{n}+\omega_{n1}\lambda_{1}+\omega_{n2}\lambda_{2}+\cdots+\omega_{nr}\lambda_{r}.
\end{aligned} 
\right.
$$ 

Estas son las ecuaciones paramétricas de la variedad afín $\mathfrak{L}$. Concretamente, son las relaciones que existen entre las coordenadas de $X$ y $P$ en el sistema de referencia $\mathfrak{R}$ y las coordenadas de $w$ en la base $B$.

En forma matricial, viene dada por

$$
\begin{pmatrix} 
x_{1} \\ 
x_{2} \\ 
\vdots \\ 
x_{n} 
\end{pmatrix} =
\begin{pmatrix} 
p_{1} \\ 
p_{2} \\ 
\vdots \\ 
p_{n} 
\end{pmatrix} +
\lambda_{1} 
\begin{pmatrix} 
\omega_{11} \\ 
\omega_{21} \\ 
\vdots \\ 
\omega_{n1} 
\end{pmatrix} +
\lambda_{2} 
\begin{pmatrix} 
\omega_{12} \\ 
\omega_{22} \\ 
\vdots \\ 
\omega_{n2} 
\end{pmatrix} +
\cdots +
\lambda_{r} 
\begin{pmatrix} 
\omega_{1r} \\ 
\omega_{2r} \\ 
\vdots \\ 
\omega_{nr} 
\end{pmatrix}.
$$

Cuando $X$ “recorre” la variedad $\mathfrak{L}$, los coeficientes $\lambda_{i}$ “recorren” el subespacio vectorial $W$, por lo que las ecuaciones anteriores pueden verse como un sistema compatible (determinado) en las incógnitas $\lambda_{i}$.


Para obtener las ecuaciones implícitas o cartesianas de $\mathfrak{L}$ basta con imponer que, en el sistema compatible (determinado) en las incógnitas $\lambda_{i}$, el rango de la matriz de coeficientes coincida con el rango de la matriz ampliada y con el número de incógnitas $\lambda_{i}$. Es decir, que 

$$
\operatorname{rg}\begin{pmatrix}
    x_{1}-p_{1} & \omega_{11} & \omega_{12} & \cdots & \omega_{1r} \\
    x_{2}-p_{2} & \omega_{21} & \omega_{22} & \cdots & \omega_{2r} \\
    \vdots & \vdots & \vdots & & \vdots \\
    x_{r}-p_{r} & \omega_{r1} & \omega_{r2} & \cdots & \omega_{rr} \\
    x_{r+1}-p_{r+1} & \omega_{r+1,1} & \omega_{r+1,2} & \cdots & \omega_{r+1,r} \\
    \vdots & \vdots & \vdots & & \vdots \\
    x_{n}-p_{n} & \omega_{n1} & \omega_{n2} & \cdots & \omega_{nr}
\end{pmatrix} =r,
$$ 

lo que es equivalente a imponer que los menores de orden $r+1$ sean cero. El resultado final es un sistema de $n-r$ ecuaciones.

También podemos considerar el sistema anterior considerando $\lambda_1,\dots,\lambda_r$ como incógnitas

$$
\left\lbrace 
\begin{aligned}
    \omega_{11}\lambda_{1}+\omega_{12}\lambda_{2}+\cdots+\omega_{1r}\lambda_{r} & = x_{1} - p_{1},\\
    \omega_{21}\lambda_{1}+\omega_{22}\lambda_{2}+\cdots+\omega_{2r}\lambda_{r} & = x_{2} - p_{2}, \\
    & \vdots \\
    \omega_{n1}\lambda_{1}+\omega_{n2}\lambda_{2}+\cdots+\omega_{nr}\lambda_{r} & = x_{n} -p_{n}.
\end{aligned} 
\right.
$$ 

Si aplicamos eliminación por filas, obtendremos $n-r$ ecuaciones (no homogéneas en general) en $x_1,\dots,x_n$ que son las ecuaciones implícitas de la variedad, y que surgen de imponer que el sistema original es compatible.

### Ejemplo

En el espacio afín usual tridimensional se considera un sistema de referencia $\mathfrak{R}=\lbrace O;B=\lbrace \mathbf{e} _{1},\mathbf{e} _{2},\mathbf{e} _{3} \rbrace \rbrace$, el punto $P$ con coordenadas en $(1,-2,1) _\mathfrak{R}$ y el susbepacio vectorial $W$ generado por los vectores $\mathbf{u} _{1}$ y $\mathbf{u} _{2}$, siendo $(1,2,-1)$ y $(2,1,1)$ las coordenadas de $\mathbf{u} _{1}$ y $\mathbf{u} _{2}$ en la base $B$, respectivamente.

Las ecuaciones paramétricas de la variedad afín que pasa por $P$ con dirección $W$ son

$$
\begin{pmatrix} 
x_{1} \\ 
x_{2} \\ 
x_{3} 
\end{pmatrix} =
\begin{pmatrix} 
1 \\ 
-2 \\ 
1 
\end{pmatrix} +
\lambda_{1} 
\begin{pmatrix} 
1 \\ 
2 \\ 
-1 
\end{pmatrix} +
\lambda_{2} 
\begin{pmatrix}
 2 \\ 
 1 \\ 
 1 
 \end{pmatrix}, \quad\lambda_{1},\lambda_{2}\in\mathbb{R}.
$$

Es decir, 

$$
\left\lbrace
\begin{aligned}
    x_{1} & = 1+\lambda_{1}+2\lambda_{2}, \\
    x_{2} & = -2+2\lambda_{1}+\lambda_{2}, \\
    x_{3} & = 1-\lambda_{1}+\lambda_{2}.
\end{aligned} 
\right.
$$

Tomando $\lambda_1$ y $\lambda_2$ como incógnitas, el sistema se transforma en el sistema 

$$
\left\lbrace 
\begin{array}{rcl} 
    \lambda_{1}+2\lambda_{2} &= & x_1-1, \\ 
    2\lambda_{1}+\lambda_{2} &= & x_{2}+2, \\
    -\lambda_{1}+\lambda_{2} &= & x_{3}-1. 
\end{array} 
\right.
$$

Aplicando eliminación gaussiana vemos que el sistema  es compatible (determinado) si, y solo si,

$$
-x_1+x_2+x_{3}+2 = 0.
$$

Por tanto, la ecuación implícita de la variedad afín que pasa por $P$ con dirección $W$ es 

$$
x_{1}-x_{2}-x_{3}=2.
$$

# Espacio afín euclídeo

Sea $\mathfrak{A}$ un espacio afín con espacio vectorial asociado $V$. Si $V$ es un espacio vectorial euclídeo, es decir, si está dotado de un producto escalar $\langle\cdot,\cdot\rangle$, entonces decimos que $\mathfrak{A}$ es un *espacio afín euclídeo*.

Sea $\mathfrak{A}$ un espacio afín euclídeo asociado al espacio vectorial $V$. Se define la función *distancia* en $\mathfrak{A}$ como la aplicación 

$$
\operatorname{d}:\mathfrak{A}\times\mathfrak{A} \to \mathbb{R}_{0}^{+},\quad \operatorname{d}(P,Q)= \Vert \overrightarrow {PQ}\Vert , 
$$

donde $\Vert \cdot \Vert$ es la norma asociada al producto escalar de $V$.

Recordemos que la norma de un vector $\mathbf{v}\in V$, asociada al producto escalar $\langle\cdot,\cdot\rangle$ en $V$, está definida por $\Vert \mathbf{v}\Vert =\sqrt{\langle \mathbf{v},\mathbf{v} \rangle}.$ 

### Ejemplo   
Consideremos el producto escalar usual en $\mathbb{R}^{n}$. Además, sea el espacio afín $\mathbb{R}^{n}$, sobre el espacio vectorial $\mathbb{R}^{n}$, con la aplicación $\phi$ definida por

$$
\phi((x_{1},\ldots,x_{n}),(y_{1},\ldots,y_{n})) = (y_{1}-x_{1},\ldots,y_{n}-x_{n}).
$$

Entonces $\mathbb{R}^{n}$ es un espacio euclídeo con distancia dada por

$$
\operatorname{d}((x_{1},\ldots,x_{n}),(y_{1},\ldots,y_{n})) = \sqrt{(y_{1}-x_{1})^{2}+\cdots+(y_{n}-x_{n})^{2}}.
$$

En particular, si en el espacio afín euclídeo tridimensional usual $\mathbb{R}^{3}$ consideramos los puntos $P=(2,3,1)$ y $Q=(0,-1,5)$, entonces la distancia entre ellos es igual a

$$
\operatorname{d}(P,Q)=\sqrt{(0-2)^{2}+(-1-3)^{2}+(5-1)^{2}}=\sqrt{4+16+16}=6.
$$

### Resultado 

Si $P$, $Q$ y $R$ son tres puntos de un espacio afín euclídeo con distancia $\operatorname{d}$, entonces se cumplen las siguientes propiedades.

1.  $\operatorname{d}(P,Q)=0$ si, y solo si, $P=Q$.

2.  $\operatorname{d}(P,Q)=\operatorname{d}(Q,P).$

3.  $\operatorname{d}(P,R) \leq \operatorname{d}(P,Q)+\operatorname{d}(Q,R)$.

## Complemento ortogonal 

Sea $\mathfrak{A}$ un espacio afín euclídeo asociado al espacio vectorial $V$. Sea $\mathfrak{L}$ una variedad afín con subespacio director $W$ y sea un punto $P\in\mathfrak{A}$.

Llamamos *complemento ortogonal* a $\mathfrak{L}$ por el punto $P$ a la variedad afín $\mathfrak{L} _{P}^{\perp}=P+W^{\perp}$.

## Proyección ortogonal de un punto sobre una variedad afín

Llamamos *referencia rectangular* en un espacio euclídeo
$\mathfrak{A}$, con espacio vectorial subyacente $V$ de dimensión $n$, a todo sistema de referencia $R=\lbrace O;B\rbrace$ tal que $B$ es una base ortonormal de $V$.

Un vector $\mathbf{v}$ se dice *ortogonal* a una variedad afín $\mathfrak{L}$, del espacio afín euclídeo $\mathfrak{A}$, si $\mathbf{v}$ es ortogonal al subespacio director de $\mathfrak{L}$. Denotaremos este hecho por $\mathbf{v}\perp\mathfrak{L}$.

Consideremos la variedad afín $\mathfrak{L}=P+W$ que pasa por $P$ con dirección $W$. Sea un punto $Q\notin\mathfrak{L}$. Sea $p_{W}(\overrightarrow{PQ})$ la proyección ortogonal de $\overrightarrow{PQ}$ sobre $W$. El único punto $Q'\in \mathfrak{L}$ tal que $\overrightarrow{PQ'}=p_{W}(\overrightarrow{PQ})$ se llama *proyección ortogonal* del punto $Q$ sobre la variedad afín $\mathfrak{L}$ y se denota por $p_{\mathfrak{L}}(Q)$.

### Resultado 

Se verifica que $\lbrace p_{\mathfrak{L}}(Q)\rbrace=\mathfrak{L}\cap \mathfrak{L}_{Q}^{\perp}$.

### Ejemplo

Hallemos la proyección ortogonal del punto $Q=(1,3,-1)$, del espacio euclídeo tridimensional usual, sobre la recta $r$ de ecuaciones paramétricas

$$
\left\lbrace 
\begin{array}{l} 
x=2\lambda, \\ 
y=2-\lambda, \\ 
z=1+2\lambda. 
\end{array} 
\right.
$$

Comenzamos tomando la variedad afín $\mathfrak{L}$ correspondiente a la recta $r$, esto es, la variedad que pasa por el punto $(0,2,1)$ y  tiene como subespacio vectorial asociado el generado por el vector $(2,-1,2)$, es decir, $W=\mathcal{L}(\lbrace(2,-1,2)\rbrace)$.

El complemento ortogonal $W^{\perp}$ de $W$ está engendrado por dos vectores linealmente independientes ortogonales a $W$. Podemos tomar, por ejemplo, $(1,2,0)$ y $(1,0,-1)$. Por tanto,

$$
W^{\perp}=\mathcal{L}\left( \lbrace(1,2,0),(1,0,-1) \rbrace\right).
$$

Así, $W^{\perp}$ es un subespacio vectorial de dimensión $2$ que admite como ecuaciones paramétricas 

$$
\left\lbrace
\begin{array}{l} 
x=\alpha+\beta, \\ 
y=2\alpha, \\ 
z=-\beta. 
\end{array} 
\right.
$$

Para hallar una ecuación implícita de $W^{\perp}$, discutimos tomando $\alpha,\beta$ como incógnitas y $x,y,z$ como parámetros. 

Por tanto, el sistema será compatible (determinado) si, y solo si,

$$
z-\frac{1}{2}y+x = 0.
$$ 

En consecuencia, una ecuación implícita de $W^{\perp}$ es 

$$
2x-y+2z=0.
$$

La variedad $\mathfrak{L}_{Q}^{\perp}$, que pasa por $Q=(1,3,-1)$ y con subespacio director $W^{\perp}$, está formada por los puntos $X=(x,y,z)$ tales que el vector
$ \overrightarrow{QX}=(x-1,y-3,z+1) $ pertenece a $W^{\perp}$, es decir, los puntos $X$ tales que $\overrightarrow{QX}$ satisface $2x-y+2z=0$.

Por tanto, $\mathfrak{L}_{Q}^{\perp}$ está formada por los puntos $X=(x,y,z)$ tales que 

$$
2(x-1)-(y-3)+2(z+1)=0.
$$

Como $\mathfrak{L}_{Q}^{\perp}$ es ortogonal a $r$, entonces su intersección con $r$ proporciona la proyección ortogonal de $Q=(1,3,-1)$ sobre $r$.

Ahora bien, si un punto de $r$ está en $\mathfrak{L}_{Q}^{\perp}$, entonces 

$$
2(2\lambda-1) - (2-\lambda-3) + 2(1+2\lambda+1) = 0 \Rightarrow 9\lambda+3=0 \Rightarrow \lambda=-\frac{1}{3}.
$$

Concluimos que la proyección ortogonal de $Q$ sobre $r$ es el punto

$$
Q'=(2\lambda, 2-\lambda, 1+2\lambda) = \left( -\frac{2}{3}, \frac{7}{3}, \frac{1}{3} \right).
$$


### Distancia de un punto a una variedad afín

Definimos la *distancia* de un punto $Q$ a una variedad afín $\mathfrak{L}=P+W$ como

$$
\operatorname{d}(Q,\mathfrak{L}) = \inf\lbrace \operatorname{d}(Q,X) \mid X\in\mathfrak{L}\rbrace.
$$

En realidad, ese ínfimo es un mínimo como vamos a ver a continuación. Para todo $X\in\mathfrak{L}$, si llamamos $Q'=p_{\mathfrak{L}}(Q)$, tenemos que $\overrightarrow{QQ'}\in W^\perp$ y $\overrightarrow{Q'X}\in W$. Así, por el Teorema de Pitágoras

$$
\operatorname{d}(Q,X)^2=\Vert \overrightarrow{QX}\Vert^2= \Vert \overrightarrow{QQ'} + \overrightarrow{Q'X}\Vert^2 = \Vert \overrightarrow{QQ'}\Vert^2+ \Vert \overrightarrow{Q'X}\Vert^2 \ge \Vert \overrightarrow{QQ'} \Vert^2 = \operatorname{d}(Q,Q')^2,
$$

por lo que

$$
\operatorname{d}(Q,\mathfrak{L}) = \operatorname{d}\left(Q,p_{\mathfrak{L}}(Q)\right).
$$

### Ejemplo

Continuando con el ejemplo anterior, la distancia de $Q=(1,3,-1)$ a la
recta $r$ de ecuaciones paramétricas

$$
\left\lbrace
\begin{array}{l} 
    x=2\lambda, \\ 
    y=2-\lambda, \\ 
    z=1+2\lambda. 
\end{array}
\right.
$$

es 

$$\begin{aligned}
    \operatorname{d}(Q,r) & = \operatorname{d}\left(Q,p_{r}(Q)\right) \\
    & = \operatorname{d}\left((1,3,-1),\left(-\frac{2}{3},\frac{7}{3},\frac{1}{3}\right)\right) \\
    & = \sqrt{\left(-\frac{2}{3}-1\right)^{2}+\left(\frac{7}{3}-3\right)^{2}+\left(\frac{1}{3}+1\right)^{2}} \\
    & = \sqrt{5}.
\end{aligned}
$$ 

Dadas dos variedades afines $\mathfrak{L}_{1}=P_{1}+W_{1}$ y
$\mathfrak{L}_{2}=P_{2}+W_{2}$, se define la distancia entre ambas como

$$
\operatorname{d}(\mathfrak{L}_{1},\mathfrak{L}_{2}) = \inf\lbrace\operatorname{d}(Q_{1},Q_{2}) : Q_{1}\in\mathfrak{L}_{1} \text{ y } Q_{2}\in\mathfrak{L}_{2}\rbrace.
$$

Si dos variedades se cortan entonces la distancia entre ellas es cero.

Si las dos variedades no se cortan, diremos que $\mathfrak{L}_1$ y $\mathfrak{L}_2$ son *paralelas* si $W_1\subseteq W_2$ o $W_2\subseteq W_1$, y diremos que se cruzan en caso contrario.

El siguiente resultado proporciona un procedimiento para calcular la distancia entre dos variedades que no se cortan (esto es, entre dos variedades que o bien se cruzan o bien son paralelas).

### Resultado

Sean $\mathfrak{L}_{1}=P _{1}+W _{1}$ y $\mathfrak{L} _{2}=P _{2}+W _{2}$ dos variedades afines que no se cortan. Entonces se verifica que

$$
\operatorname{d}(\mathfrak{L} _{1},\mathfrak{L} _{2}) = \operatorname{d}(P _{1},\mathfrak{L}),
$$

donde $\mathfrak{L}=P_{2}+(W_{1}+W_{2})$ es la variedad que contiene a $\mathfrak{L} _{2}$ y es paralela a $\mathfrak{L} _{1}$.

Para probar este hecho, vamos a demostrar primero que $\operatorname{d}(P_1,\mathfrak{L})\le \operatorname{d}(\mathfrak{L}_1,\mathfrak{L}_2)$. Sean $Q_1\in \mathfrak{L}_1$ y $Q_2\in \mathfrak{L}_2$. Vamos a buscar $C\in \mathfrak{L}=P_2+W_1+W_2$ de forma que $\overrightarrow{Q_1 Q_2}=\overrightarrow{P_1C}$. Tenemos que 

$$
\overrightarrow{Q_1 Q_2}=\overrightarrow{Q_1P_1}+\overrightarrow{P_1P_2}+\overrightarrow{P_2Q_2}.
$$

Sea $C$ el único punto del espacio afín de forma que $\overrightarrow{P_2C}=\overrightarrow{Q_1P_1}+\overrightarrow{P_2Q_2}$. Como $\overrightarrow{Q_1P_1}+\overrightarrow{P_2Q_2}\in W_1+W_2$, deducimos que $C\in \mathfrak{L}$. De esta forma 

$$
\overrightarrow{Q_1 Q_2}=\overrightarrow{P_1P_2}+\overrightarrow{P_2C}=\overrightarrow{P_1C},
$$

y por tanto $\operatorname{d}(Q_1,Q_2)=\operatorname{d}(P_1,C)\ge \operatorname{d}(P_1,\mathfrak{L})$. Por tanto, $\operatorname{d}(P_1,\mathfrak{L})\le \operatorname{d}(Q_1,Q_2)$ para todo $Q_1\in \mathfrak{L}_1$ y $Q_2\in \mathfrak{L}_2$, por lo que $\operatorname{d}(P_1,\mathfrak{L})\le \operatorname{d}(\mathfrak{L}_1,\mathfrak{L}_2)$.

Veamos ahora que $\operatorname{d}(\mathfrak{L} _1,\mathfrak{L} _2)\le  \operatorname{d}(P _1,\mathfrak{L})$. Sabemos que $\operatorname{d}(P _1,\mathfrak{L})=\operatorname{d}(P _1,p _{\mathfrak{L}}(P _1))$. 

Sea $C=p_{\mathfrak{L}}(P _1)$. Si probamos que existen $Q _1\in \mathfrak{L} _1$ y $Q _2\in \mathfrak{L} _2$ de forma que $\overrightarrow{Q _1 Q _2}=\overrightarrow{P _1C}$, entones habremos terminado, pues 

$$
\operatorname{d}(\mathfrak{L}_1,\mathfrak{L}_2)\le \operatorname{d}(Q_1,Q_2)=\operatorname{d}(P_1,C)=\operatorname{d}(P_1,\mathfrak{L}).
$$

Ahora bien, al estar $C\in \mathfrak{L}=P_2+W_1+W_2$, sabemos que $\overrightarrow{P_2C}\in W_1+W_2$. Sean $w_1\in W_1$ y $w_2\in W_2$ tales que $\overrightarrow{P_2C}=w_1+w_2$. Por ser $-w_1\in W_1$, existe $Q_1\in \mathfrak{L}_1$ tal que $-w_1=\overrightarrow{P_1Q_1}$, y en consecuencia $w_1=\overrightarrow{Q_1P_1}$. Además, existe $Q_2\in \mathfrak{L}_2$ tal que $w_2=\overrightarrow{P_2Q_2}$. Tenemos así que 

$$
\begin{aligned}
\overrightarrow{P_1C} & =\overrightarrow{P_1P_2}+\overrightarrow{P_2C}=\overrightarrow{P_1P_2}+w_1+w_2\\
& =\overrightarrow{P_1P_2}+\overrightarrow{Q_1P_1}+\overrightarrow{P_2Q_2}= \overrightarrow{Q_1Q_2}.
\end{aligned}
$$

### Distancia de un punto a un hiperplano

Sea $P=(p_1,\dots,p_n)$ un punto y $\mathfrak{H}\equiv a_1x_1+\dots+a_nx_n+b=0$ un hiperplano. Llamemos a $Q=(q_1,\dots,q_n)$ a la proyección ortogonal de $P$ en $\mathfrak{H}$, y $v=(a_1,\dots,a_n)$. Entonces $v$ y $\overrightarrow{PQ}$ son ambos perpendiculares a $\mathfrak{H}$, por lo que el ángulo que forman es $0$ o $\pi$. Por tanto, $\vert\langle \overrightarrow{PQ},v\rangle\vert =  \Vert \overrightarrow{PQ}\Vert \Vert v\Vert$, y por tanto,

$$
\operatorname{d}(P,\mathfrak{H})=\Vert \overrightarrow{PQ}\Vert = \frac{|a_1(q_1-p_1)+\dots+a_n(q_n-p_n) |}{\Vert (a_1,\dots,a_n)\Vert } = \frac{|a_1p_1+\dots+a_np_n+b|}{\sqrt{a_1^2+\dots+a_n^2}}.
$$

### Ejemplo

La distancia del punto $P=(2,3)$ a la recta $r\equiv x+y-1=0$ es 

$$
\operatorname{d}(P,r)=\frac{4}{\sqrt{2}}=2\sqrt{2}.
$$

## Producto vectorial

Sean $\mathbf{u},\mathbf{v}\in K^3$, con $K$ un cuerpo, y sean  $(u_1,u_2,u_3)$ y $(v_1,v_2,v_3)$ sus coordenadas respecto a una base $B=\lbrace\mathbf{e}_1,\mathbf{e}_2,\mathbf{e}_e\rbrace$ de $K^3$. El producto vectorial de $\mathbf{u}$ y $\mathbf{v}$ se define mediante el siguiente determinante formal

$$
\mathbf{u}\wedge \mathbf{v} = \begin{vmatrix}
\mathbf{e}_1 & \mathbf{e}_2 & \mathbf{e}_3\\
u_1 & u_2 & u_3 \\
v_1 & v_2 & v_ 3
\end{vmatrix}= 
\begin{vmatrix} u_2 & u_3 \\ v_2 & v_3 \end{vmatrix} \mathbf{e}_1 +
\begin{vmatrix} u_3 & u_1 \\ v_3 & v_1 \end{vmatrix} \mathbf{e}_2 +
\begin{vmatrix} u_1 & u_2 \\ v_1 & v_2 \end{vmatrix} \mathbf{e}_3.
$$

### Propiedades

- $(\mathbf{u} \wedge \mathbf{v})\in\mathfrak{L}(\lbrace\mathbf{u},\mathbf{v}\rbrace)^\perp$. 

- $\mathbf{u} \wedge \mathbf{v}=0$ si y sólo si $\dim(\mathfrak{L}(\lbrace\mathbf{u},\mathbf{v}\rbrace)\le 1$.

- $\Vert \mathbf{u} \wedge \mathbf{v}\Vert = \Vert \mathbf{u}\Vert \Vert\mathbf{v}\Vert-\langle\mathbf{u},\mathbf{v}\rangle^2=\Vert \mathbf{u}\Vert \Vert\mathbf{v}\Vert \sin(\measuredangle(\mathbf{u},\mathbf{v}))$.
