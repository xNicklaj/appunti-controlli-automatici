# Classificazione
## Nozione di un sistema
Un **sistema** è un'interconnessione di più parti  elementari per cui vale il principo di **azione e reazione**. Si può identificare la relazione principiale come S(u) = y, con u variabile d'ingresso e y variabile d'uscita.

Possono esserci tre casistiche di problemi:

- Noti S ed u, trovare y
- Noti S ed y, trovare u
- Noti y ed u, trovare S

## Tipo di sistema
Un sistema **statico** è un sistema per cui l'uscita y dipende soltanto dallo stato istantaneo di u, e non dagli stati precedenti del sistema. 

Un sistema **dinamico** è un sistema per cui l'uscita y diipende non soltanto dallo stato istantaneo di u, ma anche dagli stati precedenti del sistema. In questo caso la relazione tra y ed u è $y(t) = g(x(\tau), u([\tau, t]))$, dove $x(\tau)$ racchiude la **memoria** del sistema.

## Classificazione dei sistemi dinamici

Un sistema dinamico si può caratterizzare tramite la *funzione di transizione dello stato $\varphi(t, \tau, X(\tau, u([\tau, t])))$[^1]* che ne rappresenta l'evoluzione temporale dello stato, e la *funzione di uscita $\eta(t, x(t), u(t))$[^2]* che rappresenta l'evoluzione temporale dell'uscita. Quest'ultima è una funzione statica dello stato ed eventualmente dell'ingresso, sebbene una funzione di uscita che dipende dallo stato non è fisicamente realizzabile.

I sistemi dinamici possono essere a tempo **continuo**, o a tempo **discreto** (in questo caso si usa k invece di t come variabile). Se i sistemi sono a tempo discreto, anche i rispettivi ingressi ed uscite sono a tempo discreto.

Se X assume valori contenuti in $R^n$ con n finito, il sistema si dice a **stati finiti**, altrimenti è a stati infiniti. Se X è un insieme discreto allora è a stati finiti.

Un sistema si dice **lineare** quando $\varphi$ è lineare in x ed u, e quando $\tau$ è lineare in x ed u.

Un sistema si dice **stazionario** (o invariante nel tempo) se né $\phi$ né $\tau$ dipendono dal tempo.



## Casi specifici

Riguardo i sistemi a tempo continuo, si possono evidenziare questi casi specifici:

- Per un sistema **dinamico**, a **dimensione finita**, e **tempo continuo**, X(t) è soluzione di un sistema di ^^equazioni differenziali^^ del I ordine[^3].
- Per un sistema **dinamico**, a **dimensione finita**, **tempo continuo** e **lineare**, l'evoluzione temporeale dello stato del sistema è descritta da un sistema di equazioni differenziali ^^lineari^^ in x(t) e u(t).
- Per un sistema **dinamico**, a **dimensione finita**, **tempo continuo** e **LTI**, l'evoluzione temporeale dello stato del sistema è descritta da un sistema di equazioni differenziali **lineari** in x(t) e u(t) ^^a coefficienti costanti^^.

Riguardo i sistemi a tempo discreto invece, questi sono dei casi particolari:

- Per un sistema **dinamico**, a **dimensione finita**, a **tempo discreto** l'evoluzione temporale dello stato è descritta da un sistema di ^^equazioni alle differenze finite^^[^4].
- Per un sistema **dinamico**, a **dimensione finita**, a **tempo discreto** e **lineare**, si ha che l'evoluzione dello stato è descritta da un sistema di equazione alle differenze finite ^^lineari^^ in x(k) e u(k).
- Per un sistema **dinamico**, a **dimensione finita**, a **tempo discreto** ed **LTI**, l'evoluzione dello stato è descritta da un sistema di equazioni alle differenze finite lineari in x(k) e u(k) ^^a coefficienti costanti^^.

[^1]: t: istante finale, $\tau$: istante iniziale, $x(\tau)$ valore iniziale dello stato, $u([\tau, t])$ funzione d'ingresso

[^2]: x(t) valore istanteaneo della funzione del sistema, u(t) stato del sistema in t

[^3]: 
    Un'equazione differenziale ordinaria è un'equazione in cui appaiono sia la funzione x(t) che la sua derivata $\dot{x}(t)$. Per il secondo e terzo caso si ha che l'**equazione di stato** vale $\dot{x}(t) = A(t)x(t) + B(t)u(t)$ e l'**equazione di uscita** $y(t) = C(t)x(t) + D(t)u(t)$ dove A..D sono matrici.

[^4]: 
    Le equazioni alle differenze finite sono la controparte discreta delle equazioni differenziali ordinare. Per il secondo e terzo caso si ha che l'**equazione di stato** vale $x(k + 1) = Ax(k) + Bu(k)$ e l'**equazione di uscita** $y(k) = Cx(k) + Du(k)$, dove A..D sono matrici. 