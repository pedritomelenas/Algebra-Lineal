---
layout: page
title: Problemas aplicaciones lineales
tag: problemas
---
<style>
@media (min-width: 38em) {
  html {
    font-size: 18px;
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

# Aplicaciones lineales

Los ejercicios aquí mostrados han sido amablemente proporcionados por [Evangelina Santos](https://www.ugr.es/~esantos/) y maquetados por [Juan Rivas](https://github.com/MrRiversGit).

## Ejercicios resueltos 

<article>
Determina cuáles de las siguientes aplicaciones son lineales:

<ol type="a">
<li>La aplicación $f:(\mathbb{Z}_3)^2 \rightarrow (\mathbb{Z}_3)^2$, $f(x,y)=(x+1,y+2)$.</li>
<li>La aplicación $f:V \rightarrow V'$, $f(v)=0$.</li>
<li>La aplicación $f:\mathbb{R} \rightarrow \mathbb{R}$, $f(r)=r^2$.</li>
<li>La aplicación $f:(\mathbb{Z}_7)^3 \rightarrow (\mathbb{Z}_7)^2$, $f(x,y,z)=(x+y+z,28x+92z)$.</li>

</ol>
<details>
<summary>Solución</summary>

<ol type="a">
<li>La aplicación $f:(\mathbb{Z}_3)^2 \rightarrow (\mathbb{Z}_3)^2$, $f(x,y)=(x+1,y+2)$.<br>

No es aplicación lineal. Basta tomar $u=(1,0)$ y $a=2$ y comprobar que no se cumple la segunda propiedad:
$$f(au)=f(2,0)=(0,2),$$
mientras que, 
$$af(u)=2(2,2)=(1,1).$$</li>

<li>La aplicación $f:V \rightarrow V'$, $f(v)=0$.<br>

Es aplicación lineal:<br>
Para cualesquiera $u,v$ se tiene $f(u+v)=0=0+0=f(u)+f(v)$.<br>
Para todo $u$ y todo $a$ se verifica $f(au)=0=a\cdot 0=af(u)$.</li>

<li>La aplicación $f:\mathbb{R} \rightarrow \mathbb{R}$, $f(r)=r^2$.<br>

No es lineal, tomamos $u=1$ y $a=2$ y comprobamos que no se cumple la segunda propiedad de aplicación lineal:
$$af(u)=2\cdot 1^2,$$
$$f(au)=f(2)=2^2.$$</li>

<li>La aplicación $f:(\mathbb{Z}_7)^3 \rightarrow (\mathbb{Z}_7)^2$, $f(x,y,z)=(x+y+z,28x+92z)$.<br>

Es aplicación lineal. Cada componente de la imagen se calcula como una combinación lineal de las componentes del vector inicial.</li>

</ol>
</details>
</article>

<article>
Prueba que la siguiente aplicación es lineal y calcula la matriz asociada considerando las bases estándar en cada espacio vectorial.
$$D:\mathbb{R}_3[x] \to \mathbb{R}_3[x] \text{ dada por } D(p(x))=p'(x).$$

<details>
<summary>Solución</summary>

Es conocido que la derivada tiene las propiedades:

<ol type="a">
<li>La derivada de una suma es la suma de las derivadas.<br>
Es decir, dadas dos funciones (derivables, y los polinomios lo son) $f$ y $g$ se verifica
$$D(f+g)=D(f)+D(g),$$
que es la primera propiedad que debe verificar una aplicación lineal. Hay que tener cuidado porque aquí $f$ y $g$ son los vectores y $D$ es la aplicación.</li>
<li>La derivada de una constante por una función es la constante por la derivada de la función.<br>
Es deir, dadas $f$ (derivable) y $a\in \mathbb{R}$ entonces
$$D(af)=aD(f),$$
que es la segunda propiedad de aplicación lineal.</li>
</ol>

Calculemos ahora la matriz asociada a $D$ utilizando la base de $\mathbb{R}_3[x]$ (el conjunto de los polinomios con coeficientes en $\mathbb{R}$ de grado menor o igual que tres), $B_s=\{1,x,x^2,x^3\}$ en el espacio inicial y en el final, puesto que son el mismo:
$$D(1)=0=(0,0,0,0)_{B_s},$$
donde el primer cero representa a la derivada del polinomio constante igual a uno, que es el polinomio constante igual a cero, cuyas coordenadas en la base $B_s$ son $(0,0,0,0)$.
Procedemos de la misma forma con los otros tres vectores de la base:
$$\begin{array}{l}
D(x)=1=(1,0,0,0)_{B_s},\\
D(x^2)=2x=(0,2,0,0)_{B_s},\\
D(x^3)=3x^2=(0,0,3,0)_{B_s}.
\end{array}
$$
Así que la matriz asociada resulta de poner estas coordenadas por columnas:
$$M_{B_sB_s}(D)=\begin{pmatrix}
0 & 1 & 0 & 0\\
0 & 0 & 2 & 0\\
0 & 0 & 0 & 3\\
0 & 0 & 0 & 0 
\end{pmatrix}.$$

</details>
</article>