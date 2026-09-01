# Exercițiul 5(a) — complement ortogonal și proiecție (Kernel + rânduri)

Sursă: `Exercitii 6-7.pdf`, pagina 4 (enunț) / pagina 4 (soluție condensată, pentru verificare). Exact tipul de subiect P1 din `GHIDURI/cram-algaed.html`.

**Enunț:** $U=\{(x_1,x_2,x_3)\in\mathbb{R}^3\}$ supus sistemului omogen

$$\begin{cases}x_1+3x_2+7x_3=0\\2x_1+2x_2+6x_3=0\\2x_1+x_2+4x_3=0\end{cases}$$

cu $\mathbf{v}=(1,\,2,\,5)^T$, produsul scalar canonic pe $\mathbb{R}^3$.

$U$ e dat ca **nucleu** al matricei $A$, având liniile $(1,3,7)$, $(2,2,6)$, $(2,1,4)$ (fiecare ecuație = un rând din $A\mathbf{x}=0$), nu ca subspațiu generat de vectori — deci rețeta pornește diferit față de un $U=\mathrm{Sp}\{u_1,u_2,u_3\}$ obișnuit.

## Mișcarea 1 — rezolvi sistemul, găsești baza lui U

Din ecuația 2, împărțită la 2: $x_1+x_2+3x_3=0 \implies x_1=-x_2-3x_3$.

Înlocuiești în ecuația 1: $(-x_2-3x_3)+3x_2+7x_3=0 \implies 2x_2+4x_3=0 \implies x_2=-2x_3$.

Atunci $x_1=-(-2x_3)-3x_3=-x_3$.

**Verifici cu ecuația 3** (ca să confirmi că e redundantă, nu contradictorie): $2(-x_3)+(-2x_3)+4x_3=0$ ✓ — se anulează identic, deci a treia ecuație nu adaugă nicio restricție nouă (rangul lui $A$ e $2$, nu $3$).

Cu $x_3=t$ liber: $(x_1,x_2,x_3)=t\cdot(-1,\,-2,\,1)$.

$$U=\mathrm{Sp}\{(1,\,2,\,-1)\}\qquad(\dim U=1)$$

(am scris vectorul înmulțit cu $-1$ față de $(-1,-2,1)$ — e aceeași dreaptă, direcția nu contează la semn.)

### De unde vine dimensiunea (de ce $\dim U=1$, nu $2$ sau $3$)

Două moduri de-a vedea aceeași dimensiune — unul din **teoremă**, altul direct din **soluție**.

**1. Din teorema rangului (teorema rang-nulitate):**

$$\dim(\mathrm{Ker}(A)) = n - \mathrm{rang}(A)$$

unde $n$ = numărul de **necunoscute** ($x_1,x_2,x_3$, deci $n=3$), iar $\mathrm{rang}(A)$ = numărul de **ecuații independente** (nu numărul de ecuații scrise în enunț). Am arătat mai sus că a treia ecuație se anulează identic când o exprimi din primele două — deci din cele 3 ecuații, doar **2 sunt independente** → $\mathrm{rang}(A)=2$.

$$\dim U = n-\mathrm{rang}(A) = 3-2 = 1$$

**2. Direct din soluție (mai intuitiv):** ai ajuns la $(x_1,x_2,x_3) = t\cdot(-1,-2,1)$ cu $t\in\mathbb{R}$ liber — orice soluție e un multiplu al **aceluiași** vector fix. Nu ai două direcții independente, ai o singură direcție, parametrizată de un singur număr real $t$.

Dimensiunea unui subspațiu = **numărul de parametri liberi independenți** de care ai nevoie ca să descrii orice element al lui. Aici ai un singur parametru ($t$) → $\dim U=1$.

**Regula generală de reținut:** numărul de necunoscute libere care rămân după ce rezolvi sistemul (aici doar $x_3=t$, pe când $x_1,x_2$ sunt determinate în funcție de $t$) = dimensiunea subspațiului soluțiilor. Dacă ar fi rămas 2 necunoscute libere, ai fi avut $\dim U=2$ (un plan, generat de 2 vectori), nu o dreaptă.

