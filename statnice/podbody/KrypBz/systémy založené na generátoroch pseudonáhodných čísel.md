**Generátor RC4**
- skladá sa z 256 S-Boxov, obsahujú permutáciu čísel 0-255 (8b×256=2048b kľúč)
```c
rand()
i = i + 1 mod 256
j = j + S[i] mod 256
swap(S[i], S[j])
t = (S[i] + S[j]) mod 256
k = S[t]
return k
```
- inicializuje sa pomocou nasledovného kódu
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
