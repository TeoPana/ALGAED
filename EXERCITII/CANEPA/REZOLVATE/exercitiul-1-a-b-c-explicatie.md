# Exercițiul 1 (a, b, c) — probleme Cauchy pentru sisteme de EDO liniare

Sursă: `Exercitii 10.pdf`, pagina 1 (enunțuri) / pagina 2 (soluția lui (a), pentru verificare).

---

## (a) $x'=-5x+2y,\ y'=x-6y,\ x(0)=3,\ y(0)=0$

**Mișcarea 1 — matricea și spectrul**

$$A=\begin{pmatrix}-5 & 2\\ 1 & -6\end{pmatrix},\qquad p_A(\lambda)=(\lambda+5)(\lambda+6)-2=\lambda^2+11\lambda+28=(\lambda+4)(\lambda+7)$$

$$\lambda_1=-4,\qquad \lambda_2=-7$$

Vectori proprii:

$$(A+4I)v=0 \Rightarrow -v_1+2v_2=0 \Rightarrow v_1=\begin{pmatrix}2\\1\end{pmatrix}$$
$$(A+7I)v=0 \Rightarrow 2v_1+2v_2=0 \Rightarrow v_2=\begin{pmatrix}-1\\1\end{pmatrix}$$

**Mișcarea 2 — soluția generală**

$$X(t)=C_1e^{-4t}\begin{pmatrix}2\\1\end{pmatrix}+C_2e^{-7t}\begin{pmatrix}-1\\1\end{pmatrix} \implies \begin{cases}x(t)=2C_1e^{-4t}-C_2e^{-7t}\\ y(t)=C_1e^{-4t}+C_2e^{-7t}\end{cases}$$

**Mișcarea 3 — condițiile inițiale**

$$\begin{cases}x(0)=2C_1-C_2=3\\ y(0)=C_1+C_2=0\end{cases} \implies C_2=-C_1 \implies 3C_1=3 \implies C_1=1,\ C_2=-1$$

$$\boxed{x(t)=2e^{-4t}+e^{-7t},\qquad y(t)=e^{-4t}-e^{-7t}}$$

(coincide cu soluția tipărită în PDF, la pagina 2.)

---

## (b) $x'=5x-y,\ y'=x+3y,\ x(0)=0,\ y(0)=1$

**Mișcarea 1 — matricea și spectrul**

$$A=\begin{pmatrix}5 & -1\\ 1 & 3\end{pmatrix},\qquad p_A(\lambda)=(5-\lambda)(3-\lambda)+1=\lambda^2-8\lambda+16=(\lambda-4)^2$$

$\lambda=4$ e rădăcină **dublă**. Verifici dacă e diagonalizabilă:

$$A-4I=\begin{pmatrix}1&-1\\1&-1\end{pmatrix}\ \text{are rang }1 \implies \text{multipl. geom.}=1 < \text{multipl. alg.}=2$$

Deci **NU** e diagonalizabilă — mergi pe rețeta cu bloc Jordan (exact ca la exercițiul 32 din fișa cu ecuații și sisteme).

Vector propriu: $(A-4I)v=0 \Rightarrow v_1-v_2=0 \Rightarrow v=\begin{pmatrix}1\\1\end{pmatrix}$

Vector generalizat $w$, din $(A-4I)w=v$: $w_1-w_2=1$; alegi $w_2=0 \Rightarrow w=\begin{pmatrix}1\\0\end{pmatrix}$

**Mișcarea 2 — $P$, $J$ și $e^{At}$**

$$P=(v\mid w)=\begin{pmatrix}1&1\\1&0\end{pmatrix},\qquad J=\begin{pmatrix}4&1\\0&4\end{pmatrix},\qquad e^{Jt}=e^{4t}\begin{pmatrix}1&t\\0&1\end{pmatrix}$$

$$Pe^{Jt}=e^{4t}\begin{pmatrix}1&1\\1&0\end{pmatrix}\begin{pmatrix}1&t\\0&1\end{pmatrix}=e^{4t}\begin{pmatrix}1&t+1\\1&t\end{pmatrix}$$

