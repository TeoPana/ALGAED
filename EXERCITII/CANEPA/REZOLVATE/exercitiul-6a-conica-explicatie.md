# Exercițiul 6(a) — conică: rotație + translație (cazul complet)

Sursă: `Exercitii 8.pdf`, pagina 5-6. Am ales-o pentru că e **singura din setul (a)-(d) rezolvată integral în PDF** (celelalte trei sunt marcate „Analog") — și pe bună dreptate: e cea mai grea, fiindcă are **și** termen $xy$ (cere rotație), **și** termeni liniari $x,y$ (cere și translație după rotație). Exemplele deja acoperite în `GHIDURI/cram-algaed.html` (P2) au ori doar rotație, ori nu au deloc termeni liniari — asta e cazul "complet", cu ambii pași.

**Enunț:** $5x^2+12xy+10y^2-6x+4y-1=0$. Identifică tipul și adu la forma canonică.

## Mișcarea 1 — matricea formei pătratice, spectrul (partea de rotație)

Coeficientul lui $xy$ e $12$, deci $a_{12}$ = **jumătate** din el = $6$ (capcana clasică — nu uita împărțirea la 2):

$$A = \begin{pmatrix}5&6\\6&10\end{pmatrix}$$

Polinom caracteristic: $(5-\lambda)(10-\lambda)-36=\lambda^2-15\lambda+14=(\lambda-1)(\lambda-14)$

$$\lambda_1=1,\qquad \lambda_2=14$$

**Verificare rapidă:** $\delta=a_{11}a_{22}-a_{12}^2=5\cdot10-36=14>0$ — deja știi că e **elipsă** înainte să continui, doar din semnul lui $\delta$ (și din faptul că $\lambda_1\lambda_2=14=\delta$, tot pozitiv, consistent).

**Vectorii proprii** (normalizați, pentru $P$ ortogonală):

$\lambda=1$: $(A-I)v=0 \implies 2v_1+3v_2=0 \implies v=(3,-2)$, normă $\sqrt{13}$ → $v_1=(3,-2)^T/\sqrt{13}$

$\lambda=14$: $(A-14I)v=0 \implies -3v_1+2v_2=0 \implies v=(2,3)$, normă $\sqrt{13}$ → $v_2=(2,3)^T/\sqrt{13}$

$$P = \frac{1}{\sqrt{13}}\begin{pmatrix}3&2\\-2&3\end{pmatrix},\qquad \det P = \frac{9+4}{13}=1\ \checkmark\ \text{(rotație, nu simetrie)}$$

## Mișcarea 2 — substituția (rotația propriu-zisă)

$$(x,y)^T = P(x',y')^T \implies x=\frac{3x'+2y'}{\sqrt{13}},\quad y=\frac{-2x'+3y'}{\sqrt{13}}$$

Partea pătratică devine automat $\lambda_1x'^2+\lambda_2y'^2 = x'^2+14y'^2$ (nu recalculezi — asta e tot rostul diagonalizării).

Partea liniară — **aici e diferența față de exemplele mai simple**, trebuie efectiv înlocuită:

$$-6x+4y = -6\cdot\frac{3x'+2y'}{\sqrt{13}}+4\cdot\frac{-2x'+3y'}{\sqrt{13}} = \frac{(-18x'-12y')+(-8x'+12y')}{\sqrt{13}} = \frac{-26x'}{\sqrt{13}} = -2\sqrt{13}\,x'$$

(termenul în $y'$ dispare complet — nu e întâmplător: e semnul că axa de simetrie a elipsei e paralelă cu $Ox'$ după rotație.)

Ecuația devine:

$$x'^2+14y'^2-2\sqrt{13}\,x'-1=0$$

## Mișcarea 3 — translația (completarea pătratului, pasul care lipsește din cazurile simple)

Grupezi termenii cu $x'$ și completezi pătratul:

$$x'^2-2\sqrt{13}\,x' = (x'-\sqrt{13})^2-13$$

$$\big[(x'-\sqrt{13})^2-13\big]+14y'^2-1=0 \implies (x'-\sqrt{13})^2+14y'^2-14=0$$

Translația $x''=x'-\sqrt{13},\ y''=y'$ (mută originea în centrul real al elipsei):

$$x''^2+14y''^2=14 \implies \boxed{\dfrac{x''^2}{14}+\dfrac{y''^2}{1}=1}$$

**Elipsă cu semiaxele $\sqrt{14}$ (pe direcția $x''$) și $1$ (pe direcția $y''$).**

## De reținut

- **Recunoaștere rapidă a cazului "greu":** dacă enunțul are **și** $xy$ **și** cel puțin unul din $x,y$ liniar, știi din start că vei avea 2 pași de schimbare de coordonate (rotație + translație), nu unul singur.
- **Semnul care-ți spune că translația a mers bine:** după substituția liniară, dacă unul din termenii liniari (aici cel în $y'$) dispare complet, înseamnă că ai orientat corect axele — elipsa/hiperbola/parabola e simetrică față de acea axă.
- **Diferența față de P2 din `GHIDURI/cram-algaed.html`:** exemplul din ghid ($5x^2+4xy+5y^2-9=0$) nu are termeni liniari, deci se oprește după rotație. Exercițiul ăsta arată pasul următor — ce faci când mai rămân $x,y$ de gradul 1 după rotație.
- **Verificare gratuită înainte să faci tot calculul:** $\delta=a_{11}a_{22}-a_{12}^2$ îți dă tipul din prima secundă ($\delta>0$ elipsă, $=0$ parabolă, $<0$ hiperbolă) — util ca să confirmi la final că forma canonică obținută (aici elipsă) se potrivește cu predicția.