## Mișcarea 2 — complementul ortogonal, din rândurile lui A (nu din calcul direct)

**Teorema care scurtează totul:** dacă $U=\mathrm{Ker}(A)$, atunci $U^\perp = \mathrm{Im}(A^T)$ — adică $U^\perp$ e chiar **spațiul generat de rândurile lui $A$**. Are sens intuitiv: $x\in\mathrm{Ker}(A)$ înseamnă că $x$ e perpendicular pe fiecare rând al lui $A$ (din $Ax=0$, fiecare linie e un produs scalar rând·$x=0$) — deci rândurile lui $A$ sunt automat în $U^\perp$, și cum $\dim U + \dim U^\perp = 3$, ele îl generează complet.

Rândurile lui $A$: $(1,3,7),\ (2,2,6),\ (2,1,4)$. Cum $\mathrm{rang}(A)=2$ (am văzut la mișcarea 1 că a treia ecuație e dependentă), doar 2 din cele 3 rânduri sunt independente — verifici că $(2,1,4)=-\tfrac12(1,3,7)+\tfrac54(2,2,6)$ (dependent) — deci:

$$U^\perp = \mathrm{Sp}\{(1,\,3,\,7),\ (2,\,2,\,6)\}\qquad(\dim U^\perp=2)$$

**De reținut ca scurtătură pentru examen:** dacă subiectul îți dă $U$ direct ca sistem de ecuații (deci ca nucleu), NU mai treci prin Gram-Schmidt ca să găsești $U^\perp$ — rândurile matricei sistemului sunt deja o bază (sau un sistem de generatori, dacă unele rânduri sunt dependente) pentru $U^\perp$.

## Mișcarea 3 — proiecția

$U$ e generat de un singur vector $u=(1,2,-1)$, deci proiecția pe $U$ e proiecția pe un singur vector:

$$\mathrm{pr}_U\mathbf{v} = \frac{\langle \mathbf{v},u\rangle}{\langle u,u\rangle}\,u$$

$$\langle \mathbf{v},u\rangle = 1\cdot1+2\cdot2+5\cdot(-1) = 1+4-5=0$$

Numărătorul e $0$ — deci **fără să mai calculezi nimic altceva**:

$$\mathrm{pr}_U\mathbf{v} = 0 \qquad\Longrightarrow\qquad \mathbf{v}\in U^\perp \quad\text{și}\quad \mathrm{pr}_{U^\perp}\mathbf{v}=\mathbf{v}-\mathrm{pr}_U\mathbf{v}=\mathbf{v}=(1,\,2,\,5)$$

**Verificare directă:** $\mathbf{v}$ trebuie să fie perpendicular pe generatorul lui $U$ dacă e complet în $U^\perp$ — exact ce am obținut din $\langle \mathbf{v},u\rangle=0$. Coincide cu soluția din PDF: „$\mathrm{pr}_U\mathbf{v}=0$, deci $\mathbf{v}\in U^\perp$ și $\mathrm{pr}_{U^\perp}\mathbf{v}=\mathbf{v}$."

## De reținut

- **Recunoaștere:** dacă $U$ e dat printr-un sistem de ecuații (nu prin vectori generatori), e un nucleu — folosește direct rândurile matricei sistemului pentru $U^\perp$, nu Gram-Schmidt.
- **Capcană evitată aici:** nu presupune că trebuie neapărat calcul lung — dacă $\langle \mathbf{v},u\rangle=0$ iese direct, proiecția pe $U$ e $0$ și tot restul (proiecția pe $U^\perp$) e imediat $\mathbf{v}$ însuși. Verifică mereu acest produs scalar primul, înainte să te apuci de normalizări sau Gram-Schmidt inutil.
- Pentru varianta „grea" — $U$ dat prin vectori generatori posibil dependenți, cu Gram-Schmidt complet — vezi rețeta P1 din `GHIDURI/cram-algaed.html`.