(la fel ca la ex. 32: **nu calculezi efectiv $P^{-1}$**, pui direct $P^{-1}\binom{c_1}{c_2}=\binom{k_1}{k_2}$)

**Mișcarea 3 — soluția generală și condițiile inițiale**

$$X(t)=Pe^{Jt}\begin{pmatrix}k_1\\k_2\end{pmatrix} \implies \begin{cases}x(t)=k_1e^{4t}+k_2(t+1)e^{4t}\\ y(t)=k_1e^{4t}+k_2te^{4t}\end{cases}$$

$$\begin{cases}x(0)=k_1+k_2=0\\ y(0)=k_1=1\end{cases} \implies k_1=1,\ k_2=-1$$

$$x(t)=e^{4t}\big[1-(t+1)\big]=-te^{4t},\qquad y(t)=e^{4t}(1-t)$$

$$\boxed{x(t)=-te^{4t},\qquad y(t)=(1-t)e^{4t}}$$

**Verificare** (obligatorie când ai valoare proprie dublă — se greșește ușor la $w$):
$x'=-e^{4t}(1+4t)$ și $5x-y=e^{4t}(-5t-1+t)=-e^{4t}(4t+1)$ ✓
$y'=e^{4t}(3-4t)$ și $x+3y=e^{4t}(-t+3-3t)=e^{4t}(3-4t)$ ✓

---

## (c) $x'=x-y,\ y'=-4x+y,\ x(0)=1,\ y(0)=-2$

**Mișcarea 1 — matricea și spectrul**

$$A=\begin{pmatrix}1&-1\\-4&1\end{pmatrix},\qquad p_A(\lambda)=(1-\lambda)^2-4=0 \implies 1-\lambda=\pm2$$

$$\lambda_1=-1,\qquad \lambda_2=3 \quad\text{(reale, distincte)}$$

Vectori proprii:

$$(A+I)v=0 \Rightarrow 2v_1-v_2=0 \Rightarrow v_1=\begin{pmatrix}1\\2\end{pmatrix}$$
$$(A-3I)v=0 \Rightarrow -2v_1-v_2=0 \Rightarrow v_2=\begin{pmatrix}1\\-2\end{pmatrix}$$

**Mișcarea 2 — soluția generală**

$$X(t)=C_1e^{-t}\begin{pmatrix}1\\2\end{pmatrix}+C_2e^{3t}\begin{pmatrix}1\\-2\end{pmatrix} \implies \begin{cases}x(t)=C_1e^{-t}+C_2e^{3t}\\ y(t)=2C_1e^{-t}-2C_2e^{3t}\end{cases}$$

**Mișcarea 3 — condițiile inițiale**

$$\begin{cases}x(0)=C_1+C_2=1\\ y(0)=2C_1-2C_2=-2 \iff C_1-C_2=-1\end{cases} \implies C_1=0,\ C_2=1$$

$$\boxed{x(t)=e^{3t},\qquad y(t)=-2e^{3t}}$$

**Verificare:** $x'=3e^{3t}=x-y=e^{3t}+2e^{3t}$ ✓; $y'=-6e^{3t}=-4x+y=-4e^{3t}-2e^{3t}$ ✓

---

## De reținut

Trei fețe ale aceluiași subiect (P4 din `GHIDURI/cram-algaed.html`):
- **(a)** — cazul simplu, valori proprii reale distincte.
- **(b)** — valoare proprie **dublă cu un singur vector propriu** → bloc Jordan, vector generalizat din $(A-\lambda I)w=v$, apar termeni în $t\cdot e^{\lambda t}$. Verifică mereu rangul lui $A-\lambda I$ înainte să presupui diagonalizare directă.
- **(c)** — din nou reale distincte, dar observă cum una din constante ($C_1$) a ieșit $0$ — e normal, nu e semn de greșeală.
