# Exercițiul 1 (a, b, c) — probleme Cauchy pentru sisteme de EDO liniare

Sursă: `Exercitii 10.pdf`, pagina 1 (enunțuri) / pagina 2 (soluția lui (a), pentru verificare).

---

## (a) $x'=-5x+2y,\ y'=x-6y,\ x(0)=3,\ y(0)=0$

**Mișcarea 1 — matricea și spectrul**

$A$ are liniile $(-5,2)$ și $(1,-6)$. $p_A(\lambda)=(\lambda+5)(\lambda+6)-2=\lambda^2+11\lambda+28=(\lambda+4)(\lambda+7)$

$$\lambda_1=-4,\qquad \lambda_2=-7$$

Vectori proprii:

$$(A+4I)v=0 \Rightarrow -v_1+2v_2=0 \Rightarrow v_1=(2,1)^T$$
$$(A+7I)v=0 \Rightarrow 2v_1+2v_2=0 \Rightarrow v_2=(-1,1)^T$$

**Mișcarea 2 — soluția generală**

$$X(t)=C_1e^{-4t}v_1+C_2e^{-7t}v_2 \implies x(t)=2C_1e^{-4t}-C_2e^{-7t},\qquad y(t)=C_1e^{-4t}+C_2e^{-7t}$$

**Mișcarea 3 — condițiile inițiale**

$$x(0)=2C_1-C_2=3,\qquad y(0)=C_1+C_2=0 \implies C_2=-C_1 \implies 3C_1=3 \implies C_1=1,\ C_2=-1$$

$$\boxed{x(t)=2e^{-4t}+e^{-7t},\qquad y(t)=e^{-4t}-e^{-7t}}$$

(coincide cu soluția tipărită în PDF, la pagina 2.)

---

## (b) $x'=5x-y,\ y'=x+3y,\ x(0)=0,\ y(0)=1$

**Mișcarea 1 — matricea și spectrul**

$A$ are liniile $(5,-1)$ și $(1,3)$. $p_A(\lambda)=(5-\lambda)(3-\lambda)+1=\lambda^2-8\lambda+16=(\lambda-4)^2$

$\lambda=4$ e rădăcină **dublă**. Verifici dacă e diagonalizabilă:

$A-4I$ are liniile $(1,-1)$ și $(1,-1)$, rang $1 \implies$ multipl. geom. $=1<$ multipl. alg. $=2$.

Deci **NU** e diagonalizabilă — mergi pe rețeta cu bloc Jordan (exact ca la exercițiul 32 din fișa cu ecuații și sisteme).

Vector propriu: $(A-4I)v=0 \Rightarrow v_1-v_2=0 \Rightarrow v=(1, 1)^T$

Vector generalizat $w$, din $(A-4I)w=v$: $w_1-w_2=1$; alegi $w_2=0 \Rightarrow w=(1, 0)^T$

**Mișcarea 2 — $P$, $J$ și $e^{At}$**

$P=(v\mid w)$ are liniile $(1,1)$ și $(1,0)$; $J$ are liniile $(4,1)$ și $(0,4)$; $e^{Jt}=e^{4t}\cdot M$ unde $M$ are liniile $(1,t)$ și $(0,1)$.

Produsul $Pe^{Jt}$ dă o matrice cu liniile $e^{4t}(1,\ t+1)$ și $e^{4t}(1,\ t)$.

(la fel ca la ex. 32: **nu calculezi efectiv $P^{-1}$**, pui direct $P^{-1}(c_1,c_2)^T=(k_1,k_2)^T$)

**Mișcarea 3 — soluția generală și condițiile inițiale**

$$X(t)=Pe^{Jt}(k_1,k_2)^T \implies x(t)=k_1e^{4t}+k_2(t+1)e^{4t},\qquad y(t)=k_1e^{4t}+k_2te^{4t}$$

$$x(0)=k_1+k_2=0,\qquad y(0)=k_1=1 \implies k_1=1,\ k_2=-1$$

