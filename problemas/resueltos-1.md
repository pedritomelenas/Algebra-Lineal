---
layout: page
title: Problemas matrices y sistemas de ecuaciones
tag: problemas
---
<style>
@media (min-width: 38em) {
  html {
    font-size: 18px;
  }
}

.container {
    max-width: 56rem;
    }
    @media (min-width: 38em) {
    .container {
        max-width: 38rem;
    }
    }
    @media (min-width: 56em) {
    .container {
        max-width: 56rem;
    }
}


body {
  counter-reset: article;
}

article:before {
  counter-increment: article;
  content: counter(article) ". ";
}
</style>

# Matrices y sistemas de ecuaciones

Los ejercicios aquí mostrados han sido amablemente proporcionados por [Evangelina Santos](https://www.ugr.es/~esantos/) y maquetados por [Juan Rivas](https://github.com/MrRiversGit).

## Ejercicios resueltos 

<article>
Resuelve el siguiente sistema de ecuaciones lineales considerado en $\mathbb{Q}$, $\mathbb{Z}_3$ y $\mathbb{Z}_5$.

$$\left\{\begin{aligned} x_{2}-2x_{3}&= -4,\\ x_{1}+x_{2}-x_{3}&=0,\\ 2x_{1}-x_{2}+x_{3}&=3. \end{aligned}\right.$$
<details>
<summary>Solución</summary>
Usaremos el método de Gauss-Jordan, que consiste en encontrar la forma escalonada reducida del sistema de ecuaciones. Trabajaremos directamente en la matriz de coeficientes ampliada. 

<h3>Coeficientes en $\mathbb{Q}$</h3>
En primer lugar buscamos el pivote en la primera posición de la fila uno, en este caso intercambiando las posiciones de las ecuaciones una y dos:

$$\left(\begin{array}{ccc|c}
0 & 1 & -2 & -4\\
1 & 1 & -1 & 0\\
2 & -1 & 1 & 3
\end{array}\right)\sim_{f_1\rightarrow f_2} 
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & -1 & 0\\
0 & 1 & -2 & -4\\
2 & -1 & 1 & 3
\end{array}\right).$$

Ahora utilizamos el pivote para hacer ceros debajo de él, por medio de una operación elemental del tipo: a la fila $j$ se le resta la fila uno multiplicada por el coeficiente $a_{j1}$. En este caso solo hay que realizarlo para la fila tres:

$$\left(\begin{array}{ccc|c}
\boxed{1} & 1 & -1 & 0\\
0 & 1 & -2 & -4\\
2 & -1 & 1 & 3
\end{array}\right)
\sim_{f_3-2f_1\rightarrow f_3}  
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & -1 & 0\\
0 & 1 & -2 & -4\\
0 & -3 & 3 & 3
\end{array}\right).$$

Ahora procedemos de un modo similar con el pivote de la segunda ecuación, que ya está en la posición deseada, con él hacemos cero todos los elementos que están en su columna, tanto debajo como encima:

$$  
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & -1 & 0\\
0 & \boxed{1} & -2 & -4\\
0 & -3 & 3 & 3
\end{array}\right)\sim_{f_1-f_2\rightarrow f_1}  
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & -2 & -4\\
0 & -3 & 3 & 3
\end{array}\right)\sim_{f_3+3f_2\rightarrow f_3}  
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & -2 & -4\\
0 & 0 & -3 & -9
\end{array}\right).$$

Por último, normalizamos la tercera fila dividiéndola por menos tres:

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & -2 & -4\\
0 & 0 & -3 & -9
\end{array}\right)
\sim_{-\frac{1}{3}f_3\rightarrow f_3}\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & -2 & -4\\
0 & 0 & \boxed{1} & 3
\end{array}\right).$$

