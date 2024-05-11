# Movimento di sistemi dinamici LTI-TD
Nel caso di sistmei dinamici LTI-TC, si descrive x in funzione del tempo tramite la formula di Lagrange $x(t) = x_l(t) + x_f(t) = e^{At}x(0_-) + \int_{0_-}^t e^{A(t - \tau)}Bu(\tau)d\tau$, questo si traduce in tempo discreto come $x(k) = A^k x(0) + \Sigma_{i = 0}^{k-1} A^{k - i - 1}Bu(i)$, che però è difficile da usare, dunque si usa la trasformata Zeta per portare nel dominio della frequenza come:

$$\begin{cases}X(z) = z(zI - A)^{-1}x(0) + (zI - A)^{-1}BU(z)\\Y(z) = zC(zI - A)^{-1}x(0) + [C(zI-A)^{-1}B + D]U(z)\end{cases}$$
