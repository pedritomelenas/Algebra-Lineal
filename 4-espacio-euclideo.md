---
layout: page
title: Espacio euclídeo
---

# Espacios vectoriales euclídeos

*Estas notas se basan en las [transparencias](https://www.ugr.es/~arobles/MatApl(CivilADE)/Tema2_beamer.pdf) de [A. M. Robles Pérez](https://www.ugr.es/~arobles/).*


## Producto escalar

Sea $V$ un $\mathbb{R}$-espacio vectorial. Un *producto escalar* en $V$ es una aplicación

$$
\langle \cdot, \cdot \rangle \ : V \times V \rightarrow \mathbb{R}
$$

que verifica las siguientes propiedades;

1. $\langle \mathbf{u}, \mathbf{v} \rangle = \langle \mathbf{v},\mathbf{u} \rangle$ para todo $\mathbf{u}, \mathbf{v}\in V$;

2. $\langle \mathbf{u}, \mathbf{v}+\mathbf{w} \rangle = \langle \mathbf{u}, \mathbf{v} \rangle + \langle \mathbf{u}, \mathbf{w} \rangle$ para todo $\mathbf{u}, \mathbf{v},\mathbf{w}\in V$;

3. $\langle \mathbf{u}, \alpha v \rangle = \alpha \langle \mathbf{u}, \mathbf{v} \rangle$ para todo $\mathbf{u}, \mathbf{v}\in V$ y todo $\alpha\in\mathbb{R}$;

4. $\langle \mathbf{u}, \mathbf{u} \rangle \geq 0$ para todo $\mathbf{u}\in V$;

5. $\langle \mathbf{u}, \mathbf{u} \rangle = 0$ si, y sólo si, $\mathbf{u}=\mathbf{0}.$

### Ejemplos 

- $\langle \mathbf{u}, \mathbf{v} \rangle = {u}_1 {v}_1+\cdots+{u}_n {v}_n,$ para cualesquiera
    $\mathbf{u}=({u}_1,\ldots,{u}_n)$ y $\mathbf{v}=({v}_1,\ldots, {v}_n)\in \mathbb{R}^n.$

- $\langle f,g \rangle = \displaystyle\int_a^b f(x) g(x) dx,$ para cualesquiera $f$ y $g$  funciones continuas en $[a,b].$

- En particular, $\langle p,q \rangle = \displaystyle\int_a^b p(x) q(x) dx,$ para cualesquiera $p,q\in \operatorname{P}_n(\mathbb{R})$ (polinomios en una variable con coeficientes en $\mathbb{R}$ y de grado a lo sumo $n$) y $a,b\in\mathbb{R}.$

- $\langle A,B \rangle = \sum\limits_{i=1}^n \sum\limits_{j=1}^m a_{ij}b_{ij},$ para cualesquiera $A=(a_{ij}), B=(b_{ij})\in \mathcal{M}_{n\times m}(\mathbb{R}).$

Un espacio vectorial $V$ dotado de un producto escalar $\langle \cdot, \cdot \rangle$ se denomina *espacio vectorial euclídeo* y se denota por $(V;\langle \cdot, \cdot \rangle).$


## Norma

Sean $(V;\langle \cdot, \cdot \rangle)$ un espacio vectorial euclídeo y $\mathbf{u}, \mathbf{v}\in V.$ Entonces se define la *norma* del vector $\mathbf{u}$ como

$$
\Vert u\Vert=\sqrt{\langle \mathbf{u}, \mathbf{u} \rangle}.
$$

Un vector $\mathbf{u}$ se dice *unitario* si $\Vert u\Vert=1.$

### Propiedades

Para todo $\mathbf{v}\in V$ y $a\in K,$

- $\Vert \mathbf{v}\Vert \ge 0,$
- $\Vert \mathbf{v}\Vert=0$ si y sólo si $\mathbf{v}=\mathbf{0},$
- $\Vert a\mathbf{v}\Vert=\vert a\vert \Vert \mathbf{v}\Vert.$

### [Desigualdad de Cauchy-Schwartz](https://es.wikipedia.org/wiki/Desigualdad_de_Cauchy-Bunyakovsky-Schwarz)

Dados $\mathbf{u},\mathbf{v}\in V,$

$$
\vert\langle \mathbf{u},\mathbf{v}\rangle | \le \Vert \mathbf{u}\Vert \Vert \mathbf{v}\Vert.
$$

Como consecuencia de la desigualdad de Cauchy-Schwartz obtenemos que 

$$
\begin{aligned}
\Vert \mathbf{u}+\mathbf{v}\Vert^2& =\langle \mathbf{u},\mathbf{u}\rangle+\langle \mathbf{u},\mathbf{v}\rangle +\langle\mathbf{v},\mathbf{u}\rangle+\langle\mathbf{v},\mathbf{v}\rangle=\langle\mathbf{u},\mathbf{u}\rangle+\langle\mathbf{v},\mathbf{v}\rangle+2\langle \mathbf{u}, \mathbf{v}\rangle \\
& \le  \Vert \mathbf{u}\Vert^2+ \Vert \mathbf{v}\Vert^2+2\Vert \mathbf{u}\Vert \Vert\mathbf{v}\Vert=(\Vert \mathbf{u}\Vert +\Vert\mathbf{v}\Vert)^2,
\end{aligned}
$$

desigualdad que se conoce como desigualdad de Minkowski.

### Desigualdad de Minkowski

Dados $\mathbf{u},\mathbf{v}\in V,$

$$
\Vert \mathbf{u}+\mathbf{v}\Vert \le \Vert \mathbf{u}\Vert + \Vert \mathbf{v}\Vert.
$$


En virtud de la desigualdad de Cauchy-Schwartz, podemos definir el *ángulo* que determinan dos vectores no nulos $\mathbf{u}$ y $\mathbf{v}$ como el ángulo $\measuredangle(\mathbf{u},\mathbf{v})\in [0,\pi]$ tal que

$$
\cos(\measuredangle(\mathbf{u},\mathbf{v}))=\frac{\langle \mathbf{u}, \mathbf{v} \rangle}{\Vert u\Vert \Vert v\Vert}.
$$

Decimos que dos vectores, $\mathbf{u}$ y $\mathbf{v},$ son *vectores ortogonales* si $\langle \mathbf{u}, \mathbf{v} \rangle=0,$ y lo denotamos escribiendo $\mathbf{u} \perp \mathbf{v}.$

## Base ortogonal y ortonormal 

Sean $B=\lbrace\mathbf{v}_1,\ldots, \mathbf{v}_n\rbrace$ una base de $V.$ Decimos que $B$ es una *base ortogonal* de $V$ si sus vectores son ortogonales dos a dos; es decir, si $\langle \mathbf{v}_i, \mathbf{v}_j \rangle=0$ para todo $i\neq j.$

Decimos que $B$ es una *base ortonormal* de $V$ si es una base ortogonal y, además, todos sus vectores son unitarios; es decir, si $\langle \mathbf{v}_i, \mathbf{v}_j \rangle=0$ para todo $i\neq j,$ y $\Vert \mathbf{v}_i\Vert=1$ para todo $i\in\lbrace 1,\ldots,n\rbrace.$

Si $B=\lbrace\mathbf{v}_1,\ldots, \mathbf{v}_n\rbrace$ es una base ortonormal de $V,$ entonces para todo $\mathbf{u}\in V$ se verifica que

$$
\mathbf{u}=\langle \mathbf{u}, \mathbf{v}_1 \rangle \mathbf{v}_1 + \langle \mathbf{u}, \mathbf{v}_2 \rangle \mathbf{v}_2 + \cdots + \langle \mathbf{u}, \mathbf{v}_n \rangle \mathbf{v}_n,
$$

es decir, $\left(\langle \mathbf{u}, \mathbf{v}_1 \rangle,\langle \mathbf{u}, \mathbf{v}_2 \rangle,\ldots,\langle \mathbf{u}, \mathbf{v}_n \rangle\right)$ son las coordenadas de $\mathbf{u}$ en la base $B$ (o *coeficientes de Fourier*).

## Método de ortogonalización de Gram-Schmidt 

Sean $(V;\langle \cdot, \cdot \rangle)$ un espacio vectorial euclídeo y $B=\lbrace\mathbf{v}_1,\ldots, \mathbf{v}_n\rbrace$ una base dada de $V.$

Los vectores $\lbrace\mathbf{u}_1,\mathbf{u}_2,\ldots,\mathbf{u}_n\rbrace$ definidos por

$$
\begin{aligned}
    \mathbf{u}_1&=\mathbf{v}_1,\\
    \mathbf{u}_2&=\mathbf{v}_2-\dfrac{\langle \mathbf{v}_2, \mathbf{u}_1 \rangle}{\Vert \mathbf{u}_1\Vert^2} \mathbf{u}_1,\\
    \mathbf{u}_3&=\mathbf{v}_3-\dfrac{\langle \mathbf{v}_3, \mathbf{u}_1 \rangle}{\Vert \mathbf{u}_1\Vert^2} \mathbf{u}_1-\dfrac{\langle \mathbf{v}_3, \mathbf{u}_2 \rangle}{\Vert \mathbf{u}_2\Vert^2} \mathbf{u}_2,\\
    & \vdots\\
    \mathbf{u}_n&=\mathbf{v}_n-\dfrac{\langle \mathbf{v}_n, \mathbf{u}_1 \rangle}{\Vert \mathbf{u}_1\Vert^2}\mathbf{u}_1 - \dfrac{\langle \mathbf{v}_n, \mathbf{u}_2 \rangle}{\Vert \mathbf{u}_2\Vert^2} \mathbf{u}_2-\dots-\dfrac{\langle \mathbf{v}_n, \mathbf{u}_{n-1} \rangle}{\Vert \mathbf{u}_{n-1}\Vert^2} \mathbf{u}_{n-1},
\end{aligned}
$$ 

forman una base ortogonal de $V.$ Además,

$$
\left\lbrace\frac{1}{\Vert \mathbf{u}_1\Vert}\mathbf{u}_1,\ldots,\frac{1}{\Vert \mathbf{u}_n\Vert}\mathbf{u}_n\right\rbrace
$$

es una base ortonormal de $V.$

###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/3-2.html) 

## Complemento ortogonal 

Sean $(V;\langle \cdot, \cdot \rangle)$ un espacio vectorial euclídeo y $U$ un subespacio vectorial de $V.$ Un vector $\mathbf{v}\in V$ se dice *ortogonal* a $U$ si es ortogonal a todo vector de $U,$ lo que se denota por $\mathbf{v}\perp U.$

### Resultado

El conjunto $U^\perp$ formado por todos los vectores ortogonales a $U$ es un subespacio vectorial de $V.$

El subespacio $U^\perp$ se denomina *complemento ortogonal* de $U$ (respecto de $V$).


Sea $S=\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_m\rbrace$ una base de $U.$ Entonces, por linealidad,
tenemos que

$$
\mathbf{v}\perp U \text{ si, y sólo si, } \langle \mathbf{v}, \mathbf{u}_i \rangle=0 \text{ para todo } i\in\lbrace 1,\ldots,m\rbrace.
$$

Imponiendo estas $m$ condiciones a un vector genérico $\mathbf{v}\in V$ obtendremos las ecuaciones cartesianas de $U^\perp.$ Por tanto 

$$
\dim(U^\perp)=n-m.
$$

### Ejemplo

Consideremos el subespacio vectorial $U \subseteq \mathbb{R}^4$ generado por los vectores $\left\lbrace (6,3,2,0),(4,1,0,-2) \right\rbrace.$ Entonces las ecuaciones cartesianas de $U^\perp$ son

$$
\left\lbrace
\begin{array}{r} 
6x_1+3x_2+2x_3=0, \\ 
4x_1+x_2-2x_4=0. 
\end{array}\right.
$$

Además, $\left\lbrace (1,-4,3,0),(1,-2,0,1) \right\rbrace$ es una base de $U^\perp.$

## Proyección ortogonal

En un espacio vectorial euclídeo $(V;\langle \cdot, \cdot \rangle),$ consideremos un conjunto de vectores linealmente independientes  $S=\lbrace\mathbf{u} _1,\ldots,\mathbf{u} _m \rbrace \subset V.$ Además, sean $U=\mathcal{L}(S)$ y $\lbrace\mathbf{u} _{m+1},\ldots,\mathbf{u} _n \rbrace$ una base de $U^\perp.$

Si $\mathbf{v}\in V,$ entonces

$$
\mathbf{v}=a_1 \mathbf{u}_1+\cdots+a_m \mathbf{u}_m+ a_{m+1}\mathbf{u}_{m+1}+\cdots+a_n \mathbf{u}_n 
$$

y, por tanto, $\mathbf{v}=\mathbf{u}+\mathbf{w}$ con

$$
\begin{aligned}
\mathbf{u}&=a_1 \mathbf{u}_1+\cdots+a_m \mathbf{u}_m\in U,\\
\mathbf{w}=\mathbf{v}-\mathbf{u}&=a_{m+1}\mathbf{u}_{m+1}+\cdots+a_n \mathbf{u}_n\in U^\perp.
\end{aligned}
$$

Se llama *proyección ortogonal* de $\mathbf{v}$ sobre $U$ al (único) vector $\mathbf{u}\in U$ tal que $(\mathbf{v}-\mathbf{u})\perp U,$ al que denotaremos por $\mathbf{u}=p_U(\mathbf{v}).$

Para obtener $\mathbf{u}=p_U(\mathbf{v})$ podemos distinguir dos situaciones posibles.

Consideramos $\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_n\rbrace$ base ortogonal de $(V;\langle \cdot, \cdot \rangle)$ tal que $\lbrace\mathbf{u} _1,\ldots,\mathbf{u} _m\rbrace$ es base de $U$ y $\lbrace\mathbf{u} _{m+1},\ldots,\mathbf{u} _n\rbrace$ es base de $U^\perp.$

 Si $\mathbf{v}\in V,$ entonces 

 $$
 \begin{aligned}
    \mathbf{v} = & \dfrac{\langle \mathbf{v}, \mathbf{u} _1 \rangle}{\Vert \mathbf{u} _1\Vert^2}\mathbf{u} _1+\cdots+\dfrac{\langle \mathbf{v}, \mathbf{u} _m \rangle}{\Vert \mathbf{u} _m\Vert^2}\mathbf{u} _m  \\
    & + \dfrac{\langle \mathbf{v}, \mathbf{u} _{m+1} \rangle}{\Vert \mathbf{u} _{m+1}\Vert^2}\mathbf{u} _{m+1}+\cdots+\dfrac{\langle \mathbf{v}, \mathbf{u} _n \rangle}{\Vert \mathbf{u} _n\Vert^2}\mathbf{u} _n.
 \end{aligned}
 $$

 Por tanto, la proyección ortogonal de $\mathbf{v}$ sobre $U$ es

 $$
 p_U(v)=\dfrac{\langle \mathbf{v}, \mathbf{u} _1 \rangle}{\Vert \mathbf{u} _1\Vert^2}\mathbf{u} _1+\cdots+\dfrac{\langle \mathbf{v}, \mathbf{u} _m \rangle}{\Vert \mathbf{u} _m\Vert^2}\mathbf{u} _m.
 $$

Supongamos ahora que $(V;\langle \cdot, \cdot \rangle)$ es un espacio vectorial euclídeo y que $S=\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_m\rbrace$ es una base (no necesariamente ortogonal) de un subespacio vectorial $U$ de $V.$

 Si $\mathbf{v}\in V$ y $\mathbf{u}=p_U(\mathbf{v}),$ entonces $\langle \mathbf{v}-\mathbf{u}, \mathbf{w} \rangle=0$ para todo $\mathbf{w}\in U.$ Por tanto, $\langle \mathbf{v}-\mathbf{u}, \mathbf{u}_j \rangle=0$ para  todo $j\in \lbrace 1,\dots,m\rbrace.$

 Ahora, si $\mathbf{u}=a_1 \mathbf{u}_1+\cdots+a_m \mathbf{u}_m,$ entonces

 $$
\langle \mathbf{v}-a_1\mathbf{u}_1-\cdots-a_m \mathbf{u}_m,\mathbf{u}_j \rangle=0, j\in\lbrace 1,\ldots,m\rbrace,
 $$

 es decir, $a_1,\dots,a_m$ es solución del sistema

 $$
\left\lbrace\begin{array}{cl}
    \langle \mathbf{u}_1,\mathbf{u}_1 \rangle x_1 + \cdots + \langle \mathbf{u}_m,\mathbf{u}_1 \rangle x_m & = \ \langle \mathbf{v},\mathbf{u}_1 \rangle, \\
    & \ \vdots \\
    \langle \mathbf{u}_1,\mathbf{u}_m \rangle x_1 + \cdots + \langle \mathbf{u}_m,\mathbf{u}_m \rangle x_m & = \ \langle \mathbf{v},\mathbf{u}_m \rangle.
 \end{array}\right.
 $$

A la matriz de coeficientes de este sistema 

$$
G = \begin{pmatrix} 
\langle \mathbf{u}_1,\mathbf{u}_1 \rangle & \cdots & \langle \mathbf{u}_m,\mathbf{u}_1 \rangle \\ 
\vdots & & \vdots \\ 
\langle \mathbf{u}_1,\mathbf{u}_m \rangle & \cdots & \langle \mathbf{u}_m,\mathbf{u}_m \rangle 
\end{pmatrix},
$$

se le conoce como *matriz de Gram* de $\langle \cdot,\cdot\rangle$ asociada a la base $\lbrace\mathbf{u}_1,\ldots,\mathbf{u}_m\rbrace$ de $U.$

Si $B=\lbrace\mathbf{v}_1,\dots,\mathbf{v}_n\rbrace$ es una base de $V,$ y $G$ es la matriz de Gram de $\langle \cdot,\cdot\rangle$ respecto de esa base, para cualesquiera $\mathbf{u}$ y $\mathbf{v}$ de $V$ con coordenadas $(u_1,\dots,u_n)$ y $(v_1,\dots,v_n),$ se tiene que 

$$
\langle \mathbf{u},\mathbf{v}\rangle =(u_1,\dots,u_n)\ G 
\begin{pmatrix} 
v_1\\ 
\vdots\\ 
v_n
\end{pmatrix}.
$$

###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/3-1.html) 

### Teorema de Pitágoras

Nótese que si $\mathbf{u}$ y $\mathbf{v}$ son ortogonales, entonces 

$$
\Vert \mathbf{u}+\mathbf{v}\Vert^2=\langle \mathbf{u},\mathbf{u}\rangle+\langle \mathbf{u},\mathbf{v}\rangle +\langle\mathbf{v},\mathbf{u}\rangle+\langle\mathbf{v},\mathbf{v}\rangle=\langle\mathbf{u},\mathbf{u}\rangle+\langle\mathbf{v},\mathbf{v}\rangle=\Vert \mathbf{u}\Vert^2+ \Vert \mathbf{v}\Vert^2.
$$

Sea $\mathbf{v}$ un vector cualquiera de un espacio vectorial $V$ y $\mathbf{u}$ un elemento cualquiera de de un subespacio $U.$ Entonces 

$$
\Vert \mathbf{v}-\mathbf{u} \Vert = \Vert \mathbf{v}-p_U(\mathbf{v})+p_U(\mathbf{v})-\mathbf{u} \Vert, 
$$

y como $\mathbf{v}-p_U(\mathbf{v})\in U^\perp$ y $p_U(\mathbf{v})-\mathbf{w}\in U,$ aplicando el Teorema de Pitágoras tenemos que 

$$
\Vert \mathbf{v}-\mathbf{u} \Vert^2 = \Vert \mathbf{v}-p_U(\mathbf{v)}\Vert^2+\Vert p_U(\mathbf{v})-\mathbf{u} \Vert^2, 
$$

cantidad que es siempre mayor o igual que $\Vert \mathbf{v}-p_U(\mathbf{v})\Vert^2$; se da la igualdad si y sólo si $p_ U(\mathbf{v})=\mathbf{u}.$ Tenemos así demostrado el Teorema de Mejor Aproximación.

### Teorema de Mejor Aproximación

Dados $\mathbf{v}\in V$ y $U$ un subespacio vectorial, se tiene que para todo $\mathbf{u}\in U,$

$$
\Vert \mathbf{v}- p_U(\mathbf{v})\Vert \le \Vert \mathbf{v}-\mathbf{u}\Vert,
$$

dándose la igualdad para $\mathbf{u}=p_U(\mathbf{v}).$

###### $\to$ [Ejemplo Merino-Santos](https://www.ugr.es/~lmerino/3-3.html) 


# Diagonalización por semejanza ortogonal de matrices simétricas

Sea $(V,\langle,\rangle)$ un espacio vectorial euclídeo. Un endomorfismo $f:V\to V$ se dice *simétrico* (o *autoadjunto*) si para todo $\mathbf{u},\mathbf{v}\in V$ se tiene que 

$$
\langle f(\mathbf{u}),\mathbf{v}\rangle =\langle \mathbf{u},f(\mathbf{v})\rangle.
$$

Si $B=\lbrace \mathbf{e} _1,\dots,\mathbf{e} _n\rbrace$ es una base ortonormal de $V,$ y $A=\mathcal{M}(f;B),$ entonces $a _{ij}=\langle f(\mathbf{e} _j),\mathbf{e}_i\rangle=\langle \mathbf{e} _j,f(\mathbf{e} _i) \rangle=a _{ji},$ y por tanto $A$ es simétrica.

El recíproco también es cierto pues si $A$ es simétrica, entonces si $x$ y $y$ son las coordenadas de $\mathbf{u}$ y $\mathbf{v},$ respectivamente, tenemos que $\langle f(\mathbf{u}),\mathbf{v}\rangle = (Ax)^ty=x^tA^ty=x^t(Ay)=\langle \mathbf{u},f(\mathbf{v})\rangle.$

### Resultado

El endomorfismo $f$ es autoadjunto si y sólo si su matriz respecto de una base ortonormal es simétrica.

Sea $A\in \mathcal{M}_n(\mathbb{R})$ simétrica. Supongamos que $\lambda=a+i b$ es un valor propio complejo de $A.$ Existen $x,y\in \mathbb{R}^n$ tales que $A(x+iy)=(a+ib)(x+iy).$ Por tanto,

$$
Ax+iAy=A(x+iy)=(a+ib)(x+iy)=(ax-yb)+i(bx+ay).
$$

Igualando parte real con parte imaginaria, obtenemos $Ax=ax-yb$ y $Ay=bx+ay.$ Usamos ahora que $A$ es simétrica (y por tanto su endomorfismo asociado es autoadjunto)

$$
\begin{aligned}
\langle Ax ,y\rangle & =\langle ax-yb,y\rangle =a\langle x,y\rangle - b \langle y,y\rangle,\\
\langle x, Ay\rangle &= \langle x, bx+ay\rangle =b\langle x,x\rangle + a \langle x,y\rangle.
\end{aligned}
$$

Como $\langle Ax,y\rangle =\langle x,Ay\rangle,$ tenemos que 

$$
0=b(\langle x,x\rangle +\langle y,y\rangle),
$$

y como $\langle x,x\rangle + \langle y,y\rangle >0,$ deducimos que $b=0.$ Tenemos así el siguiente resultado.

### Resultado

Todos los valores propios de una matriz simétrica con entradas reales son reales.

Supongamos ahora que $\lambda_1,\dots,\lambda_m$ son todos los valores propios (reales) de $A.$ Como $\lambda_i\neq \lambda_j$ con $i\neq j,$ si $\mathbf{v}\in V_{\lambda_i}\cap V_{\lambda_j}$ y $x$ son las coordenadas de $\mathbf{v},$ tenemos que $Ax=\lambda_ix=\lambda_jx,$ por lo que $x=0$ y $\mathbf{v}=0.$ Esto quiere decir que $V_{\lambda_i}\cap V_{\lambda_j}=\lbrace\mathbf{0}\rbrace.$ De esta forma la suma $V_{\lambda_1}+\dots+V_{\lambda_m}$ es directa. Sea $U=V_{\lambda_1}\oplus \dots \oplus V_{\lambda_m}.$ 

Si $f$ es el endomorfismo que viene determinado por $A,$ entonces $f(U)\subseteq U.$ Es más, por ser $f$ autoadjunto, si $\mathbf{u}\in U$ y $\mathbf{v}\in U^\perp,$ por ser $f(\mathbf{u})\in U,$ se tiene que $0=\langle \mathbf{v},f(\mathbf{u})\rangle= \langle f(\mathbf{v}),\mathbf{u}\rangle,$ por lo que $f(\mathbf{v})\in U^\perp,$ esto es, $f(U^\perp)\subseteq U^\perp.$ Si $U^\perp\neq \lbrace \mathbf{0}\rbrace,$ entonces $f$ restringido a $U^\perp$ tendrá al menos una valor propio $\lambda.$ Si $\mathbf{v}$ es un vector propio asociado a $\lambda,$ $f(\mathbf{v})=\lambda\mathbf{v},$ por lo que $\lambda\in \lbrace\lambda_1,\dots,\lambda_m\rbrace,$ lo que lleva a $\mathbf{v}\in U\cap U^\perp=\lbrace\mathbf{0}\rbrace,$ lo que es absurdo. Por tanto $U^\perp=\lbrace \mathbf{0}\rbrace$ y $U=\mathbb{R}^n.$ Acabamos de probar el siguiente resultado.

### Teorema espectral para matrices simétricas reales

Toda matriz simétrica con entradas reales es diagonalizable.

Veamos ahora que los subespacios propios son además ortogonales entre sí. Si $\lambda$ y $\mu$ son dos valores distintos de $A$ (simétrica con entradas reales), y $\mathbf{u}$ y $\mathbf{v}$ son vectores propios asociados a $\lambda$ y $\mu$ respectivamente, entonces 

$$
\begin{aligned}
\langle f(\mathbf{u}),\mathbf{v}\rangle &=\lambda \langle \mathbf{u},\mathbf{v}\rangle,\\
\langle \mathbf{u},f(\mathbf{v})\rangle &= \mu\langle \mathbf{u},\mathbf{v}\rangle,
\end{aligned}
$$

con $f$ el endomorfismo determinado por $A.$ Como $f$ es autoadjunto, $(\lambda-\mu)\langle \mathbf{u},\mathbf{v}\rangle=0,$ y al ser $\lambda\neq \mu,$ concluimos que $\langle \mathbf{u},\mathbf{v}\rangle=0.$ 

Esto nos permite escoger dentro de cada subespacio asociado a cada valor propio de $A$ una base ortonormal. Al juntarlas todas obtenemos una base ortonormal de $V,$ y tenemos que la expresión de $f$ en esa base ortonormal es diagonal. Si llamamos $P$ a la matriz de paso (sus columnas son las coordenadas de los vectores de nuestra base ortonormal), entonces $P P^t=I_n,$ por lo que $P^{-1}=P^t.$ Estas matrices se denominan *ortogonales*. 

### Resultado

Si $A$ es una matriz simétrica con entradas reales, entonces existen $P$ ortogonal y una matriz diagonal $D$ tales que $D=P^tAP.$

### Ejemplo

Sea 

$$
A=\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}.
$$ 

Entonces, $D=Q^{-1}AQ,$ con 

$$
Q=\begin{pmatrix}1 - \sqrt{2} & 1 + \sqrt{2}\\1 & 1\end{pmatrix},\quad D=\begin{pmatrix}- \sqrt{2} & 0\\0 & \sqrt{2}\end{pmatrix}.
$$

Nótese que $Q$ no es ortogonal. Si tomamos $\mathbf{u}=(1-\sqrt{2},1)$ y $\mathbf{v}=(1+\sqrt{2},1),$ entonces la matriz $P$ cuyas columnas son $\frac{1}{\Vert \mathbf{u}\Vert }\mathbf{u}$ y $\frac{1}{\Vert\mathbf{v}\Vert}\mathbf{v}$ verifica que $D=P^tAP.$

###### $\to$ [Ejercicios resueltos]({{ site.baseurl | absolute_url }}{% link problemas/resueltos-4.md %}) 


## Autoevaluación

<iframe src="{{ site.baseurl | absolute_url }}{% link /assets/autoevaluacion/euclideo.html %}" style="border:none;" height="600" width="100%" title="autoevaluación"></iframe>
