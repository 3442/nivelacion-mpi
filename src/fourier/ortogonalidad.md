# Ortogonalidad

## Espacios lineales

Inicialmente trataremos el caso de **especios vectoriales** conocidos con
vectores de la forma \\([ x_1, x_2, x_3, \ldots]^T\\). Esta idea será
generalizada a vectores abstractos, definidos por varias condiciones de
linealidad que no son relevantes para la discusión. Estos vectores pueden
**combinarse linealmente** para producir otro vector:
\\[\mathbf{x} = c_1\mathbf{u_1} + c_2\mathbf{u_2} + \ldots\\]

Trataremos conjuntos de vectores \\(\\{ \mathbf{u} \\}\\) **linealmente
independientes**, es decir, que no pueden reescribirse uno en términos del
otro.

Intuitivamente, una **base** de un espacio vectorial es un conjunto de vectores
linealmente independientes tal que cualquier vector en el espacio vectorial
puede representarse como una combinación lineal de una serie de coeficientes
con esta base. Por ejemplo, el vector \\((2, 3, 4)\\) en \\(\mathbb{R}^3\\)
puede engenendarse de esta manera con la **base canónica** \\(\\{(1, 0, 0), (0,
1, 0), (0, 0, 1)\\}\\):
\\[(2, 3, 4) = 2\cdot(1, 0, 0) + 3\cdot(0, 1, 0) + 4\cdot(0, 0, 1)\\]

## Operaciones dentro de espacios

Algunas operaciones de interés que pueden definirse para un espacio lineal son:

- La **métrica**: en vectores euclídeos es la "distancia geométrica" entre dos
  puntos.
  \\[d : \mathbb{V}\times\mathbb{V}\to \mathbb{R}\\]
  Por ejemplo, la métrica en \\(\mathbb{R}^2\\) es
  \\[d(\mathbf{u}, \mathbf{v}) = \\|\mathbf{u} - \mathbf{v}\\|\\]

- La **norma**: generaliza la idea de "magnitud".
  \\[\\|\mathbf{u}\\| : \mathbb{V}\to\mathbb{R}\\]
  Para los espacios euclídeos, esto es simplemente \\(\sqrt{x_1^2 + x_2^2 + \ldots}\\).

- El **producto interno**: generaliza al producto punto. Determina "cuánto" de un
  vector hay en otro vector, lo cual está muy asociado al ángulo entre vectores.
  \\[\langle\mathbf{u}, \mathbf{v}\rangle : \mathbb{V}\times\mathbb{V}\to\mathbb{F}\\]
  En cualquier espacio con producto interno, se puede reexpresar la norma como
  \\[\langle\mathbf{u}, \mathbf{u}\rangle = \\|\mathbf{u}\\|^2\\]

- El **ángulo**: también es una generalización. Siempre se cumple que:
  \\[\cos(\angle(\mathbf{u}, \mathbf{v})) = \frac{\langle\mathbf{u}, \mathbf{v}\rangle}{\\|\mathbf{u}\\|\\|\mathbf{v}\\|}\\]

Por tanto, dos vectores son **ortogonales** (perpendiculares) si el ángulo entre ellos es de \\(90^{\circ}\\), lo cual se cumple si el producto interno es cero.

## Espacios funcionales

Intuitivamente, podemos entender a una función como un **vector funcional**
que tiene tantas dimensiones como permite su dominio. Por ejemplo, si definimos
una función \\(f(n)\\) bajo el dominio \\(\\{1, 2, 3\\}\\) como:
\\[f(n) = \\begin{cases}1;&x = 1\\\\2;&x = 2\\\\1;&x = 3\\end{cases}\\]

Entonces, *solo dentro de este dominio*, puede decirse que \\(f(n)\\) corresponde
al vector \\([1, 2, 1]^T\\). Si hablamos ahora de una función \\(f(n) : \mathbb{N}
\to \mathbb{N}\\) dada por:
\\[f(n) = \frac{n(n + 1)}{2}\\]

Entonces obtenemos respectivamente un vector cuya enésima dimensión es el enésimo
natural, es decir, un vector de **infinitas dimensiones**. El vector funcional
será ahora \\([0, 1, 3, 6, 10, 15, \ldots]^T\\). Si se define una función sobre los
enteros, \\(f(n) : \mathbb{Z}\to\mathbb{Z}\\):
\\[f(n) = (-1)^n n^2\\]

Entonces una vez más se tiene un vector funcional de infinitas dimensiones,
pero ahora no existe una "primera" dimensión. El vector será \\([\ldots, 4, -1, 0,
-1, 4, \ldots]^T\\).

Tómese finalmente a una función real,
\\[f(x) = e^x\\]

Ya no podemos expresar el vector funcional utilizando notación matricial, ya
que el vector funcional es ahora **continuo** y no discreto. Por ejemplo, la
dimensión \\(\sqrt{2}\\) del vector \\(f(x)\\) es \\(e^{\sqrt{2}}\\). Sobra
decir que todo lo anterior se extiende también a los complejos. Extender a
vectores de infinitas y continuas dimensiones lleva a que el producto interno es
ahora una integral definida para un intervalo \\([a, b]\\):
\\[\langle f(x), g(x)\rangle = \int_a^b{f^*(x)g(x)\mathrm{d}x}\\]

A partir de lo anterior se pueden expresar las demás operaciones. Por ejemplo,
la norma se vuelve:
\\[\\|f(x)\\| = \sqrt{\langle f(x), f(x)\rangle} = \sqrt{\int_a^b{|f(x)|^2\mathrm{d}x}}\\]

El **ángulo entre dos funciones** es exactamente igual que para otros espacios:
\\[\cos(\angle(f(x), g(x))) = \frac{\langle f(x), g(x)\rangle}{\\|f(x)\\|\\|g(x)\\|}\\]

Esto quiere decir que **dos funciones son ortogonales** en un intervalo \\([a,
b]\\) (posiblemente todo \\(\mathbb{R}\\)) si su producto interno es cero.
Entonces, es posible conformar una **base funcional ortogonal** que es capaz de
**sintetizar** cualquier función en el dominio dado a través de una combinación
lineal.