$$x(t)=e^{4t}\big[1-(t+1)\big]=-te^{4t},\qquad y(t)=e^{4t}(1-t)$$

$$\boxed{x(t)=-te^{4t},\qquad y(t)=(1-t)e^{4t}}$$

**Verificare** (obligatorie când ai valoare proprie dublă — se greșește ușor la $w$): derivezi soluția găsită direct și o compari cu partea dreaptă a sistemului, calculată tot cu soluția găsită. Dacă coincid, e corectă.

Derivarea lui $x(t)=-t\cdot e^{4t}$ e un produs, deci regula produsului $(uv)'=u'v+uv'$ cu $u=-t$ ($u'=-1$) și $v=e^{4t}$ ($v'=4e^{4t}$):

$$x'(t) = (-1)e^{4t} + (-t)(4e^{4t}) = -e^{4t}-4te^{4t} = -e^{4t}(1+4t)$$

La fel pentru $y(t)=(1-t)e^{4t}$, cu $u=1-t$ ($u'=-1$):

$$y'(t) = (-1)e^{4t} + (1-t)(4e^{4t}) = e^{4t}\big[-1+4(1-t)\big] = e^{4t}(3-4t)$$

Acum compari cu partea dreaptă a sistemului original, calculată cu $x(t)$ și $y(t)$ găsite:

$$5x-y = 5(-te^{4t}) - (1-t)e^{4t} = e^{4t}(-5t-1+t) = -e^{4t}(4t+1) = x' \quad ✓$$
$$x+3y = -te^{4t} + 3(1-t)e^{4t} = e^{4t}(-t+3-3t) = e^{4t}(3-4t) = y' \quad ✓$$

---

## (c) $x'=x-y,\ y'=-4x+y,\ x(0)=1,\ y(0)=-2$

**Mișcarea 1 — matricea și spectrul**

$A$ are liniile $(1,-1)$ și $(-4,1)$. $p_A(\lambda)=(1-\lambda)^2-4=0 \implies 1-\lambda=\pm2$

$$\lambda_1=-1,\qquad \lambda_2=3 \quad\text{(reale, distincte)}$$

Vectori proprii:

$$(A+I)v=0 \Rightarrow 2v_1-v_2=0 \Rightarrow v_1=(1,2)^T$$
$$(A-3I)v=0 \Rightarrow -2v_1-v_2=0 \Rightarrow v_2=(1,-2)^T$$

**Mișcarea 2 — soluția generală**

$$X(t)=C_1e^{-t}v_1+C_2e^{3t}v_2 \implies x(t)=C_1e^{-t}+C_2e^{3t},\qquad y(t)=2C_1e^{-t}-2C_2e^{3t}$$

**Mișcarea 3 — condițiile inițiale**

$$x(0)=C_1+C_2=1,\qquad y(0)=2C_1-2C_2=-2 \iff C_1-C_2=-1 \implies C_1=0,\ C_2=1$$

$$\boxed{x(t)=e^{3t},\qquad y(t)=-2e^{3t}}$$

**Verificare:** $x'=3e^{3t}=x-y=e^{3t}+2e^{3t}$ ✓; $y'=-6e^{3t}=-4x+y=-4e^{3t}-2e^{3t}$ ✓

---

## De reținut

Trei fețe ale aceluiași subiect (P4 din `GHIDURI/cram-algaed.html`):
- **(a)** — cazul simplu, valori proprii reale distincte.
- **(b)** — valoare proprie **dublă cu un singur vector propriu** → bloc Jordan, vector generalizat din $(A-\lambda I)w=v$, apar termeni în $t\cdot e^{\lambda t}$. Verifică mereu rangul lui $A-\lambda I$ înainte să presupui diagonalizare directă.
- **(c)** — din nou reale distincte, dar observă cum una din constante ($C_1$) a ieșit $0$ — e normal, nu e semn de greșeală.
