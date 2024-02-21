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
A=matrix(QQ,[[0,1,-2],[1,1,-1],[2,-1,1]]) #matriz de coeficientes
b=vector(QQ,[-4,0,3]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
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
A=matrix(GF(3),[[0,1,-2],[1,1,-1],[2,-1,1]]) #matriz de coeficientes
b=vector(GF(3),[-4,0,3]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
show(Ab,"~",Ab.rref())
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
A=matrix(GF(5),[[0,1,-2],[1,1,-1],[2,-1,1]]) #matriz de coeficientes
b=vector(GF(5),[-4,0,3]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
show(Ab,"~",Ab.rref())
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

$$\begin{align*}\left(\begin{array}{ccc|c}
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
\end{array}\right)\\
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
\end{align*}
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(7),[[1,1,1],[1,2,1],[0,1,0]]) #matriz de coeficientes
b=vector(GF(7),[2,1,3]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
show(Ab,"~",Ab.rref())
</script>
</div>  

En el último paso no hemos escrito las operaciones elementales puesto que se da una circunstancia muy especial: el único elemento no nulo es el pivote. Eso hace que operar con esta fila sea muy sencillo, solo borra los elementos de su columna sin cambiar nada más.

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$) entonces el sistema es incompatible.

<h3>En $\mathbb{Z}_5$:</h3>

$$\begin{align*}
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
\end{array}\right)\\
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
\end{align*}
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[1,1,1],[1,2,1],[0,1,0]]) #matriz de coeficientes
b=vector(GF(5),[2,1,3]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
show(Ab,"~",Ab.rref())
</script>
</div>   

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$), el sistema es incompatible.

<h3>En $\mathbb{Z}_3$:</h3>

$$\begin{align*}
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
\end{array}\right)\\
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
\end{align*}
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(3),[[1,1,1],[1,2,1],[0,1,0]]) #matriz de coeficientes
b=vector(GF(3),[2,1,3]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
show(Ab,"~",Ab.rref())
</script>
</div>  

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$), el sistema es incompatible.

<h3>En $\mathbb{Q}$:</h3>

$$\begin{align*}
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
\end{array}\right)\\
\sim_{\frac{1}{4}f_3\rightarrow f_3} 
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 3\\
0 & \boxed{1} & 0 &  -1\\
0 & 0 & 0 & 1\\
\end{array}\right)
\sim_{\tiny \begin{array}{l} f_1-3f_3\rightarrow f_1\\
f_2+f_3\rightarrow f_2 \end{array}}
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 1 & 0\\
0 & \boxed{1} & 0 &  0\\
0 & 0 & 0 & \boxed{1}\\
\end{array}\right).
\end{align*}
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(QQ,[[1,1,1],[1,2,1],[0,1,0]]) #matriz de coeficientes
b=vector(QQ,[2,1,3]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
show(Ab,"~",Ab.rref())
</script>
</div>  

Como hay un pivote en la columna de términos independientes (es decir, aparece la ecuación $0=1$), el sistema es incompatible.
</details>
</article>

<article>
En el cuerpo $\mathbb{Z}_5$ se considera la matriz
$$C = \begin{pmatrix} 1&1&1&1 \\ 0&2&1&2 \\ 0&4&1&1 \\ \end{pmatrix}.$$

<ol type="a">
  <li>Calcula la forma de Hermite por filas de $C$.</li>
  <li>Calcula la forma de Hermite por columnas de $C$.</li>
  <li>Elige una submatriz cuadrada de $C$ de orden tres que sea regular y calcula su inversa.</li>
</ol>

<details>
<summary>Solución</summary>
<ol type="a">
<li>Forma de Hermite por filas.</li>
Realizamos operaciones elemntales por filas hasta obtener una matriz escalonada reducida por filas:

$$
\begin{align*}
\left( 
\begin{array}{rrrr}
\boxed{1} & 1 & 1 & 1\\
0 & 2 & 1 & 2\\
0 & 4 & 1 & 1\\
\end{array}
\right) & \sim_{\begin{array}{l} 3f_2\rightarrow f_2\end{array}}
\left(
\begin{array}{rrrr}
\boxed{1} & 1 & 1 & 1\\
0 & 1 & 3 & 1\\
0 & 4 & 1 & 1\\
\end{array}
\right)\sim_{ \begin{array}{l} f_3-4f_2\rightarrow f_3\end{array}}
\left( 
\begin{array}{rrrr}
\boxed{1} & 0 & 3 & 0\\
0 & \boxed{1} & 3 & 1\\
0 & 0 & 4 & 2\\
\end{array}
\right) \\
& \sim_{ \begin{array}{l} 4f_3\rightarrow f_3\end{array}}
\left( 
\begin{array}{rrrr}
\boxed{1} & 0 & 3 & 0\\
0 & \boxed{1} & 3 & 1\\
0 & 0 &\boxed{1} & 3\\
\end{array}
\right)\sim_{ \begin{array}{l} f_1-3f_3\rightarrow f_1\\
f_2-3f_3\rightarrow f_2 \end{array}}
\left(
\begin{array}{rrrr}
\boxed{1} & 0 & 0 & 1\\
0 &\boxed{1} & 0 & 2\\
0 & 0 & \boxed{1} & 3\\
\end{array}
\right).
\end{align*}
$$

Por tanto la forma de Hermite por filas es 

$$\left( 
\begin{array}{rrrr}
1 & 0 & 0 & 1\\
0 & 1 & 0 & 2\\
0 & 0 & 1 & 3\\
\end{array}
\right).$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[1,1,1,1],[0,2,1,2],[0,4,1,1]])
show(A,"~",A.rref())
</script>
</div> 

<li>Forma de Hermite por columnas.</li>
Como el número de pivotes en la forma de Hermite por columnas coincide con el que hay en la de filas, entonces la única posibilidad es que sea 
$$\left( 
\begin{array}{rrrr}
\boxed{1} & 0 & 0 & 0\\
0 & \boxed{1} & 0 & 0\\
0 & 0 & \boxed{1} & 0\\
\end{array}
\right).$$

Comprobemos el resultado obtenido con <code>sage</code> (para eso transponemos la matriz, calculamos su forma escalonada reducida por filas, y volvemos a transponer).

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[1,1,1,1],[0,2,1,2],[0,4,1,1]])
show(A,"~",(A.T).rref().T)
</script>
</div> 


