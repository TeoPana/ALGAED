# Exercițiul 33 — sistem de ecuații diferențiale cu valori proprii complexe

Sursă: `Fisa exercitii - ecuatii si sisteme de ecuatii diferentiale.pdf`, pagina 11.

Sistemul e $X' = AX$ cu $A$ având liniile $(-1,\ 5)$ și $(-1,\ 1)$, și condiții inițiale $x(0)=-1,\ y(0)=1$ (alea se văd doar în ecuațiile finale, dar de-acolo se deduc).

## Mișcarea 1 — valorile și vectorii proprii

Polinomul caracteristic:

$$p_A(\lambda) = \lambda^2 + 4 = 0 \implies \lambda_{1,2} = \pm 2i$$

Valori proprii complexe, deci treci direct la forma reală (nu mai cauți vector propriu separat pentru fiecare, doar pentru $\lambda_1 = 2i$):

$$(A - 2iI)v = 0 \implies v = \begin{pmatrix} 1-2i \\ 1 \end{pmatrix}$$

**Verificare rapidă dacă vrei să reconstruiești singur:** din $A - 2i I$ cu liniile $(-1-2i,\ 5)$ și $(-1,\ 1-2i)$, linia a doua dă $-v_1+(1-2i)v_2=0 \Rightarrow v_1=(1-2i)v_2$; iei $v_2=1 \Rightarrow v_1=1-2i$.

## Mișcarea 2 — matricea reală P și $e^{At}$

Separi partea reală și partea imaginară a lui $v$:

$$\mathrm{Re}(v) = \begin{pmatrix}1\\1\end{pmatrix}, \quad \mathrm{Im}(v) = \begin{pmatrix}-2\\0\end{pmatrix} \implies P = \begin{pmatrix}1 & -2\\1 & 0\end{pmatrix}$$

Pentru $\lambda = \alpha \pm i\beta$ (aici $\alpha=0,\ \beta=2$), forma reală standard e:

$$e^{Dt} = \begin{pmatrix}\cos 2t & \sin 2t \\ -\sin 2t & \cos 2t\end{pmatrix}$$

**Regula pe care o folosești mereu la subiectul ăsta:** $e^{At} = Pe^{Dt}P^{-1}$, dar **nu calculezi efectiv $P^{-1}$** — pui direct $P^{-1}(c_1,\,c_2)^T = (k_1,\,k_2)^T$ (constante arbitrare noi) și continui doar cu $P\cdot e^{Dt}$.

$$P \cdot e^{Dt} = \begin{pmatrix}1 & -2\\1 & 0\end{pmatrix}\begin{pmatrix}\cos 2t & \sin 2t \\ -\sin 2t & \cos 2t\end{pmatrix} = \begin{pmatrix}\cos 2t+2\sin 2t & \sin 2t-2\cos 2t \\ \cos 2t & \sin 2t\end{pmatrix}$$

## Mișcarea 3 — soluția generală și constantele

$$X(t) = (Pe^{Dt})\begin{pmatrix}k_1\\k_2\end{pmatrix} \implies \begin{cases}x(t) = k_1(\cos 2t+2\sin 2t)+k_2(\sin 2t-2\cos 2t)\\ y(t) = k_1\cos 2t + k_2\sin 2t\end{cases}$$

Pui $t=0$ ($\cos 0=1,\ \sin 0=0$):

$$\begin{cases}x(0) = k_1 - 2k_2 = -1\\ y(0) = k_1 = 1\end{cases} \implies k_1=1,\ k_2=1$$

Înlocuiești și grupezi termenii după $\sin 2t$ și $\cos 2t$:

$$\begin{cases}x(t) = 3\sin 2t - \cos 2t\\ y(t) = \sin 2t + \cos 2t\end{cases}$$

## De reținut pentru examen

E exact tipul P4 din `GHIDURI/cram-algaed.html`: de îndată ce polinomul caracteristic dă $\lambda=\pm i\beta$ (fără parte reală), soluția e o combinație de $\sin$ și $\cos$ — practic o curbă închisă (elipsă/cerc) în planul de fază, nu exponențială crescătoare/descrescătoare.
