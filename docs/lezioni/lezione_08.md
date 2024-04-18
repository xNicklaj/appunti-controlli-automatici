# Analisi Modale per sistemi dinamici LTI TC
Studio delle caratteristiche del movimento libero $x_l(t)$ di un sistema dinamico lineare tempo invariante e tempo continuo di ordine n descritto dall'equazione di stato $\dot{x}(t) = Ax(t)$.

Non essendovi la parte forzata, la forma della soluzione è $x_l(t) = e^{At}x(0_-)$.

## Esempio semplice
Supponendo la matrice A puramente diagonale, con n autovalori $\lambda_1,...,\lambda_n$ reali e distinti.

Dato un sistema con tre variabili di stato $x_1, x_2, x_3$, si ha che:

$$\begin{bmatrix}\dot{x_1}\\\dot{x_2}\\\dot{x_3}\end{bmatrix} = \begin{bmatrix}\lambda_1&0&0\\0&\lambda_2&0\\0&0&\lambda_3\end{bmatrix} \cdot \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}$$

Che si può riscrivere in forma di Lagrange:

$$\begin{bmatrix}x_1(t)\\x_2(t)\\x_3(t)\end{bmatrix} = \begin{bmatrix}e^{\lambda_1t}&0&0\\0&e^{\lambda_2t}&0\\0&0&e^{\lambda_3t}\end{bmatrix} \cdot \begin{bmatrix}x_1(0_-)\\x_2(0_-)\\x_3(0_-)\end{bmatrix}$$

I modi naturali sono quelli nella forma $e^{\lambda_it}$, ovvero quelle funzioni esponenziali associate agli autovalori.
## Introduzione

L'analisi modale è lo studio asintotico del comportamento dei modi naturali associati al sistema.

- Un modo si dice *convergente* se $\lim_{t\to\infty}|m(t)| = 0$, ed avviene quando $\lambda$ è minore di 0; 
- Un modo si dice *limitato* se $0 \le |m(t)| \le M \le \infty$, ed avviene quando $\lambda$ è uguale a 0;
- Un modo si dice *divergente* se $\lim_{t\to\infty}|m(t)| = \infty$, ed avviene quando $\lambda$ è maggiore di 0.

Si possono studiare le proprietà del movimento libero tramite la trasformazione di similarità $e^{At} = Te^{\overline{A}t}T^{-1}$, dove T è una matrice costante ed A è una matrice diagonale o diagonale a blocchi.  

![alt text](../img/lezione_08.md/image.png)

Per blocchi corrispondenti a coppie di autovalori complessi e coniugati del tipo $\lambda = \sigma \pm j\omega$, la matrice $\overline{A} = \begin{bmatrix}\sigma&\omega\\\omega&\sigma\end{bmatrix}$

## Calcolo autovalori di una matrice.
Se la matrice è diagonale o triangolare, gli autovalori sono sulla diagonale, perfettamente visibili senza effettuare operazioni, altrimenti,
per trovare gli autovalori di una matrice non diagonale, si usa il polinomio caratteristico, definito come il determinante di $A - \lambda I$:

$P_c = det\begin{bmatrix}A_{11} - \lambda&A_{12}&A_{13}\\A_{21}&A_{22} - \lambda&A_{23}\\A_{31}&A_{32}&A_{33}-\lambda\end{bmatrix} = 0$.

Per le matrici triangolari a blocchi o diagonali a blocchi, gli autovalori sono la combinazione degli autovalori dei blocchi sulla diagonale.


## Analisi per sistemi lineari a tempo continuo       
Avendo l'evoluzione dello stato $\dot{x} = Ax + Bu$, si realizza la matrice esponenziale come $e^{At}$. Questo però è molto oneroso computazionalmente, quindi si studia in alcuni casi specifici (diagonali a blocchi o triangolari a blocchi).

Una volta trovati gli autovalori, si considerano molteplicità e insieme degli autovalori.

### Reali e distinti
Il modo associato all'autovalore è $e^{\lambda t}$. Quindi passando allo studio della caratteristica dei modi, si ha che un modo è convergente, se l'autovalore associato al modo è minore di zero, viceversa, è divergente. Se l'autovalore è nullo, allora il modo è limitato.

In questo caso, le regole di divergenza per minore / maggiore di zero rimangono uguali, tuttavia il modo diverge anche se $\lambda$ è uguale a 0.