<li>Una submatriz cuadrada de orden tres regular y su inversa.</li>
Hay cuatro elecciones posibles. Solo damos un ejemplo de cómo calcularlo.
Elegimos por ejemplo las tres primeras columnas (como el determinante vale $2-4=-2=3$ en  $\mathbb{Z}_5$, es regular) y unimos una matriz identidad a la derecha. Para calcular la inversa realizamos operaciones elementales por filas en las filas de $(A\mid I)$:

$$
\begin{align*}
(A \mid I)& =\left( 
\begin{array}{rrr|rrr}
\boxed{1} & 1 & 1 & 1 & 0 & 0\\
0 & 2 & 1 & 0 & 1 & 0\\
0 & 4 & 1 & 0 & 0 & 1\\
\end{array}
\right)\sim_{ \begin{array}{l} 3f_2\rightarrow f_2\end{array}}
\left( 
\begin{array}{rrr|rrr}
\boxed{1} & 1 & 1 & 1 & 0 & 0\\
0 & \boxed{1} & 3 & 0 & 3 & 0\\
0 & 4 & 1 & 0 & 0 & 1\\
\end{array}
\right) \sim_{ \begin{array}{l} f_3-4f_2\rightarrow f_3\end{array}} 
\left(
\begin{array}{rrr|rrr}
\boxed{1} & 0 & 3 & 1 & 2 & 0\\
0 & \boxed{1} & 3 & 0 & 3 & 0\\
0 & 0 & 4 & 0 & 3 & 1\\
\end{array}
\right)  \\
& \sim_{ \begin{array}{l} 4f_3\rightarrow f_3\end{array}}
\left(
\begin{array}{rrr|rrr}
\boxed{1} & 0 & 3 & 1 & 2 & 0\\
0 & \boxed{1} & 3 & 0 & 3 & 0\\
0 & 0 & \boxed{1} & 0 & 2 & 4\\
\end{array}
\right) \sim_{ \begin{array}{l} f_1-3f_3\rightarrow f_1\\
f_2-3f_3\rightarrow f_2 \end{array}}
\left( 
\begin{array}{rrr|rrr}
\boxed{1} & 0 & 0 & 1 & 1 & 3\\
0 & \boxed{1} & 0 & 0 & 2 & 3\\
0 & 0 & \boxed{1} & 0 & 2 & 4\\
\end{array}
\right)=(I\mid A^{-1}).
\end{align*}
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[1,1,1],[0,2,1],[0,4,1]])
I=matrix(GF(5),[[1,0,0],[0,1,0],[0,0,1]]) #matriz identidad
AI=A.augment(I,subdivide=True) #matriz aumentada
show(AI,"~",AI.rref())
</script>
</div>  

Finalmente comprobamos que es inversa:
$$\left( 
\begin{array}{rrr}
1 & 1 & 1 \\
0 & 2 & 1 \\
0 & 4 & 1 \\
\end{array}
\right)\left( 
\begin{array}{rrr}
1 & 1 & 3 \\
0 & 2 & 3 \\
0 & 2 & 4 \\
\end{array}
\right)=\left( 
\begin{array}{rrr}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{array}
\right).$$

</ol>
</details>
</article>

<article>
Encuentra, si es posible, $P \in \mathcal{M}_{4}(\mathbb{Z}_3)$, regular, tal que $PA=B$, donde
$$A = \begin{pmatrix} 1&1&0&2&1 \\ 2&1&1&2&0 \\ 0&2&1&0&2 \\ 0&1&2&1&0 \end{pmatrix}, \qquad B = \begin{pmatrix} 1&1&0&1&2 \\ 1&2&2&1&0 \\ 1&0&1&2&0 \\ 2&2&0&0&0 \end{pmatrix}.$$

<details>
<summary>Solución</summary>

Sabemos que $A\sim_f B$ si y sólo si existe  $P$ regular tal que $PA=B$. Por tanto, primero comprobaremos que $A$ y $B$ tienen la misma forma escalonada reducida por filas, calculando además las matrices de paso. Si coinciden, entonces usando las matrices de paso que hemos calculado, podremos encontrar $P$.

<ol type="a">
<li> En primer lugar calculamos las formas de Hermite por filas para comprobar que ambas, la de $A$ y la de $B$ son iguales. Al mismo tiempo calcularemos matrices de paso correspondientes a cada una de ellas.</li>

$$
\begin{align*}
(A \mid I) & = \left(\begin{array}{ccccc|cccc}
\boxed{1} & 1 & 0 & 2 & 1 & 1 & 0 & 0 & 0  \\
2 & 1 & 1 & 2 & 0 & 0 & 1 & 0 & 0  \\ 
0 & 2 & 1 & 0 & 2 & 0 & 0 & 1 & 0 \\ 
0 & 1 & 2 & 1 & 0 & 0 & 0 & 0 & 1 \\
\end{array}\right)\sim_f  \left(\begin{array}{ccccc|cccc}
\boxed{1} & 1 & 0 & 2 & 1 & 1 & 0 & 0 & 0  \\
0 & 2 & 1 & 1 & 1 & 1 & 1 & 0 & 0  \\ 
0 & 2 & 1 & 0 & 2 & 0 & 0 & 1 & 0 \\ 
0 & 1 & 2 & 1 & 0 & 0 & 0 & 0 & 1 \\
\end{array}\right) \\
& \sim_f  \left(\begin{array}{ccccc|cccc}
\boxed{1} & 1 & 0 & 2 & 1 & 1 & 0 & 0 & 0  \\
0 & \boxed{1} & 2 & 2 & 2 & 2 & 2 & 0 & 0  \\ 
0 & 2 & 1 & 0 & 2 & 0 & 0 & 1 & 0 \\ 
0 & 1 & 2 & 1 & 0 & 0 & 0 & 0 & 1 \\
\end{array}\right)
\sim_f  \left(\begin{array}{ccccc|cccc}
\boxed{1} & 0 & 1 & 0 & 2 & 2 & 1 & 0 & 0  \\
0 & \boxed{1} & 2 & 2 & 2 & 2 & 2 & 0 & 0  \\ 
0 & 0 & 0 & 2 & 1 & 2 & 2 & 1 & 0 \\ 
0 & 0 & 0 & 2 & 1 & 1 & 1 & 0 & 1 \\
\end{array}\right) \\ 
& \sim_f  \left(\begin{array}{ccccc|cccc}
\boxed{1} & 0 & 1 & 0 & 2 & 2 & 1 & 0 & 0  \\
0 & \boxed{1} & 2 & 2 & 2 & 2 & 2 & 0 & 0  \\ 
0 & 0 & 0 & \boxed{1} & 2 & 1 & 1 & 2 & 0 \\ 
0 & 0 & 0 & 0 & 0 & 2 & 2 & 2 & 1 \\
\end{array}\right)
\sim_f  \left(\begin{array}{ccccc|cccc}
\boxed{1} & 0 & 1 & 0 & 2 & 2 & 1 & 0 & 0  \\
0 & \boxed{1} & 2 & 0 & 1 & 0 & 0 & 2 & 0  \\ 
0 & 0 & 0 & \boxed{1} & 2 & 1 & 1 & 2 & 0 \\ 
0 & 0 & 0 & 0 & 0 & 2 & 2 & 2 & 1 \\
\end{array}\right)=(H_A|P_A).
\end{align*}$$

