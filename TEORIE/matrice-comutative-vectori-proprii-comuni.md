# Matrice diagonalizabile cu aceiași vectori proprii — comutativitate

Notă de teorie, gap identificat la examenul din 2026 (cerința L4).

## Rezultatul central

Dacă $A$ și $B$ sunt diagonalizabile **și au aceiași vectori proprii** (aceeași bază de diagonalizare $P$), atunci $A$ și $B$ **comută**: $AB=BA$.

**De ce:** $A=PDP^{-1}$, $B=PD'P^{-1}$ cu același $P$. Matricele diagonale comută mereu între ele ($DD'=D'D$, se înmulțesc element cu element pe diagonală), deci:

$$AB = PDP^{-1}PD'P^{-1}=PDD'P^{-1}=PD'DP^{-1}=PD'P^{-1}PDP^{-1}=BA$$

## Rețeta pentru „găsește parametrul astfel încât să aibă aceiași vectori proprii"

1. Găsești valorile și vectorii proprii ai matricei complet determinate (fără parametru).
2. Pentru fiecare vector propriu $v$ găsit, impui ca matricea cu parametru să-l aibă tot pe $v$ ca vector propriu: $B_m\cdot v = \mu\cdot v$ pentru un $\mu$ oarecare — adică $B_m v$ trebuie să fie **coliniar** cu $v$.
3. Din condiția de coliniaritate rezultă o ecuație în parametru.

## Exemplu verificat

$A$ are liniile $(1,1)$ și $(0,2)$ (triunghiulară) → valori proprii $1,2$ direct de pe diagonală. Vectori proprii: $\lambda=1\to(1,0)$, $\lambda=2\to(1,1)$.

$B_m$ are liniile $(m,1)$ și $(0,3)$. $(1,0)$ e automat vector propriu al lui $B_m$ pentru **orice** $m$ (proprietate a matricelor triunghiulare superior: primul vector canonic e mereu vector propriu, cu valoarea proprie = colțul stânga-sus).

Pentru ca $(1,1)$ să fie și el vector propriu: $B_m(1,1)^T=(m+1, 3)^T$ trebuie să fie multiplu de $(1,1)^T$ — adică ambele componente egale: $m+1=3 \implies m=2$.

**Interpretare geometrică:** cu $m=2$, $A$ și $B_2$ acționează ca întinderi de-a lungul acelorași două direcții fixe — comută pentru că "nu se încurcă una pe alta": aplicate în orice ordine, întind fiecare direcție cu factorul ei propriu, indiferent de ordine.

## De reținut

- **Recunoaștere:** dacă enunțul cere un parametru astfel încât două matrice să "admită aceiași vectori proprii" sau să comute, du-te direct la condiția de coliniaritate — nu diagonaliza matricea cu parametru de la zero.
- **Scurtătură pentru matrice triunghiulare:** primul vector canonic $(1,0,\ldots,0)$ e mereu vector propriu al oricărei matrice triunghiular superioare, cu valoarea proprie = primul element de pe diagonală — verifică asta gratuit înainte de calcul.
- Vezi rezolvarea completă la (L4) în `SUBIECTE/Subiecte Examen 2026 - rezolvare.md`.
