# Geometrie analitică — plan mediator, proiecție pe dreaptă, arie triunghi

Notă de teorie, gap identificat la examenul din 2026 (cerința L1) — niciun ghid existent nu acoperea geometria clasică cu puncte/drepte/plane în spațiu.

## Trei formule de bază

$$\langle a,b\rangle = a_1b_1+a_2b_2+a_3b_3,\qquad ‖a‖=\sqrt{\langle a,a\rangle}$$

$$a\times b = (a_2b_3-a_3b_2,\ a_3b_1-a_1b_3,\ a_1b_2-a_2b_1)$$

$a\times b$ e perpendicular pe amândoi $a$ și $b$ — de-asta e util ca **normală de plan** sau ca bază pentru arii.

## Rețeta 1 — planul mediator al unui segment $[AB]$

Planul mediator = planul care trece prin mijlocul lui $[AB]$ și e perpendicular pe $AB$.

1. Mijlocul: $M = (A+B)/2$.
2. Normala planului = direcția $\overrightarrow{AB} = B-A$.
3. Ecuația planului prin $M$ cu normala $n$: $n_1(x-M_1)+n_2(y-M_2)+n_3(z-M_3)=0$.

**Exemplu verificat** ($A(0,2,4)$, $B(2,0,-2)$): $M=(1,1,1)$, $\overrightarrow{AB}=(2,-2,-6)\sim(1,-1,-3)$.

$$1(x-1)-1(y-1)-3(z-1)=0 \implies x-y-3z+3=0$$

## Rețeta 2 — proiecția unui punct pe o dreaptă

Dreapta trece prin $A$ cu direcția $d$. Punctul de proiectat e $C$.

1. $\overrightarrow{AC}=C-A$.
2. $t = \dfrac{\overrightarrow{AC}\cdot d}{d\cdot d}$ (parametrul pe dreaptă unde cade proiecția).
3. Proiecția: $P = A+t\cdot d$.

**Exemplu verificat** ($C(1,-1,3)$, dreapta $AB$ cu $d=(1,-1,-3)$): $\overrightarrow{AC}=(1,-3,-1)$, $t=\dfrac{1+3+3}{1+1+9}=\dfrac{7}{11}$.

$$P = A+\frac{7}{11}d = \left(\frac{7}{11}, \frac{15}{11}, \frac{23}{11}\right)$$

## Rețeta 3 — aria unui triunghi din produs vectorial

$$\mathrm{Aria}(\triangle ABC) = \frac12 ‖\overrightarrow{AB}\times\overrightarrow{AC}‖$$

**Exemplu verificat:** $\overrightarrow{AB}=(2,-2,-6)$, $\overrightarrow{AC}=(1,-3,-1)$.

$$\overrightarrow{AB}\times\overrightarrow{AC} = (-16,-4,-4) \implies \mathrm{Aria}=\frac12\sqrt{256+16+16}=\frac12\sqrt{288}=6\sqrt2$$

## De reținut

- **Recunoaștere:** dacă enunțul dă puncte concrete în $\mathbb{R}^3$ (nu vectori abstracți dintr-un spațiu vectorial), e aproape sigur geometrie analitică clasică — folosește produs scalar/vectorial direct, nu Gram-Schmidt.
- Planul mediator și proiecția pe dreaptă folosesc **aceeași direcție** ca "normală"/"vector director" — nu le confunda: pentru plan, direcția segmentului e *normala*; pentru proiecție pe dreaptă, aceeași direcție e *vectorul director* al dreptei.
- Vezi rezolvarea completă la (L1) în `SUBIECTE/Subiecte Examen 2026 - rezolvare.md`.
