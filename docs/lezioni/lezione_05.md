# Sistemi meccanici in rotazione

Un corpo puntiforme in rotazione segue la seconda legge di newton $J\ddot{\theta}(t) = J\frac{d^2\theta(t)}{dt^2} = T(t)$. Le variabili importanti sono la posizione angolare $\theta$ e la velocità angolare $\omega$; J è definito momento d'inerzia e $J\ddot{\theta}(t)$ è definito *coppia d'inerzia*. Il sistema di riferimento standard vede la rotazione positiva nel senso in cui viene applicata la coppia di forze; se la coppia è in verso antiorario allora sarebbe meglio scegliere come positive le rotazioni antiorarie. Se il sistema presenta più coppie è necessario fare una scelta arbitraria.

Unità: [T] = N m, [$\theta$] = rad, [J] = kg $m^2$.

Per rappresentare in 2D una rotazione, si usa il vettore normale al piano di rotazione ottenuto tramite la regola della mano destra (antiorario verso sinistra, orario verso destra).

## Molla torsionale
![alt text](../img/image07.png)

Agli estremi della molla vi saranno due coppie torsionali uguali e opposte, date da $T(t) = K[\theta_+(t) - \theta_-(t)]$.

Unità: [T] = N m, [$\theta$] = rad, [K] = $\frac{N m}{rad}$
## Smorzatore

![alt text](../img/image08.png)

La coppia di attrito è dovuta alla velocità relativa dei due corpi. $T(t) = \beta[\omega_+(t) - \omega_-(t)] = \beta[\dot{\theta}_+(t) \dot{\theta}_-(t)]$

Unità: [T] = N m, [$\dot{\theta}$] = $\frac{rad}{s}$, [K] = $\frac{N m s}{rad}$