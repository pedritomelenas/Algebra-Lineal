# Diagonalización por semejanza ortogonal de matrices simétricas

Sea $(V,\langle,\rangle)$ un espacio vectorial euclídeo. Un endomorfismo $f:V\to V$ se dice *simétrico* (o *autoadjunto*) si para todo $\mathbf{u},\mathbf{v}\in V$ se tiene que 

$$
\langle f(\mathbf{u}),\mathbf{v}\rangle =\langle \mathbf{u},f(\mathbf{v})\rangle.
$$

Si $B=\lbrace \mathbf{e}_1,\dots,\mathbf{e}_n\rbrace$ es una base ortonormal de $V$, y $A=\mathcal{M}(f;B)$, entonces $a_{ij}=\langle f(\mathbf{e}_j),\mathbf{e}_i\rangle=\langle \mathbf{e}_j,f(\mathbf{e_i}) \rangle=a_{ji}$, y por tanto $A$ es simétrica.

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

Supongamos ahora que $\lambda_1,\dots,\lambda_m$ son todos los valores propios (reales) de $A$. Como $\lambda_i\neq \lambda_j$ con $i\neq j$, si $\mathbf{v}\in V_{\lambda_i}\cap V_{\lambda_j}$ y $x$ son las coordenadas de $\mathbf{v}$, tenemos que $Ax=\lambda_ix=\lambda_jx$, por lo que $x=0$ y $\mathbf{v}=0$. Esto quiere decir que $V_{\lambda_i}\cap V_{\lambda_j}=\lbrace\mathbf{0}\rbrace$. De esta forma la suma $V_{\lambda_1}+\dots+V_{\lambda_m}$ es directa. Sea $U=V_{\lambda_1}\oplus \dots \oplus V_{\lambda_m}$. Si $f$ es el endomorfismo que viene determinado por $A$, entonces $f(U)\subseteq U$. Es más, por ser $f$ autoadjunto, si $\mathbf{u}\in U$ y $\mathbf{w}\in U^\perp$, por ser $f(\mathbf{u})\in U$, se tiene que $0=\langle \mathbf{v},f(\mathbf{u})\rangle= \langle f(\mathbf{v}),\mathbf{u}\rangle$, por lo que $f(\mathbf{v})\in U^\perp$, esto es, $f(U^\perp)\subseteq U^\perp$. Si $U^\perp\neq \lbrace \mathbf{0}\rbrace$, entonces $f$ restringido a $U^\perp$ tendrá al menos una valor propio $\lambda$. Si $\mathbf{v}$ es un vector propio asociado a $\lambda$, $f(\mathbf{v})=\lambda\mathbf{v}$, por lo que $\lambda\in \lbrace\lambda_1,\dots,\lambda_m\rbrace$, lo que lleva a $\mathbf{v}\in U\cap U^\perp=\lbrace\mathbf{0}\rbrace$, lo que es absurdo. Por tanto $U^\perp=\lbrace \mathbf{0}\rbrace$ y $U=\mathbb{R}^n$. Acabamos de probar el siguiente resultado.

### Teorema espectral para matrices simétricas reales

Toda matriz simétrica con entradas reales es diagonalizable.


Si $\lambda$ y $\mu$ son dos valores distintos de $A$ (simétrica con entradas reales), y $\mathbf{u}$ y $\mathbf{v}$ son vectores propios asociados a $\lambda$ y $\mu$ respectivamente, entonces 

$$
\begin{aligned}
\langle f(\mathbf{u}),\mathbf{v}\rangle &=\lambda \langle \mathbf{u},\mathbf{v}\rangle,\\
\langle \mathbf{u},f(\mathbf{v})\rangle &= \mu\langle \mathbf{u},\mathbf{v}\rangle,
\end{aligned}
$$

con $f$ el endomorfismo determinado por $A$. Como $f$ es autoadjunto, $(\lambda-\mu)\langle \mathbf{u},\mathbf{v}\rangle=0$, y al ser $\lambda\neq \mu$, concluimos que $\langle \mathbf{u},\mathbf{v}\rangle$. 

Esto nos permite escoger dentro de cada subespacio asociado a cada valor propio de $A$ una base ortonormal. Al juntarlas todas obtenemos una base ortonormal de $V$, y tenemos que la expresión de $f$ en esa base ortonormal es diagonal. Si llamamos $P$ a la matriz de paso (sus columnas son las coordenadas de los vectores de nuestra base ortonormal), entonces $P P^t=I_n$, por lo que $P^{-1}=P^t$. Estas matrices se denominan *ortogonales*. 

### Resultado

Si $A$ es una matriz simétrica con entradas reales, entonces existen $P$ ortogonal y una matriz diagonal $D$ tales que $D=P^tAP$.

### Ejemplo

Sea $A=\begin{pmatrix}1 & 1\\1 & -1\end{pmatrix}$. Entonces, $D=Q^{-1}AQ$, con 

$$
Q=\begin{pmatrix}1 - \sqrt{2} & 1 + \sqrt{2}\\1 & 1\end{pmatrix},\quad D=\begin{pmatrix}- \sqrt{2} & 0\\0 & \sqrt{2}\end{pmatrix}.
$$

