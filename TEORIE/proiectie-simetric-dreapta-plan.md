# Proiecția și simetricul unui punct față de o dreaptă / un plan

Notă de teorie, din gap-urile de seminar (Alg_sem_1, Alg_sem_9) — completează `TEORIE/geometrie-analitica-plan-dreapta.md`.

## Rețeta — proiecția unui punct pe o dreaptă, și simetricul

Dreaptă $d$ prin punctul $M_0$ cu direcția $v$; punct $A$ de proiectat.

1. Scrii planul $\pi_1$ perpendicular pe $d$ ce conține $A$ — normala lui $\pi_1$ e chiar $v$.
2. Intersectezi $\pi_1$ cu $d$ → punctul de proiecție $B$.
3. Simetricul $C$ față de dreaptă: $B$ e mijlocul lui $[AC]$, deci $C = 2B - A$.

## Rețeta — proiecția unui punct pe un plan, și simetricul

Plan $\pi$ cu normala $n$; punct $A$ de proiectat.

1. Scrii dreapta $d_1$ prin $A$, perpendiculară pe $\pi$ — direcția lui $d_1$ e chiar $n$.
2. Intersectezi $d_1$ cu $\pi$ → punctul de proiecție $D$.
3. Simetricul $E$ față de plan: $D$ e mijlocul lui $[AE]$, deci $E = 2D - A$.

**Observație:** cele două rețete sunt "în oglindă" — la dreaptă, planul perpendicular e cel pe care-l intersectezi; la plan, dreapta perpendiculară e cea pe care o intersectezi. Nu le încurca.

## Exemplu verificat — proiecție pe dreaptă

$A(2,1,1)$, dreapta $d$: $\dfrac{x}{1}=\dfrac{y-1}{1}=\dfrac{z}{2}$ (deci direcția $v=(1,1,2)$, punct pe $d$: $(0,1,0)$).

**Mișcarea 1:** planul $\pi_1$ perpendicular pe $d$ prin $A$, cu normala $v=(1,1,2)$:

$$1(x-2)+1(y-1)+2(z-1)=0 \implies x+y+2z=5$$

**Mișcarea 2:** parametrizezi $d$: $(x,y,z)=(t,\ 1+t,\ 2t)$, înlocuiești în $\pi_1$:

$$t+(1+t)+2(2t)=5 \implies 6t+1=5 \implies t=\tfrac23$$

$$B = \left(\tfrac23,\ \tfrac53,\ \tfrac43\right)$$

**Mișcarea 3:** simetricul $C=2B-A$:

$$C = \left(\tfrac43-2,\ \tfrac{10}3-1,\ \tfrac83-1\right) = \left(-\tfrac23,\ \tfrac73,\ \tfrac53\right)$$

**Verificare:** $B$ trebuie să fie pe $d$ (verifici direct: $2/3=2/3$, $(5/3-1)/1=2/3$, $(4/3)/2=2/3$ — toate egale, e pe dreaptă ✓) și $\overrightarrow{AB}$ trebuie să fie perpendicular pe... de fapt paralel cu $v$ (verifici $\overrightarrow{AB}=B-A=(-4/3,2/3,1/3)$ e proporțional cu $v=(1,1,2)$? Nu direct — dar $B$ satisface deja $\pi_1$ și $d$ simultan, ceea ce garantează corectitudinea).

## Exemplu verificat — proiecție pe plan

$A(2,1,1)$, planul $\pi: 2x+y-3z=-5$ (normala $n=(2,1,-3)$).

**Mișcarea 1:** dreapta $d_1$ prin $A$ cu direcția $n$: $(x,y,z)=(2+2t,\ 1+t,\ 1-3t)$.

**Mișcarea 2:** înlocuiești în $\pi$:

$$2(2+2t)+(1+t)-3(1-3t)=-5 \implies 2+14t=-5 \implies t=-\tfrac12$$

$$D = \left(1,\ \tfrac12,\ \tfrac52\right)$$

**Verificare:** $2(1)+\tfrac12-3\cdot\tfrac52 = 2+0{,}5-7{,}5=-5$ ✓ (satisface $\pi$).

**Mișcarea 3:** simetricul $E=2D-A$:

$$E = (2-2,\ 1-1,\ 5-1) = (0,\ 0,\ 4)$$

## De reținut

- **Recunoaștere:** dacă cerința e "proiecția lui $A$ pe [dreaptă/plan]" urmată de "simetricul", rețeta e mereu în 3 pași: (1) obiectul perpendicular prin $A$, (2) intersecția, (3) $2\times\text{proiecție}-A$.
- Verificarea proiecției e gratuită: trebuie să satisfacă simultan ecuația dreptei/planului ȘI să fie pe perpendiculara prin $A$ — dacă ai greșit undeva, una din cele două verificări pică.