$$
\begin{align*}
(B \mid I) & = \left(\begin{array}{ccccc|cccc}
\boxed{1} & 1 & 0 & 1 & 2 & 1 & 0 & 0 & 0  \\
1 & 2 & 2 & 1 & 0 & 0 & 1 & 0 & 0  \\ 
1 & 0 & 1 & 2 & 0 & 0 & 0 & 1 & 0 \\ 
2 & 2 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\
\end{array}\right)\sim_f \left(\begin{array}{ccccc|cccc}
\boxed{1} & 1 & 0 & 1 & 2 & 1 & 0 & 0 & 0  \\
0 & 1 & 2 & 0 & 1 & 2 & 1 & 0 & 0  \\ 
0 & 2 & 1 & 1 & 1 & 2 & 0 & 1 & 0 \\ 
0 & 0 & 0 & 1 & 2 & 1 & 0 & 0 & 1 \\
\end{array}\right) \\
& \sim_f \left(\begin{array}{ccccc|cccc}
\boxed{1} & 0 & 1 & 1 & 1 & 2 & 2 & 0 & 0  \\
0 & \boxed{1} & 2 & 0 & 1 & 2 & 1 & 0 & 0  \\ 
0 & 0 & 0 & \boxed{1} & 2 & 1 & 1 & 1 & 0 \\ 
0 & 0 & 0 & 1 & 2 & 1 & 0 & 0 & 1 \\
\end{array}\right) \sim_f \left(\begin{array}{ccccc|cccc}
\boxed{1} & 0 & 1 & 0 & 2 & 1 & 1 & 2 & 0  \\
0 & \boxed{1} & 2 & 0 & 1 & 2 & 1 & 0 & 0  \\ 
0 & 0 & 0 & \boxed{1} & 2 & 1 & 1 & 1 & 0 \\ 
0 & 0 & 0 & 0 & 0 & 0 & 2 & 2 & 1 \\
\end{array}\right)=(H_B \mid P_B).
\end{align*}
$$

<li> Hemos comprobado que $H_A=H_B$ y por tanto $A\sim_f B$ y existe una matriz $P$ tal que $PA=B$.</li>
<li> Para calcular $P$ podemos ayudarnos de las matrices de paso $P_A$ y $P_B$ calculadas:</li>
$$P_A A=H_A=H_B=P_B B,$$
y por tanto
$$P_A A=P_B B.$$
Como $P_B$ es regular, 
$$(P_B)^{-1}P_A A=B.$$
Luego una matriz que verifica la condición pedida sería el producto $(P_B)^{-1}P_A$.

Para calcularla necesitamos en primer lugar calcular la inversa de $P_B$, también usando operaciones elementales por filas.

$$\begin{align*}
(P_B \mid I) & = \left(\begin{array}{cccc|cccc}
 1 & 1 & 2 & 0  & 1 & 0 & 0 & 0\\
 2 & 1 & 0 & 0  & 0 & 1 & 0 & 0\\ 
 1 & 1 & 1 & 0  & 0 & 0 & 1 & 0\\ 
 0 & 2 & 2 & 1  & 0 & 0 & 0 & 1\\
\end{array}\right)\sim_f \left(\begin{array}{cccc|cccc}
 \boxed{1} & 1 & 2 & 0  & 1 & 0 & 0 & 0\\ 
 2 & 1 & 0 & 0  & 0 & 1 & 0 & 0\\ 
 1 & 1 & 1 & 0  & 0 & 0 & 1 & 0\\ 
 0 & 2 & 2 & 1  & 0 & 0 & 0 & 1\\
\end{array}\right) \\
& \sim_f \left(\begin{array}{cccc|cccc}
 \boxed{1} & 1 & 2 & 0  & 1 & 0 & 0 & 0\\ 
 0 & 2 & 2 & 0  & 1 & 1 & 0 & 0\\
 0 & 0 & 2 & 0  & 2 & 0 & 1 & 0\\ 
 0 & 2 & 2 & 1  & 0 & 0 & 0 & 1\\
\end{array}\right)\sim_f
\left(\begin{array}{cccc|cccc}
 \boxed{1} & 1 & 2 & 0  & 1 & 0 & 0 & 0\\ 
 0 & 2 & 2 & 0  & 1 & 1 & 0 & 0\\
 0 & 0 & 2 & 0  & 2 & 0 & 1 & 0\\ 
 0 & 2 & 2 & 1  & 0 & 0 & 0 & 1\\
\end{array}\right) \\
& \sim_f \left(\begin{array}{cccc|cccc}
 \boxed{1} & 1 & 2 & 0  & 1 & 0 & 0 & 0\\ 
 0 & \boxed{1} & 1 & 0  & 2 & 2 & 0 & 0\\
 0 & 0 & 2 & 0  & 2 & 0 & 1 & 0\\ 
 0 & 2 & 2 & 1  & 0 & 0 & 0 & 1\\
\end{array}\right)
\sim_f \left(\begin{array}{cccc|cccc}
 \boxed{1} & 1 & 2 & 0  & 1 & 0 & 0 & 0\\ 
 0 & \boxed{1} & 1 & 0  & 2 & 2 & 0 & 0\\
 0 & 0 & 2 & 0  & 2 & 0 & 1 & 0\\ 
 0 & 0 & 0 & 1  & 2 & 2 & 0 & 1\\
\end{array}\right) \\
& \sim_f \left(\begin{array}{cccc|cccc}
 \boxed{1} & 1 & 2 & 0  & 1 & 0 & 0 & 0\\ 
 0 & \boxed{1} & 1 & 0  & 2 & 2 & 0 & 0\\
 0 & 0 & \boxed{1} & 0  & 1 & 0 & 2 & 0\\ 
 0 & 0 & 0 & \boxed{1}  & 2 & 2 & 0 & 1\\
\end{array}\right)
\sim_f \left(\begin{array}{cccc|cccc}
 \boxed{1} & 1 & 0 & 0  & 2 & 0 & 2 & 0\\ 
 0 & \boxed{1} & 0 & 0  & 1 & 2 & 1 & 0\\
 0 & 0 & \boxed{1} & 0  & 1 & 0 & 2 & 0\\ 
 0 & 0 & 0 & \boxed{1}  & 2 & 2 & 0 & 1\\
\end{array}\right) \\
& \sim_f \left(\begin{array}{cccc|cccc}
 \boxed{1} & 0 & 0 & 0  & 1 & 1 & 1 & 0\\ 
 0 & \boxed{1} & 0 & 0  & 1 & 2 & 1 & 0\\
 0 & 0 & \boxed{1} & 0  & 1 & 0 & 2 & 0\\ 
 0 & 0 & 0 & \boxed{1}  & 2 & 2 & 0 & 1\\
\end{array}\right).
\end{align*}$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
PB=matrix(GF(3),[[1,1,2,0],[2,1,0,0],[1,1,1,0],[0,2,2,1]]) 
I=matrix(GF(3),[[1,0,0,0],[0,1,0,0],[0,0,1,0],[0,0,0,1]]) #matriz identidad
PBI=PB.augment(I,subdivide=True) #matriz aumentada
show(PBI,"~",PBI.rref())
</script>
</div> 