Nótese que $P$ no es ortogonal. Si tomamos $\mathbf{u}=(1-\sqrt{2},1)$ y $\mathbf{v}=(1+\sqrt{2},1)$, entonces la matriz $P$ cuyas columnas son $\frac{1}{||\mathbf{u}||}\mathbf{u}$ y $\frac{1}{||\mathbf{v}||}\mathbf{v}$ verifica que $D=P^tAP$.

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
\left\{
\begin{aligned}
\alpha & & = 1 \\
\alpha &+\beta & =3,
\end{aligned}
\right.
$$

que es un sistema compatible determinado, con solución $\alpha=1$ y $\beta=2$. Así nuestra recta es $y=1+2x$.

Supongamos ahora que queremos calcular una recta que pase por los puntos $(0,1)$, $(1,3)$ y $(2,2)$. Eso nos lleva a resolver el sistema 

$$
\left\{
\begin{aligned}
\alpha  & = 1 \\
\alpha +\beta & =3,\\
\alpha +2\beta & = 2.
\end{aligned}
\right.
$$

Este sistema no tiene solución. Tomamos 

$$
A=\begin{pmatrix}1 & 0\\1 & 1\\1 & 2\end{pmatrix}.
$$

Tenemos que $A^tA=\begin{pmatrix}3 & 3\\3 & 5\end{pmatrix}$, y que el sistema 

$$
A^tA\begin{pmatrix} \alpha\\ \beta\end{pmatrix} = A^t \begin{pmatrix} 1\\ 3\\ 2\end{pmatrix},
$$

$$
\begin{pmatrix}3 & 3\\3 & 5\end{pmatrix} \begin{pmatrix} \alpha\\ \beta\end{pmatrix} = \begin{pmatrix} 6 \\ 7 \end{pmatrix},
$$

tiene solución (única) $\alpha=3/2$, $\beta=1/2$. Así, la recta $y=\frac{3}2+\frac{1}2 x$ es la que verifica que al evaluar $x$ en $0$, $1$ y $2$ proporciona los valores más cercanos a $1$, $3$ y $2$ (y son $3/2$, $2$ y $5/2$). 

## Espacios de filas y columnas de $A^tA$

Sea $A\in\mathcal{M}_{m\times n}(K)$. Si $x\in \operatorname{N}(A)$, entonces $Ax=0$, y $A^tAx=0$, por lo que $x\in \operatorname{N}(A^tA)$. Supongamos ahora que $x\in \operatorname{N}(A^tA)$, y veamos que $x\in \operatorname{N}(A)$. Sabemos que $Ax=0$ si y sólo si $|| Ax||=0$. Ahora bien, si tomamos la norma asociada al producto escalar usual,

$$
|| Ax||^2= \langle Ax,Ax\rangle = (Ax)^t(Ax)=x^tA^tAx=x^t0=0.
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

## Soluciones mínimo-cuadráticas

Sea $A\in \mathcal{M}_{m\times n}(K)$ y $b\in K^m$. Consideremos el sistema lineal de ecuaciones

$$
Ax=b.
$$

Un elemento $z$ de $K^m$ es una *solución mínimo-cuadrática* de $Ax=b$ si la norma $|| Az-b ||$ es mínima, esto es $\operatorname{d}(Az,b)=\operatorname{d}(b,\operatorname{C}(A))$ (estamos usando la distancia y normas asociados a un producto escalar usual en $K^m$).

Por lo que vimos antes, $z$ es una solución mínimo-cuadrática si y sólo si es solución del sistema de ecuaciones 

$$
A^tAz=A^tb.
$$

Este sistema siempre es compatible, pues $A^tb\in \operatorname{C}(A^t)=\operatorname{C}(A^tA)$. Además, el sistema será compatible determinado si $A^tA$ tiene rango máximo, y esto es equivalente a que $A$ tenga rango pleno por columnas. En ese caso, recordemos que $A^I=(A^tA)^{-1}A^t$ es una inversa a la izquierda de $A$, por lo que $z=(A^tA)^{-1}A^tb=A^Ib$.

### Resultado

Las soluciones minimo-cuadráticas de $Ax=b$ son las soluciones de $A^tAz=A^tb$ (que siempre es un sistema compatible). Además, existe una única solución mínimo-cuadrática si $A$ es de rango pleno por columnas, y en ese caso la solución es $A^Ib$.


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

Sea ahora $x$ otra solución del sistema. Entonces $A(x-A^Db)=0$, y por tanto $x-A^Db\in \operatorname{N}(A)$. De esta forma, $x=A^Db+z$ con $Az=0$. Tenemos así que $||x||^2 = ||A^Db||^2+||z||^2+2\langle z,A^Db\rangle$. Pero 

$$
\langle z,A^Db\rangle=z^t(A^t(AA^t)^{-1})b=(Az)^t(AA^t)^{-1}b= 0 (AA^t)^{-1}b=0,
$$

por lo que 
$$
||x||^2 = ||A^Db||^2+||z||^2 \ge || A^Db||.
$$

### Resultado

Sea $A\in \mathcal{M}_{m\times n}(K)$$ una matriz de rango pleno y sea $b\in K^m$. Entonces el sistema $Ax=b$ es compatible y la solución de norma mínima es $x=A^Db$.