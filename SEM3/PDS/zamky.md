riadenie transakcií pomocou zamykania
dva druhy zámkov:
- zdieľaný zámok (S-lock) - umožnuje čítanie, zabezpečuje nemennosť záznamov.
- exkluzívny zímok (X-lock) - v danom momente vlastní iba jedna transakcia, druhá nemôže získať ani S ani X lock

matica zamykania:

```
|   | S | X | - |
| S | Y | N | Y |
| X | N | N | Y |
| - | Y | Y | Y |
```

základné operácie:
- R-lock - pred operáciou read, pridelenie S-lock
- W-lock - pred operáciou write alebo read(ak bude nasledovaná writom), X-lock
- unlock - uvoľnenie zámku

dobre definovaná transakcia:
- každá operácia read je predchádzaná buď R-lock alebo W-lock a nasleduje Unlock
- každá operácia write predchádzaná W-lock a nasledovaná Unlock

serializovateľnosť - ak sú všetky transakcie zabezpečené dvojfázovým uzamykacím protokolom, tak sú všetky možné rozvrhy serializovateľné

rozšírenie typu zámkov - intention:
- intention-shared(IS)
- intention-exclusive(IX)
- shared and intention-exclusive(SIX)

```
|      | IS | IX | S | S IX | X |
|  IS  |  Y |  Y | Y |   Y  | x |
|  IX  |  Y |  Y | x |   x  | x |
|   S  |  Y |  x | Y |   x  | x |
| S IX |  Y |  x | x |   x  | x |
|   X  |  Y |  x | x |   x  | x |
```
