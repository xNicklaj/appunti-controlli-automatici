# Equilibrio di un sistema dinamico
Un sistema dinamico si dice in equilibrio quando, dato il movimento dello stato, questo non cambia quando gli ingressi sono costanti. Ne consegue, che anche l'uscita del sistema sarà costante. si definisce il punto di equilibrio $(\overline{x}, \overline{u})$.

## Valutazione di un punto di equilibrio per sistemi LTI-TC
Dato un sistema LTI descritto tramite lo stato $\dot{x} = Ax + Bu$ e l'uscita $y = Cx + Du$, avendo compreso che nel punto di equilibrio, non vi è cambiamento dello stato, allora si ha che $\dot{x} = 0$. Quindi si può trovare il punto di equilibrio a partire dalla derivata di x.

Nel caso specifico degli LTI-TC, si ha quindi che, se e **solo se** A è invertibile (determinante di A diverso da 0), allora $\overline{x} = -A^{-1}B\overline{u}$ e $\overline{y} = (-CA^{-1}B + D)\overline{u}$. Se non è invertibile allora possono esserci infiniti punti di equilibrio, o nessuno.

## Valutazione di un punto di equilibrio per sistemi LTI-TD
Analogamente il discorso vale per il tempo discreto, ma invece di usare le differenziali, si utilizzano le equazioni alle differenze $x[k + 1] = x[k] = Ax[k] + Bx[k]$, e si trova il punto come $\overline{x} = (I_n - A)^{-1}B\overline{u}$ e $\overline{y} = (C(I_n - A)^{-1}B + D)\overline{u}$ se e solo se $(I_n - A)$ è **invertibile**.

## Linearizzazione
Per sistemi non lineari, è possibile scomporre lo stato e l'uscita del sistema in tanti piccoli intervalli lineari, approssimando tramite Taylor. Questo porta a definire delle matrici A, B, C e D particolari che possono approssimare un modello lineare. Si definiscono così:

- A è la Jacobiana di f(x, u) rispetto ad x
- B è la Jacobiana di f(x, u) rispetto ad u
- C è la Jacobiana di g(x, u) rispetto ad x
- D è la Jacobiana di g(x, u) rispetto ad u

| Funzione | x | u |
| -------- | -------- | -- |
| f(x, u) | $\begin{bmatrix}\frac{\partial f_1}{\partial x_1}&...&\frac{\partial f_1}{\partial x_n}\\...&...&...\\\frac{\partial f_n}{\partial x_1}&...&\frac{\partial f_n}{\partial x_n}\end{bmatrix}$ | $\begin{bmatrix}\frac{\partial f_1}{\partial u_1}&...&\frac{\partial f_1}{\partial u_n}\\...&...&...\\\frac{\partial f_n}{\partial u_1}&...&\frac{\partial f_n}{\partial u_n}\end{bmatrix}$ |
| g(x, u) | $\begin{bmatrix}\frac{\partial g_1}{\partial x_1}&...&\frac{\partial g_1}{\partial x_n}\\...&...&...\\\frac{\partial g_n}{\partial x_1}&...&\frac{\partial g_n}{\partial x_n}\end{bmatrix}$ | $\begin{bmatrix}\frac{\partial g_1}{\partial u_1}&...&\frac{\partial g_1}{\partial u_n}\\...&...&...\\\frac{\partial g_n}{\partial u_1}&...&\frac{\partial g_n}{\partial u_n}\end{bmatrix}$ |

Queste matrici contengono normalmente funzioni del tempo, ma se le si consideri nell'intorno dell'equilibrio, diventano invarianti e quindi dei numeri costanti.