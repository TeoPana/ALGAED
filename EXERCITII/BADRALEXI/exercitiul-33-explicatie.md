# Exercițiul 33 — sistem de ecuații diferențiale cu valori proprii complexe

Sursă: `Fisa exercitii - ecuatii si sisteme de ecuatii diferentiale.pdf`, pagina 11.

Sistemul e $X' = AX$ cu $A$ având liniile $(-1,\ 5)$ și $(-1,\ 1)$, și condiții inițiale $x(0)=-1,\ y(0)=1$ (alea se văd doar în ecuațiile finale, dar de-acolo se deduc).

## Mișcarea 1 — valorile și vectorii proprii

Polinomul caracteristic:

$$p_A(\lambda) = \lambda^2 + 4 = 0 \implies \lambda_{1,2} = \pm 2i$$

Valori proprii complexe, deci treci direct la forma reală (nu mai cauți vector propriu separat pentru fiecare, doar pentru $\lambda_1 = 2i$):

$$(A - 2iI)v = 0 \implies v = (1-2i,\ 1)^T$$

**Verificare rapidă dacă vrei să reconstruiești singur:** din $A - 2i I$ cu liniile $(-1-2i,\ 5)$ și $(-1,\ 1-2i)$, linia a doua dă $-v_1+(1-2i)v_2=0 \Rightarrow v_1=(1-2i)v_2$; iei $v_2=1 \Rightarrow v_1=1-2i$.

## Mișcarea 2 — matricea reală P și $e^{At}$

Separi partea reală și partea imaginară a lui $v$:

$\mathrm{Re}(v)=(1,1)^T$, $\mathrm{Im}(v)=(-2,0)^T \implies P$ are liniile $(1,-2)$ și $(1,0)$.

Pentru $\lambda = \alpha \pm i\beta$ (aici $\alpha=0,\ \beta=2$), forma reală standard $e^{Dt}$ are liniile $(\cos2t,\ \sin2t)$ și $(-\sin2t,\ \cos2t)$.

**Regula pe care o folosești mereu la subiectul ăsta:** $e^{At} = Pe^{Dt}P^{-1}$, dar **nu calculezi efectiv $P^{-1}$** — pui direct $P^{-1}(c_1,c_2)^T = (k_1,k_2)^T$ (constante arbitrare noi) și continui doar cu $P\cdot e^{Dt}$.

Produsul $P \cdot e^{Dt}$ dă o matrice cu liniile $(\cos2t+2\sin2t,\ \sin2t-2\cos2t)$ și $(\cos2t,\ \sin2t)$.

## Mișcarea 3 — soluția generală și constantele

$$X(t) = (Pe^{Dt})(k_1,k_2)^T \implies x(t) = k_1(\cos 2t+2\sin 2t)+k_2(\sin 2t-2\cos 2t),\qquad y(t) = k_1\cos 2t + k_2\sin 2t$$

Pui $t=0$ ($\cos 0=1,\ \sin 0=0$):

$$x(0) = k_1 - 2k_2 = -1,\qquad y(0) = k_1 = 1 \implies k_1=1,\ k_2=1$$

Înlocuiești și grupezi termenii după $\sin 2t$ și $\cos 2t$:

$$x(t) = 3\sin 2t - \cos 2t,\qquad y(t) = \sin 2t + \cos 2t$$

## De reținut pentru examen

E exact tipul P4 din `GHIDURI/cram-algaed.html`: de îndată ce polinomul caracteristic dă $\lambda=\pm i\beta$ (fără parte reală), soluția e o combinație de $\sin$ și $\cos$ — practic o curbă închisă (elipsă/cerc) în planul de fază, nu exponențială crescătoare/descrescătoare.
