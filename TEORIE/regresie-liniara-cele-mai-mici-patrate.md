# Dreapta de regresie (cele mai mici pătrate aplicate la puncte)

Notă de teorie, gap identificat la examenul din 2026 (cerința E1b) — deși metoda celor mai mici pătrate era menționată teoretic în `Exercitii 8.pdf`, nu exista un exemplu concret de dreaptă de regresie.

## Ideea

Ai $n$ puncte $(x_i,y_i)$ care nu stau exact pe o dreaptă. Cauți dreapta $y=mx+b$ care minimizează suma pătratelor abaterilor verticale — asta e exact o problemă de cele mai mici pătrate (pseudosoluție a unui sistem supradeterminat).

## Formulele directe

$$m = \frac{n\Sigma xy - \Sigma x\Sigma y}{n\Sigma x^2 - (\Sigma x)^2},\qquad b = \frac{\Sigma y - m\Sigma x}{n}$$

unde sumele sunt peste toate cele $n$ puncte.

**Scurtătură dacă $\Sigma x=0$** (media lui $x$ e $0$ — verifică asta primul, simplifică enorm): $m=\dfrac{\Sigma xy}{\Sigma x^2}$, $b=\dfrac{\Sigma y}{n}$.

## Exemplu verificat

Puncte $(-5,-2),(-2,0),(3,3),(4,5)$: $n=4$, $\Sigma x=0$, $\Sigma y=6$, $\Sigma xy=39$, $\Sigma x^2=54$.

Cum $\Sigma x=0$, folosești scurtătura:

$$m=\frac{39}{54}=\frac{13}{18},\qquad b=\frac{6}{4}=\frac32$$

$$y = \frac{13}{18}x + \frac32$$

## De unde vin formulele (dacă ți se cere derivarea)

Sistemul supradeterminat $mx_i+b=y_i$ (pentru toate punctele) se scrie matriceal $A\binom{m}{b}=y$ cu $A$ având coloanele $(x_i)$ și $(1)$. Pseudosoluția vine din ecuațiile normale $A^TA\binom{m}{b}=A^Ty$:

$A^TA$ are liniile $(\Sigma x^2,\ \Sigma x)$ și $(\Sigma x,\ n)$; $A^Ty$ are componentele $(\Sigma xy,\ \Sigma y)$.

Rezolvi acest sistem $2\times2$ pentru $m,b$ — de-acolo ies formulele de mai sus.

## De reținut

- **Recunoaștere:** dacă enunțul dă un set de puncte și cere "dreapta de regresie" sau "cea mai bună aproximare liniară", e exact acest tip — nu confunda cu o dreaptă care trece EXACT prin puncte (asta ar fi un sistem determinat, nu regresie).
- Verifică mereu $\Sigma x$ primul — dacă e $0$, calculul se scurtează dramatic.
- Vezi rezolvarea completă la (E1b) în `SUBIECTE/Subiecte Examen 2026 - rezolvare.md`.
