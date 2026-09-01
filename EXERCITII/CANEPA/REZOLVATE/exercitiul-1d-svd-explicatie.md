# Exercițiul 1(d) — descompunerea SVD a unei matrice 2×3

Sursă: `Exercitii 8.pdf`, pagina 1. Am ales-o pe (d) dintre cele cinci (a-e) pentru că e singura **nepătratică cu 3 valori singulare distincte, inclusiv una zero** — cere calcul complet în $\mathbb{R}^3$ pentru $V$, plus o bază pentru nucleul lui $A$. Exact tipul P3 din `GHIDURI/cram-algaed.html`.

**Enunț:** $A$ e o matrice $2\times3$, cu liniile $(3,\,2,\,2)$ și $(2,\,3,\,-2)$.

## Mișcarea 1 — $A^TA$ și spectrul (de aici vine V)

$$A^TA=\begin{pmatrix}13&12&2\\12&13&-2\\2&-2&8\end{pmatrix}$$

(fiecare intrare $(A^TA)_{ij}$ = produsul scalar dintre coloana $i$ și coloana $j$ a lui $A$ — de exemplu $(A^TA)_{11}=3^2+2^2=13$, $(A^TA)_{12}=3\cdot2+2\cdot3=12$.)

**Polinomul caracteristic** (matrice $3\times3$, deci cubică — dezvolți determinantul pe prima linie):

$$\det(A^TA-\lambda I) = -\lambda^3+34\lambda^2-225\lambda = -\lambda(\lambda^2-34\lambda+225)$$

$$\lambda=0 \quad\text{sau}\quad \lambda^2-34\lambda+225=0 \implies \lambda=\frac{34\pm\sqrt{1156-900}}{2}=\frac{34\pm16}{2}$$

$$\lambda_1=25,\qquad \lambda_2=9,\qquad \lambda_3=0 \quad\text{(descrescător — așa se numerotează mereu la SVD)}$$

**Verificare rapidă (gratuită):** suma valorilor proprii = urma matricei: $25+9+0=34=13+13+8$ ✓.

### Vectorii proprii (coloanele lui V)

**$\lambda=25$:** $(A^TA-25I)v=0$. Din primele două linii obții $v_3=6v_1-6v_2$; din a treia, combinat cu asta, rezultă $v_1=v_2$, deci $v_3=0$. Cu $v_1=v_2=1$: $v=(1,\,1,\,0)$, normă $\sqrt2$ →

$$v_1 = \left(\tfrac{1}{\sqrt2},\,\tfrac{1}{\sqrt2},\,0\right)^T$$

**$\lambda=9$:** $(A^TA-9I)v=0$ dă $v_2=-v_1$ și $v_3=4v_1$. Cu $v_1=1$: $v=(1,\,-1,\,4)$, normă $\sqrt{1+1+16}=3\sqrt2$ →

$$v_2 = \left(\tfrac{1}{3\sqrt2},\,-\tfrac{1}{3\sqrt2},\,\tfrac{4}{3\sqrt2}\right)^T$$

(în soluția din PDF apare cu semn schimbat — $(-1,1,-4)/(3\sqrt2)$ — e aceeași dreaptă, semnul unui vector propriu e mereu arbitrar.)

**$\lambda=0$:** aici $(A^TA)v=0$ e chiar $\mathrm{Ker}(A)$ (nucleul lui $A^TA$ coincide cu nucleul lui $A$, pentru matrice reale). Rezolvi direct $3v_1+2v_2+2v_3=0$ și $2v_1+3v_2-2v_3=0$: adunându-le, $5v_1+5v_2=0 \implies v_1=-v_2$; înlocuit, $v_2=2v_3$. Cu $v_3=1$: $v=(-2,\,2,\,1)$, normă $3$ →

$$v_3 = \left(-\tfrac23,\,\tfrac23,\,\tfrac13\right)^T$$