Luego una posible $P$ es
$$P=(P_B)^{-1}P_A=\left(\begin{array}{cccc}
 1 & 1 & 1 & 0\\ 
 1 & 2 & 1 & 0\\
 1 & 0 & 2 & 0\\ 
 2 & 2 & 0 & 1\\
\end{array}\right) \left(\begin{array}{cccc}
 2 & 1 & 0 & 0  \\
 0 & 0 & 2 & 0  \\ 
 1 & 1 & 2 & 0 \\ 
 2 & 2 & 2 & 1 \\
\end{array}\right)= \left(\begin{array}{cccc}
 0 & 2 & 1 & 0  \\
 0 & 2 & 0 & 0  \\ 
 1 & 0 & 1 & 0 \\ 
 0 & 1 & 0 & 1 \\
\end{array}\right).$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
PBI=matrix(GF(3),[[1,1,1,0],[1,2,1,0],[1,0,2,0],[2,2,0,1]]) 
PA=matrix(GF(3),[[2,1,0,0],[0,0,2,0],[1,1,2,0],[2,2,2,1]])
P=PBI*PA
A=matrix(GF(3),[[1,1,0,2,1],[2,1,1,2,0],[0,2,1,0,2],[0,1,2,1,0]]) 
B=matrix(GF(3),[[1,1,0,1,2],[1,2,2,1,0],[1,0,1,2,0],[2,2,0,0,0]]) 
P*A==B
</script>
</div> 

</ol>
</details>
</article>

<article>
Sea $$A=\left (\begin{array}{cccc} 2 & 1 & 3 & 0 \\ 1 & 2 & 1 & 1 \\ 3 & 4 & 2 & 1 \end{array}\right ) \in \mathcal{M}_{3\times 4}({\mathbb{Z}}_5)$$

<ol type="a">
  <li>Encuentra una matriz $B$ tal que $A\cdot B = Id$.</li>
  <li>Encuentra todas las matrices $B$ que cumplan la propiedad anterior.</li>
  <li>¿Existe una matriz $C$ tal que $C\cdot A = Id$?</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>$B$ tal que $A\cdot B = Id$.</li>

¿Qué orden debe tener $B$?<br>

Como la identidad es una matriz cuadrada, podemos calcular el orden de la matriz $B$ que nos piden:

<table class="default">
  <tr>
    <td>$A$</td>
    <td>$\cdot B$</td>
    <td>$=I$</td>
  </tr>
  <tr>
    <td>$3\times 4$</td>
    <td>$4\times$ ?</td>
    <td>$3\times 3$</td>
  </tr>
</table>
Una idea posible<br>
Si calculamos la forma de Hermite por columnas de $A$ y la matriz de paso, a la que llamaremos $Q$, entonces $A\cdot Q=H$. $H$ no es la matriz identidad, por supuesto, porque tiene orden $3\times 4$, pero puede parecerse bastante. Calculémosla:

$$\left[ \begin{array}{c}
A\\
\hline
I_4
\end{array}\right]=\left (\begin{array}{cccc}
2 & \boxed{1} & 3 & 0 \\ 1 & 2 & 1 & 1 \\ 3 & 4 & 2 & 1\\
\hline
1 & 0 & 0 &0\\
0 & 1 & 0 &0\\
0 & 0 & 1 &0\\
0 & 0 & 0 &1\\
 \end{array}\right)\sim_c 
\left (\begin{array}{cccc}
\boxed{1} & 0 & 0 & 0 \\ 2 & 2 & 1 & 0 \\ 
4 & 0 & 1 & 0\\
\hline
0 & 1 & 0 &0\\
1 & 3 & 0 & 2\\
0 & 0 & 0 &1\\
0 & 0 & 1 &0\\
\end{array}\right) \sim_c 
\left (\begin{array}{cccc}
\boxed{1} & 0 & 0 & 0 \\ 
2 & \boxed{1} & 1 & 0 \\ 
4 & 0 & 1 & 0\\
\hline
0 & 3 & 0 &0\\
1 & 4 & 0 & 2\\
0 & 0 & 0 &1\\
0 & 0 & 1 &0\\
\end{array}\right) \sim_c
$$ 

$$
\sim_c 
\left (\begin{array}{cccc}
\boxed{1} & 0 & 0 & 0 \\ 
0 & \boxed{1} & 0 & 0 \\ 
4 & 0 & \boxed{1} & 0\\
\hline
4 & 3 & 2 &0\\
3 & 4 & 1 & 2\\
0 & 0 & 0 &1\\
0 & 0 & 1 &0\\
\end{array}\right) \sim_c
\left (\begin{array}{cccc}
\boxed{1} & 0 & 0 & 0 \\ 
0 & \boxed{1} & 0 & 0 \\ 
0 & 0 & \boxed{1} & 0\\
\hline
1 & 3 & 2 &0\\
4 & 4 & 1 & 2\\
0 & 0 & 0 &1\\
1 & 0 & 1 &0\\
\end{array}\right)=\left[ \begin{array}{c}
H\\
\hline
Q
\end{array}\right].
$$ 

