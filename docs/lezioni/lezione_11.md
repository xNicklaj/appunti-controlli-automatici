# Stabilità
Un sistema si dice stabile se è poco sensibile a perturbazioni sullo stato iniziale.
Considerando $Y(s) = H_o x_{0_-} + H(s)U(s)$, dove il primo termine è la risposta libera e la seconda quella forzata, si suddivide la stabilità in interna ed esterna esaminando le due risposte separatamente.

## Stabilità interna
Si parla di stabilità interna quando non esiste uno stato iniziale degenere per cui la risposta libera è instabile.

Per determinare la stabilità interna si analizzano gli autovalori di A, tramite le seguenti condizioni di stabilità applicate a tutti gli autovalori:

| Tempo continuo | Tempo Discreto |
| --- | --- |
| $Re(autovalore) < 0$ | \| autovalore \| < 1 |

Si possono usare degli altri criteri per determinare la stabilità interna anche avendo soltanto la matrice di trasferimento.

Nel caso di tempo continuo si possono usare:

- Criterio di cartesio
- Criterio di Routh-Harwitz

Nel caso di tempo discreto invece si possono suare

- 3 disequazioni strane
- Criterio di Jury

### Criterio di cartesio
Dato $H(s) = \frac{N(s)}{D(s)}$, il cui grado del denominatore è minore o uguale a due, allora si può usare anche solo il criterio di cartesio.

Dato $D(s) = as^2 + bs + c$, il numero di variazioni di segno tra a, b e c costitiuisce il numero massimo di radici reali positive di D(s) o questo stesso diminuito di un multiplo di 2. 

Se questo è zero, ovvero a, b e c sono tutti concordi, il numero di radici reali positive è zero, quindi è stabile.

La stessa regola, applicata a D(-s), indica il numero massimo di radici reali negative.


### Criterio di Routh-Harwitz
Dato $H(s) = \frac{N(s)}{D(s)}$, il cui grado del denominatore è maggiore di due, allora si devono usare sia cartesio che Routh.

![alt text](../img/lezione_11.md/image.png)

### Disequazioni strane
Dato $H(s) = \frac{N(s)}{D(s)}$, il cui grado del denominatore è minore o uguale a due, allora si può usare anche solo il criterio delle disequazioni strane.

Le tre disequazioni sono:

- $D(1) = 0$
- $(-1)^n D(-1) > 0$
- $|a_n| > |a_0|$

### Criterio di Jury

## Stabilità esterna
Si parla di stabilità esterna quando non esiste un ingresso degenere per cui la risposta forzata è instabile.

Per determinare la stabilità interna si analizzano i poli di H(s), tramite le seguenti condizioni di stabilità applicate a tutti i poli:

| Tempo continuo | Tempo Discreto |
| --- | --- |
| $Re(polo) < 0$ | \| polo \| < 1 |

!!! note

    Notare che i poli di H(s) sono un sottoinsieme degli autovalori di A. $Poles\{H(s)\} \in Eig\{A\}$.
    Si ha quindi l'implicazione che stabilità interna implica stabilità esterna, ma non viceversa.