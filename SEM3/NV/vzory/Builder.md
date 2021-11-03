**Builder**
kreačný návrhový vzor
separuje čo od ako
2 triedy (director, builder)
typicky export do rôznych formátov
použiť keď skladaný objekt je zložený z rôznych ďaľších objektov

![[ukazka_buildera.png]]
jeden riadiaci objekt riadi stavbu rôznych typov domov a používa rozhranie a jeho triedy na stavbu

![[builder_spolupraca.png]]

Príbuzné vzory:
[[Abstract_factory]] - podobná, ale stavia rodinu objektov, Builder stavia jeden zložitý objekt
[[Composite]] - to, čo builder stavia