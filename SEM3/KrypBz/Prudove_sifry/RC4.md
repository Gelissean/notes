Máme 256 S boxov, ktoré obsahujú niektorú permutáciu čísel 0-255

```c
rand()
i = i + 1 mod 256
j = j + S[i] mod 256
swap(S[i], S[j])
t = (S[i] + S[j]) mod 256
k = S[t]
return k
```
Klúč môže byť až 256*8 = 2048 bitov

inicializácia:
```c
for i = 0 to 255
{
	S[i] = i
}
j = 0
for i = 0 to 255
{
	j = (j + S[i] + K[i]) mod 256
	swap(S[i], S[j])
}
i = 0
j = 0
```

Nachádza sa tu rovnaké nebezpečenstvo pri viacnásobnom používaní rovnakého kľúča ako pri Vernamovej šifre