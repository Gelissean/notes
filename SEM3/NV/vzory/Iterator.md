Iterator
umožnuje prechádzať prvkami kompozitu bez odhalenia detailov
zapúzdruje prechod zložitými štruktúrami
možnosť filtrov

dôležitá efektívna implementácia

v c++ kniznica `<algorithm>`
	
Kedy použiť:
	prístup na jednotlivé prvky kompozitu bez ich odhalenia
	vhodnejší prechod než pomocou for(foreach)
	jednotné rozhranie pre prechod zložených štruktúr

![[iterator_implementacia.png]]
![[Iterator_spolupraca.png]]	

umožnuje jednoducho prechádzať štruktúrou a meniť algoritmy prechodu (preorder, inorder, postorder)
zjednodušuje rozhranie zložitého objektu
	
príbuzné vzory
[[Composite]]
[[Factory_method]] - často spôsob tvorby iterátoru
	(aspoň [[Abstract_factory]])
[[Memento]] - ukladá stav iterátora, skrýva implementačné detaily
[[Proxy]] - špeciálny typ Zástupcu


![[factory_method_priklad.png]]
každá trieda si vytvorí vlastný iterátor, s ktorým vie dobre a efektívne pracovať