Así que 
$$\left(\begin{array}{cccc}
2 & 1 & 3 & 0 \\ 1 & 2 & 1 & 1 \\ 3 & 4 & 2 & 1\\
\end{array}\right)
\left (\begin{array}{ccc|c}
1 & 3 & 2 &0\\
4 & 4 & 1 & 2\\
0 & 0 & 0 &1\\
1 & 0 & 1 &0\\
\end{array}\right)=\left (\begin{array}{ccc|c}
\boxed{1} & 0 & 0 & 0 \\ 
0 & \boxed{1} & 0 & 0 \\ 
0 & 0 & \boxed{1} & 0\\
\end{array}\right). 
$$

Una solución:<br>

Observando el producto anterior nos damos cuenta de que si tomamos solo las 3 primeras columnas de $Q$ tenemos una matriz que verifica la condición.
Así que una posible matriz $B$ es 

$$
B=\left (\begin{array}{ccc}
1 & 3 & 2 \\
4 & 4 & 1 \\
0 & 0 & 0 \\
1 & 0 & 1 \\
\end{array}\right).$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(GF(5),[[2,1,3,0],[1,2,1,1],[3,4,2,1]]) 
B=matrix(GF(5),[[1,3,2],[4,4,1],[0,0,0],[1,0,1]]) 
I=matrix(GF(5),[[1,0,0],[0,1,0],[0,0,1]])
A*B==I
</script>
</div> 

<li>Todas las matrices $B$ que cumplen la propiedad anterior.</li>
En realidad el planteamiento es sencillo, sería resolver:
$$\left(\begin{array}{cccc}
2 & 1 & 3 & 0 \\ 1 & 2 & 1 & 1 \\ 3 & 4 & 2 & 1\\
\end{array}\right)
\left (\begin{array}{ccc}
x_1 & y_1 & z_1 \\
x_2 & y_2 & z_2\\
x_3 & y_3 & z_3\\
x_4 & y_4 & z_4\\
\end{array}\right)=\left (\begin{array}{ccc}
1 & 0 & 0 \\ 
0 & 1 & 0  \\ 
0 & 0 & 1 \\
\end{array}\right) 
$$

que puede parecer complicado, son $12$ incógnitas, pero realmente no se mezclan (por eso las  he designado con letras distintas).
El primer sistema será el que corresponde a las $x$'s:

$$\left(\begin{array}{cccc}
2 & 1 & 3 & 0 \\ 1 & 2 & 1 & 1 \\ 3 & 4 & 2 & 1\\
\end{array}\right)
\left (\begin{array}{c}
x_1 \\
x_2 \\
x_3 \\
x_4\\
\end{array}\right)=\left (\begin{array}{c}
1 \\ 
0   \\ 
0  \\
\end{array}\right) 
$$

con matriz ampliada

$$\left(\begin{array}{cccc|c}
2 & 1 & 3 & 0 & 1\\ 1 & 2 & 1 & 1 & 0 \\ 3 & 4 & 2 & 1 & 0\\
\end{array}\right)$$

y las correspondientes a los sistemas para las $y$'s y las $z$'s:

$$\left(\begin{array}{cccc|c}
2 & 1 & 3 & 0 & 0\\ 1 & 2 & 1 & 1 & 1 \\ 3 & 4 & 2 & 1 & 0\\
\end{array}\right) \hspace{1cm} \left(\begin{array}{cccc|c}
2 & 1 & 3 & 0 & 0\\ 1 & 2 & 1 & 1 & 0 \\ 3 & 4 & 2 & 1 & 1\\
\end{array}\right).$$

Como se resuelven haciendo o.e. por filas sobre la matriz de coeficientes, los tres pueden resolverse simultáneamente utilizando la matriz:

$$\left(\begin{array}{cccc|ccc}
2 & 1 & 3 & 0 & 1 & 0 & 0\\ 1 & 2 & 1 & 1 & 0 & 1 & 0 \\ 3 & 4 & 2 & 1 & 0 & 0 & 1\\
\end{array}\right)$$

que incluye las tres columnas de términos independientes.

Utilizamos el método de Gauss-Jordan:

$$\left(\begin{array}{cccc|ccc}
2 & 1 & 3 & 0 & 1 & 0 & 0\\ \boxed{1} & 2 & 1 & 1 & 0 & 1 & 0 \\ 3 & 4 & 2 & 1 & 0 & 0 & 1\\
\end{array}\right)\sim_f 
\left(\begin{array}{cccc|ccc}
\boxed{1} & 2 & 1 & 1 & 0 & 1 & 0 \\ 
0 & 2 & 1 & 3 & 1 & 3 & 0\\ 
0 & 0 & 0 & 1 & 1 & 0 & 1\\
\end{array}\right)\sim_f
$$

$$
\sim_f 
\left(\begin{array}{cccc|ccc}
\boxed{1} & 2 & 1 & 1 & 0 & 1 & 0 \\ 
0 & \boxed{1} & 3 & 4 & 3 & 4 & 0\\ 
0 & 0 & 0 & 1 & 1 & 0 & 1\\
\end{array}\right)\sim_f
\left(\begin{array}{cccc|ccc}
\boxed{1} & 0 & 0 & 3 & 4 & 3 & 0 \\ 
0 & \boxed{1} & 3 & 4 & 3 & 4 & 0\\ 
0 & 0 & 0 & \boxed{1} & 1 & 0 & 1\\
\end{array}\right)\sim_f
$$

$$
\sim_f
\left(\begin{array}{cccc|ccc}
\boxed{1} & 0 & 0 & 0 & 1 & 3 & 2 \\ 
0 & \boxed{1} & 3 & 0 & 4 & 4 & 1\\ 
0 & 0 & 0 & \boxed{1} & 1 & 0 & 1\\
\end{array}\right).
$$

Eligiendo en cada caso la columna de términos independientes que corresponde tendremos la solución de los tres sistemas.
Por tanto la solución de cada uno de los sistemas es

