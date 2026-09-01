# Spații vectoriale — verificare din axiome, extragere bază, completare la bază

Notă de teorie, din gap-urile de seminar (Alg_sem_3, Alg_sem_4, Alg_sem_5) — pașii "de la zero" pe care exercițiile de subspații/proiecție îi presupun deja făcuți.

## Rețeta 1 — verifici dacă o submulțime $U\subseteq V$ e subspațiu vectorial

Trei condiții, toate obligatorii:

1. $0\in U$ (vectorul nul aparține lui $U$).
2. $u_1,u_2\in U \implies u_1+u_2\in U$ (închidere la adunare).
3. $u\in U,\ \lambda\in\mathbb{R} \implies \lambda u\in U$ (închidere la înmulțirea cu scalar).

**Cea mai rapidă cale de a arăta că NU e subspațiu:** găsești un contraexemplu la oricare din cele 3 condiții — de obicei condiția 3 (scalar negativ) cade prima.

### Exemplu — E subspațiu

$U=((x,y,z)\in\mathbb{R}^3 \mid x+y=z)$. Verifici: $0+0=0$ ✓ (condiția 1). Dacă $x_1+y_1=z_1$ și $x_2+y_2=z_2$, atunci $(x_1+x_2)+(y_1+y_2)=z_1+z_2$ ✓ (condiția 2). Dacă $x+y=z$, atunci $\lambda x+\lambda y=\lambda z$ pentru orice $\lambda$ ✓ (condiția 3). **$U$ e subspațiu.**

### Exemplu — NU e subspațiu

$U=((x,y)\in\mathbb{R}^2 \mid x\ge0,\ y\ge0)$ (primul cadran). Ia $u=(1,1)\in U$ și $\lambda=-1$: $\lambda u=(-1,-1)\notin U$ — condiția 3 pică. **$U$ NU e subspațiu** (deși conține $0$ și e închis la adunare — trebuie să pice UNA din cele 3, nu neapărat toate).

## Rețeta 2 — extragi o bază dintr-un sistem de generatori posibil dependent

Dacă $U=\mathrm{Sp}(u_1,\ldots,u_k)$ și nu știi dacă $u_1,\ldots,u_k$ sunt independenți:

1. Pui vectorii ca linii (sau coloane) într-o matrice, calculezi rangul (Gauss).
2. Rangul = dimensiunea lui $U$.
3. Găsești un minor nenul de ordinul = rang — liniile/coloanele implicate în acel minor dau o bază.

### Exemplu verificat

$w_1=(1,2,1)$, $w_2=(2,1,-1)$, $w_3=(4,5,1)$. Verifici dacă $w_3$ e combinație a celorlalte: $w_3=aw_1+bw_2 \implies a+2b=4,\ 2a+b=5,\ a-b=1$. Din a treia: $a=1+b$; înlocuit în a doua: $2(1+b)+b=5\implies b=1,\ a=2$; verifici prima: $2+2=4$ ✓.

$$w_3=2w_1+w_2 \implies \text{dependent} \implies \text{bază: }(w_1,w_2),\ \dim U=2$$

**Coordonate:** pentru $v=(3,3,0)\in U$, rezolvi $v=cw_1+dw_2$: $c+2d=3,\ 2c+d=3,\ c-d=0\implies c=d$. Înlocuit: $3c=3\implies c=d=1$. Verifici a doua: $2+1=3$ ✓.

$$v=w_1+w_2 \implies \text{coordonatele lui }v\text{ în baza }(w_1,w_2)\text{ sunt }(1,1)$$

## Rețeta 3 — completezi un set independent la o bază a întregului spațiu

Dacă ai $k<n=\dim V$ vectori independenți, adaugi $n-k$ vectori "evidenți" (de obicei din baza canonică sau polinoame simple) și verifici că tot setul rămâne independent.

### Exemplu verificat

$P_1=1+2X+X^3$, $P_2=2+X+2X^2$, $P_3=3+X^2+X^3$, independenți în $\mathbb{R}_{\le3}[X]$ ($\dim=4$). Lipsește 1 vector — adaugi $P_4=1$ (polinomul constant) și verifici independența celor 4 (se confirmă prin calcul).

**Coordonatele lui $P(X)=3X+X^2$** în baza $(P_1,P_2,P_3,P_4)$: rezolvi $P=\lambda_1P_1+\lambda_2P_2+\lambda_3P_3+\lambda_4P_4$ egalând coeficienții pe fiecare putere a lui $X$:

$$X^3:\ \lambda_1+\lambda_3=0 \qquad X^2:\ 2\lambda_2+\lambda_3=1 \qquad X^1:\ 2\lambda_1+\lambda_2=3 \qquad X^0:\ \lambda_1+2\lambda_2+3\lambda_3+\lambda_4=0$$

$$\implies \lambda_1=1,\ \lambda_2=1,\ \lambda_3=-1,\ \lambda_4=0$$

**Verificare:** $X^3$: $1+(-1)=0$ ✓; $X^2$: $2(1)+(-1)=1$ ✓; $X^1$: $2(1)+1=3$ ✓; $X^0$: $1+2-3+0=0$ ✓.

## De reținut

- **Regula de aur pentru "NU e subspațiu":** un singur contraexemplu la oricare din cele 3 condiții e suficient — nu verifica pe toate dacă prima pică deja.
- Rangul matricei formate din vectorii generatori = dimensiunea subspațiului generat, indiferent câți vectori "în plus" (dependenți) ai în listă.
- Completarea la bază nu are o soluție unică — orice alegere de vectori suplimentari care păstrează independența totală funcționează.