Por último usamos este pivote para hacer ceros el resto de entradas de su columna:

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & -2 & -4\\
0 & 0 & \boxed{1} & 3
\end{array}\right)
\sim_{f_1-f_3\rightarrow f_1}\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 0 & 1\\
0 & \boxed{1} & -2 & -4\\
0 & 0 & \boxed{1} & -3
\end{array}\right)\sim_{f_2+2f_3\rightarrow f_2}\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 0 & 1\\
0 & \boxed{1} & 0 & 2\\
0 & 0 & \boxed{1} & 3
\end{array}\right).$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(QQ,[[0,1,-2],[1,1,-1],[2,-1,1]])
b=matrix(QQ,[-4,0,3]).transpose()
Ab=block_matrix([[A,b]])
show(Ab,"~",Ab.rref())
</script>
</div>  


El sistema asociado a esta matriz tiene exactamente las mismas soluciones que el de partida (son sistemas equivalentes), y ha quedado de la siguiente manera:

$$
\left\{\begin{aligned}
x_{1}&= 1,\\
x_{2}&=2,\\
x_{3}&=3.
\end{aligned}\right.
$$

Luego es un sistema compatible determinado, y su única solución es $$(1,2,3).$$

<h3> Coeficientes en $\mathbb{Z}_3$ </h3>

En primer lugar vamos a substituir los coeficientes por representantes en $\{0,1,2\}$:

$$\left(\begin{array}{ccc|c}
0 & 1 & 1 & 2\\
1 & 1 & 2 & 0\\
2 & 2 & 1 & 0
\end{array}\right).$$

Y ahora calculamos la forma escalonada reducida por filas de esa matriz. Buscamos un pivote para la primera columna, que puede ser perfectamente el primer elemento de la segunda fila.

$$\left(\begin{array}{ccc|c}
0 & 1 & 1 & 2\\
1 & 1 & 2 & 0\\
2 & 2 & 1 & 0
\end{array}\right)\sim_{f_1\rightarrow f_2}\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 0\\
0 & 1 & 1 & 2\\
2 & 2 & 1 & 0
\end{array}\right).$$

Para eliminar la otra entrada no nula de la primera columna, que está en la tercera fila, multiplicamos la primera por $-2$ y se lo sumamos a la última fila. Como $-2$ módulo $3$ es $1$, esto equivale a sumarle a la tercera la primera fila.

$$\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 0\\
0 & 1 & 1 & 2\\
2 & 2 & 1 & 0
\end{array}\right)\sim_{f_3+f_1\rightarrow f_3}\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 0\\
0 & 1 & 1 & 2\\
0 & 0 & 0 & 0
\end{array}\right).$$

Ahora señalamos (ya está hecho) el pivote de la segunda fila y lo usamos para hacer cero el resto de posiciones de su columna:

$$\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 0\\
0 & \boxed{1} & 1 & 2\\
0 & 0 & 0 & 0
\end{array}\right)\sim_{f_1+2f_2\rightarrow f_1}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 1\\
0 & \boxed{1} & 1 & 2\\
0 & 0 & 0 & 0
\end{array}\right).
$$

Obtenemos así la forma escalonada reducida de nuestra matriz de coeficientes ampliada. 


Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(3),[[0,1,-2,-4],[1,1,-1,0],[2,-1,1,3]])
show(A,"~",A.rref())
</script>
</div>  

Puesto que la tercera fila ha quedado $0=0$, la correspondiente ecuación  se puede eliminar, quedando el siguiente sistema que es equivalente al de partida:

$$
\left\{\begin{aligned}
x_{1}+x_3&= 1,\\
x_{2}+x_3&=2.\\
\end{aligned}\right.
$$

Donde podemos despejar $x_1$ y $x_2$ (que son las incógnitas que corresponden con los pivotes) y usar $x_3$ como parámetro (la incógnita restante), quedando las soluciones parametrizadas de la siguiente forma:

$$
\left.\begin{aligned}
x_{1}&= 1+2\lambda\\
x_{2}&=2+2\lambda\\
x_3&=\lambda 
\end{aligned}\right\}, \lambda \in \mathbb{Z}_3.
$$

Luego este sistema tiene el siguiente conjunto de soluciones:

$$\{ (1,2,0), (0,1,1),(2,0,2)\}.$$