$$
\begin{array}{|l|l|l}
x_1=1 & y_1= 3 & z_1=2\\ 
x_2=4+2\lambda_1 & y_2=4+2\lambda_2 & z_2=1+2\lambda_3\\
x_3=\lambda_1 & y_3=\lambda_2 &z_3=\lambda_3\\
x_4=1 & y_4=0 & z_4=1\\
\end{array} \hspace{.5cm} \lambda_1,\lambda_2,\lambda_3\in \mathbb{Z}_5.$$

Es decir, todas las matrices son de la forma:

$$\left(\begin{array}{ccc}
1 &  3 & 2\\ 
4+2\lambda_1 & 4+2\lambda_2 & 1+2\lambda_3\\
\lambda_1 & \lambda_2 &\lambda_3\\
1 & 0 & 1\\
\end{array}\right)\hspace{.5cm} \lambda_1,\lambda_2,\lambda_3\in \mathbb{Z}_5.$$

<li>$C$ tal que $C\cdot A = Id$.</li>
Si pensamos primero en el orden de $C$, debería ser


<table class="default">
  <tr>
    <td>$C$</td>
    <td>$\cdot A$</td>
    <td>$=I$</td>
  </tr>
  <tr>
    <td>$?\times 3$</td>
    <td>$3\times$ 4</td>
    <td>$3\times 3$</td>
  </tr>
</table>


entonces ?$=4$. 


El argumento más fácil de utilizar es posterior al momento en que nos encontramos en el desarrollo del tema. Se usa:
$$rg(A\cdot B)\leq mín\{rg(A),rg(B)\}$$
en este caso, por los órdenes de $A$ y $C$ su rango máximo posible es $3$, luego $rg(C\cdot A)\leq 3$ mientra que $rg(I_4)=4.$

También es posible plantearlo de una forma similar al apartado 2, al resolver los sistemas encontraremos que son incompatibles.
</ol>

</details>
</article>

