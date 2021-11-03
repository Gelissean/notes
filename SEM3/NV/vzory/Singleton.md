singleton

Jedináčik
trieda môže mať iba jednu inštanciu v systéme

Schránka, súborový systém, manažér okien

Možnosť rozšíriť o potomkov, ktorí nemodifikujú kód jedináčika

Niekoľko spôsobov implementácie
- Library class
```c
public class Math { 
    // Documentation 
	public static final double E = 2.71828;
	public static final double PI = 3.14159; 
	public static double sin() {} 
	public static double cos() {} 
	public static double min() {} 
	public static double max() {} 
	public static double round() {}
}
```
- Verejná konštanta
```c
public class Singleton { 
	public static final Singleton instance = new Singleton();
	private Singleton() { 
		// initialization 
	} 
}
```
- Lazy initialization
```c
public class Singleton { 
	private static Singleton instance;
	protected Singleton() {
		// initialization 
	}
	public Singleton getInstance() {
		if (instance == null)
			instance = new Singleton();
		return instance; 
	} 
}
```
- niekoľko potomkov
![[simpleton_potomkovia.png]]

Flexibilnejší ako statická trieda, polymorfizmus, jednoduchá rozšíriteľnosť.
Použiť namiesto globálnych premenných

Príbuzné vzory:
[[Abstract_factory]]
[[Builder]]
[[Prototype]]