Por tanto, en el caso de tomar coeficientes en $\mathbb{Z}_3$, obtenemos un sistema compatible indeterminado.

<h3>Coeficientes en $\mathbb{Z}_5$</h3>

En primer lugar vamos a sustituir los coeficientes por sus respectivos  representantes en $\{0,1,2,3,4\}$:

$$\left(\begin{array}{ccc|c}
0 & 1 & 3 & 1\\
1 & 1 & 4 & 0\\
2 & 4 & 1 & 3
\end{array}\right).$$

Procedemos com en los casos anteriores, buscando un pivote con el que reducir la primera columna.

$$\left(\begin{array}{ccc|c}
0 & 1 & 3 & 1\\
1 & 1 & 4 & 0\\
2 & 4 & 1 & 3
\end{array}\right)
\sim_{f_1\rightarrow f_2}\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 4 & 0\\
0 & 1 & 3 & 1\\
2 & 4 & 1 & 3
\end{array}\right) \sim_{f_3+3f_1\rightarrow f_3}\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 4 & 0\\
0 & \boxed{1} & 3 & 1\\
0 & 2 & 3 & 3
\end{array}\right).$$

Procedemos con la segunda fila (y columna):

$$\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 4 & 0\\
0 & \boxed{1} & 3 & 1\\
0 & 2 & 3 & 3
\end{array}\right)
\sim_{f_1+4f_2\rightarrow f_1}\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & 3 & 1\\
0 & 2 & 3 & 3
\end{array}\right)\sim_{f_3+3f_2\rightarrow f_3}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & 3 & 1\\
0 & 0 & 2 & 1
\end{array}\right).
$$

Teniendo en cuenta que $2^{-1}=3$ en $\mathbb{Z}_5$:

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & 3 & 1\\
0 & 0 & 2 & 1
\end{array}\right)\sim_{3f_3\rightarrow f_3}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & 3 & 1\\
0 & 0 & \boxed{1} & 3
\end{array}\right).
$$

Por último usamos este pivote para hacer todos los ceros que sea posible:

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 4\\
0 & \boxed{1} & 3 & 1\\
0 & 0 & \boxed{1} & 3
\end{array}\right)\sim_{f_1+4f_3\rightarrow f_1}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 0 & 1\\
0 & \boxed{1} & 3 & 1\\
0 & 0 & \boxed{1} & 3
\end{array}\right)\sim_{f_2+2f_3\rightarrow f_2}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 0 & 1\\
0 & \boxed{1} & 0 & 2\\
0 & 0 & \boxed{1} & 3
\end{array}\right).
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[0,1,-2,-4],[1,1,-1,0],[2,-1,1,3]])
show(A,"~",A.rref())
</script>
</div>  

Nos ha quedado el sistema (equivalente al original):

