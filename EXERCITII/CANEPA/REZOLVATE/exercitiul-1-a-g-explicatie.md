# Exercițiul 1 (a) și (g) — ecuații diferențiale liniare de ordin superior

Sursă: `Exercitii-11.pdf`, pagina 1 (enunțuri + soluții condensate, pentru verificare). Am ales (a) pentru că e singura de ordin 3 din listă (ecuație caracteristică cubică), și (g) pentru că e cea mai grea dintre cele de ordin 2 — combină o rădăcină dublă cu rezonanță pe un termen polinomial.

---

## (a) $x'''-x''-4x'+4x=0,\ x(0)=3,\ x'(0)=1,\ x''(0)=9$

Ecuație **omogenă de ordin 3** — aceeași rețetă ca la ordin 2, doar că ecuația caracteristică e cubică și ai 3 constante de determinat.

**Mișcarea 1 — ecuația caracteristică**

$$\lambda^3-\lambda^2-4\lambda+4=0$$

Cauți o rădăcină „ghicită" printre divizorii termenului liber ($\pm1,\pm2,\pm4$). Încerci $\lambda=1$: $1-1-4+4=0$ ✓ — deci $(\lambda-1)$ e factor.

Împarți: $\lambda^3-\lambda^2-4\lambda+4 = (\lambda-1)(\lambda^2-4) = (\lambda-1)(\lambda-2)(\lambda+2)$.

$$\lambda_1=1,\qquad \lambda_2=2,\qquad \lambda_3=-2 \quad\text{(reale, distincte)}$$

**Mișcarea 2 — soluția generală**

Trei rădăcini distincte → sumă simplă de exponențiale, la fel ca la ordin 2, doar cu un termen în plus:

$$x(t) = C_1e^{t}+C_2e^{2t}+C_3e^{-2t}$$

$$x'(t) = C_1e^{t}+2C_2e^{2t}-2C_3e^{-2t}$$
$$x''(t) = C_1e^{t}+4C_2e^{2t}+4C_3e^{-2t}$$

**Mișcarea 3 — sistemul din condițiile inițiale**

$$\begin{cases}x(0)=C_1+C_2+C_3=3\\ x'(0)=C_1+2C_2-2C_3=1\\ x''(0)=C_1+4C_2+4C_3=9\end{cases}$$

Din prima ecuație: $C_1=3-C_2-C_3$. O înlocuiești în celelalte două:

$$(3-C_2-C_3)+2C_2-2C_3=1 \implies C_2-3C_3=-2$$
$$(3-C_2-C_3)+4C_2+4C_3=9 \implies 3C_2+3C_3=6 \implies C_2+C_3=2$$

Din a doua: $C_2=2-C_3$. Înlocuiești în prima: $(2-C_3)-3C_3=-2 \implies -4C_3=-4 \implies C_3=1$, deci $C_2=1$, apoi $C_1=3-1-1=1$.

$$\boxed{x(t) = e^{t}+e^{2t}+e^{-2t}}$$

**Verificare:** $x(0)=1+1+1=3$ ✓; $x'(0)=1+2-2=1$ ✓; $x''(0)=1+4+4=9$ ✓ — coincide cu soluția din PDF.

---

## (g) $x''-2x'+x=6te^t+3$ (fără condiții inițiale în enunț — rămâne cu $C_1,C_2$)

Cazul cel mai încărcat din listă: rădăcină dublă **și** rezonanță pe partea neomogenă. Se rezolvă cu **principiul superpoziției** — desparți membrul drept în bucăți simple, rezolvi separat, aduni rezultatele.

**Mișcarea 1 — omogena**

$$\lambda^2-2\lambda+1=(\lambda-1)^2=0 \implies \lambda=1 \text{ (dublă)}$$

$$x_0(t) = (C_1+C_2t)e^{t}$$

**Mișcarea 2 — superpoziție: desparți dreapta în două probleme**

$$x''-2x'+x=6te^t \qquad(i)$$
$$x''-2x'+x=3 \qquad(ii)$$

**(ii) e simplă — nicio rezonanță.** Dreapta e constantă, $\mu=0$; $\mu=0$ nu e printre rădăcini ($\lambda=1$), deci $m=0$: $x_{p2}=a$. Înlocuiești ($x_{p2}'=x_{p2}''=0$): $a=3$.

**(i) e cazul de rezonanță.** Dreapta e $6t\cdot e^{t}$ — polinom de gradul 1 ori $e^{\mu t}$ cu $\mu=1$. Dar $\mu=1$ **este** rădăcină, și încă **dublă** — deci $m=2$. Forma corectă:

$$x_{p1}(t) = t^2(At+B)e^{t} = (At^3+Bt^2)e^{t}$$

**Trucul de calcul (evită derivarea brută):** scrii $x_{p1}=u\cdot e^{t}$ cu $u=At^3+Bt^2$. Pentru că $\lambda=1$ e rădăcină dublă a ecuației caracteristice, operatorul $x''-2x'+x$ aplicat pe $u\,e^{t}$ se simplifică direct la $e^{t}u''$ (derivatele lui $u$ de ordin 0 și 1 se anulează exact, ca la orice rezonanță de ordinul al doilea):

$$x_{p1}''-2x_{p1}'+x_{p1} = e^{t}u''$$

Deci ecuația devine $e^{t}u''=6t\,e^{t}\implies u''=6t$. Cu $u=At^3+Bt^2$: $u''=6At+2B$.

$$6At+2B=6t \implies A=1,\ B=0 \implies x_{p1}(t)=t^3e^{t}$$

**Mișcarea 3 — adunarea soluțiilor**

$$x(t) = x_0(t)+x_{p1}(t)+x_{p2}(t) = (C_1+C_2t)e^{t}+t^3e^{t}+3$$

$$\boxed{x(t) = C_1e^{t}+C_2te^{t}+t^3e^{t}+3}$$

(coincide cu soluția din PDF; nu se cere valoare numerică pentru $C_1,C_2$ pentru că enunțul nu dă condiții inițiale la acest punct.)

---

## De reținut

- **(a)** arată că rețeta de la ordin 2 (ecuație caracteristică → soluție generală → sistem din condiții inițiale) se extinde direct la ordin 3 — doar aritmetica sistemului liniar crește cu o necunoscută.
- **(g)** e „coșmarul" tipului P5: rădăcină dublă **plus** rezonanță pe un termen polinomial din dreapta. Regulile combinate: dacă ai deja rădăcină dublă și pe deasupra $\mu$ coincide cu ea, $m$ se ia din **multiplicitatea lui $\mu$ ca rădăcină** (aici $2$, nu $1$) — de-asta apare $t^3$, nu doar $t^2$, în soluția finală.
- Vezi și `TEORIE/metoda-coeficientilor-nedeterminati-mu.md` pentru explicația generală a lui $\mu$ și $m$.
