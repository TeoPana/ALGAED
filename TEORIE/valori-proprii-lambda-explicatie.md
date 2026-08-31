# Ce e λ (valoarea proprie) — legătura cu sistemele de EDO

Notă de teorie, ilustrată cu exemple din `EXERCITII/CANEPA/REZOLVATE/exercitiul-1-a-b-c-explicatie.md` și `EXERCITII/BADRALEXI/exercitiul-33-explicatie.md`.

## Ce e λ

În sistemele de forma $X' = AX$ (unde $A$ e o matrice constantă și $X(t)=\begin{pmatrix}x(t)\\y(t)\end{pmatrix}$), cauți soluții de forma

$$X(t) = e^{\lambda t} v$$

adică un vector fix $v$ care doar se "umflă" sau "se micșorează" exponențial în timp, fără să-și schimbe direcția. Dacă pui asta în $X'=AX$, obții

$$\lambda e^{\lambda t} v = A e^{\lambda t} v \implies Av = \lambda v$$

Asta e chiar definiția **valorii proprii**: $\lambda$ e un număr pentru care există un vector nenul $v$ (vectorul propriu) pe care matricea $A$ îl transformă doar prin scalare — nu îl rotește, nu îi schimbă forma, doar îl întinde/micșorează de $\lambda$ ori.

**De unde ies numeric:** din $\det(A-\lambda I)=0$ — polinomul caracteristic. De-asta primul pas din fiecare exercițiu e mereu ăsta.

## Ce înseamnă concret în exercițiile rezolvate

- **Ex. 1(a)** — $\lambda_1=-4,\ \lambda_2=-7$: două valori reale, negative. Fiecare direcție proprie ($v_1,v_2$) se contractă exponențial spre $0$, doar cu viteze diferite. De-asta soluția e o sumă simplă $C_1e^{-4t}v_1+C_2e^{-7t}v_2$ — fiecare termen "trăiește" independent pe direcția lui proprie.

- **Ex. 1(c)** — $\lambda_1=-1,\ \lambda_2=3$: o direcție se contractă ($-1$), cealaltă se dilată ($3$). E un punct-șa (saddle) în planul de fază.

- **Ex. 1(b)** — $\lambda=4$ **dublă**, dar cu un singur vector propriu (rang-deficiență la $A-4I$). Aici $\lambda$ nu-ți dă decât o singură direcție proprie, deci soluția nu poate fi doar $e^{4t}v$ — trebuie completată cu un vector generalizat $w$ și apare termenul $t\,e^{4t}$. Practic $\lambda$ îți spune viteza de creștere exponențială, dar geometria (câte direcții proprii independente ai) îți spune dacă ai nevoie de bloc Jordan.

- **Ex. 33** — $\lambda=\pm 2i$, **complexe**, fără parte reală. Aici $e^{\lambda t}$ nu mai e o exponențială reală — e $e^{i\beta t}=\cos\beta t + i\sin\beta t$, adică rotație pură, fără creștere/scădere. De-asta soluția finală e o combinație de $\sin 2t$ și $\cos 2t$: traiectoria se învârte în cerc/elipsă în jurul originii, nu tinde spre $0$ și nu explodează.

## Regula generală de citit dintr-o privire

| Forma lui λ | Comportamentul soluției |
|---|---|
| real, negativ | decade exponențial spre 0 |
| real, pozitiv | crește exponențial |
| real, dublu, un singur vector propriu | crește/decade, dar cu factor suplimentar $t$ (bloc Jordan) |
| complex, $\alpha\pm i\beta$ cu $\alpha=0$ | oscilează, amplitudine constantă (cerc/elipsă) |
| complex, $\alpha\pm i\beta$ cu $\alpha\ne0$ | oscilează și crește/decade (spirală) |

Practic, în orice exercițiu de tipul P4/P5 din `GHIDURI/cram-algaed.html`, primul lucru pe care-l calculezi ($\lambda$) îți spune deja, înainte să scrii vreo soluție, *forma calitativă* a răspunsului — restul e doar aritmetica de potrivit constantele la condițiile inițiale.
