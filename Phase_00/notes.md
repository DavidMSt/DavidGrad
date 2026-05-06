# Notes Phase 0

We use a 1D Mass-spring-damper model. In this example, given by:

$\sum F = -kx-c\dot x + F_{\text{external}} = m\ddot x$

The externally applied forces here are the input we have for the system, $F_{\text{external}}=0$ we have a passive system .
 

$\sum F = -kx-c\dot x = m\ddot x \leftrightarrow \ddot x = -\frac {kx}{m} -\frac{c\dot x}{m}$

Modifiying into first order partial differentiators with $q=x$ and $\dot q = \dot x$, gives: 

$$
\begin{align*}
q_1 &= \dot x\\
q_2 &= -\frac{k}{m}x - \frac {c}{m}q_1
\end{align*}
$$