A a B sa dohodnú na veľkom prvočásle a čísle s, 1 < s < p,
Čísla s,p môžu byť verejné, použiteľné opakovane aj pre viac používateľov.

A:
- zvolí a < p tajné
- vypočíta $\alpha = s^a \mod p$
- odošle $\alpha$
- príjme $\beta$
- vypočíta kľúč $K_A = \beta^a \mod p$

B:
- zvolí b < p tajné
- vypočíta $\beta = s^b \mod p$
- odošle $\beta$
- príjme $\alpha$
- vypočíta kľúč $K_B = \alpha^a \mod p$

nebezpečenstvo: zachytenie hesla ("sprostredkovanie")