$$
\left\{\begin{aligned}
x_{1}&= 1,\\
x_{2}&=2,\\
x_{3}&=3.
\end{aligned}\right.
$$

Luego este sistema tiene una única solución:

$$(1,2,3),$$

y de esta forma es compatible determinado.
</details>
</article>

<article>
Resuelve el siguiente sistema de ecuaciones lineales considerado en $\mathbb{Q}$, $\mathbb{Z}_3$, $\mathbb{Z}_5$ y $\mathbb{Z}_2$.

$$\left\{\begin{aligned} x-y+z+t+v&=0,\\ x+y+z+t-v&=0,\\ -x-y+z+t-v&=0. \end{aligned}\right.$$

<details>
<summary>Solución</summary>

Este sistema es homogéneo, es decir, la columna de términos independientes es entera de ceros. Puesto que las operaciones elementales en esa columna siempre la mantienen igual, solo escribiremos la matriz de coeficientes. 
Además, un sistema homogéneo siempre es Compatible puesto que admite la solución $(0,0,0,0,0)$.

<h3>Coeficientes en $\mathbb{Q}$</h3>
$$\left(\begin{array}{rrrrr}
\boxed{1} & -1 & 1 & 1 & 1\\
1 & 1 & 1 & 1 & -1\\
-1 & -1 & 1 & 1 & -1
\end{array}\right)\sim_{\tiny \begin{array}{l} f_2-f_1\rightarrow f_2\\
f_3+f_1\rightarrow f_3 \end{array}} 
\left(\begin{array}{rrrrr}
\boxed{1} & -1 & 1 & 1 & 1\\
0 & 2 & 0 & 0 & -2\\
0 & -2 & 2 & 2 & 0
\end{array}\right).$$

Podemos tomar como pivote el segundo elemento de la segunda fila o utilizarla antes para hacer cero en la posición $(3,2)$. Estaríamos apartándonos del método de Gauss-Jordan, pero al ser la forma de escalonada reducida por filas de la matriz única, no importa cuál es el camino para obtenerla.

$$\left(\begin{array}{rrrrr}
\boxed{1} & -1 & 1 & 1 & 1\\
0 & 2 & 0 & 0 & -2\\
0 & -2 & 2 & 2 & 0
\end{array}\right)
\sim_{f_3+f_2\rightarrow f_3}  
\left(\begin{array}{rrrrr}
\boxed{1} & -1 & 1 & 1 & 1\\
0 & 2 & 0 & 0 & -2\\
0 & 0 & 2 & 2 & -2
\end{array}\right).$$

Ahora sí tomamos como pivote el segundo elemento de la segunda fila y con él hacemos cero todos los elementos que están en su columna; después continuamos con el pivote de la tercera fila:

$$\left(\begin{array}{rrrrr}
\boxed{1} & -1 & 1 & 1 & 1\\
0 & 2 & 0 & 0 & -2\\
0 & 0 & 2 & 2 & -2
\end{array}\right)
\sim_{\tiny \begin{array}{l} \frac{1}{2}f_2\rightarrow f_2\\
f_1+f_2\rightarrow f_1 \end{array}}\left(\begin{array}{rrrrr}
\boxed{1} & 0 & 1 & 1 & 0\\
0 & \boxed{1} & 0 & 0 & -1\\
0 & 0 & 2 & 2 & -2
\end{array}\right)\sim_{\tiny \begin{array}{l} \frac{1}{2}f_3\rightarrow f_3 \\f_1-f_3\rightarrow f_1 \end{array}} 
\left(\begin{array}{rrrrr}
\boxed{1} & 0 & 0 & 0 & 1\\
0 & \boxed{1} & 0 & 0 & -1\\
0 & 0 & \boxed{1} & 1 & -1
\end{array}\right).$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(QQ,[[1,-1,1,1,1],[1,1,1,1,-1],[-1,-1,1,1,-1]])
show(A,"~",A.rref())
</script>
</div>  

Como ya tenemos una matriz escalonada reducida por filas, el sistema no puede simplificarse más. Solo queda escribir las soluciones: para ello observamos que las incógnitas $x,y$ y $z$ están listas para ser despejadas, son las que corresponden a los pivotes. Las que no corresponden a pivotes se utilizan como parámetros (o variables libres). La solución del sistema queda:  

$$\left.\begin{aligned}
x&=-\lambda_2\\
y&=\lambda_2\\
z&=-\lambda_1+\lambda_2\\
t&=\lambda_1 \\
v&=\lambda_2 
\end{aligned}\right\},   \lambda_1, \lambda_2 \in \mathbb{Q}.$$

luego es un sistema compatible Indeterminado.

<h3>Coeficientes en $\mathbb{Z}_3$</h3>
Este ejemplo es un caso muy especial, puesto que todos los coeficientes del sistema son unos y menos unos (también podrían haber sido ceros y razonaríamos igual), y estos elementos se pueden usar en cualquier cuerpo en el que $1\not = -1$. 

Si repasamos las operaciones utilizadas, son también válidas en $\mathbb{Z}_3$ y en $\mathbb{Z}_5$ (aunque multiplicar por $\frac{1}{2}$ correspondería a multiplicar por $2$ en $\mathbb{Z}_3$ o por $3$ en $\mathbb{Z}_5$).

Comprobemos el razonamiento con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(3),[[1,-1,1,1,1],[1,1,1,1,-1],[-1,-1,1,1,-1]])
show(A,"~",A.rref())
</script>
</div> 


