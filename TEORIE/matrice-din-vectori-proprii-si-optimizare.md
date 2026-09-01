# Reconstrucția matricei din vectori/valori proprii + optimizarea formei pătratice

Notă de teorie, gap identificat la examenul din 2026 (cerința E2) — reconstrucția "inversă" (dai vectorii proprii, găsești matricea) și optimizarea pe cerc unitate nu apăreau ca rețete explicite în ghidurile existente.

## Rețeta 1 — reconstrucția matricei simetrice din vectori proprii ortonormați

Dacă ți se dau $v_1,\ldots,v_n$ **ortonormați** (verifică asta — produs scalar $0$ între ei, normă $1$ fiecare) și valorile proprii corespunzătoare $\lambda_1,\ldots,\lambda_n$:

1. $P = (v_1\mid\ldots\mid v_n)$ (coloane = vectorii proprii) — automat ortogonală, deci $P^{-1}=P^T$.
2. $D=\mathrm{diag}(\lambda_1,\ldots,\lambda_n)$.
3. $A = PDP^T$ (matrice simetrică garantat, fiindcă $P$ ortogonală).

**Verificări gratuite după calcul:** $\mathrm{tr}(A)=\Sigma\lambda_i$; $\det A = \Pi\lambda_i$.

**Exemplu verificat:** $v_1=\tfrac15(4,3)$, $v_2=\tfrac15(-3,4)$, $\lambda_1=1,\lambda_2=-1$.

$$A = \frac{1}{25}\cdot(\text{matrice cu liniile }(4,3),(3,-4))\cdot(\text{matrice cu liniile }(4,3),(-3,4)) = \frac{1}{25}\big[\text{liniile }(7,24),(24,-7)\big]$$

Verificare: $\mathrm{tr}(A)=0=1+(-1)$ ✓; $\det A=-1=1\cdot(-1)$ ✓.

**Interpretare geometrică specială — valori proprii $\pm1$:** dacă toate valorile proprii sunt $+1$ sau $-1$ și matricea e simetrică, $A$ e o **reflexie** (nu doar o întindere) — reflectă spațiul față de subspațiul generat de vectorii proprii cu $\lambda=1$, inversând direcțiile cu $\lambda=-1$.

## Rețeta 2 — min/max al formei pătratice pe cerc/sferă unitate

Pentru $q(v)=v^TAv$ cu $A$ simetrică, restricționat la $‖v‖=1$:

$$\min_{‖v‖=1} q(v) = \lambda_{\min},\qquad \max_{‖v‖=1} q(v) = \lambda_{\max}$$

atinse exact în direcția vectorilor proprii corespunzători.

**De ce:** scrii $v$ în baza ortonormată de vectori proprii, $q(v)=\Sigma\lambda_ix_i^2$ cu $\Sigma x_i^2=1$ (păstrat de norma $1$) — o combinație convexă de $\lambda_i$ e mereu între $\lambda_{\min}$ și $\lambda_{\max}$, cu egalitate doar când toată "greutatea" e pe un singur $\lambda$.

**Exemplu verificat:** cu $A$ din rețeta 1 ($\lambda=1,-1$): $\min q=-1$ (la $v_2$), $\max q=1$ (la $v_1$) — nu mai trebuie recalculat nimic, valorile proprii sunt deja răspunsul.

## De reținut

- **Recunoaștere rețeta 1:** enunțul dă vectori proprii + valori proprii, cere matricea — verifică ORTONORMALITATEA vectorilor dați înainte de a presupune $P^{-1}=P^T$.
- **Recunoaștere rețeta 2:** orice "min/max al $q(v)=v^TAv$ pe cerc/sferă unitate" se rezolvă **fără optimizare efectivă** — sunt direct valorile proprii extreme ale lui $A$.
- Cele două rețete se înlănțuie des: (a) reconstruiești $A$ din vectori proprii, (b) folosești aceleași valori proprii pentru min/max — nu recalcula valorile proprii ale lui $A$ de la zero la punctul (b), le ai deja din enunț.
- Vezi rezolvarea completă la (E2) în `SUBIECTE/Subiecte Examen 2026 - rezolvare.md`, și demonstrația generală la exercițiul 7 din `EXERCITII/CANEPA/REZOLVATE/Exercitii 8.pdf`.
