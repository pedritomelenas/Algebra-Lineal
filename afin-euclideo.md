# Espacio afín euclídeo

*Estas notas se basan en las [transparencias](https://www.ugr.es/~arobles/MatApl(CivilADE)/Tema5_beamer.pdf) de [A. M. Robles Pérez](https://www.ugr.es/~arobles/).*

## Motivación

Consideremos el sistema de ecuaciones $Ax=b$ sobre un cuerpo $K$. Si $x$ e $y$ son soluciones, entonces $Ax=Ay=b$, y por tanto $A(x-y)=0$, esto es, $x-y$ está en el núcleo de la aplicación lineal asociada a la matriz $A$, que es un espacio vectorial. De hecho, si $x_0$ es una solución del sistema ($Ax_0=b$) y $x$ es cualquier otra solución, entonces $x=x_0+(x-x_0)$. Esto es, $x$ es el trasladado de $x_0$ mediante un vector del (sub)espacio vectorial con ecuaciones $Ax=0$. Así, el conjunto de soluciones $S$ de $Ax=b$ es de la forma 

$$
S=x_0+W,
$$

con $W$ el conjunto de soluciones de $Ax=0$, y para cualesquiera dos soluciones $x,y\in S$, tenemos que $y-x\in W$.

## Espacio afín

Sea $V$ un espacio vectorial real (cuyos elementos llamaremos *vectores* o *direcciones*)

Sea $\mathcal{A}$ un conjunto no vacío cuyos elementos denominaremos *puntos*

Decimos que $\mathcal{A}$ es un *espacio afín sobre* $V$ si existe una aplicación 

$$
\phi: \mathcal{A}\times\mathcal{A} \to V
$$

tal que a cada par ordenado de puntos $(P,Q) \in \mathcal{A}\times\mathcal{A}$ le hace corresponder un vector $\phi(P,Q) \in V$ (denotado por $\overrightarrow{PQ}$) de forma que se satisfacen las siguientes propiedades.

1. Para cada punto $P\in\mathcal{A}$ y cada vector $\mathbf{v}\in V$, existe un único punto $Q\in\mathcal{A}$ tal que $\overrightarrow{PQ}=\mathbf{v}$.
2. Para cualesquiera puntos $P, Q, R \in \mathcal{A}$, se verifica la igualdad $\overrightarrow{PQ}+\overrightarrow{QR}=\overrightarrow{PR}$.


El espacio afín se denotará por $(\mathcal{A},V,\phi)$, aunque habitualmente se omitirá la referencia a la aplicación $\phi$ e, incluso, a $V$.

### Propiedades 

Sea $(\mathcal{A},V,\phi)$ un espacio afín. 

1.  $\overrightarrow{PQ}=\overrightarrow{O_{V}}$ si y sólo si  $P=Q$.
3.  $\overrightarrow{PQ}=-$ $\overrightarrow{QP}$ para cualesquiera $P, Q\in\mathcal{A}$.
4.  Si $\overrightarrow{PQ}=\overrightarrow{P'Q'}$ entonces   $\overrightarrow{PP'}=\overrightarrow{QQ'}$ para cualesquiera  $P, P', Q, Q'\in\mathcal{A}$ (regla del paralelogramo).
5.  $\overrightarrow{PQ}+\overrightarrow{QR}+\overrightarrow{RP}=\overrightarrow{O_{V}}$    (relación de Chasles).

### Ejemplo 

Supongamos que $\mathcal{A}=\mathbb{R}^{n}$ y que $V=\mathbb{R}^{n}$. Si $P,Q\in\mathcal{A}$ están dados por $P=(p_{1},\ldots,p_{n})$ y $Q=(q_{1},\ldots,q_{n})$, definimos la aplicación $\phi$ por 

$$
\phi(P,Q)= (q_{1}-p_{1},\ldots,q_{n}-p_{n}).
$$

Es fácil comprobar que $(\mathcal{A},V,\phi)$ es un espacio afín (el llamado *espacio afín usual*) y que se cumplen las propiedades de la transparencia anterior. 

## Dimensión de un espacio afín

Se define la *dimensión del espacio afín $\mathcal{A}$* como la dimensión del espacio vectorial $V$.

La dimensión del espacio afín del ejemplo anterior es$n$, ya que su espacio vectorial subyacente, $\mathbb{R}^{n}$, es $n$ dimensional.


## Sistemas de referencia 

Sea $\mathcal{A}$ un espacio afín sobre $V$ de dimensión $n$. Un *sistema de referencia afín* en $\mathcal{A}$ es un conjunto de la forma $\mathcal{R}=\lbrace O;B\rbrace$, donde $O\in\mathcal{A}$ (denominado *origen del sistema de referencia*) y $B=\lbrace\mathbf{e}_{1},\mathbf{e}_{2},\ldots,\mathbf{e}_{n}\rbrace$ es una base de $V$.

Sea $P\in\mathcal{A}$. Como $\overrightarrow{OP}\in V$, entonces existen escalares $x_{1},x_{2},\ldots,x_{n}\in\mathbb{R}$ tales que 

$$
\overrightarrow{OP}=x_{1}\mathbf{e}_{1}+x_{2}\mathbf{e}_{2}+\cdots+x_{n}\mathbf{e}_{n}.
$$

Diremos que $(x_{1},x_{2},\ldots,x_{n})$ son las *coordenadas de $P$ respecto de $\mathcal{R}$* y las denotaremos por $P=(x_{1},x_{2},\ldots,x_{n}) _{\mathcal{R}}$.


### Ejemplo

En el espacio afín usual tridimensional, consideramos el sistema de referencia determinado por

-  el origen $O=(1,1,-1)$,

-  la base $B=\lbrace(1,1,1),(1,1,0),(1,0,0)\rbrace$.

Calculemos las coordenadas del punto $P=(5,4,3)$.

Como $\overrightarrow{OP}=\phi(O,P) = (5,4,3) - (1,1,-1) = (4,3,4)$, tenemos que hallar las coordenadas de este vector respecto de $B$, es decir, los valores $x_{1}, x_{2}, x_{3}$ tales que

$$
(4,3,4) = x_{1}(1,1,1) + x_{2}(1,1,0) + x_{3}(1,0,0).
$$

Resolviendo el sistema, obtenemos que $P=(4,-1,1)_\mathcal{R}$


##  Variedades afines 

Sean $\mathcal{A}$ un espacio afín sobre el espacio vectorial $V$, $P\in\mathcal{A}$ y $W$ un subespacio vectorial de $V$.

Se denomina *variedad afín* de $\mathcal{A}$ asociada a $W$ con base en el punto $P$ al conjunto

$$
\mathcal{L}=\left\lbrace X\in\mathcal{A} : \overrightarrow{PX}\in W\right\rbrace,
$$

que se denota por $\mathcal{L}=P+W$.

### Ejemplo
En el espacio afín tridimensional usual, calculemos la
variedad afín $\mathcal{L}$ que pasa por el punto $P=(1,-1,1)$ con subespacio asociado

$$
W=\left\lbrace (w_{1},w_{2},w_{3})\in\mathbb{R}^{3}\mid w_{3}=w_{1}+w_{2} \right\rbrace.
$$

Recordemos que la aplicación $\phi$ asociada al espacio afín tridimensional usual está dada por $\phi((p_1,p_2,p_3),(q_1,q_2,q_3))=(q_{1}-p_{1},q_{2}-p_{2},q_{3}-p_{3})$.

Entonces tenemos que 

$$
\begin{aligned}
    \mathcal{L} & = \left\lbrace X\in\mathcal{A} \mid \overrightarrow{PX}\in W \right\rbrace  = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid (x_{1},x_{2},x_{3})-(1,-1,1) \in W \right\rbrace \\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid (x_{1}-1,x_{2}+1,x_{3}-1) \in W \right\rbrace \\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid x_{3}-1=(x_{1}-1)+(x_{2}+1) \right\rbrace  \\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid x_{3}-1=x_{1}+x_{2} \right\rbrace\\
    & = \left\lbrace(x_{1},x_{2},x_{3}) \in\mathbb{R}^{3} \mid x_{1}+x_{2}-x_{3}=-1 \right\rbrace.
\end{aligned}
$$

### Propiedad 

Sea la variedad afín $\mathcal{L}=\left\lbrace X\in\mathcal{A} : \overrightarrow{PX}\in W \right\rbrace$. Si $Q\in\mathcal{L}$, entonces se verifica que $\mathcal{L}=\left\lbrace X\in\mathcal{A} \mid \overrightarrow{QX}\in W\right\rbrace$.

En otras palabras, si $\mathcal{L}=P+W$ y $Q\in\mathcal{L}$, entonces $\mathcal{L}=Q+W$.

Deducimos que la definición de variedad afín es independiente del punto base.

Se define la *dimensión de la variedad afín* $\mathcal{L}=P+W$ como la dimensión de $W$.

En el ejemplo anterior, $\dim W=2$, por lo que $\dim\mathcal{L}=2$. Por tanto, la variedad afín $\mathcal{L}$ es un plano.


## Algunas variedades afines destacables

1.  Si $\mathcal{L}=P+W$ con $W=\lbrace\mathbf{0}\rbrace$, entonces $\mathcal{L}$ se reduce a un punto y $\dim\mathcal{L}=0$. Las variedades afines de dimensión $0$ son los puntos.

2.  Si $\mathcal{L}=P+W$ con $W=L(\lbrace\mathbf{u}\rbrace)$, $\mathbf{u}\neq\mathbf{0}$,  entonces $\dim\mathcal{L}=1$. Se trata de la *recta* que “pasa” por el punto $P$ con dirección $\mathbf{u}$.

3.  Si $\mathcal{L}=P+W$, donde una base de $W$ es
    $B_{W}=\lbrace\mathbf{u},\mathbf{v}\rbrace$, entonces $\dim\mathcal{L}=2$. Se trata de un *plano* que “pasa” por el punto $P$ con vectores directores $\mathbf{u}$ y $\mathbf{v}$.

4.  Si $\mathcal{L}=P+W$ con $\dim W=n-1$ y $\dim V=n$, entonces $\dim\mathcal{L}=n-1$. Se trata de un *hiperplano* que “pasa” por el punto $P$ con dirección dada por el subespacio vectorial definido por la base de $W$ considerada.

5.  Dado un espacio afín $\mathcal{A}$ y $P_0,\dots,P_n$ puntos de $\mathcal{A}$, la variedad generada por $P_0,\dots,P_n$ es la menor variedad afín que contiene a estos puntos, que es $P_0+W$, donde $W$ es el espacio vectorial generado por $\overrightarrow {P_0P_1},\dots,\overrightarrow {P_0P_n}$. Diremos que $P_0,\dots, P_n$ son afinmente independientes si los vectores $\overrightarrow {P_0P_1},\dots,\overrightarrow {P_0P_n}$ son linealmente independientes (esta definición no depende de la elección de $P_0$).

## Suma e intersección de variedades

Si $\mathcal{L_1}=P_1+W_1$ y $\mathcal{L_2}=P_2+W_2$ son dos variedades afines tales que existe $P\in\mathcal{L_1}\cap \mathcal{L_2}$, entonces 

$$
\mathcal{L_1}\cap \mathcal{L_2}= P+(W_1\cap W_2).
$$ 

Si $\mathcal{L_1}$ y  $\mathcal{L_2}$ no se cortan, entonces su intersección es vacía.

La variedad suma de $\mathcal{L_1}$ y $\mathcal{L_2}$ se define como la menor variedad que contiene a ambas (o como la variedad que genera la unión de ambas). En este caso, 

$$
\mathcal{L_1}+\mathcal{L_2}=P_1+(\operatorname{L}(\overrightarrow {P_1P_2})+W_1+W_2).
$$

## Variedades afines: ecuaciones 

Es posible asociar ecuaciones paramétricas e implícitas a las variedades afines.

Sea $(\mathcal{A},V,\phi )$ un espacio afín de dimensión $n$.

Sea $\mathcal{L}=P+W$ la variedad afín que “pasa” por el punto $P\in\mathcal{A}$ con subespacio director $W$.

Sea $\mathcal{R}=\lbrace O;B\rbrace$ un sistema de referencia para $\mathcal{A}$ con $B=\lbrace\mathbf{e}_{1},\dots,\mathbf{e}_{n}\rbrace$.

Supongamos que $\dim W=r$, con $1\leq r<n$, y que  $\lbrace\mathbf{u} _{1},\dots,\mathbf{u} _{r}\rbrace$ es una base de $W$.

Si $X\in\mathcal{L}$, entonces existe un único vector $\mathbf{w}\in W$ tal que $X=P+\mathbf{w}$. Para dicho vector,  $\overrightarrow{PX}$ existirán escalares $\lambda_{1},\lambda_{2},\dots,\lambda_{r}$ tales que 

$$
\mathbf{w}=\lambda_{1}\mathbf{u}_{1}+\lambda_{2}\mathbf{u}_{2}+\cdots+\lambda_{r}\mathbf{u}_{r}.
$$

Como $B$ es base de $V$ y $W$ es un subespacio de $V$, cada vector $\mathbf{u}_{i}$ se puede expresar en la base $B$, por lo que existen escalares $\omega_{ij}$ tales que 

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

Por otra parte, supongamos que las coordenadas de $\overrightarrow{OX}$ y $\overrightarrow{OP}$, en la base $B$, son $(x_{1},x_{2},\ldots,x_{n})^{T}$ y $(p_{1},p_{2},\ldots,p_{n})^{T}$, respectivamente.

Entonces, de la igualdad 

$$
\overrightarrow{OX}=\overrightarrow{OP}+\mathbf{w}
$$ 

se deduce que 

$$
\left\lbrace 
\begin{aligned}
    x_{1} & = p_{1}+\omega_{11}\lambda_{1}+\omega_{12}\lambda_{2}+\cdots+\omega_{1r}\lambda_{r}, \\
    x_{2} & = p_{2}+\omega_{21}\lambda_{1}+\omega_{22}\lambda_{2}+\cdots+\omega_{2r}\lambda_{r}, \\
    & \;\; \vdots \\
    x_{n} & = p_{n}+\omega_{n1}\lambda_{1}+\omega_{n2}\lambda_{2}+\cdots+\omega_{nr}\lambda_{r}.
\end{aligned} 
\right.
$$ 

Estas son las ecuaciones paramétricas de la variedad afín $\mathcal{L}$. Concretamente, son las relaciones que existen entre las coordenadas de $X$ y $P$ en el sistema de referencia $\mathcal{R}$ y las coordenadas de $w$ en la base $B$.

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

Cuando $X$ “recorre” la variedad $\mathcal{L}$, los coeficientes $\lambda_{i}$ “recorren” el subespacio vectorial $W$, por lo que las ecuaciones anteriores pueden verse como un sistema compatible (determinado) en las incógnitas $\lambda_{i}$.


Para obtener las ecuaciones implícitas o cartesianas de $\mathcal{L}$ basta con imponer que, en el sistema compatible (determinado) en las incógnitas $\lambda_{i}$, el rango de la matriz de coeficientes coincida con el rango de la matriz ampliada y con el número de incógnitas $\lambda_{i}$. Es decir, que 

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
    & \;\; \vdots \\
    \omega_{n1}\lambda_{1}+\omega_{n2}\lambda_{2}+\cdots+\omega_{nr}\lambda_{r} & = x_{n} -p_{n}.
\end{aligned} 
\right.
$$ 

Si aplicamos eliminación por filas, obtendremos $n-r$ ecuaciones (no homogéneas en general) en $x_1,\dots,x_n$ que son las ecuaciones implícitas de la variedad, y que surgen de imponer que el sistema original es compatible.

### Ejemplo

En el espacio afín usual tridimensional se considera un sistema de referencia $\mathcal{R}=\lbrace O;B=\lbrace\mathbf{e}_{1},\mathbf{e}_{2},\mathbf{e}_{3}\rbrace\rbrace$, el punto $P$ con coordenadas en $(1,-2,1)_\mathcal{R}$ y el susbepacio vectorial $W$ generado por los vectores $\mathbf{u}_{1}$ y $\mathbf{u}_{2}$, siendo
$(1,2,-1)$ y $(2,1,1)$ las coordenadas de $\mathbf{u}_{1}$ y $\mathbf{u}_{2}$ en la base $B$, respectivamente.

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

Sea $\mathcal{A}$ un espacio afín con espacio vectorial asociado $V$. Si $V$ es un espacio vectorial euclídeo, es decir, si está dotado de un producto escalar $\langle\cdot,\cdot\rangle$, entonces decimos que $\mathcal{A}$ es un *espacio afín euclídeo*.

Sea $\mathcal{A}$ un espacio afín euclídeo asociado al espacio vectorial $V$. Se define la función *distancia* en $\mathcal{A}$ como la aplicación 

$$
\operatorname{d}:\mathcal{A}\times\mathcal{A} \to \mathbb{R}_{0}^{+},\quad \operatorname{d}(P,Q)= \Vert \overrightarrow {PQ}\Vert , 
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

Sea $\mathcal{A}$ un espacio afín euclídeo asociado al espacio vectorial $V$. Sea $\mathcal{L}$ una variedad afín con subespacio director $W$ y sea un punto $P\in\mathcal{A}$.

Llamamos *complemento ortogonal* a $\mathcal{L}$ por el punto $P$ a la variedad afín $\mathcal{L}_{P}^{\perp}=P+W^{\perp}$.

## Proyección ortogonal de un punto sobre una variedad afín

Llamamos *referencia rectangular* en un espacio euclídeo
$\mathcal{A}$, con espacio vectorial subyacente $V$ de dimensión $n$, a todo sistema de referencia $R=\lbrace O;B\rbrace$ tal que $B$ es una base ortonormal de $V$.

Un vector $\mathbf{v}$ se dice *ortogonal* a una variedad afín $\mathcal{L}$, del espacio afín euclídeo $\mathcal{A}$, si $\mathbf{v}$ es ortogonal al subespacio director de $\mathcal{L}$. Denotaremos este hecho por $\mathbf{v}\perp\mathcal{L}$.

Consideremos la variedad afín $\mathcal{L}=P+W$ que pasa por $P$ con dirección $W$. Sea un punto $Q\notin\mathcal{L}$. Sea $p_{W}(\overrightarrow{PQ})$ la proyección ortogonal de $\overrightarrow{PQ}$ sobre $W$. El punto $Q'=P+p_{W}(\overrightarrow{PQ})$ se llama *proyección ortogonal* del punto $Q$ sobre la variedad afín $\mathcal{L}$ y se denota por $p_{\mathcal{L}}(Q)$.

### Resultado 

Se verifica que $Q'=p_{\mathcal{L}}(Q)=\mathcal{L\cap L}_{Q}^{\perp}$.

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

Comenzamos tomando la variedad afín $\mathcal{L}$ correspondiente a la recta $r$, esto es, la variedad que pasa por el punto $(0,2,1)$ y  tiene como subespacio vectorial asociado el generado por el vector $(2,-1,2)$, es decir, $W=L(\lbrace(2,-1,2)\rbrace)$.

El complemento ortogonal $W^{\perp}$ de $W$ está engendrado por dos vectores linealmente independientes ortogonales a $W$. Podemos tomar, por ejemplo, $(1,2,0)$ y $(1,0,-1)$. Por tanto,

$$
W^{\perp}=\operatorname{L}\left( \lbrace(1,2,0),(1,0,-1) \rbrace\right).
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

La variedad $\mathcal{L}_{Q}^{\perp}$, que pasa por $Q=(1,3,-1)$ y con subespacio director $W^{\perp}$, está formada por los puntos $X=(x,y,z)$ tales que el vector
$ \overrightarrow{QX}=(x-1,y-3,z+1) $ pertenece a $W^{\perp}$, es decir, los puntos $X$ tales que $\overrightarrow{QX}$ satisface $2x-y+2z=0$.

Por tanto, $\mathcal{L}_{Q}^{\perp}$ está formada por los puntos $X=(x,y,z)$ tales que 

$$
2(x-1)-(y-3)+2(z+1)=0.
$$

Como $\mathcal{L}_{Q}^{\perp}$ es ortogonal a $r$, entonces su intersección con $r$ proporciona la proyección ortogonal de $Q=(1,3,-1)$ sobre $r$.

Ahora bien, si un punto de $r$ está en $\mathcal{L}_{Q}^{\perp}$, entonces 

$$
2(2\lambda-1) - (2-\lambda-3) + 2(1+2\lambda+1) = 0 \Rightarrow 9\lambda+3=0 \Rightarrow \lambda=-\frac{1}{3}.
$$

Concluimos que la proyección ortogonal de $Q$ sobre $r$ es el punto

$$
Q'=(2\lambda, 2-\lambda, 1+2\lambda) = \left( -\frac{2}{3}, \frac{7}{3}, \frac{1}{3} \right).
$$


### Distancia de un punto a una variedad afín

Definimos la *distancia* de un punto $Q$ a una variedad afín $\mathcal{L}=P+W$ como

$$
\operatorname{d}(Q,\mathcal{L}) = \inf\lbrace \operatorname{d}(Q,X) \mid X\in\mathcal{L}\rbrace.
$$

En realidad, ese ínfimo es un mínimo, ya que 

$$
\operatorname{d}(Q,\mathcal{L}) = \operatorname{d}\left(Q,p_{\mathcal{L}}(Q)\right).
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

Dadas dos variedades afines $\mathcal{L}_{1}=P_{1}+W_{1}$ y
$\mathcal{L}_{2}=P_{2}+W_{2}$, se define la distancia entre ambas como

$$
\operatorname{d}(\mathcal{L}_{1},\mathcal{L}_{2}) = \inf\lbrace\operatorname{d}(Q_{1},Q_{2}) : Q_{1}\in\mathcal{L}_{1}\;\text{ y }\;Q_{2}\in\mathcal{L}_{2}\rbrace.
$$

Si dos variedades se cortan entonces la distancia entre ellas es cero.

El siguiente resultado proporciona un procedimiento para calcular la distancia en caso contrario (esto es, entre dos variedades que o bien se cruzan o bien son paralelas).

### Resultado

Sean $\mathcal{L}_{1}=P_{1}+W_{1}$ y $\mathcal{L}_{2}=P_{2}+W_{2}$ dos variedades afines que no se cortan. Entonces se verifica que

$$
\operatorname{d}(\mathcal{L}_{1},\mathcal{L}_{2}) = d(P_{1},\mathcal{L}),
$$

donde $\mathcal{L}=P_{2}+(W_{1}+W_{2})$ es la variedad que contiene a $\mathcal{L}_{2}$ y es paralela a $\mathcal{L}_{1}$.

### Distancia de un punto a un hiperplano

Sea $P=(p_1,\dots,p_n)$ un punto y $\mathcal{H}\equiv a_1x_1+\dots+a_nx_n+b=0$ un hiperplano. Llamemos a $Q=(q_1,\dots,q_n)$ a la proyección ortogonal de $P$ en $\mathcal{H}$, y $v=(a_1,\dots,a_n)$. Entonces $v$ y $\overrightarrow{PQ}$ son ambos perpendiculares a $\mathcal{H}$, por lo que el ángulo que forman es $0$ o $\pi$. Por tanto, $|\langle \overrightarrow{PQ},v\rangle| =  \Vert \overrightarrow{PQ}\Vert \Vert v\Vert$, y por tanto,

$$
\operatorname{d}(P,\mathcal{H})=\Vert \overrightarrow{PQ}\Vert = \frac{|a_1(q_1-p_1)+\dots+a_n(q_n-p_n) |}{\Vert (a_1,\dots,a_n)\Vert } = \frac{|a_1p_1+\dots+a_np_n+b|}{\sqrt{a_1^2+\dots+a_n^2}}.
$$

### Ejemplo

La distancia del punto $P=(2,3)$ a la recta $r\equiv x+y-1=0$ es 

$$
\operatorname{d}(P,r)=\frac{4}{\sqrt{2}}=2\sqrt{2}.
$$

## Producto vectorial

Sean $\mathbf{u},\mathbf{v}\in K^3$, con $K$ un cuerpo, y sean  $(u_1,u_2,u_3)$ y $(v_1,v_2,v_3)$ sus coordenadas respecto a una base $B=\lbrace\mathbf{e}_1,\mathbf{e}_2,\mathbf{e}_e\rbrace$ de $K^3$. El producto vectorial de $\mathbb{u}$ y $\mathbb{v}$ se define mediante el siguiente determinante formal

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

- $(\mathbf{u} \wedge \mathbf{v})\in\mathcal{L}(\lbrace\mathbf{u},\mathbf{v}\rbrace)^\perp$. 

- $\mathbf{u} \wedge \mathbf{v}=0$ si y sólo si $\dim(\mathcal{L}(\lbrace\mathbf{u},\mathbf{v}\rbrace)\le 1$.

- $\Vert \mathbf{u} \wedge \mathbf{v}\Vert = \Vert \mathbf{u}\Vert \Vert\mathbf{v}\Vert-\langle\mathbf{u},\mathbf{v}\rangle^2=\Vert \mathbf{u}\Vert \Vert\mathbf{v}\Vert \sin(\measuredangle(\mathbf{u},\mathbf{v}))$.