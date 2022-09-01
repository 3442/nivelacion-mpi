# Aplicaciones de las transformadas integrales

## ¿Por qué utilizar Fourier si existe Laplace?

La transformada de Fourier puede parecer obsoleta, puesto que las transformadas
de Laplace son más generales y ergonómicas. Por razones históricas, el término
"transformada de Laplace" va casi siempre asociado a la transformada
unilateral, a pesar de que en la sección anterior se dijo que la versión
completa es la forma bilateral. En la práctica, esta interpretación histórica
es siempre utilizada. Laplace desarrolló la transformada unilateral, la
bilateral fue una extensión posterior. Como resultado de esto, las herramientas
de análisis usuales son:

- Sistemas acausales y estudio de frecuencias implican Fourier. Por esta razón,
  se le encuentra frecuentemente en teoría de audio y vídeo, técnicas de
  transmisión analógica, algoritmos de compresión, etc. La interpretación
  espectral solo existe para \\(\sigma = 0\\), por lo cual sigue siendo
  necesaria la transformada de Fourier. La transformada bilateral no es de uso
  común; en vez de ella se utiliza Fourier, posiblemente con una exponencial
  adjunta para corrección de convergencia.

- La solución de ecuaciones diferenciales ordinarias, generalmente originadas
  de sistemas físicos y por tanto causales, es el fuerte de la transformada
  unilateral o transformada convencional de Laplace.

## Solución de ecuaciones diferenciales

La transformada unilateral permite resolver ecuaciones diferenciales con
relativa facilidad. Recordarse que deben establecerse condiciones iniciales.

\\[
\begin{align*}
4y' &= 2y'' + 2y - \delta(t - 2) \\\\
\implies 4\mathcal{L_u}\\{y'\\} &= 2\mathcal{L_u}\\{y''\\} + 2\mathcal{L_u}\\{y\\} - \mathcal{L_u}\\{\delta(t - 2)\\} \\\\
\implies 4sY_u(s) - y(0) &= 2(s(sY_u(s) - y(0)) - y'(0)) + 2Y_u(s) - e^{-2s} \\\\
\implies 4sY_u(s) &= 2s²Y_u(s) + 2Y_u(s) - e^{-2s} \\\\
\implies (2s² - 4s + 2)Y_u(s) &= e^{-2s} \\\\
\implies Y_u(s) &= e^{-2s}\cdot\frac{1}{2s^2 - 4s + 2} \\\\
&= \frac{e^{-2s}}{2}\frac{1}{(s - 1)^2} \\\\
\implies y(t) &= \frac{1}{2}\mathcal{L_u}^{-1}\left\\{e^{-2s}\cdot\frac{1}{(s - 1)^2}\right\\} \\\\
&= \frac{1}{2}\mathcal{L_u}^{-1}\left\\{\frac{1}{(s - 1)^2}\right\\}\vert_{t \mapsto t - 2} \\\\
&= \frac{1}{2}\left[\mathcal{L_u}^{-1}\left\\{\frac{1}{s^2}\right\\}e^t\right]\vert_{t \mapsto t - 2} \\\\
&= \frac{1}{2}\left[te^t u(t)\right]\vert_{t \mapsto t - 2} \\\\
&= \boxed{\frac{1}{2}(t - 2)e^{t - 2}u(t - 2)}
\end{align*}
\\]
