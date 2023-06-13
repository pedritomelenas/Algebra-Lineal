---
layout: page
title: Aplicaciones lineales
---

# Aplicaciones lineales

*Este guión está basado en los guiones de [ALEM](https://www.ugr.es/~pedro/alem/).*

Sean $V$ y $V'$ dos espacios vectoriales sobre el mismo cuerpo $K$. Una aplicación $f:V\to V'$ es *lineal* (o un homomorfismo) si

1. para todo $\mathbf{u},\mathbf{v}\in V$,
    $f(\mathbf{u}+\mathbf{v})=f(\mathbf{u})+f(\mathbf{v})$,

2. para todo $a\in K$ y $\mathbf{v}\in V$,
    $f(a\mathbf{v})=af(\mathbf{v})$.

Esto equivale a decir que para todo $a,b\in K$ y todo $\mathbf{u},\mathbf{v}\in V$, se tiene que 

$$
f(a\mathbf{u}+b\mathbf{v})=af(\mathbf{u})+bf(\mathbf{v}).
$$

### Ejemplo

Sea $f:\mathbb{R}^3 \to \mathbb{R}^2$, $f(x,y,z)=(x+y,x+z)$. Veamos que es lineal. Si tomamos $a,a'\in \mathbb{R}$ y $(x,y,z),(x',y',z')\in \mathbb{R}^3$, entonces

$$
\begin{aligned}
f(a(x,y,z)+a'(x',y',z'))&=f(ax+a'x',ay+a'y',az+a'z')\\
&=(ax+a'x'+ay+a'y',ax+a'x'+az+a'z')\\
&=a(x+y,x+z)+a'(x'+y',x'+z')\\
&=af(x,y,z)+a'f(x',y',z').
\end{aligned}
$$

### Propiedades 

Sea $f:V\to V'$ una aplicación lineal entre los espacios vectoriales $V$ y $V'$. 

