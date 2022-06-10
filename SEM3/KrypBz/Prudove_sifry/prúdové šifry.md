$$y_1, y_2, \dots, y_n = E_{k_1}(x_1), E_{k_2}(x_2), \dots,  E_{k_n}(x_n)$$

cézarovskú a vigenerovskú šifru mo%zno upraviť tak, že namiesto operácie (+) vykonáme (*) XOR

šifra one time pad - Vernamova šifra
prúd znakov priameho textu, prúd kľúčov (napríklad z RNG), prúd znakov zašifrovaného textu
kľúč musí byť aspoň tak dlhý, ako je správa, nesmie sa použiť viac ako raz

V prípade útoku pri použití toho istého prúdu viac krát:
postupnosti priameho textu: a, b
kľúč: k
$y_i = a_i (*)k_i$
$z_i = b_i (*) k_i$
vyjadrí sa postupnosť w
$w_i = y_i (*)z_i$=>$w_i = a_i (*)b_i$

postupnosť w je postupnosť znakov jedného priameho textu zašifrovaná postupnosťou iného priameho textu, nesie dostatok informácie na odhalenie postupnosti bitov kľúča
Následne sa posúvajú oba textu voči sebe, pri odhalení správnej vzdialenosti počet zhôd znakov stúpne