# Aplicații liniare al căror domeniu e un spațiu de matrice

Notă de teorie, gap identificat la examenul din 2026 (cerința L3) — tip complet nou, neacoperit în ghidurile existente.

## Ideea

Până acum, aplicațiile liniare aveau domeniul $\mathbb{R}^n$. Aici domeniul e $\mathcal{M}_n(\mathbb{R})$ (spațiul matricelor $n\times n$) — dar rețeta rămâne identică, doar că **baza canonică e formată din matrice**, nu din vectori.

Pentru $\mathcal{M}_2(\mathbb{R})$, baza canonică e $E_{11},E_{12},E_{21},E_{22}$ (matricea cu $1$ pe poziția $(i,j)$ și $0$ în rest).

## Rețeta

1. Calculezi $f(E_{ij})$ pentru fiecare element al bazei canonice — rezultatul e tot o matrice $n\times n$.
2. „Aplatizezi" fiecare $f(E_{ij})$ într-un vector din $\mathbb{R}^{n^2}$ (citind matricea pe linii sau pe coloane, consecvent).
3. Aceste vectori aplatizați devin **coloanele** matricei lui $f$ în raport cu baza canonică.
4. De aici încolo, Ker/Im/rang se calculează exact ca la o aplicație liniară obișnuită.

## Exemplu verificat — comutatorul $f(X)=AX-XA$

Cu $A$ având liniile $(1,2)$ și $(2,1)$:

- $f(E_{11})$: liniile $(0,-2)$ și $(2,0)$
- $f(E_{12})$: liniile $(-2,0)$ și $(0,2)$
- $f(E_{21})$: liniile $(2,0)$ și $(0,-2)$
- $f(E_{22})$: liniile $(0,2)$ și $(-2,0)$

Observă imediat: $f(E_{21})=-f(E_{11})$ și $f(E_{22})=-f(E_{12})$ — doar 2 din cele 4 coloane sunt independente.

$$\mathrm{Im}(f)=\mathrm{Sp}(f(E_{11}), f(E_{12})),\qquad \dim\mathrm{Im}(f)=2$$

## De reținut

- **Recunoaștere:** dacă domeniul aplicației e $\mathcal{M}_n(\mathbb{R})$ (nu $\mathbb{R}^n$ sau un spațiu de polinoame), tot ce trebuie e să identifici baza canonică potrivită și să calculezi $f$ pe fiecare element al ei — restul e identic cu orice altă aplicație liniară.
- **Proprietate utilă pentru comutator:** $f(X)=AX-XA$ e întotdeauna **antisimetrică** în sensul că trace-ul imaginii e $0$ (trace$(AX-XA)=$trace$(AX)-$trace$(XA)=0$, fiindcă trace$(AX)=$trace$(XA)$ mereu) — deci $\mathrm{Im}(f)$ e conținut în subspațiul matricelor cu urmă zero, un fapt care poate scurta calculul dimensiunii.
- Vezi rezolvarea completă la (L3) în `SUBIECTE/Subiecte Examen 2026 - rezolvare.md`.
