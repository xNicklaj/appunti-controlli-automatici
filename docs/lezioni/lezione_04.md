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

## Passaggio al dominio del tempo

Se il sistema è SISO la Matrice di trasferimento diventa una funzione di trasferimento $H(s) = \frac{N_H(s)}{D_H(s)} = \frac{b_ms^m + b_{m-1}s^{m-1}+...+b_1s + b_0}{s^n+a_{n-1}s^{n-1}+...+ a_1s +a_0}$ per ogni $m \le n$.

- Se m < n allora la fdt è propria, ovvero il sistema è proprio.
- Se m = n allora la fdt non è strettamente propria, il sistema è improprio.

La realizzabilità è data dal fatto che un sistema reale ha più poli che zeri, in quanto nessun sistema reale ha una banda infinita (I poli buttano giù la banda).

Un'altra rappresentazione è $H(s) = K_{\infty}\frac{(s-z_1)(s-z_2)...(s-z_m)}{(s-p_1)(s-p_2)...(s-p_n)}$.
Il coefficiente è il $K_{\infty} = \lim_{s\rightarrow \infty}s^{n-m}H(s)$. Questa rappresentazione è molto utile per avere ad occhio zeri e poli.

## Rappresentazione complessi
Date le radici complesse $s = \sigma_0 \pm j\omega_0$, queste si possono rappresentare come pulsazione naturale $\omega_n = \sqrt{\sigma_0^2 + \omega_0^2}$ e smorzamento $\zeta = sin(\theta)$

NOTA IMPORTANTE: $\theta$ è preso dall'asse y degli immaginari in senso antiorario.

Se si usa la rappresentazione di zeri e poli si trasforma $H(s) = K_\infty \frac{\Pi(s-z_i)\Pi(s^2 +2\zeta_{z_i})}{}$ DA COMPLETARE SLIDE 28.

## Esercizi
### Esercizio 1

$F(s) = \frac{b_ms^m + b_{m-1}s^{m-1}+...+b_1s + b_0}{s^n+a_{n-1}s^{n-1}+...+ a_1s +a_0}$ con più poli che zeri, e non ci sono zeri e poli in comune. Inoltre la funzione presenta solo poli **distinti**.

Si può fattorizzare come $F(s) = \frac{b_ms^m + b_{m-1}s^{m-1}+...+b_1s + b_0}{(s-p_1)(s-p_2)...(s-p_n)}$ e poi si scompone infratti semplici (sviluppo di Heaviside).

Se ipotizzo che tutti i poli sono distinti, allora $F(s) = \Sigma_{i = 1}^n\frac{R_i}{(s-p_i)}$. Dato che la trasformata di laplace è lineare, anche l'antitrasformata lo è e quindi è semplice antitrasformare.
Quindi si calcolano i residui come $R_i = lim_{s\to p_i}(s-p_i)F(s)$.

---

Considerando il sistema $\dot{x}(t) = \begin{bmatrix}0&1\\-2&3\end{bmatrix}x(t) + \begin{bmatrix}1\\0\end{bmatrix}u(t)$, con $x(0) = \begin{bmatrix}2\\2\end{bmatrix}$ e $U(s) = \frac{2}{s}$ si trova $X(s) = (sI-A)^{-1}x(0) + (sI-A)^{-1}BU(s)$. Il componente principale da saper fare è la matrice inversa:

$(sI-A)^{-1} = \frac{1}{det(SI-A)}Adj(sI-A)$[^1]

$Adj(sI-A)$ è la trasposta della matrice dei complementi algebrici di (sI - A).

[^1]: Matrice aggiunta di (sI - A)

Nel nostro caso $(sI- A)^{-1} = \begin{bmatrix}\begin{bmatrix}s&0\\0&s\end{bmatrix}-\begin{bmatrix}0&1\\-2&-3\end{bmatrix}\end{bmatrix}^{-1}$ $= \begin{bmatrix}s&-1\\2&s+3\end{bmatrix}^{-1}$ $= \frac{1}{s^2 + 3s + 2}\begin{bmatrix}s+3&-2\\1&s\end{bmatrix}^{T}$ $= \frac{1}{s^2 + 3s + 2}\begin{bmatrix}s+3&1\\-2&s\end{bmatrix}$ $=\begin{bmatrix}\frac{s+3}{s^2 + 3s + 2}&\frac{1}{s^2 + 3s + 2}\\\frac{-2}{s^2 + 3s + 2}&\frac{s}{s^2 + 3s + 2}\end{bmatrix}$.

!!!warning "Matrice aggiunta per matrici 2x2"
    
    SOLO per matrici 2x2 si calcola facilmente scambiando i termini sulla diagonale principale e cambiando di segno quelli sulla diagonale secondaria.

Quindi $X_l(s) = \begin{bmatrix}\frac{2s+8}{(s+1)(s+2)}\\\frac{2s-4}{(s+1)(s+2)}\end{bmatrix}$ e $X_f(s) = \begin{bmatrix}\frac{s+3}{(s+1)(s+2)}\\\frac{-2}{(s+1)(s+2)}\end{bmatrix}\cdot \frac{2}{s}$ $= \begin{bmatrix}\frac{s(s+3)}{s(s+1)(s+2)}\\\frac{-4}{s(s+1)(s+2)}\end{bmatrix}$.

Infine $X(s) = X_l(s) + X_f(s) = \begin{bmatrix}\frac{2s^2+10s+6}{s(s+1)(s+2)}\\\frac{2s^2-4s+4}{s(s+1)(s+2)}\end{bmatrix}$. Dunque si calcolano i residui:

- $R_1^(1) = lim_{s\to0}sX_1(s) = lim_{s\to 0}\frac{2s^2+10+6}{(s+1)(s+2)} = 3$
- $R_2^{1} = \lim_{s\to -1}\frac{2s^2 +10s +6}{s(s+2)} = -2$
- $R_3^{1} = \lim_{s\to -2}\frac{2s^2 +10s +6}{s(s+1)} = -3$

Quindi $X_1(s) = \frac{3}{s}+ \frac{2}{s+1}-\frac{3}{s+2}$.

Analogamente per $X_2$ si ha che $X_2(s) = -\frac{2}{s} - \frac{2}{s+1} + \frac{6}{s+2}$.

Ricordando che $L{\frac{R}{s-a}} = Re^{at}\epsilon(t)$ si antitrasforma come $x(t) = \begin{bmatrix}x_1(t)\\x_2(t)\end{bmatrix} = \begin{bmatrix}3+2e^{-t} -3e^{-2t}\\-2-2e^{-t}+6e^{-2t}\end{bmatrix}\epsilon(t)$.

Per il calcolo di residui con radici complesse coniugate, supponendo che $p_1$ e $p_2$ siano coniugati $R_1$ ed $R_2$ sono radici coniugate. Si può anche semplificare l'antitrasformata come $2|R_1|e^{\sigma_0t}cos(\omega_0 t + arg(R_1))\varepsilon(t)$, dove $|R_1| = \sqrt(Re^2{R_1} + Im^2(R_1))$ e $arg(R_1) = tan^{-1}\frac{Im(R_1)}{Re(R_1)}$.