Galoisove pole $GF(2^8)$ (aj v [[Hill]])
$b_7x^7 + b_6x^6+ b_5x^5 + b_4x^4 + b_3x^3 + b_2x^2 + b_1x^1 + b_0$
takýmto polynómom možno modelovať bajty:
${01010111}$ => $x^6+x^4+x^2+x+1$
sčítaniu bajtov $(+)$ zodpovedá operácia XOR po bitoch
násobenie bajtov $(*)$ sa definuje ako
$p(x) (*)q(x) = p(x).q(x) \mod m(x)$

AES využíva ireducibilný polynóm
$m(x) = x^8+x^4+x^3+x+1$

Inverzný prvok prvku b možno vypočítať rozšíreným Euklidovým algoritmom.
Pre AES stačí vypočítať tabuľku binárnej operácia (\*)(rozmer 256 x 256) a pre každé b =1, ..., 255 nájsť c tak aby $b (*) c = 1$, potom $b^{-1}=c$

platí
$1 = b^{2^8-1} = b^{255} = b * b^244$
teda $b^{-1} = b^{244}$

**AES**
bloková šifra
blok 128b
kľúč 128, 192 alebo 256b

128b priamy text sa berie ako 16 8b bajtov
$a_{00}a_{10}a_{20}a_{30}a_{01}a_{11}a_{21}a_{31}a_{02}a_{12}a_{22}a_{32}a_{03}a_{13}a_{23}a_{33}$
a usporiadajú sa do tabuľky
![[AES_vstup_usporiadanie.png]]
Na každý bajt sa vykonajú dve operácie:
__Operácia SubBytes__
1. ku každému bajtu sa nájde inverzný prvok
2. vypocíta sa bajt
![[AES_vypocet.png]]
__Operácia ShiftRows__
1. prvý riadok ostáva
2. druhý riadok sa posúva o bajt
3. tretí riadok sa posúva o 2 bajty
4. štvrtý riadok sa posúva o 3 bajty

následne sa vykoná **operácia MixColumns**
každý stĺpec vynásobíme maticou M
![[AES_MixColumns.png]]

poslednou operáciou je **operácia AddRoundKey**
kde sa každý bajt sčíta s prvkom príslušného kľúča
$B = A (+) K$

**Šifrovací algoritmus**:
1. Inicializačné kolo
	1. AddRoundKey
2. for Round = 1 to $N_r$ -1
	1. SubBytes
	2. ShiftRows
	3. MixColumns
	4. AddRoundKey
3. Záverečné kolo (bez MixColumns)
	1. SubBytes
	2. ShiftRows
	3. AddRoundKey

**Dešifrovací algoritmus**:
1. Inicializačné kolo
	1. AddRoundKey
2. for Round = 1 to $N_r$ -1
	1. InvSubBytes
	2. InvShiftRows
	3. InvMixColumns
	4. AddRoundKey
3. Záverečné kolo (bez MixColumns)
	1. InvSubBytes
	2. InvShiftRows
	3. AddRoundKey

Poradie InvShiftRows a InvSubBytes je zameniteľné
využíva sa inverzná matica $M^-1$

**Expanzia kľúča**:
ak nie je poradové číslo i deliteľné 4 tak
$W_i = W_{i-4}(+)W_{i-1}$
ak je deliteľné 4 tak
$W_i = W_{i-4} (+) SubByte(RotByte(W_{i-1}))(+)Rcon(i/4)$
kde
$Rcon(i) = [{x^{i-1}}{00}{00}{00}]$
$RotByte[w_1, w_2, w_3, w_4] = [w_2, w_3, w_4, w_1]$