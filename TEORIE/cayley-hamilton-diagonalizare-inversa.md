# Cayley-Hamilton pentru inversă, și diagonalizarea "inversă"

Notă de teorie, din gap-urile de seminar (Alg_sem_7, Alg_sem_8) — două tehnici distincte de diagonalizarea directă.

## Rețeta 1 — calculezi $A^{-1}$ din polinomul caracteristic (Cayley-Hamilton)

**Teorema Cayley-Hamilton:** orice matrice $A$ verifică propriul polinom caracteristic: $P_A(A)=0$.

Dacă $P_A(\lambda)=\lambda^n+c_{n-1}\lambda^{n-1}+\ldots+c_1\lambda+c_0$, atunci:

$$A^n+c_{n-1}A^{n-1}+\ldots+c_1A+c_0I=0$$

Dacă $c_0\ne0$ (echivalent, $A$ e inversabilă — $c_0=\pm\det A$), izolezi $I$ și scoți $A$ factor din rest, ceea ce-ți dă direct $A^{-1}$ fără eliminare Gauss.

### Exemplu verificat ($2\times2$)

$A$ are liniile $(1,2)$ și $(2,3)$. Polinom caracteristic:

$$P_A(\lambda) = (1-\lambda)(3-\lambda)-4 = \lambda^2-4\lambda-1$$

Cayley-Hamilton: $A^2-4A-I=0 \implies A^2-4A=I \implies A(A-4I)=I$

$$\implies A^{-1}=A-4I$$

Cu $A-4I$ având liniile $(-3,2)$ și $(2,-1)$:

$$A^{-1} = \text{matrice cu liniile }(-3,2)\text{ și }(2,-1)$$

**Verificare:** $A\cdot(A-4I)$ dă liniile $(1\cdot(-3)+2\cdot2,\ 1\cdot2+2\cdot(-1))=(1,0)$ și $(2\cdot(-3)+3\cdot2,\ 2\cdot2+3\cdot(-1))=(0,1)$ — adică $I_2$ ✓.

**De ce e mai rapid decât Gauss:** nu mai rezolvi niciun sistem — doar aduni/scazi matrice, o dată ce ai polinomul caracteristic (pe care oricum îl calculezi la orice exercițiu cu valori proprii).

## Rețeta 2 — diagonalizare "inversă": dat $A^n$, găsești $A$

Enunțul îți dă direct puterea $A^n$ (sau chiar $A^n$ diagonalizată) și cere $A$.

1. Diagonalizezi $A^n = PD_nP^{-1}$, unde $D_n=\mathrm{diag}(\mu_1,\ldots,\mu_k)$ (valorile proprii ale lui $A^n$).
2. Valorile proprii ale lui $A$ sunt $\lambda_i$ astfel încât $\lambda_i^n=\mu_i$ — extragi rădăcina de ordin $n$ (atenție la semn dacă $n$ e par).
3. **Vectorii proprii ai lui $A$ sunt aceiași** cu ai lui $A^n$ (dacă $Av=\lambda v$, atunci $A^nv=\lambda^nv$ — același $v$).
4. $A = PDP^{-1}$ cu același $P$ ca la $A^n$, dar $D=\mathrm{diag}(\lambda_1,\ldots,\lambda_k)$.

### Exemplu construit și verificat

Presupui $A^2$ are liniile $(4,0)$ și $(0,9)$ (deja diagonală, $\mu_1=4,\mu_2=9$, cu vectorii proprii canonici $e_1,e_2$).

$$\lambda_1=\sqrt4=2,\qquad \lambda_2=\sqrt9=3 \implies A=\text{matrice cu liniile }(2,0)\text{ și }(0,3)$$

**Verificare:** $A^2$ = liniile $(4,0)$ și $(0,9)$ ✓ (înmulțești $A$ cu ea însăși).

**Atenție la ambiguitatea de semn:** dacă $n$ e par, $\lambda_i$ ar putea fi și $-\sqrt{\mu_i}$ — enunțul trebuie să specifice o condiție suplimentară (ex. "$A$ are valori proprii pozitive") ca soluția să fie unică; altfel, orice combinație de semne pe diagonala lui $D$ dă o soluție validă pentru $A$.

## De reținut

- **Recunoaștere Cayley-Hamilton:** dacă ți se cere $A^{-1}$ și ai deja (sau calculezi ușor) polinomul caracteristic, nu mai face Gauss — Cayley-Hamilton e mai scurt.
- **Recunoaștere diagonalizare inversă:** dacă enunțul dă o PUTERE a matricei ($A^2$, $A^4$, etc.) și cere matricea originală, vectorii proprii NU se schimbă — doar valorile proprii se "de-ridică la putere".
- Cayley-Hamilton funcționează la orice dimensiune, dar la $n\times n$ mare polinomul caracteristic devine el însuși greu de calculat — pentru matrice mari, diagonalizarea directă (dacă e posibilă) rămâne adesea mai simplă.
