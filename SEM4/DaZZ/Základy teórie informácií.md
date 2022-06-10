Príklad:
skupina s 50 pacientami
$A_1 = \{A_{1,1}; A_{1,2}\} = dedičnosť$,  (5 yes, 45 no)
$A_2 = \{A_{2,1}; A_{2,2}\} = vek$,  (25 young, 25 elder)
$A_3 = \{A_{3,1}; A_{3,2}; \dots; A_{3,49}\} = priezvisko$,  (2 majú rovnaké priezvisko)

**Pravdepodobnosť**
$$p(A) = \frac{m_A}{m_A + m_{\bar{A}}}$$
$$p(A_{1,1})=\frac{5}{5+45}=0,1;p(A_{1,2})=\frac{45}{45+5}=0,9$$
- V prípade $A_{1,2}$ je príliš vysoká pravdepodobnosť, málo informácií

**Informácia**
$$I(A_{i,j}) = -log_2p(A_{i,j}) \textrm{bit}$$
**Entropia** - stredný priemer info
$$H(A_i) = \sum_{j=1}^np(A_{i,j})×I(A_{i,j})\textrm{bit}$$
- suma všetkých informácií daného atribútu × ich pravdepodobnosť

**Pojem informácií**
$$I = H(\textrm{old}) - H(\textrm{new})$$
***
**Pravdepodobnosť**
personálna - $p(A_{j,1})$ a $p(B_{j,2})$
spoločná (joint) - $p(B_{j,2}, A_{j,1}) = p(B_{j,2}× A_{j,1})$
podmienená (condition) - $p(B_{j,2}| A_{j,1}) = p(B_{j,2},A_{j,1})/p(A_{j,1})$

**Informácia**
personálna - $I(A_{j,1})$ a $I(B_{j,2})$
spoločná (joint) - $I(B_{j,2}, A_{j,1})$
podmienená (condition) - $I(B_{j,2}| A_{j,1}) = I(B_{j,2},A_{j,1})-I(A_{j,1})$
vzájomná - $I(B_{j,2}; A_{j,1}) = I(B_{j,2})-I(B_{j,2}|A_{j,1})$
                 - $I(B_{j,2};A_{j,1}) = I(B_{j,2}) + I(A_{j,1}) - I(B_{j,2},A_{j,1})$

**Entropia**
personálna - $H(A)$ a $H(B)$
spoločná (joint) - $H(BA) = \sum\sum p(B_{j,2},A_{j,1})I(B_{j,2},A_{j,1})$
podmienená (condition) - $H(B|A) = H(B,A)-H(A)$
                                         - $H(B|A)=\sum\sum p(B_{j,2},A_{j,1})I(B_{j,2}|A_{j,1})$
vzájomná - $H(B;A) = H(B)-H(B|A)$
                 - $H(B;A) = H(B) + H(A) - H(B,A)$
                 - $H(B;A) = \sum\sum p(B_{j,2},A_{j,1})I(B_{j,2};A_{j,1})$


