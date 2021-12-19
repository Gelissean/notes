AES
Advanced Encryption Standard

Galoisove pole - algebraická štruktúra s operáciami násobenia a sčítania
$GF(2^8) = b_7x^7 + b_6x^6 + b_5x^5 + b_4x^4 + b_3x^3 + b_2x^2 + b_1x^1 + b_0$

sčítanie zodpovedá bajtovej operácií XOR po bitoch

násobenie
$p(x) *  q(x) = p(x).q(x) mod m(x)$

AES používa ireducibilný polynóm $m(x) = x^8 + x^4 + x^3 + 1$.

násobenie číslom 2
![[AES_nasobenie.png]]