Las soluciones en $\mathbb{Z}_3$ serían

$$\left.\begin{aligned}
x&=2\lambda_2\\
y&=\lambda_2\\
z&=2\lambda_1+\lambda_2\\
t&=\lambda_1 \\
v&=\lambda_2 
\end{aligned}\right\},  \lambda_1, \lambda_2 \in \mathbb{Z}_3.$$

y por tanto es compatible indeterminado y tiene un total de $9$ soluciones.

<h3>Coeficientes en $\mathbb{Z}_5$</h3>

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[1,-1,1,1,1],[1,1,1,1,-1],[-1,-1,1,1,-1]])
show(A,"~",A.rref())
</script>
</div> 

Como hemos comentado, la matriz escalonada reducida es la misma, luego las soluciones son:

$$\left.\begin{aligned}
x&=4\lambda_2\\
y&=\lambda_2\\
z&=4\lambda_1+\lambda_2\\
t&=\lambda_1 \\
v&=\lambda_2 
\end{aligned}\right\},  \ \lambda_1, \lambda_2 \in \mathbb{Z}_5,$$

y por tanto es compatible indeterminado y tiene un total de $25$ soluciones.

<h3>Coeficientes en $\mathbb{Z}_2$</h3>

$$\left(\begin{array}{ccccc}
\boxed{1} & 1 & 1 & 1 & 1\\
1 & 1 & 1 & 1 & 1\\
1 & 1 & 1 & 1 & 1
\end{array}\right)\sim_{\tiny \begin{array}{l} f_2-f_1\rightarrow f_2\\
f_3-f_1\rightarrow f_3 \end{array}} 
\left(\begin{array}{ccccc}
\boxed{1} & 1 & 1 & 1 & 1\\
0 & 0 & 0 & 0 & 0\\
0 & 0 & 0 & 0 & 0
\end{array}\right),$$

luego la única incógnita despejada sería $x$, y las soluciones dependerían de $4$ parámetros:

$$\left.\begin{aligned}
x&=\lambda_1+\lambda_2+\lambda_3+\lambda_4\\
y&=\lambda_1\\
z&=\lambda_2\\
t&=\lambda_3 \\
v&=\lambda_4 
\end{aligned}\right\},  \lambda_i \in \mathbb{Z}_2,\ i\in\{1,2,3,4\},$$

luego es compatible indeterminado y tiene un total de $2^4=16$ soluciones.
</details>
</article>

<article>
Resuelve el siguiente sistema de ecuaciones lineales considerado en $\mathbb{Q}$, $\mathbb{Z}_3$, $\mathbb{Z}_5$ y $\mathbb{Z}_7$.

$$\left\{\begin{aligned} x_{1}+x_{2}+x_{3}&= 2,\\ x_{1}+2x_{2}+x_{3}&=1,\\ x_{2}&=3. \end{aligned}\right.$$

<details>
<summary>Solución</summary>

Trabajaremos directamente con la matriz de coeficientes ampliada, buscando en cada caso la forma escalonada reducida por filas.

<h3>En $\mathbb{Z}_7$:</h3>

$$\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
1 & 2 & 1 & 1\\
0 & 1 & 0 &  3
\end{array}\right)\sim_{f_2-f_1\rightarrow f_2}
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
0 & \boxed{1} & 0 & 6\\
0 & 1 & 0 &  3
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-f_2\rightarrow f_2\\
f_3-f_1\rightarrow f_3 \end{array}} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & 6\\
0 & 0 & 0 &  4
\end{array}\right),
$$

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & 6\\
0 & 0 & 0 &  4
\end{array}\right)
\sim_{2f_3\rightarrow f_3} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 &  6\\
0 & 0 & 0 & 1\\
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-3f_3\rightarrow f_1\\
f_2-6f_3\rightarrow f_2 \end{array}}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 0\\
0 & \boxed{1} & 0 &  0\\
0 & 0 & 0 & \boxed{1}\\
\end{array}\right).
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(7),[[1,1,1,2],[1,2,1,1],[0,1,0,3]])
show(A,"~",A.rref())
</script>
</div> 

