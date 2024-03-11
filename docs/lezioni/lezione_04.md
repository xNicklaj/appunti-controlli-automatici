# Movimento di sistemi dinamici LTI
Il comporamento di un sistema dinamico LTI è dato dalle equazioni:

$x(t) = Ax(t) + Bu(t)$
$y(t) = Cx(t) + Du(t)$

L'espressione di x(t) si calcola coon la formula di Lagrange: $x(t) = e^{At}x(0_-) + \int_{0_-}^t e^{A(t - \tau)}Bu(\tau)d\tau$ $= x_l(t) + x_f(t)$.

La trasformata unilatera di Laplace vale $F(s) = L{f(t)} = \int_{0_-}^\inf f(t)e^{-st}dt$ dove la variabile $s = \sigma + j\omega$. Questa trasformata gode di properietà di linearità.

## Trasformate note
### Derivazione

### Integrazione

### Prodotto di convoluzione

### Trasformate note

| f(t) | (s) |
| ---- | --- |
| $\delta(t)$ | 1 |
| $\varepsilon(t)$ | $\frac{1}{s}$ |
| $\frac{t^n}{n!}$ | $\frac{1}{s^{n+1}}$ |

!!! note "Riguardo $\varepsilon$"

    $\varepsilon$ è il gradino unitario, quello che in altre materie si indica con u(t), ma essendo u(t) riservato all'uscita in questa materia, allora si usa $\varepsilon$.

!!! math "Rapporto tra gradino e delta"

    Il gradino è definito come l'integrale dell'impulso delta. 

## Schema della soluzione
Normalmente per risolvere il sistema si prendono le equazioni del dominio del tempo, si trasformano tramite la trasformata di Laplace (che semplifica i conti algebrici), si risolve e poi si riportano X(s) ed Y(s) nel dominio del tempo con l'antitrasformata.

Dati $\dot{x}(t) = Ax(t) + Bu(t)$ e $y(t) = Cx(t) + Du(t)$:

Si trasforma con laplace come: $L{\dot{x}(t)} = sX(s) - x(0) = AX(s) + BU(s)$. Dunque $sI_NX(s) - x_0 = AX(s) + BU(s)$ $\rightarrow sX(s) - AX(s)$ $= x_0 + BU(s)$ $\rightarrow (sI_N - A)X(s) = x_0 + BU(s)$ $\rightarrow X(s) = (sI_N - A)^{-1}x_0 + (sI_N - A)^{-1}BU(s)$.

- $x(t)$ è un vettore ad N righe, dunque lo è anche $X(s)$.
- A è una matrice quadrata.
- L'obbiettivo è trovare $X(s)$.
- La matrice inversa di $(sI_N - A)$ potrebbe non esistere. Affinché questa esista, il determinante di $(sI_N - A)$ dev'essere diverso da 0.
- Questa soluzione è corretta per tutti gli s diversi dagli autovalori di A.
- Secondo la formula di lagrange $x(t) = e^{At}x_0 + e^{At}*Bu(t)$.

Per y(t) si ha che $Y(s) = C(sI - A)^{-1}x(0_-) + [C(sI - A)^{-1}B + D] U(s)$ dove il primo termine è la risposta libera e il secondo termine è la riposta forzata.

- $C(sI-A)^{-1}B + D$ + chiamata matrice di trasferimento $H(s)$.

Nei sistemi MIMO (p ingressi e q entrate) inizialmente a riposo (ovvero in cui $x(0_-) = 0$) H(s) è nella forma:


$\begin{bmatrix}Y_1(s)\\...\\ Y_i(s)\\...\\ Y_q(s)\end{bmatrix} = \begin{bmatrix}H_{11} &...&H_{1j}(s)&...&H_{1p}(s)\\H_{i1} &...&H_{ij}(s)&...&H_{ip}(s)\\H_{q1} &...&H_{qj}(s)&...&H_{qp}(s)\end{bmatrix} \cdot \begin{bmatrix}U_1(s)\\ ... \\ U_j(s) \\ ... \\ U_p(s)\end{bmatrix}$

Dunque $H_{ij}(s) = \frac{Y_i(s)}{U_j(s)}$, ovvero il contributo del j-esimo ingresso sulla i-esima uscita (supponendo gli altri ingressi nulli).