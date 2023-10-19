**CIENCIA DE DATOS**
#PROYECTO II
##Integrantes:
Julio César Cerón Hernández (CH14018)
Kevin Hernan Hercules Orellana (HO15000)

**Ejercicio matemático
** Sea $u:\Omega \cup \partial \Omega \to \mathbb{R}$ una función que es de clase $C^{2}$ en $\Omega$. Supongamos que $p \in \Omega$ es un punto de $\Omega$ y que la bola cerrada $B_{\rho}=B_{\rho}(p)$ de radio $\rho$ centrada en $p$ está contenida en $\Omega$ para $0 < \rho \leq R$. Definimos $I(\rho)$ mediante la fórmula.
$$I(\rho)= \dfrac{1}{\rho} \int_{\partial B_{\rho}} u ~ds$$
Demuestre que $\lim\limits_{\rho \to 0} I(\rho)=2\pi u(p).$}

**Solución
Para este ejercicio ocuparemos el siguiente resultado:
$\textbf{Teorema 1.}$ Supongamos que $f_{n} \to f$ uniformemente en un intervalo $[a,b]$ y que cada función $f_{n}$ es continua en $[a,b]$, definamos una sucesión $\{ g_{n} \}$ mediante
$$g_{n}= \int_{a}^{x} f_{n}(t) ~ dt \qquad \text{si $x \in [a,b]$,}$$
y pongamos 
$$g(x)= \int_{a}^{x} f(t) ~ dt.$$
Entonces $g_{n} \to g$ uniformemente en $[a,b]$. Simbólicamente, tenemos
$$\lim_{n \to \infty} \int_{a}^{x} f_{n}(t) ~ dt = \int_{a}^{x} \lim_{n \to \infty} f_{n}(t) ~ dt.$$\\
Este resultado se demuestra en el libro (Tom M. Apostol. Calculo con funciones de una variable, con una introducción al algebra lineal. Volumen I, segunda edición. Capítulo 11, pág 425. )

Siguiendo con la solución del problema, tenemos que 
$$B_{\rho}=B_{\rho}(p)$$
es una bola cerrada contenida en $\Omega \subset \mathbb{R}^{2}$, entonces
$$B_{\rho}= B_{\rho}(p) \subset \mathbb{R}^{2}$$

con lo cual $\partial B_{\rho}$ es una circunferencia en $\mathbb{R}^{2}$. Entonces su ecuación es
$$(x-h)^{2}+(y-k)^{2}= \rho ^{2}$$
donde  $p=(h,k) \in \Omega$ es el centro de la circunferencia. Sabemos que haciendo
$$x-h= \rho \cos(t) \Rightarrow x(t)=h+\rho \cos(t)$$
$$y-k= \rho \sen(t) \Rightarrow y(t)= k+ \rho \sen(t)$$

con lo cual tenemos que una parametrización de $\partial B_{\rho}$ es
$$\gamma(t)=(h+\rho \cos(t), k+ \rho \sin(t)), \quad 0 \leq t \leq 2\pi$$
Además
$$\gamma^{\prime}(t)=(- \rho \sin(t), \rho \cos(t)) $$

$$\Rightarrow ||\gamma^{\prime}(t)|| = \sqrt{(-\rho \sin(t))^{2}+(\rho \cos(t))^{2}} = \rho \sqrt{\sen^{2}(t)+\cos^{2}(t)}= \rho$$

Entonces tenemos

$$\begin{align*}
  \int_{\partial B_{\rho}} u ~ ds &= \int_{0}^{2\pi} u(\gamma(t)) ||\gamma^{\prime}(t)|| ~ dt\\
  &= \int_{0}^{2\pi} u(\gamma(t)) \rho ~ dt\\
  &= \rho \int_{0}^{2\pi} u(\gamma(t)) ~ dt.
\end{align*}$$


Con lo cual
$$\begin{align*}
    \lim_{\rho \to 0} I(\rho)&= \lim_{\rho \to 0} \dfrac{1}{\rho} \int_{\partial B_{\rho}} u ~ ds\\
    &= \lim_{\rho \to 0} \dfrac{\rho}{\rho} \int_{0}^{2\pi} u(\gamma(t)) ~ dt \hspace{4cm} \text{(sustituyendo $\int_{\partial B_{\rho}} u ~ ds$) }\\
    &= \lim_{\rho \to 0} \int_{0}^{2\pi} u(\gamma(t)) ~ dt\\
    &=  \int_{0}^{2\pi} \lim_{\rho \to 0} u(\gamma(t)) ~ dt\\
    &= \int_{0}^{2\pi} \lim_{\rho \to 0} u(h+\rho \cos(t), k+ \rho \sin(t)) ~ dt\\
    &= \int_{0}^{2\pi} u(h,k) ~ dt \hspace{5cm} \text{ (ya que $u$ es de clase $C^{2}$)}\\
    &= \int_{0}^{2\pi} u(p) ~ dt\\
    &= u(p) \int_{0}^{2\pi} ~ dt= 2\pi u(p).
\end{align*}$$

por lo tanto 
$$\lim_{\rho \to 0} I(\rho)= 2\pi u(p).$$
que es lo que queriamos demostrar.
