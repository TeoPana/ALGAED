# Subiecte Examen 2026 — rezolvare completă

Rezolvare pentru `Subiecte Examen 2026.jpg`. Toate rezultatele verificate prin înlocuire directă.

---

## (S) Aplicație liniară, Ker, Im, proiecție

$f:\mathbb{R}_{\le2}[X]\to\mathbb{R}^3$, $f(P)=(P(0)-P'(0),\ P(1)-P(0),\ -P(0)+2P'(0)+P'(1))$.

**(a)** Pentru $P=a+bX+cX^2$: $P(0)=a$, $P'(0)=b$, $P(1)=a+b+c$, $P'(1)=b+2c$.

$$f(P) = (a-b,\ b+c,\ -a+3b+2c)$$

Matricea lui $f$ în raport cu bazele canonice (coloane = imaginile lui $1,X,X^2$):

$$M=\begin{pmatrix}1&-1&0\\0&1&1\\-1&3&2\end{pmatrix}$$

**Ker(f):** $Ma=0 \Rightarrow a=b,\ c=-b$, a treia ecuație e redundantă. Cu $b=t$: $(a,b,c)=t(1,1,-1)$.

$$\mathrm{Ker}(f)=\mathrm{Sp}\{1+X-X^2\},\qquad \dim\mathrm{Ker}(f)=1$$

Din teorema rangului: $\dim\mathrm{Im}(f)=3-1=2$. Verifici că $f(X^2)=(0,1,2)=f(1)+f(X)$ (dependent), deci:

$$\mathrm{Im}(f)=\mathrm{Sp}\{(1,0,-1),\,(-1,1,3)\},\qquad \dim\mathrm{Im}(f)=2$$

**(b)** $v=(0,1,2)$ — observă că e exact $f(X^2)$, deja arătat mai sus ca fiind combinația $(1,0,-1)+(-1,1,3)$. Deci $v\in\mathrm{Im}(f)$ **direct, fără calcul**:

$$\mathrm{pr}_{\mathrm{Im}(f)}v = v = (0,1,2),\qquad \mathrm{pr}_{\mathrm{Im}(f)^\perp}v = 0$$

**Interpretare geometrică:** $v$ se află complet în planul $\mathrm{Im}(f)$ (normala planului e $(1,0,-1)\times(-1,1,3)=(1,-2,1)$; verifici $v\cdot(1,-2,1)=0-2+2=0$ ✓) — nu are nicio componentă perpendiculară pe imagine.

---

## (L1) Plan mediator, proiecție pe dreaptă, arie triunghi

$A(0,2,4)$, $B(2,0,-2)$, $C(1,-1,3)$.

**(a)** Mijlocul $[AB]$: $M=(1,1,1)$. Direcția $AB=(2,-2,-6)\sim(1,-1,-3)$ = normala planului mediator.

$$1(x-1)-1(y-1)-3(z-1)=0 \implies \boxed{x-y-3z+3=0}$$

**(b)** Proiecția lui $C$ pe dreapta $AB$: $\overrightarrow{AC}=(1,-3,-1)$, $d=(1,-1,-3)$.

$$t=\frac{\overrightarrow{AC}\cdot d}{d\cdot d}=\frac{1+3+3}{1+1+9}=\frac{7}{11}$$

$$P_{\mathrm{proiecție}} = A+t\,d = \left(\frac{7}{11},\,\frac{15}{11},\,\frac{23}{11}\right)$$

**Aria $\triangle ABC$:** $\overrightarrow{AB}\times\overrightarrow{AC} = (2,-2,-6)\times(1,-3,-1) = (-16,-4,-4)$

$$\mathrm{Aria}=\frac12\|\overrightarrow{AB}\times\overrightarrow{AC}\| = \frac12\sqrt{256+16+16}=\frac12\sqrt{288}=\boxed{6\sqrt2}$$

---

## (L2) Bază, dimensiune, coordonate într-un subspațiu din 5 vectori

$v_1=(1,2,3,4)$, $v_2=(1,-1,0,1)$, $v_3=(3,0,3,6)$, $v_4=(0,1,0,1)$, $v_5=(2,2,3,6)$.

**(a)** Rezolvi $v_3=av_1+bv_2$: din componentele 1 și 3, $a=1,b=2$ — verifici pe toate 4 componentele, iese exact. $v_3=v_1+2v_2$, **dependent**.

Rezolvi $v_5=av_1+bv_2+cv_4$: din componenta 3, $a=1$; din componenta 1, $b=1$; din componenta 2, $c=1$ — verifici pe a 4-a componentă, iese exact. $v_5=v_1+v_2+v_4$, **dependent**.

$v_1,v_2,v_4$ rămân independente (rang 3, verificat prin eliminare Gauss).

$$\text{bază: }\{v_1,v_2,v_4\},\qquad \dim_{\mathbb{R}}W=3$$

**(b)** $w=(2,0,3,4)=a\,v_1+b\,v_2+c\,v_4$: din comp. 3, $a=1$; din comp. 1, $b=1$; din comp. 2, $2-1+c=0\Rightarrow c=-1$; verifici comp. 4: $4+1-1=4$ ✓.

$$w = v_1+v_2-v_4 \in W,\qquad \text{coordonate: }(1,\,1,\,-1)$$

---

## (L3) Aplicație liniară pe matrice: comutatorul $f(X)=AX-XA$

$A$ are liniile $(1,2)$ și $(2,1)$.

**(a)** Calculezi $f$ pe fiecare element al bazei canonice $\{E_{11},E_{12},E_{21},E_{22}\}$:

$$f(E_{11})=\begin{pmatrix}0&-2\\2&0\end{pmatrix},\quad f(E_{12})=\begin{pmatrix}-2&0\\0&2\end{pmatrix},\quad f(E_{21})=\begin{pmatrix}2&0\\0&-2\end{pmatrix},\quad f(E_{22})=\begin{pmatrix}0&2\\-2&0\end{pmatrix}$$

Matricea lui $f$ (coloane = imaginile de mai sus, ca vectori în $\mathbb{R}^4$):

$$M_f=\begin{pmatrix}0&-2&2&0\\-2&0&0&2\\2&0&0&-2\\0&2&-2&0\end{pmatrix}$$

**(b)** Observi $f(E_{21})=-f(E_{11})$ și $f(E_{22})=-f(E_{12})$ — doar 2 coloane independente.

$$\mathrm{Im}(f)=\mathrm{Sp}\left\{\begin{pmatrix}0&-2\\2&0\end{pmatrix},\ \begin{pmatrix}-2&0\\0&2\end{pmatrix}\right\},\qquad \dim\mathrm{Im}(f)=2$$

---

## (L4) Matrice diagonalizabile cu aceiași vectori proprii

**(a)** $A=PDP^{-1}$, $B=PD'P^{-1}$ (același $P$, fiindcă au aceiași vectori proprii). Matricele diagonale comută întotdeauna ($DD'=D'D$), deci:

$$AB = PDP^{-1}PD'P^{-1}=PDD'P^{-1}=PD'DP^{-1}=PD'P^{-1}PDP^{-1}=BA$$

**(b)** $A$ are liniile $(1,1)$ și $(0,2)$: valori proprii $1,2$ (matrice triunghiulară). Vectori proprii: $\lambda=1\to(1,0)$; $\lambda=2\to(1,1)$.

$B_m$ are liniile $(m,1)$ și $(0,3)$: $(1,0)$ e automat vector propriu al lui $B_m$ pentru orice $m$ (valoare proprie $m$). Pentru ca $(1,1)$ să fie și el vector propriu: $B_m(1,1)^T=(m+1,\,3)^T$ trebuie să fie multiplu de $(1,1)^T$, deci $m+1=3$.

$$\boxed{m=2}$$

**Interpretare geometrică:** cu $m=2$, $A$ și $B_2$ acționează ca întinderi de-a lungul acelorași două direcții fixe $(1,0)$ și $(1,1)$ — $A$ întinde de $1\times$, respectiv $2\times$; $B_2$ întinde de $2\times$, respectiv $3\times$. Fiindcă au aceleași direcții invariante, aplicate în orice ordine dau aceeași transformare compusă (comută, conform (a)).

---

## (E1) Complement ortogonal (4D) și dreaptă de regresie

**(a)** $U=\mathrm{Sp}\{(1,1,1,1),\,(-5,-2,3,4)\}$. Rezolvi $x\cdot u_1=0,\ x\cdot u_2=0$:

$$x_1+x_2+x_3+x_4=0,\qquad -5x_1-2x_2+3x_3+4x_4=0$$

Cu $x_3=s,\ x_4=t$ liberi: $x_1=\dfrac{5s+6t}{3},\ x_2=-\dfrac{8s+9t}{3}$. Alegi $(s,t)=(3,0)$ și $(0,3)$:

$$w_1=(5,-8,3,0),\qquad w_2=(2,-3,0,1)$$

Gram-Schmidt: $e_1=w_1/\|w_1\|=(5,-8,3,0)/(7\sqrt2)$. Ortogonalizezi $w_2$ față de $w_1$ ($w_1\cdot w_2=34$, $\|w_1\|^2=98$):

$$w_2'=w_2-\frac{34}{98}w_1=\frac{1}{49}(13,-11,-51,49),\qquad \|w_2'\cdot49\|=42\sqrt3$$

$$U^\perp\text{: bază ortonormată } \left\{\frac{(5,-8,3,0)}{7\sqrt2},\ \frac{(13,-11,-51,49)}{42\sqrt3}\right\}$$

**(b)** Puncte $(-5,-2),(-2,0),(3,3),(4,5)$. $\Sigma x=0,\ \Sigma y=6,\ \Sigma xy=39,\ \Sigma x^2=54$ ($n=4$).

$$m=\frac{n\Sigma xy-\Sigma x\Sigma y}{n\Sigma x^2-(\Sigma x)^2}=\frac{4\cdot39}{4\cdot54}=\frac{13}{18},\qquad b=\frac{\Sigma y-m\Sigma x}{n}=\frac{6}{4}=\frac32$$

$$\boxed{y=\frac{13}{18}x+\frac32}$$

(grafic: dreaptă crescătoare, pantă $\approx0{,}72$, taie $Oy$ la $1{,}5$; cele 4 puncte urmăresc aproximativ traiectoria — de exemplu la $x=4$, dreapta dă $y\approx4{,}39$, apropiat de punctul real $(4,5)$.)

---

## (E2) Matrice din vectori/valori proprii, optimizare formă pătratică

**(a)** $v_1=\tfrac15(4,3)$, $v_2=\tfrac15(-3,4)$ — ortonormați (verifici $v_1\cdot v_2=0$, $\|v_i\|=1$), deci $A$ simetrică: $A=PDP^T$ cu $P=\tfrac15$ având liniile $(4,-3)$ și $(3,4)$, $D=\mathrm{diag}(1,-1)$.

$$A = \frac{1}{25}\begin{pmatrix}4&3\\3&-4\end{pmatrix}\begin{pmatrix}4&3\\-3&4\end{pmatrix} = \boxed{\frac{1}{25}\begin{pmatrix}7&24\\24&-7\end{pmatrix}}$$

(verificare: $\mathrm{tr}(A)=0=\lambda_1+\lambda_2$ ✓; $\det A=-1=\lambda_1\lambda_2$ ✓)

**Interpretare geometrică:** valori proprii $\pm1$, matrice simetrică $\Rightarrow$ $A$ e o **reflexie** — reflectă planul față de dreapta generată de $v_1$ (direcția fixă, $\lambda=1$), inversând direcția perpendiculară ($v_2$, $\lambda=-1$).

**(b)** Din rezultatul general (exercițiul 7 din `Exercitii 8.pdf`): $\min q = \lambda_{\min}$, $\max q=\lambda_{\max}$ pe cercul unitate.

$$\min q(v) = -1 \ (\text{la } v_2), \qquad \max q(v) = 1\ (\text{la } v_1)$$

---

## (E3) Gram-Schmidt + ecuație diferențială cu coeficienți din partea (a)

**(a)** $v_1=(1,2)$, $v_2=(3,1)$. Gram-Schmidt: $v_1\cdot v_2=5$, $\|v_1\|^2=5$, deci

$$f_1=v_1=(1,2),\qquad f_2=v_2-\frac{5}{5}v_1=(3,1)-(1,2)=(2,-1)$$

Coordonatele lui $w=(4,3)$ în baza ortogonală $\{f_1,f_2\}$ (nenormalizată — de-asta se numesc $\alpha$, nu proiecții pe versori):

$$\alpha_1=\frac{w\cdot f_1}{\|f_1\|^2}=\frac{4+6}{5}=2,\qquad \alpha_2=\frac{w\cdot f_2}{\|f_2\|^2}=\frac{8-3}{5}=1$$

(verificare: $2(1,2)+1(2,-1)=(4,3)=w$ ✓)

**(b)** $x'=\alpha_1x+\alpha_2e^t=2x+e^t$, $x(0)=1$.

Omogenă: $x_h=Ce^{2t}$. Particulară: $\mu=1$ nu e rădăcină ($\lambda=2$), $x_p=ae^t$: $ae^t=2ae^t+e^t\Rightarrow a=-1$.

$$x(t)=Ce^{2t}-e^t,\qquad x(0)=C-1=1\Rightarrow C=2$$

$$\boxed{x(t)=2e^{2t}-e^t}$$

(verificare: $x'=4e^{2t}-e^t=2x+e^t=2(2e^{2t}-e^t)+e^t=4e^{2t}-e^t$ ✓)

---

## (E4) Sistem de EDO, direcții invariante $y=kx$

**(a)** $x'=2x-y,\ y'=3x-2y$. $A$ are liniile $(2,-1)$ și $(3,-2)$, $\det(A-\lambda I)=\lambda^2-1=0\Rightarrow\lambda=\pm1$.

$\lambda=1$: $(A-I)v=0\Rightarrow v_1=v_2\Rightarrow v=(1,1)$. $\lambda=-1$: $(A+I)v=0\Rightarrow v_2=3v_1\Rightarrow v=(1,3)$.

$$\boxed{X(t)=C_1e^{t}(1,1)+C_2e^{-t}(1,3)}$$

**(a) [a doua cerință]** Caută $y=kx$: din $y'=kx'$ și sistem, $(3-2k)x=(2k-k^2)x$ pentru orice $x$ $\Rightarrow k^2-4k+3=0\Rightarrow(k-1)(k-3)=0$.

$$\boxed{k=1\ \text{sau}\ k=3}$$

Nu e o coincidență — sunt exact pantele $y/x$ ale celor doi vectori proprii $(1,1)$ și $(1,3)$: liniile $y=x$ și $y=3x$ sunt traiectorii invariante (soluții-drepte) ale sistemului.

---

## (E5) Ecuație de ordin 2 cu rezonanță — Cauchy

$x''+3x'+2x=e^{-t+1}=e\cdot e^{-t}$, $x(0)=0,\ x'(0)=e$.

Omogenă: $\lambda^2+3\lambda+2=(\lambda+1)(\lambda+2)=0\Rightarrow\lambda=-1,-2$. $x_h=C_1e^{-t}+C_2e^{-2t}$.

$\mu=-1$ **este** rădăcină (simplă) $\Rightarrow$ rezonanță, $m=1$: $x_p=a\,t\,e^{-t}$.

$$x_p''+3x_p'+2x_p = ae^{-t}(t-2)+3ae^{-t}(1-t)+2ate^{-t}=ae^{-t}\big[(t-2)+3(1-t)+2t\big]=ae^{-t}$$

$$ae^{-t}=e\cdot e^{-t}\implies a=e \implies x_p=e\,t\,e^{-t}=t\,e^{1-t}$$

$$x(t)=C_1e^{-t}+C_2e^{-2t}+te^{1-t}$$

$$x(0)=C_1+C_2=0,\qquad x'(0)=-C_1-2C_2+e=e\implies -C_1-2C_2=0$$

Din cele două: $C_1=-C_2$ și $C_1=-2C_2\Rightarrow -C_2=-2C_2\Rightarrow C_2=0\Rightarrow C_1=0$.

$$\boxed{x(t)=t\,e^{1-t}}$$

**Verificare directă:** $x(0)=0$ ✓; $x'(t)=e^{1-t}(1-t)$, $x'(0)=e$ ✓; $x''+3x'+2x=e^{1-t}[(t-2)+3(1-t)+2t]=e^{1-t}=e^{-t+1}$ ✓ — partea omogenă dispare complet, soluția e doar termenul particular.

---

## De reținut din subiectul ăsta

- **(S)** și **(E1)(a)** arată același truc: dacă vectorul dat pentru proiecție e vizibil o combinație a generatorilor (sau evident perpendicular pe ei), proiecția iese fără niciun calcul — verifică asta primul.
- **(E3)** — atenție la diferența „bază ortogonală" vs. „ortonormată": dacă enunțul cere coordonate față de baza ortogonală (nenormalizată) din Gram-Schmidt, formula e $\alpha_i=\dfrac{w\cdot f_i}{\|f_i\|^2}$, nu $w\cdot e_i$ direct.
- **(E4)** — a doua cerință (soluții $y=kx$) e practic recunoașterea directă a direcțiilor proprii, fără să mai rezolvi sistemul complet.
- **(E5)** — cazul de rezonanță unde partea omogenă se anulează complet din condițiile inițiale nu e o eroare — verifică mereu cu înlocuire directă înainte să suspectezi o greșeală de calcul.