<article>
Dado el sistema de ecuaciones con coeficientes en $\mathbb{Q}$
$$\left\{\begin{aligned} x - ay + (a+1)z & = 4, \\ ax + 2y + z & = -1. \end{aligned}\right.$$
Discútelo según los valores del parámetro $a$, y resuélvelo para $a=-1$.

<details>
<summary>Solución</summary>

En este tipo de ejercicio utilizaremos el Teorema de Rouché-Frobenius (TRF) junto a los distintos métodos para calcular el rango de una matriz.

En primer lugar escribimos la matriz ampliada del sistema

$$(A|b)=\left( \begin{array}{rcc|r}
1 & -a & a+1 & 4\\
a & 2 & 1 & -1
\end{array}\right).$$

Puesto que el orden de matriz de coeficientes es $2\times3$ y el de la ampliada $2\times4$, en el caso de que $rg(A)=2$, entonces $rg(A|b)=2$ (puesto que no puede haber más de dos pivotes, uno por fila) y usando TRF el sistema será C.I.. 
Puesto que el rango no cambia si realizamos cualquier o.e. por columnas, para calcular $rg(A)$ realizamos algunas, por ejemplo:
$${\small A=\left( \begin{array}{rcc}
1 & -a & a+1 \\
a & 2 & 1  
\end{array}\right) \sim_c \left( \begin{array}{rcc}
1 & -a & 1 \\
a & 2 & 3 
\end{array}\right) \sim_c \left( \begin{array}{rcc}
1 & -a & 0 \\
a & 2 & 3-a 
\end{array}\right) }.$$ 
Para el rango de esta matriz es muy fácil utilizar el cálculo de determinantes:
Si
$\begin{vmatrix}
1 & 0 \\
a & 3-a
\end{vmatrix}= 3-a \not = 0$ 
el rango de $A$ es dos.
(También se podría haber hecho en la matriz $A$ directamente, pero este determinante es muy sencillo de calcular y de determinar cuándo es distinto de $0$).<br>

Entonces tenemos que en todos los casos en los que $a\not = 3$ tendremos  $rg(A)=rg(A|b)=2< \text{ nº incóg.}$ y el sistema es C.I..<br>
Solo nos queda estudiar el caso $a=3$, para el que podemos proceder como en los ejercicios del comienzo del tema: 

$$(A|b)=\left( \begin{array}{rrr|r}
\boxed{1} & -3 & 4 & 4\\
3 & 2 & 1 & -1
\end{array}\right)\sim_f  \left( \begin{array}{rrr|r}
\boxed{1} & 0 & 1 & 5/11\\
0 & 1 & -1 & -13/11
\end{array}\right).$$

O bien, podemos volver a aplicar el TRF, en este caso observamos que tomando las dos primeras columnas de $A$ se tiene

$\begin{vmatrix}
1 & 3 \\
-3 & 2
\end{vmatrix}=2+9=11$ luego $rg(A)=2$ y el mismo razonamiento nos lleva a que también en este caso es C.I.. <br>

Solución: siempre es C.I. dependiendo de un parámetro.<br>

Para el caso $a=-1$ utilizamos G-J:
$$(A|b)=\left( \begin{array}{rrr|r}
\boxed{1} & 1 & 0 & 4\\
-1 & 2 & 1 & -1
\end{array}\right)\sim_f \left( \begin{array}{rrr|r}
\boxed{1} & 1 & 0 & 4\\
0 & 3 & 1 & 3
\end{array}\right)\sim_f \left( \begin{array}{rrr|r}
\boxed{1} & 1 & 0 & 4\\
0 & \boxed{1} & 1/3 & 1
\end{array}\right)\sim_f \left( \begin{array}{rrr|r}
\boxed{1} & 0 & -1/3 & 3\\
0 & \boxed{1} & 1/3 & 1
\end{array}\right).
$$

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(QQ,[[1,1,0],[-1,2,1]]) #matriz de coeficientes
b=vector(QQ,[4,-1]) #término independiente
Ab=A.augment(b,subdivide=True) #matriz aumentada
show(Ab,"~",Ab.rref())
</script>
</div>  

</details>
</article>

<article>
Calcula el rango de la siguiente matriz, con coeficientes en $\mathbb{Z}_3$, según los valores de los parámetros $a$ y $b$.
$$\begin{pmatrix} 1 & a & 0 & 1 \\ 2 & 1 & 1 & b \\ 0 & a & b & a+b \end{pmatrix}$$

<details>
<summary>Solución</summary>

El rango máximo posible de esta matriz es 3. Elegimos una submatriz cuadrada de orden 3 y calculamos su determinante. ¿Cuál?
Dos condiciones: que no se vea a ojo que vale 0 y que sea fácil de calcular.
Por ejemplo
$$
\begin{vmatrix}
1 & a & 0  \\ 2 & 1 & 1  \\ 0 & a & b 
\end{vmatrix}=_{
(C_2-aC_1 \rightarrow C_2)}= \begin{vmatrix}
1 & 0 & 0  \\ 2 & 1-2a & 1  \\ 0 & a & b 
\end{vmatrix}=(1-2a)b-a=(1+a)b+2a=2a+b+ab.
$$
¿Es fácil decidir cuándo es $0$ y cuándo no?
$\mathbb{Z}_3$ tiene una ventaja, $a$ y $b$ pueden tomar solo 3 valores posibles.

Podemos examinar todos los casos en una tabla de doble entrada, donde en cada casillero escribiremos el valor del determinante:
$$det(A)=b(1-2a)-a=2a+b+ab$$
con el paso previo:<br>

$a=0, det(A)= b$<br>
$a=1, det(A)= 2b+2$<br>
$a=2, det(A)= 1$<br>

<table class="default">
  <tr>
    <td>$_b \setminus  ^a$</td>
    <td>0</td>
    <td>1</td>
    <td>2</td>
  </tr>
  <tr>
    <td>0</td>
    <td>0</td>
    <td>2</td>
    <td>1</td>
  </tr>
  <tr>
    <td>1</td>
    <td>1</td>
    <td>1</td>
    <td>1</td>
  </tr>
  <tr>
    <td>2</td>
    <td>2</td>
    <td>0</td>
    <td>1</td>
  </tr>
</table>

De la observación de la tabla anterior deducimos que $rg(A)=3$ para 7 de los 9 casos, siempre que el determinante es distinto de $0$.
Ahora, estudiamos los dos casos particulares que nos faltan:<br>

$a=0=b$<br>
$$
\begin{pmatrix}
1 & 0 & 0 & 1 \\ 2 & 1 & 1 & 0 \\ 0 & 0 & 0 & 0
\end{pmatrix}
$$
que tiene rango 2 puesto que hay una fila entera de ceros y en las otras dos se pueden hacer pivotes.<br>

$a=1, b=2$<br>
$$
\begin{pmatrix}
1 & 1 & 0 & 1 \\ 2 & 1 & 1 & 2 \\ 0 & 1 & 2 & 0
\end{pmatrix}\sim_f \begin{pmatrix}
1 & 1 & 0 & 1 \\ 0 & 2 & 1 & 0 \\ 0 & 1 & 2 & 0
\end{pmatrix}
$$
que también tiene rango 2 ¿porqué? Recordemos que estamos en $\mathbb{Z}_3$.

</details>
</article>

<article>
<ol type="a">
<li>Calcula el determinante de la matriz con coeficientes en $\mathbb{Q}$:</li>
$$A=\left( \begin{array}{cccc} 3-\lambda & 1 & 1 & 0\\ 5 &-\lambda & 0 & 0\\ 0 & -\lambda & -\lambda & 1\\ 0 & -1 & -1 & 2-\lambda \end{array}\right).$$
<li>Calcula el rango de la matriz $A$ según los valores de $\lambda$ considerando sus coeficientes en $\mathbb{Z}_3$.</li>
<li>Discute el sistema de ecuaciones con matriz ampliada $A$ considerando sus coeficientes en $\mathbb{Q}$.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">
<li>Determinante.</li>
Para calcular el determinante más fácilmente realizamos una operación elemental de tipo 3: a la segunda columna le restamos la tercera

$$|A|=\left| \begin{array}{cccc}
3-\lambda & 1 & 1 & 0\\
5 &-\lambda & 0 & 0\\
0 & -\lambda & -\lambda & 1\\
0 & -1 & -1 & 2-\lambda 
\end{array}\right|=\left| \begin{array}{cccc}
3-\lambda & 0 & 1 & 0\\
5 &-\lambda & 0 & 0\\
0 & 0 & -\lambda & 1\\
0 & 0 & -1 & 2-\lambda 
\end{array}\right|=(-\lambda)\left| \begin{array}{ccc}
3-\lambda &  1 & 0\\
0 &  -\lambda & 1\\
0 &  -1 & 2-\lambda 
\end{array}\right|$$

donde hemos desarrollado por la segunda columna, y desarrollando ahora por la primera columna
$$|A|=(-\lambda)(3-\lambda)[(-\lambda)(2-\lambda)+1]=(-\lambda)(3-\lambda)(\lambda -1)^2$$ 
y este resultado es válido en cualquier cuerpo.

<li>Rango.</li>
Puesto que el cálculo del determinante es válido en $\mathbb{Z}_3$, cuando $\lambda=2$ la matriz tiene rango 4 (observamos que $2$ no es raíz del polinomio que tenemos descompuesto en factores lineales, y por tanto el determinante es distinto de $0$); en cambio, para los casos $\lambda=0,1$ (que son raíces del polinomio obtenido) es menor o igual que 3. Para estos casos calculamos el rango mediante operaciones elementales:<br>

$\boxed{\lambda=0}$<br>
$$A=\left( \begin{array}{cccc}
0 & 1 & 1 & 0\\
2 &0 & 0 & 0\\
0 & 0 & 0 & 1\\
0 & 2 & 2 & 2 
\end{array}\right)\sim_{f}\left( \begin{array}{cccc}
0 & 1 & 1 & 0\\
1 &0 & 0 & 0\\
0 & 0 & 0 & 1\\
0 & 0 & 0 & 2 
\end{array}\right)\sim_{f}\left( \begin{array}{cccc}
1 & 0 & 0 & 0\\
0 &1 & 1 & 0\\
0 & 0 & 0 & 1\\
0 & 0 & 0 & 0 
\end{array}\right)$$ luego el rango es 3. <br>

$\boxed{\lambda=1}$<br>
$$A=\left( \begin{array}{cccc}
2 & 1 & 1 & 0\\
2 &2 & 0 & 0\\
0 & 2 & 2 & 1\\
0 & 2 & 2 & 1 
\end{array}\right)\sim_{f}\left( \begin{array}{cccc}
2 & 1 & 1 & 0\\
0 &1 & 2 & 0\\
0 & 2 & 2 & 1\\
0 & 0 & 0 & 0 
\end{array}\right)$$
que tiene rango 3.<br>

<li>Sistema de ecuaciones.</li>

Como la matriz ampliada tiene rango 4 para $\lambda\not = 0,1,3$, y la de coeficientes solo tiene tres columnas y por tanto el rango máximo es 3, en estos casos el sistema es incompatible. Nos queda estudiar los casos particulares $\lambda=0,1,3$:<br>

$\boxed{\lambda=0}$
$$\left( \begin{array}{ccc|c}
3 & 1 & 1 & 0\\
5 & 0 & 0 & 0\\
0 & 0 & 0 & 1\\
0 & -1 & -1 & 2 
\end{array}\right).$$

Como aparece la ecuación $0=1$ entonces también es incompatible.<br>

$\boxed{\lambda=1}$
$$\left( \begin{array}{ccc|c}
2 & 1 & 1 & 0\\
5 & -1 & 0 & 0\\
0 & -1 & -1 & 1\\
0 & -1 & -1 & 1 
\end{array}\right)\sim_{f}\left( \begin{array}{ccc|c}
2 & 0 & 0 & 1\\
5 & -1 & 0 & 0\\
0 & -1 & -1 & 1\\
0 & 0 & 0 & 0 
\end{array}\right)$$

en este caso la matriz de coeficientes tiene rango 3, y por tanto el sistema es compatible determinado.<br>

$\boxed{\lambda=3}$
$$\left( \begin{array}{ccc|c}
0 & 1 & 1 & 0\\
5 & -3 & 0 & 0\\
0 & -3 & -3 & 1\\
0 & -1 & -1 & -1 
\end{array}\right)\sim_{f}\left( \begin{array}{ccc|c}
0 & 1 & 1 & 0\\
5 & -3 & 0 & 0\\
0 & -3 & -3 & 1\\
0 & 0 & 0 & -1 
\end{array}\right)$$

y de nuevo aparece la ecuación $0=1$ con lo que en este caso es incompatible.
</ol>

</details>
</article>

<article>
<ol type="a">
<li>Calcula el determinante de la matriz $A\in \mathcal{M}_4(\mathbb{R})$:
$$A=\left(\begin{array}{rccc} 1 & 1 & 1 & 0\\ a & a-1 & a & 1\\ 1 & 1 & 1 & a-1\\ 1 & a & 0 & 0  \end{array}\right).$$</li>
<li>Calcula el rango de $A$ según los valores de $a$.</li>
<li>Calcula la forma de Hermite por filas $A$ según los valores de $a$.</li>
<li>Discute el sistema de ecuaciones 
$$\left\{\begin{aligned} 
x+y+z&=0,\\
ax+(a-1)y+az&=1,\\
x+y+z&=a-1\\ 
x+ay&=0. 
\end{aligned}\right.$$
según los valores de $a$.</li>
</ol>

<details>
<summary>Solución</summary>

<ol type="a">

<li>Determinante</li>
$$|A|=\left|\begin{array}{rccc}
1 & 1 & 1 & 0\\
a & a-1 & a & 1\\
1 & 1 & 1 & a-1\\
1 & a & 0 & 0 
\end{array}\right|= \left|\begin{array}{rccc}
0 & 0 & 1 & 0\\
0 & -1 & a & 1\\
0 & 0 & 1 & a-1\\
1 & a & 0 & 0 
\end{array}\right|
$$
donde a la primera y a la segunda columnas le hemos restado la tercera. Ahora, desarrollando el determinante por la primera columna (y el de orden 3 que aparece de nuevo por su primera columna):
$$
|A|= (-1) \left|\begin{array}{ccc}
0 & 1 & 0\\
-1 & a & 1\\
0 & 1 & a-1\\
\end{array}\right|= (-1)^3 \left|\begin{array}{cc}
1 & 0\\
1 & a-1\\
\end{array}\right|=1-a.
$$

<li>Rango.</li>
Como $|A|=a-1$, si $a\not = 1$ el rango de $A$ es 4. Solo queda calcular el rango si $a=1$. Como después se pide calcular la forma de Hermite por filas, lo realizamos ahora:

$$A=\left(\begin{array}{rccc}
1 & 1 & 1 & 0\\
1 & 0 & 1 & 1\\
1 & 1 & 1 & 0\\
\mathbf{1} & 1 & 0 & 0 
\end{array}\right)\sim_f \left(\begin{array}{rccc}
0 & 0 & 1 & 0\\
0 & -1 & 1 & 1\\
0 & 0 & 1 & 0\\
\mathbf{1} & 1 & 0 & 0 
\end{array}\right)\sim_f \left(\begin{array}{rccc}
\mathbf{1} & 1 & 0 & 0 \\
0 & 0 & \mathbf{1} & 0\\
0 & -1 & 1 & 1\\
0 & 0 & 1 & 0\\
\end{array}\right)\sim_f
$$

$$\sim_f  \left(\begin{array}{rccc}
\mathbf{1} & 1 & 0 & 0 \\
0 & 0 & \mathbf{1} & 0\\
0 & -1 & 0 & 1\\
0 & 0 & 0 & 0\\
\end{array}\right)\sim_f \left(\begin{array}{rccc}
\mathbf{1} & 0 & 0 & 1 \\
0 & \mathbf{1} & 0 & -1\\
0 & 0 & \mathbf{1} & 0\\
0 & 0 & 0 & 0\\
\end{array}\right).
$$

Así, si $a=1$ el rango es $3$.

Comprobemos el resultado obtenido con <code>sage</code>.

<div class="sage">
<script type="text/x-sage">
A=matrix(QQ,[[1,1,1,0],[1,0,1,1],[1,1,1,0],[1,1,0,0]]) #matriz de coeficientes
show(A,"~",A.rref())
</script>
</div>  

<li>Forma de Hermite por filas.</li>
Cuando $a\not = 1$ como el rango es $4$, la forma de Hermite por filas es $I_4$, para $a=1$ es la calculada en el apartado anterior.

<li>Discusión del sistema.</li>
Como la matriz ampliada del sistema es $A$, entonces cuando $a\not = 1$ la matriz ampliada tiene rango 4 mientras que la de coeficientes como máximo podría tener rango 3, así que el sistema es incompatible; en el caso $a=1$, usando la forma de Hermite por filas de $A$ que hemos calculado observamos que el sistema es compatible determinado.
</ol>

</details>
</article>