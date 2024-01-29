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

</style>

# Matrices y sistemas de ecuaciones
## Ejercicios resueltos 

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
\end{array}\right)\sim_{f_1\leftrightarrow f_2} 
\left(\begin{array}{ccc|c}
\boxed{1} & 1 & -1 & 0\\
0 & 1 & -2 & -4\\
2 & -1 & 1 & 3
\end{array}\right).$$

Ahora utilizamos el pivote para hacer ceros debajo de él, por medio de una operación elemental del tipo: a la fila $j$ se le resta la fila uno multiplicada por el coeficiente $a_{j1}$. En este caso solo hay que realizarlo para la fila tes:

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

Comprobemos el resultado obtenido con `sage`.

<div class="sage">
<script type="text/x-sage">
A=matrix(QQ,[[0,1,-2,-4],[1,1,-1,0],[2,-1,1,3]])
show(A,"~",A.rref())
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
\end{array}\right)\sim_{f_1\leftrightarrow f_2}\left(\begin{array}{ccc|c}
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


Comprobemos el resultado obtenido con `sage`.

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
\end{aligned}\right\},\quad \lambda \in \mathbb{Z}_3.
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
\sim_{f_1\leftrightarrow f_2}\left(\begin{array}{ccc|c}
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

Comprobemos el resultado obtenido con `sage`.

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