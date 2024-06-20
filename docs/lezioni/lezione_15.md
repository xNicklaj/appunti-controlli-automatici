# Progettazione del controllore
Il controllore è composto da diverse reti.

## Guadagno di rete
Il primo pezzo del controllore è il guadagno $K_c$ che moltiplica tutte le altre reti.

## Tipologia di erorre
Si usano le tabelle degli errori per mettere tanti integratori quanti sono necessari per raggiungere la tipologia di errore richiesta.
Se Ga è di tipo h, il controllore può inseguire segnali di grado minore ad h con errore nullo, o di grado h con errore costante.

## Studio segno di Kc
Se il sistema è a stabilità regolare[^1], allora $K_c > 0$, altrimenti su deve usare Nyquist.

[^1]:
    Si ha stabilità regolare se il sistema non ha singolarità con parte reale maggiore di zero (minima rotazione di fase), se nel diagramma di bode del module viene attraversato 0 dB una volta sola e se nel diagramma di bode della fase si attraversa 180 gradi una volta sola (un solo margine di fase / guadagno).

## Conversione delle specifiche
Usando le specifiche richieste si deve arrivare ad avere la  $\omega_{\text{crossover, des}}$ e il margine di fase $M_\varphi$.

## Rete derivatrice (o anticipatrice)
La rete derivatrice consente di recuperare fase nel diagramma di Bode.

Funzione di rete: $\frac{1 + \tau_d \cdot s}{1 + \frac{\tau_d}{m_d}\cdot s}$, dove $m_d$ indica la curva da selezionare, mentre $\tau_d$ indica il punto di lavoro della curva. Si trova la costante di tempo come $\tau_d = \frac{X_d}{\omega_{c_\text{desiderata}}}$, se vuoi il massimo $X_d = \sqrt{m_d}$.

## Rete integratrice (o attenuatrice)
La rete integratrice consente di recuperare modulo nel diagramma di Bode.

Si prende il modulo $M_b$ sempre in $\omega_c$ che ora sarà aumentato leggermente e si converte in numeri naturali come $m_{i} = 10^{\frac{M_{dB}}{20}}$. Si trova la costante di tempo come $\tau_i = \frac{X_i}{\omega_{c_\text{desiderata}}}$.

Si cerca di contenere $m_i \approx 20$.

## Zero reale
Questa rete ti permette di recuperare fase con un aumento di modulo contenuto MA si può usare soltanto se nel controllore è stato inserito un integratore. La funzione di rete è $R_Z = 1 + \tau_Z\cdot s$. Come al solito $tau_z = \frac{X_z}{\omega_{c_\text{desiderata}}}$

!!!note 
    Se invece di avere $K_{F_i} hai $K_{G_i}$, allora $K{G_i} = \frac{K_{F_i}}{K_r}$.