En el último paso no hemos escrito las operaciones elementales puesto que se da una circunstancia muy especial: el único elemento no nulo es el pivote. Eso hace que operar con esta fila sea muy sencillo, solo borra los elementos de su columna sin cambiar nada más.

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$) entonces el sistema es incompatible.

<h3>En $\mathbb{Z}_5$:</h3>

$$
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
1 & 2 & 1 & 1\\
0 & 1 & 0 &  3
\end{array}\right)\sim_{f_2-f_1\rightarrow f_2}
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
0 & \boxed{1} & 0 & 4\\
0 & 1 & 0 &  3
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-f_2\rightarrow f_2\\
f_3-f_1\rightarrow f_3 \end{array}} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & 4\\
0 & 0 & 0 &  4
\end{array}\right),
$$

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & 4\\
0 & 0 & 0 &  4
\end{array}\right)
\sim_{4f_3\rightarrow f_3} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 &  4\\
0 & 0 & 0 & 1\\
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-3f_3\rightarrow f_1\\
f_2-4f_3\rightarrow f_2 \end{array}}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 0\\
0 & \boxed{1} & 0 &  0\\
0 & 0 & 0 & \boxed{1}\\
\end{array}\right).
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[1,1,1,2],[1,2,1,1],[0,1,0,3]])
show(A,"~",A.rref())
</script>
</div> 

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$), el sistema es incompatible.

<h3>En $\mathbb{Z}_3$:</h3>

$$
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
1 & 2 & 1 & 1\\
0 & 1 & 0 &  0
\end{array}\right)\sim_{f_2-f_1\rightarrow f_2}
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
0 & \boxed{1} & 0 & 4\\
0 & 1 & 0 &  3
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-f_2\rightarrow f_2\\
f_3-f_1\rightarrow f_3 \end{array}} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & 4\\
0 & 0 & 0 &  4
\end{array}\right),
$$

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & 4\\
0 & 0 & 0 &  4
\end{array}\right)
\sim_{4f_3\rightarrow f_3} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 &  4\\
0 & 0 & 0 & 1\\
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-3f_3\rightarrow f_1\\
f_2-4f_3\rightarrow f_2 \end{array}}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 0\\
0 & \boxed{1} & 0 &  0\\
0 & 0 & 0 & \boxed{1}\\
\end{array}\right).
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(3),[[1,1,1,2],[1,2,1,1],[0,1,0,3]])
show(A,"~",A.rref())
</script>
</div> 

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$), el sistema es incompatible.

<h3>En En $\mathbb{Q}$:</h3>

$$
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
1 & 2 & 1 & 1\\
0 & 1 & 0 &  3
\end{array}\right)\sim_{f_2-f_1\rightarrow f_2}
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & 1 & 2\\
0 & \boxed{1} & 0 & -1\\
0 & 1 & 0 &  3
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-f_2\rightarrow f_2\\
f_3-f_1\rightarrow f_3 \end{array}} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & -1\\
0 & 0 & 0 &  4
\end{array}\right),
$$

$$\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 & -1\\
0 & 0 & 0 &  4
\end{array}\right)
\sim_{\frac{1}{4}f_3\rightarrow f_3} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 &  -1\\
0 & 0 & 0 & 1\\
\end{array}\right)\sim_{\tiny \begin{array}{l} f_1-3f_3\rightarrow f_1\\
f_2+f_3\rightarrow f_2 \end{array}}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 0\\
0 & \boxed{1} & 0 &  0\\
0 & 0 & 0 & \boxed{1}\\
\end{array}\right).
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(QQ,[[1,1,1,2],[1,2,1,1],[0,1,0,3]])
show(A,"~",A.rref())
</script>
</div> 

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$), el sistema es incompatible.
</details>

</article>