- $f(\mathbf{0})=\mathbf{0}$ (el primer $\mathbf{0}$ es de $V$ y el segundo de $V'$).

- $f(-\mathbf{v})=-f(\mathbf{v})$.

- Sea $B=\lbrace\mathbf{v}_1,\ldots, \mathbf{v}_n\rbrace$ una base de  $V$, y $\lbrace\mathbf{v}_1',\ldots, \mathbf{v}_n'\rbrace\subseteq V'$. Entonces existe una única aplicación lineal $f:V\to V'$ verificando que $f(\mathbf{v}_1)=\mathbf{v}_1',\ldots, f(\mathbf{v}_n)=\mathbf{v}_n'$ (toda aplicación lineal queda unívocamente determinada por las imágenes de los elementos de una base).

## Expresión matricial una aplicación lineal

Sea $f:V\to V'$ una aplicación lineal, y $B=\lbrace\mathbf{v}_1,\ldots, \mathbf{v}_n\rbrace$ y $B'=\lbrace\mathbf{v}_1',\ldots, \mathbf{v}_m'\rbrace$ bases de $V$ y $V'$, respectivamente. Sean $\mathbf{x}=x_1\mathbf{v}_1+\cdots+ x_n \mathbf{v}_n$ y $f(\mathbf{x})=x_1'\mathbf{v}_1'+\cdots + x_m'\mathbf{v}_m\in V'$. Queremos estudiar la relación que existe entre las coordenadas de $\mathbf{x}$ y $f(\mathbf{x})$ en $B$ y $B'$, respectivamente.

Supongamos que 

$$
\begin{matrix}
  f(\mathbf{v}_1)=a_{11}\mathbf{v}_1'+\cdots+a_{m1}\mathbf{v}_m',\\
  \vdots \\
  f(\mathbf{v}_n)=a_{1n}\mathbf{v}_1'+\cdots+a_{mn}\mathbf{v}_m'.
\end{matrix}
$$ 

Entonces 

$$
\begin{aligned}
 f(\mathbf{x}) & =  f(x_1\mathbf{v}_1+\cdots+ x_n\mathbf{v}_n)= x_1f(\mathbf{v}_1)+\cdots+x_nf(\mathbf{v}_n)\\
& =  x_1(a_{11}\mathbf{v}_1'+\cdots+a_{m1}\mathbf{v}_m')+\cdots+x_n(a_{1n}\mathbf{v}_1'+\cdots+a_{mn}\mathbf{v}_m')\\
& =  (x_1a_{11}+\cdots+ x_na_{n1})\mathbf{v}_1'+\cdots+(x_1a_{1m}+\cdots+x_na_{nm})\mathbf{v}_m'.
\end{aligned}
$$ 

Así 

$$\left\lbrace 
 \begin{aligned}
  x_1' & =a_{11}x_1+\cdots+ a_{1n}x_n,\\
  \vdots\\
  x_m' & =a_{m1}x_1+\cdots+ a_{mn}x_n,
 \end{aligned}
 \right.
$$ 

que se conocen como *ecuaciones* de la aplicación lineal respecto de las bases $B$ y $B'$.

Estas ecuaciones se pueden expresar de forma matricial como

$$
\begin{pmatrix}
x_1' \\ 
\vdots \\
x_m'
\end{pmatrix}= 
\begin{pmatrix}
 a_{11} & \ldots & a_{1n} \\
 \vdots & \ddots & \vdots \\
 a_{m1} & \ldots & a_{mn} 
\end{pmatrix}
\begin{pmatrix}
x_1\\ 
\vdots\\
x_n
\end{pmatrix}
.
$$

La matriz 

$$
\mathcal{M}(f;B,B')=A=\begin{pmatrix}
 a_{11} & \ldots & a_{1n} \\
 \vdots & \ddots & \vdots \\
 a_{m1} & \ldots & a_{mn} 
\end{pmatrix}
$$ 

es la *matriz asociada* a la aplicación lineal $f$ respecto de las bases $B$ y $B'$.

### Ejemplo

Volvamos al ejemplo $f:\mathbb{R}^3 \to \mathbb{R}^2$, $f(x,y,z)=(x+y,x+z)$. Tomemos en $\mathbb{R}^3$ la base $B=\lbrace (1,0,0),(0,1,0),(0,0,1)\rbrace$ y en $\mathbb{R}^2$ la base $B'=\lbrace(1,0),(0,1)\rbrace$. Como $f(1,0,0)=(1,1)$, $f(0,1,0)=(1,0)$ y $f(0,0,1)=(0,1)$, tenemos que la matriz asociada $f$ en las bases $B$ y $B'$ es 

$$
\mathcal{M}(f;B,B')=
\begin{pmatrix}
1 & 1 & 0\\
1 & 0 & 1
\end{pmatrix}.
$$

Podemos comprobar que 

$$
\begin{pmatrix}
1 & 1 & 0\\
1 & 0 & 1
\end{pmatrix} 
\begin{pmatrix}
x\\
y\\
z
\end{pmatrix}=
\begin{pmatrix}
x+y\\
x+z
\end{pmatrix}.
$$


### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/4-1.html)

Sea $f:V_1\to V_2$ una aplicación lineal, y sea $A=\mathcal{M}(f;B_1,B_2)$ con $B_1$ una base de $V_1$ y $B_2$ una base del espacio vectorial $V_2$. Si $\bar{B}_1$ y $\bar{B}_2$ son bases de $V_1$ y $V_2$, respectivamente, podemos calcular $\mathcal{M}(f;\bar{B}_1,\bar{B}_2)$ usando la deficinión de matriz asociada a una aplicación lineal, esto es determinando las coordenadas de las imágenes por $f$ de los vectores de $\bar{B}_1$ respecto de $\bar{B}_2$, o bien podemos multiplicar apropiadamente $A$ con las matrices de cambio de base de $\bar{B}_1$ a $B_1$ y de $B_2$ a $\bar{B}_2$. Sea $A_1$ (respectivamente $A_2$) la matriz de cambio de base de $\bar{B}_1$ a $B_1$ (respectivamente de $\bar{B}_2$ a $B_2$). Nótese que

$$
A_1=\mathcal{M}(I_{V_1};\bar{B}_1,B_1),
$$

con $I_{V_1}:V_1\to V_1$ la aplicación identidad ($I_{V_1}(v)=v$ para todo $v\in V_1$). Así $A_2^{-1}=\mathcal{M}(I_{V_2};B_2,\bar{B_2})$. Por tanto,

$$
\mathcal{M}(f;\bar{B}_1,\bar{B}_2)
    =\mathcal{M}(I_{V_2};B_2,\bar{B}_2)\mathcal{M}(f;B_1,B_2)\mathcal{M}(I_{V_1};\bar{B_1},B_1)=A_2^{-1}A A_1.
$$

La matriz $A_1$ toma las coordenadas de un vector $v$ en $V_1$ respecto de $\bar{B}_1$ y nos devuelve sus coordenadas en la base $B_1$, posteriormente la matriz $A$ calcula las coordenadas de $f(v)$ respecto de la base $B_2$, y finalmente $A_2^{-1}$ devuelve las coordenadas de $f(v)$ respecto de $\bar{B}_2$.

### Ejemplo

Volvamos de nuevo al ejemplo $f:\mathbb{R}^3 \to \mathbb{R}^2$, $f(x,y,z)=(x+y,x+z)$, pero ahora vamos a calcular la matriz asociada a $f$ respecto de las bases $B_1=\lbrace (1,1,1),(1,1,0),(1,0,0)\rbrace$ y $B_1'=\lbrace (1,1),(1,-1)\rbrace$. Podemos aplicar la definición o bien multiplicar $\mathcal{M}(f;B,B')$ por las matrices de cambio de base apropiadas. 

Como $f(1,1,1)=(2,2)=2(1,1)$, $f(1,1,0)=(2,1)=\frac{3}2(1,1)+\frac{1}2(1,-1)$ y $f(1,0,0)=(1,1)=1(1,1)$, tenemos que 

$$
\mathcal{M}(f;B_1,B_1')=
\begin{pmatrix}
2 & \frac{3}2 & 1\\
0 & \frac{1}2 & 0
\end{pmatrix}.
$$

Por otro lado,

$$
\begin{aligned}
\mathcal{M}(f;B_1,B_1') &= \mathcal{M}(I_2;B',B_1') \mathcal{M}(f;B,B')\mathcal{M}(I_3;B_1,B)\\
& = \mathcal{M}(I_2;B_1',B')^{-1} \mathcal{M}(f;B,B')\mathcal{M}(I_3;B_1,B)\\
&= 
\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}^{-1}
\begin{pmatrix}
1 & 1 & 0\\
1 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 1 & 1\\
1 & 1 & 0\\
1 & 0 & 0
\end{pmatrix}\\
&=
\begin{pmatrix}
2 & \frac{3}2 & 1\\
0 & \frac{1}2 & 0
\end{pmatrix}.
\end{aligned}
$$

<div class="sage">
<script type="text/x-sage">
show(matrix([[1,1],[1,-1]])^(-1)*matrix([[1,1,0],[1,0,1]])\
    *matrix([[1,1,1],[1,1,0],[1,0,0]]))
</script>
</div>  


### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/4-3.html)

## Núcleo e imagen de una aplicación lineal

El *núcleo* de $f$,  

$$
\operatorname{N}(f)=\lbrace  \mathbf{v}\in V : f(\mathbf{v})=\mathbf{0}\rbrace,
$$ 

es un subespacio vectorial de $V$.

La *imagen* de $f$, 

$$
\operatorname{Im}(f)=\lbrace f(\mathbf{v}) : \mathbf{v}\in V\rbrace,
$$ 

es un subespacio vectorial de $V'$.


Una aplicación lineal es un

1. *monomorfismo* si es inyectiva,

2. *epimorfismo* si es sobreyectiva,

3. *isomorfismo* si es biyectiva.

### Propiedades 

Sea $f:V\to V'$ una aplicación lineal.

- $f$ es un monomorfismo si y sólo si $\operatorname{N}(f)=\lbrace\mathbf{0}\rbrace$.

- $f$ es un epimorfismo si y sólo si $\operatorname{Im}(f)=V'$.

- Si $V=\mathcal{L}(\lbrace\mathbf{v}_1,\ldots,\mathbf{v}_n\rbrace)$, entonces $\operatorname{Im}(f)=\mathcal{L}(\lbrace  f(\mathbf{v}_1),\ldots, f(\mathbf{v}_n)\rbrace)$.

- Si $f$ es un monomorfismo y $\lbrace\mathbf{v}_1,\ldots,\mathbf{v}_n\rbrace$ son linealmente  independientes, entonces $\lbrace f(\mathbf{v}_1),\ldots, f(\mathbf{v}_n)\rbrace$ también son linealmente independientes.

- Si $f$ es un epimorfismo y $\lbrace\mathbf{v}_1,\ldots,\mathbf{v}_m\rbrace$ es un sistema de generadores de $V$, entonces $\lbrace f(\mathbf{v}_1),\ldots, f(\mathbf{v}_m)\rbrace$ es un sistema de generadores de $V'$. 

- Si $f$ es un isomorfismo, también lo es $f^{-1}$.

- Si $A$ es la matriz asociada a $f$ respecto de unas bases $B$ y $B'$ de $V$ y $V'$, respectivamente, entonces 

    $$
    \dim(\operatorname{Im}(f))=\operatorname{rg}(A)
    $$ 

    y 

    $$
    \dim(\operatorname{N}(f))=\dim(V)-\operatorname{rg}(A).
    $$ 

    En particular, 

    $$
    \dim(\operatorname{N}(f))+\dim(\operatorname{Im}(f))=\dim(V).
    $$

- Si $B=\lbrace\mathbf{v}_1,\ldots, \mathbf{v}_n\rbrace$ una base de $V$, entonces, $\lbrace f(\mathbf{v}_1),\dots, f(\mathbf{v}_n)\rbrace$ es una base de $V'$ si y sólo si $f$ es un isomorfismo. Esto equivale a que $\mathcal{M}(f;B,B')$ es regular.

Los espacios vectoriales $V$ y $V'$ diremos que son isomorfos si existe un isomorfismo $f:V\to V'$, y lo denotaremos por $V\cong V'$.

## Consecuencia
Los espacios $V$ y $V'$ son isomorfos si y sólo si $\dim(V)=\dim(V')$.


### Ejemplo

Calculemos el núcleo y la imagen de $f:\mathbb{R}^3 \to \mathbb{R}^2$, $f(x,y,z)=(x+y,x+z)$. 

El núcleo es el conjunto de elementos $(x,y,z)$ de $\mathbb{R}^3$ tales que $f(x,y,z)=(0,0)$, y por tanto tiene como ecuaciones cartesianas 

$$
\left\lbrace
\begin{array}{l}
x+y=0,\\
x+z=0.
\end{array}
\right.
$$

Una base de $\operatorname{N}(f)$ es $\lbrace (1,-1,-1)\rbrace$, en particular $f$ no es inyectiva.

La imagen de $f$ está generada por la imagen de los vectores de uns sistema de generadores de $\mathbb{R}^3$. Como $f(1,0,0)=(1,0)$ y $f(0,0,1)=(0,1)$, tenemos que la imagen de $f$ es todo $\mathbb{R}^2$ (y por tanto es sobreyectiva).

Nótese que $3=\dim(\mathbb{R}^3)=\dim(\operatorname{N}(f))+\dim(\operatorname{Im}(f))=1+2$.


### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/4-2.html)

## Espacio vectorial cociente

Sea $U$ un subespacio vectorial de $V$. Definimos en $V$ la siguiente relación de equivalencia: $\mathbf{x}\ R\ \mathbf{y}$ si $\mathbf{x}-\mathbf{y}\in U$. Denotamos por $\frac{V}U$ al conjunto cociente $\frac{V}R$.

- El conjunto $\frac{V}U$ es un espacio vectorial con las operaciones $[\mathbf{x}]+[\mathbf{y}]=[\mathbf{x}+\mathbf{y}]$ y $k[\mathbf{x}]=[k\mathbf{x}]$. A dicho espacio vectorial se le conoce como espacio vectorial cociente de $V$ sobre $U$.

- Si $\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_m\rbrace$ es una base
de $U$ y la ampliamos a una base de $V$, $\lbrace\mathbf{u}_1,\ldots, \mathbf{u} _m,\mathbf{u} _{m+1},\ldots,\mathbf{u} _n\rbrace$, entonces $\lbrace [\mathbf{u} _{m+1}],\ldots, [\mathbf{u} _n]\rbrace$ es una base de $\frac{V}U$. Así

 $$
 \dim\left(\frac{V}U\right) = \dim(V)-\dim(U).
 $$

### Primer teorema de isomorfía 

Si $f:V\to V'$ es una aplicación lineal, entonces los espacios vectoriales $\frac{V}{\operatorname{N}(f)}$ e $\operatorname{Im}(f)$ son isomorfos; el isomorfismo viene dado por $[\mathbf{v}]\mapsto f(v)$.

En particular, recuperamos así la fórmula $\dim(V)=\dim(\operatorname{N}(f))+\dim(\operatorname{Im}(f))$.

### Segundo teorema de isomorfía 

Si $U_1$ y $U_2$ son subespacios de $V$, entonces los espacios
vectoriales $\frac{U_2}{U_1\cap U_2}$ y $\frac{U_1+U_2}{U_1}$ son
isomorfos. En particular, recuperamos la fórmula $\dim(U_1)+\dim(U_2)=\dim(U_1+U_2)+\dim(U_1\cap U_2).$

## Diagonalización de matrices

Recordemos que una *matriz diagonal* es una matriz cuadrada que tiene todas sus entradas nulas, salvo eventualmente las de la diagonal. Una matriz cuadrada $A$ es *diagonalizable* si existen una matriz diagonal $D$ y una matriz regular $P$ tales que $A=PDP^{-1}$.

La diagonalización de matrices es útil por ejemplo para el cálculo de potencias grandes de una matriz, ya que

$$
A^r=(PDP^{-1})^r=PDP^{-1}PDP^{-1}\stackrel{r-1}{\ldots}PDP^{-1}=PD^rP^{-1}.
$$

De igual forma, se puede calcular la raiz cuadrada de una matriz. Si los elementos de la diagonal de $D$ son no negativos, y llamamos $\sqrt{D}$ a la matriz que tiene en la diagonal las raíces cuadradas (negativas o positivas) de los valores de la diagonal de $D$, entonces 

$$
(P\sqrt{D}P^{-1})^2=PDP^{-1}=A.
$$

En adelante, $A$ representará una matriz cuadrada de orden $n\times n$ sobre un cuerpo $K$.

Un elemento $\lambda\in K$ es un *valor propio* de $A$ si existe $\mathbf{v}\in K^n\setminus\lbrace (0,\ldots,0)\rbrace$ tal que $A\mathbf{v}=\lambda \mathbf{v}$. En tal caso diremos que $\mathbf{v}$ es un *vector propio* asociado al valor propio $\lambda$.

### Teorema de caracterización de los valores propios 

Sea $A\in \mathcal{M}_{n}(K)$, con $K$ un cuerpo y $n$ un entero positivo.  Un elemento $\lambda \in K$ es un valor propio de $A$ si y sólo si

$$
\vert A-\lambda I_n\vert =0.
$$

Así, los valores propios de $A$ son las raíces del polinomio $\vert A-\lambda I_n\vert \in K[\lambda]$, que se conoce como *polinomio característico* de $A$, y lo denotaremos por $p_A(\lambda)$. Nótese que
$\operatorname{gr}(p_A(\lambda)=n$.

### Propiedades 

1. Si $A$ es una matriz triangular, entonces sus valores propios son los valores de la diagonal.

2. Los valores propios de $A$ y $A^t$ coinciden.

3. $\vert A\vert =0$ si y sólo si 0 es un valor propio de $A$.

4. Si $A$ es regular y $\lambda$ es un valor propio de $A$, entonces $\lambda^{-1}$ lo es de $A^{-1}$.


Si $\lambda$ es un valor propio de $A$, entonces

$$
V(\lambda)=\lbrace  \mathbf{x}\in K^n \: (A-\lambda I_n)\mathbf{x}=\mathbf{0}\rbrace,
$$ 

(en este caso $\mathbf{0}=(0,\ldots,0)\in K^n$) es un subespacio vectorial de $K^n$. Dicho subespacio lo llamamos *subespacio vectorial propio* asociado al valor propio $\lambda$.


Sean $\lambda_1,\ldots,\lambda_k$ los valores propios de la matriz $A$. A la multiplicidad de la raíz $\lambda_i$ de $p_A(\lambda)$ la llamaremos *multiplicidad algebraica* de $\lambda_i$, mientras que la dimensión de $V(\lambda_i)$ es la *multiplicidad geométrica* de $\lambda_i$.

Nótese que si $\lambda$ es un valor propio de $A$, y si tomamos una base de $V(\lambda)$ y la ampliamos a una de $K^n$, entonces la matriz de $A$ respecto de esa base tiene la forma 

$$
\left(\begin{array}{c|c}
\lambda I_r & M \\ 
\hline
0 & N
\end{array}
\right),
$$

con $r=\dim(V(\lambda))$. Por tanto el polinomio característico tendrá la forma $(x-\lambda)^rP_N(x)$, y eso implica que la multiplicidad algebraica de $\lambda$ es al menos $r$.

### Resultado 

La multiplicidad geométrica de un valor propio es menor o igual que su multiplicidad algebraica.

### Criterio de diagonalización

La matriz $A\in \mathcal{M}_n(K)$ es diagonalizable si, y sólo si, la suma de las multiplicidades algebraicas de los valores propios de $A$ es $n$ y además para todo valor propio las multiplicidades algebraica y geométrica coinciden.

### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/5-1.html)

### Método para diagonalizar una matriz

Sea $A\in \mathcal{M}_n(K)$.

1. Calculamos $p_A(\lambda)$, sus raíces $\lambda_1,\dots, \lambda_k$  y sus multiplicidades algebraicas, $m_1,\dots, m_k$.

2. Si $m_1+\cdots+m_k\neq n$, $A$ no es diagonalizable.

3. En caso contrario, para cada $\lambda_i$, calculamos el subespacio  propio $V(\lambda_i)$ y su dimensión. Si dicha dimensión no coincide con $m_i$ para algún $i$, entonces $A$ no es diagonalizable.

4. Llegado este paso, la matriz $A$ es diagonalizable y $D$ es la matriz que tiene en la diagonal $m_1$ entradas $\lambda_1$, $m_2$ entradas $\lambda_2$, y así hasta $m_k$ entradas $\lambda_k$. La  matriz de paso $P$ se construye colocando en las primeras $m_1$    columnas una base de $V(\lambda_1)$, a continuación en las siguientes $m_2$ columnas una base de $V(\lambda_2)$, y así hasta que colocamos en las últimas $m_k$ columnas una base de $V(\lambda_k)$.

### $\to$ [Ejemplo Merino-Santos 1](https://www.ugr.es/~lmerino/5-2.html) y [2](https://www.ugr.es/~lmerino/5-3.html)

### Ejemplo no diagonalizable (Forma de Jordan)

Sea 

$$
A=\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0\\
-2 & -2 & 0 & 1\\
-2 & 0 &-1 &-2
\end{pmatrix}.
$$

Su polinomio característico es $p_A(x)= x^{4} - 2 x^{2} + 1$, cuyas raíces son $1$ y $-1$ con multiplicidad $2$.

Por un lado $V(1)=\operatorname{N}(A-I)=\mathcal{L}(\lbrace (1,0,-2,0),(3,-4,0,-2)\rbrace)$ y $V(-1)=\operatorname{N}(A+I)=\mathcal{L}(\lbrace (0,0,1,-1)\rbrace)$. Por tanto $A$ no es diagonalizable, pues la multiplicidad algebraica de $-1$ es $2$, mientras que la geométrica es $1$. 

Nos falta un vector, que lo buscamos en $\operatorname{N}(A+I)^2=\mathcal{L}(\lbrace (0,0,1,0),(0,0,0,1)\rbrace)$. Tenemos pues que $(A+I)^2(0,0,0,1)^t=(0,0,0,0)$, por lo que $(A+I)(0,0,0,1)^t\in \operatorname{N}(A+I)$. Si tomamos $u_2=(0,0,0,1)\not\in \operatorname{N}(A+I)$ y $u_1=(A+I)u_2=(0,0,1,-1)\in \operatorname{N}(A+I)$, tenemos que $A u_1=-u_1$ y $A u_2=u_1-u_2$. 

Completamos nuestra base con $u_3=(1,0,-2,0)\in \operatorname{N}(A-I)$ y $u_3=(3,-4,0,-2)\in\operatorname{N}(A-I)$, y escribimos $P=(u_1 u_2 u_3 u_4)$ (por columnas), obteniendo

$$
P^{-1}AP=J=\left(
\begin{array}{rrrr}
-1 & 1 & 0 & 0\\
0 & -1 & 0 & 0\\
0 & 0 & 1 & 0\\
0 & 0 & 0 & 1
\end{array}\right).
$$

Así, $A=PJP^{-1}$.

### Ejemplo: migraciones

(Adaptado de [I. Ojeda, J. Gago, [Métodos matemáticos para la Estadística](https://publicauex.unex.es/libro/metodos-matematicos-para-estadistica_135467/)].)

Cada día de clase los alumnos cambian de la bancada norte a la sur (y viceversa) siguiendo las siguientes proporciones.
- Un 50% de los alumnos de la bancada norte permanece en su sitio, mientras que la otra mitad se va a la bancada sur.
- Un cuarto de los alumnos de la bancada sur se quedan donde estaban la clase anterior, mientras que tres cuartos deciden moverse a la bandada norte.

Llamemos $p_1=(n_1,s_1)$ a la proporción de alumnos que había el primer día de clase en cada bancada. El segundo día la proporción sería $p_2=(n_2,s_2)$, con

$$
\begin{matrix}
n_2=\frac{1}2 n_1+\frac{3}4 s_1,\\
s_2=\frac{1}{2} n_1+ \frac{1}4 s_1. 
\end{matrix}
$$

Y esto lo podemos expresar de forma matricial como 

$$
A p_1 = p_2, A=\begin{pmatrix}
\frac{1}2 & \frac{1}4\\
\frac{1}2 & \frac{3}4
\end{pmatrix}.
$$

<div class="sage">
<script type="text/x-sage">
A=matrix([[1/2,1/4],[1/2,3/4]])
g1=DiGraph(A)
g1.graphplot(edge_labels=True).show()</script>
</div>  

Si lo que queremos comprobar es la proporción de alumnos que habrá en cada bancada después de $n$ clases, lo que tenemos que calcular es 

$$
p_n = A
p_{n-1} = \dots = A^n p_0.
$$

El vector $p_i$ es un vector con coordenadas no negativas y que suman uno (un **vector estocástico**). Las columnas de $A$ también son vectores estocásticos. Las matrices de esta forma se conocen como **matrices de Markov** (o estocásticas).

El producto de una matriz de Markov por un vector estocástico devuelve un vector estocástico. Estas matrices siempre tienen un autovalor igual a uno, y el resto tienen valor absoluto menor o igual que uno.

Veamos cómo evoluciona la proporción de alumnos en cada bancada después de 20 días de clase, suponiendo que el primer día ser repartieron la mitad en cada bancada.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1/2,1/4],[1/2,3/4]])
p=matrix([[1/2,1/2]]).T
for i in range(20):
    print(1.0*p.T)
    p=A*p</script>
</div>  

Veamos cómo sería el comportamiento general (y asintótico). Si $A$ es diagonalizable, entonces existe $P$ regular y $D$ diagonal tal que $A=PDP^{-1}$. Por tanto, $A^n=PD^nP^{-1}$.  

<div class="sage">
<script type="text/x-sage">
A=matrix([[1/2,1/4],[1/2,3/4]])
show(A)
D,P=A.diagonalization()
show(P)
show(D)
show(P*D*P^(-1))
</script>
</div>  

Claramente $D^n$ tiende a una matriz cuya diagonal es $(1,0)$.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1/2,1/4],[1/2,3/4]])
D,P=A.diagonalization()
show(D)
D[1,1]=0
show(D)
Ainf=P*D*P^(-1)
show(Ainf)
p=matrix([[1/2,1/2]]).T
show(Ainf*p)
</script>
</div>  

De hecho para $p=(a,1-a)$ también obtendremos que el valor asintótico es el mismo, y corresponde con el vector asociado al valor propio asociado al 1 cuya suma de coordenadas es uno.

<div class="sage">
<script type="text/x-sage">
A=matrix([[1/2,1/4],[1/2,3/4]])
D,P=A.diagonalization()
D[1,1]=0
a=var("a")
Ainf=P*D*P^(-1)
p=matrix([[a,1-a]]).T
show(Ainf*p)
v1=P[:,0]
show(v1/(Matrix([[1,1]])*v1))
</script>
</div>  


## Autoevaluacion

<iframe src="{{ site.baseurl | absolute_url }}{% link /assets/autoevaluacion/aplicaciones-lineales.html %}" style="border:none;" height="600" width="100%" title="autoevaluación"></iframe>
