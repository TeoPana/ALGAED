# Ce e μ (mu) — metoda coeficienților nedeterminați la EDO neomogene

Notă de teorie, ilustrată cu exemplul din `GHIDURI/cram-algaed.html` (P5): $x''+4x'+4x=4$, $x(0)=0$, $x'(0)=0$.

## De unde vine μ

$\mu$ e **rata exponențială ascunsă în partea dreaptă** a ecuației (în termenul $g(t)$, forța care "împinge" sistemul). Nu se alege — se citește direct din forma lui $g(t)$, scriind-o (mental) ca:

$$g(t) = \text{polinom în } t \cdot e^{\mu t}$$

- Dacă $g(t) = e^{5t}$, atunci $\mu = 5$.
- Dacă $g(t) = t^2 e^{-3t}$, atunci $\mu = -3$.
- Dacă $g(t) = \cos(\omega t)$ sau $\sin(\omega t)$, atunci "$\mu$" e complex: $\mu = \pm i\omega$ (se verifică dacă $\pm i\omega$ e printre rădăcinile caracteristice).
- **Dacă $g(t) = k$ (o constantă)** — o constantă se gândește ca $k \cdot e^{0\cdot t}$, pentru că $e^{0\cdot t}=1$. Deci **o constantă e, matematic, cazul particular $\mu=0$**.

## De ce contează μ

$m$ (exponentul lui $t$ din soluția particulară $x_p$) = **de câte ori e $\mu$ rădăcină a ecuației caracteristice**. Asta se numește *rezonanță*: dacă forța din dreapta "vibrează" exact pe aceeași rată ca soluția omogenă, forma simplă (fără $t$ suplimentar) nu mai funcționează — la substituție ai obține $0=k$, o contradicție — și trebuie înmulțit cu $t^m$ ca soluția particulară să se desprindă de cea omogenă.

Tabelul complet (din `GHIDURI/cram-algaed.html`, P5):

| Omogenă | Forma dreptei $g(t)$ | Soluția particulară |
|---|---|---|
| $\lambda_1\ne\lambda_2$ (rădăcini distincte) | $g(t)=k$ | $x_p = a\cdot t^m$ |
| $\lambda$ dublă | $g(t)=e^{\mu t}$ | $x_p = a\cdot t^m\cdot e^{\mu t}$ |
| $\lambda=\alpha\pm i\beta$ | $g(t)=\cos\omega t$ sau $\sin\omega t$ | $x_p = t^m(a\cos\omega t + b\sin\omega t)$ |

unde $m$ = multiplicitatea lui $\mu$ (respectiv $\pm i\omega$) printre rădăcinile ecuației caracteristice ($m=0$ dacă nu e deloc rădăcină — cazul obișnuit, fără rezonanță).

## Exemplul rezolvat

$x''+4x'+4x=4$: ecuația caracteristică $\lambda^2+4\lambda+4=0=(\lambda+2)^2$ are rădăcina $\lambda=-2$ (dublă).

Dreapta e $g(t)=4$, deci $\mu=0$ (cazul constantei).

Verifici: e $\mu=0$ printre rădăcinile caracteristice ($\lambda=-2$)? **Nu** — $0\neq-2$. Deci $m=0$ (nicio rezonanță) și încerci direct forma cea mai simplă, fără niciun $t$ în plus: $x_p=a$ (o constantă).

**Contraexemplu (rezonanță):** dacă dreapta ar fi fost $g(t)=4e^{-2t}$ (adică $\mu=-2$, exact rădăcina dublă), atunci $m=2$ (fiindcă $-2$ e rădăcină dublă) și ar fi trebuit $x_p=a\cdot t^2\cdot e^{-2t}$ — asta e situația de rezonanță semnalată în „capcanele" din P5 (`GHIDURI/cram-algaed.html`): dacă μ e rădăcină, forma simplă nu merge și trebuie înmulțit cu $t^m$.
