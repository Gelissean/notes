umožnuje navrhnúť optimalizéru využiť nejaký špecifický spôsob práce s dátami

join order:
- ordered
- star - podľa kardinality

join method
- use_Nl(table1 table2) - nested loops
- use_merge(table1 table2) - sort-merge join
- use_hash(table1 table2) - hash join
- leading(table) - vybraná tabuľka bude prvá

`INSERT /*+APPEND*/ into ...` - kontrolný mechanizmus spustený až na konci vykonania príkazu

zobrazovacie:
- all_rows
- first_rows