## Mișcarea 2 — valorile singulare și Σ

$$\sigma_i=\sqrt{\lambda_i} \implies \sigma_1=5,\quad \sigma_2=3,\quad \sigma_3=\sqrt0=0$$

$\Sigma$ are **forma lui $A$** ($2\times3$, nu $3\times3$ — atenție, e cea mai frecventă capcană la SVD nepătratic):

$$\Sigma=\begin{pmatrix}5&0&0\\0&3&0\end{pmatrix}$$

## Mișcarea 3 — matricea U (doar pentru σ nenule)

$$u_i = \frac1{\sigma_i}Av_i$$

$$Av_1 = \begin{pmatrix}3&2&2\\2&3&-2\end{pmatrix}\begin{pmatrix}1/\sqrt2\\1/\sqrt2\\0\end{pmatrix} = \left(\tfrac{5}{\sqrt2},\,\tfrac{5}{\sqrt2}\right)^T \implies u_1=\frac15Av_1=\left(\tfrac1{\sqrt2},\,\tfrac1{\sqrt2}\right)^T$$

$$Av_2 = \begin{pmatrix}3&2&2\\2&3&-2\end{pmatrix}\begin{pmatrix}-1/(3\sqrt2)\\1/(3\sqrt2)\\-4/(3\sqrt2)\end{pmatrix} = \left(-\tfrac{3}{\sqrt2},\,\tfrac{3}{\sqrt2}\right)^T \implies u_2=\frac13Av_2=\left(-\tfrac1{\sqrt2},\,\tfrac1{\sqrt2}\right)^T$$

(folosesc aici $v_2$ cu semnul din PDF, ca $u_2$ să iasă identic cu soluția tipărită.)

$U$ e $2\times2$ (nu are nevoie de a treia coloană — $\sigma_3=0$ nu produce un $u_3$ prin formulă; dacă ar fi cerut explicit, s-ar completa ortonormal, dar aici $U$ e deja completă cu doar 2 coloane fiindcă $A$ are 2 linii).

$$U=\begin{pmatrix}1/\sqrt2 & -1/\sqrt2\\ 1/\sqrt2 & 1/\sqrt2\end{pmatrix}$$

## Rezultat final

$$A = U\Sigma V^T,\qquad U=\begin{pmatrix}1/\sqrt2&-1/\sqrt2\\1/\sqrt2&1/\sqrt2\end{pmatrix},\quad \Sigma=\begin{pmatrix}5&0&0\\0&3&0\end{pmatrix},\quad V=\begin{pmatrix}1/\sqrt2&-1/(3\sqrt2)&-2/3\\1/\sqrt2&1/(3\sqrt2)&2/3\\0&-4/(3\sqrt2)&1/3\end{pmatrix}$$

Coincide exact cu soluția din PDF.

## De reținut

- **De ce (d) e cea mai grea din setul (a)-(e):** e singura cu $A^TA$ de $3\times3$ *și* trei valori proprii distincte nenule + zero — deci cere polinom caracteristic cubic complet, nu doar o matrice $2\times2$ ușor de diagonalizat ca la (b) sau (c).
- **Capcana #1:** $\sigma=\sqrt\lambda$, niciodată $\lambda$ direct.
- **Capcana #2:** $\Sigma$ are forma lui $A$ ($m\times n$), nu a lui $A^TA$ ($n\times n$) — aici $A$ e $2\times3$, deci $\Sigma$ e $2\times3$, cu o coloană întreagă de zero pentru $\sigma_3=0$.
- **Capcana #3:** coloanele lui $V$ se ordonează **descrescător** după $\lambda$ — dacă schimbi ordinea, $\Sigma$ nu mai corespunde cu $U$ și $V$.
- $\lambda=0$ (ultima coloană a lui $V$) e mereu un vector din $\mathrm{Ker}(A)$ — dacă $A$ are rang complet, nu apare deloc un $\sigma=0$.