| Autovalore | Comportamento |
| ----- | ---- |
| < 0   | Convergente |
| 0     | Divergente |
| > 0   | Divergente |

### Reali e non distinti
In questo caso, considerando i $\mu^{'}$ autovalori associati a $\lambda$, si ha che il modo associato all'autovalore $(\lambda, \mu_i)$ è pari a $t^{\mu_i - 1}e^{\lambda t}$. Non è importante ricavare $\mu^{'}$, ma basta sapere che $\mu^{'} < \mu$ (molteplicità algebrica).



| Autovalore | Comportamento |
| ----- | ---- |
| < 0   | Convergente |
| 0     | Limitato |
| > 0   | Divergente |


### Complessi e distinti
In questo caso, l'autovalore si scrive come $\lambda = \sigma \pm j\omega$. Quindi per ogni coppia di autovalori vi è una coppia di modi associati, e si trovano come come $e^{\sigma t}cos(\omega t)$ e $e^{\sigma t}sin(\omega t)$.

In questo caso, se $\sigma$, ovvero la parte reale del numero complesso è minore di zero, allora il modo associato è *convergente*, e l'area del modo è contenuta all'interno dell'inviluppo, ovvero all'interno di $e^{\sigma t}$ (sup) e $e^{-\sigma t}$ (inf). Viceversa, se è maggiore di zero è *divergente*.

Se invece $\sigma$ è nullo, l'inviluppo è tra 1 e -1, e quindi il modo è un semplice seno / coseno tra 1 e -1 *oscillante*.

| Re{Autovalore} | Comportamento |
| ----- | ---- |
| < 0   | Convergente |
| 0     | Limitato |
| > 0   | Divergente |

### Complessi e non distinti
In questo caso, la forma della coppia di modi naturali che esce è $t^{\mu_i - 1}e^{\sigma t}cos(\omega t)$ e $t^{\mu_i - 1}e^{\sigma t}sin(\omega t)$.

| Autovalore | Comportamento |
| ----- | ---- |
| < 0   | Convergente |
| 0     | Divergente |
| > 0   | Divergente |

### Costante di tempo
Per i modi naturali a tempo continuo convergenti, si può definire la costante di tempo $\tau = \left|{\frac{1}{Re(\lambda)}}\right|$.

## Analisi per sistemi lineari a tempo discreto      
### Reali e distinti
In questo caso il modo naturale si scrive come $\lambda^k$

| Autovalore | Comportamento |
| ----- | ---- |
| \|$\lambda$\| < 1   | Convergente |
| \|$\lambda$\| = 1     | Limitato o alternato |
| \|$\lambda$\| > 1   | Divergente |

### Reali e non distinti
Come per il tempo continuo, si dovrebbe tenere in considerazione la molteplicità geometrica dell'autovalore, e si scrive il modo come $k^{\mu^{'}_i-1}\lambda^k$.

| Autovalore | Comportamento |
| ----- | ---- |
| \|$\lambda$\| < 1   | Convergente |
| \|$\lambda$\| = 1     | Divergente |
| \|$\lambda$\| > 1   | Divergente |

### Complessi e distinti
In questo caso si usa la scrittura modulo/fase per descrivere gli autovalori complessi $\lambda = \sigma \pm j\omega$ $=\upsilon e^{\pm j\theta}$. Dopo aver ricavato questa rappresentazione, si può trovare la coppia di modi come $\upsilon^kcos(\theta k)$ e $\upsilon^ksin(\theta k)$

| Autovalore | Comportamento |
| ----- | ---- |
| $\upsilon$ < 1   | Convergente |
| $\upsilon$ = 1     | Limitato o alternato |
| $\upsilon$ > 1   | Divergente |

### Complessi e non distinti
Come per il tempo continuo, si dovrebbe tenere in considerazione la molteplicità geometrica della coppia di autovalori complessi e coniugati, scrivendo la coppia di modi come $k^{\mu^{'}_i - 1}\upsilon^k cos(\theta k)$ e $k^{\mu^{'}_i - 1}\upsilon^k sin(\theta k)$.

| Autovalore | Comportamento |
| ----- | ---- |
| \|$\lambda$\| < 1   | Convergente |
| \|$\lambda$\| = 1     | Divergente |
| \|$\lambda$\| > 1   | Divergente |