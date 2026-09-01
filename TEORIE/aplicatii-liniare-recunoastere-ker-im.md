# Aplicații liniare — verificarea liniarității și Ker/Im de la zero

Notă de teorie, din gap-ul de seminar (Alg_sem_6) — pasul dinaintea celui acoperit deja în `TEORIE/aplicatii-liniare-pe-matrice.md` (acolo presupuneam deja că știi că funcția e liniară).

## Rețeta — verifici dacă $f$ e aplicație liniară

$f$ e liniară dacă și numai dacă $f(x+y)=f(x)+f(y)$ **și** $f(\lambda x)=\lambda f(x)$ pentru orice $x,y$ și orice scalar $\lambda$ — sau, echivalent, într-un singur pas: $f(\lambda x+y)=\lambda f(x)+f(y)$.

**Semnale rapide de NEliniaritate** (verifică-le primele, înainte de calcul complet):
- Termen constant adăugat/scăzut (ex. $x-1$) — dacă $f(0)\ne0$, sigur nu e liniară.
- Termeni de grad $\ge2$ în variabile (ex. $y^2$, $x\cdot y$, $z^3$).
- Funcții neliniare aplicate variabilelor (ex. $\sin x$, $|x|$).

### Exemplu — E liniară

$f:\mathbb{R}^2\to\mathbb{R}^3$, $f(x,y)=(2x+3y,\ y,\ x-y)$ — toate componentele sunt combinații liniare de $x,y$, fără termeni constanți sau de grad $\ge2$. **E liniară.**

### Exemplu — NU e liniară

$f:\mathbb{R}^2\to\mathbb{R}^3$, $f(x,y)=(x-1,\ x+y,\ 2x-y)$ — prima componentă are $-1$ constant: $f(0,0)=(-1,0,0)\ne(0,0,0)$. **NU e liniară** (orice aplicație liniară duce $0$ în $0$ — verificarea asta e cea mai rapidă).

## Rețeta — matricea, Ker, Im (o dată confirmată liniaritatea)

1. Calculezi $f$ pe fiecare element al bazei canonice a domeniului.
2. Rezultatele devin coloanele matricei $M(f)$.
3. $\mathrm{Ker}(f)$: rezolvi $M(f)x=0$ (sistem omogen).
4. $\mathrm{Im}(f)$: spațiul generat de coloanele lui $M(f)$ (elimini coloanele dependente).
5. **Verificare gratuită:** $\dim\mathrm{Ker}(f)+\dim\mathrm{Im}(f) = \dim(\text{domeniu})$ (teorema rangului).

## Exemplu complet verificat

$f:\mathbb{R}^2\to\mathbb{R}^3$, $f(x,y)=(2x+3y,\ y,\ x-y)$.

$$f(1,0)=(2,0,1),\qquad f(0,1)=(3,1,-1)$$

$$M(f) = \text{matrice cu liniile }(2,3),\ (0,1),\ (1,-1)$$

**Ker(f):** $M(f)(x,y)^T=0 \implies 2x+3y=0,\ y=0,\ x-y=0$. Din $y=0$ și $x-y=0 \implies x=0$. Verifici prima: $0=0$ ✓.

$$\mathrm{Ker}(f)=(0),\qquad \dim\mathrm{Ker}(f)=0$$

**Im(f):** cele 2 coloane $(2,0,1)$ și $(3,1,-1)$ sunt independente (nu sunt proporționale), deci:

$$\mathrm{Im}(f)=\mathrm{Sp}((2,0,1),\ (3,1,-1)),\qquad \dim\mathrm{Im}(f)=2$$

**Verificare:** $0+2=2=\dim\mathbb{R}^2$ ✓ (teorema rangului).

**Injectivitate/surjectivitate, gratis din dimensiuni:**
- $\mathrm{Ker}(f)=(0) \implies f$ **injectivă**.
- $\dim\mathrm{Im}(f)=2 < 3=\dim\mathbb{R}^3 \implies f$ **NU e surjectivă**.

## De reținut

- **Ordinea corectă:** întâi confirmi liniaritatea (sau o presupui, dacă enunțul spune explicit "aplicația liniară $f$"), abia apoi calculezi matricea.
- $f$ injectivă $\iff \mathrm{Ker}(f)=(0)$; $f$ surjectivă $\iff \dim\mathrm{Im}(f)=\dim(\text{codomeniu})$ — nu trebuie calcul suplimentar dincolo de Ker/Im, doar compari dimensiunile.
- Domeniul poate fi și un spațiu de polinoame sau matrice (vezi `TEORIE/aplicatii-liniare-pe-matrice.md`) — rețeta e identică, doar baza canonică se schimbă.
