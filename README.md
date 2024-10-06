# Java Alapok

## Bevezetés

Szia! Ez a dokumentáció célja, hogy segítsen a Java programozási nyelv alapjainak megértésében. Remélem már van tapasztalatod programozás terén, de ha nem, akkor nek baj, csak lehet, hogy kicsit nehezebb lesz megértened. A Java egy rendkívül népszerű, objektumorientált programozási nyelv, amelyet széleskörűen használnak a szoftverfejlesztésben, webfejlesztésben, mobilalkalmazások fejlesztésében és még sok más területen.

## Tartalomjegyzék

1. [Környezet Beállítása](#környezet-beállítása)
2. [Java Alapfogalmak](#java-alapfogalmak)
3. [Alapvető Nyelvi Szerkezet](#alapvető-nyelvi-szerkezet)
4. [Objektumorientált Programozás](#objektumorientált-programozás)
5. [Következő Lépések](#következő-lépések)

## Környezet Beállítása

### 1. Java Telepítése

A Java Development Kit (JDK) telepítése szükséges a Java programok futtatásához és fejlesztéséhez.

- **JDK letöltése**: [Java SE Development Kit](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
- **Telepítés**: Kövesd a letöltött fájl utasításait.

### 2. IDE kiválasztása

A fejlesztéshez (én személy szerint nagyon ajánlom) szükséged lesz egy integrált fejlesztői környezetre (IDE). Ajánlott IDE-k:

- [IntelliJ IDEA](https://www.jetbrains.com/idea/)
- [Eclipse](https://www.eclipse.org/)
- [NetBeans](https://netbeans.apache.org/)

# Java Alapfogalmak

 ## 1. Változók

A változók tárolják az adatokat a program futása során. Java-ban többféle adattípus létezik:

- `int` - egész számok
- `double` - lebegőpontos számok
- `char` - karakterek
- `String` - karakterláncok
- `boolean` - logikai értékek (igaz/hamis)

 **Példa**:

```java
int szam = 10;
double pi = 3.14;
char karakter = 'A';
String szoveg = "Helló, világ!";
boolean igaz = true;
```

 ## Operátorok


Java-ban többféle operátor található. Ezek arra szolgálnak, hogy a matematikai műveleteket el tudjuk végezni.

**Aritmetikai operátorok**: +, -, *, /, %
**Összehasonlító operátorok**: ==, !=, >, <, >=, <=
**Logikai operátorok**: &&, ||, !


 ## Feltételes utasítások

A feltételes utasítások segítségével a programokban döntéseket hozhatunk a program futása során. A Java-ban a leggyakrabban használt feltételes utasítások a `if`, `else if`, `else` és a `switch` szerkezetek. 
Mi most csak az `if-else`-el fogunk foglalkozni.

```java
if (szam > 5) {
    System.out.println("A szám nagyobb, mint 5.");
} else {
    System.out.println("A szám nem nagyobb, mint 5.");
}
```

Mint láthatod a fenti példában, az `if` után meg kell adni a kondíciót, hogy mit történjen `ha` és az `else` után pedig, hogy mit történjen, `ha nem`.


 ## Ciklusok

A ciklusok lehetővé teszik, hogy ismételt műveleteket végezzünk. Kétféle módon tudjuk használni.
Az első a `for ciklus`

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

A második a `while ciklus`

```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

Ha kezdő vagy, én mindenképpen a `while` ciklust javaslom, sokkal átláthatóbb.



# Objektumorientált Programozás

A Java az objektumorientált programozás paradigmájára épül, amely a következő alapelveket tartalmazza:


**Osztályok**

   Az osztályok a programban használt objektumok sablonjai.
A Java-ban az osztályok a következő elemeket tartalmazhatják:
1. _Attribútumok_: Ezek az osztályhoz tartozó adatok. Az attribútumok képviselik az osztály állapotát.
2. _Konstruktorok_: Ezek speciális metódusok, amelyeket az osztály példányainak (objektumainak) létrehozásakor hívnak meg. A konstruktorok lehetővé teszik, hogy kezdeti értékeket adjunk az attribútumoknak.
3. _Metódusok_: Ezek a funkciók, amelyeket az osztály példányai hajtanak végre. A metódusok végzik a különböző műveleteket, amelyeket az objektumok elvégezhetnek.

Nézzünk egy példát! Legyen egy Autó osztályunk   

```java
// Az Auto osztály, amely egy autót reprezentál
class Auto {
    // Az osztály attribútumai
    String szin;      // Az autó színe
    String marke;     // Az autó márkája
    int evjarat;      // Az autó évjárata

    // Konstruktor, amely inicializálja az attribútumokat
    Auto(String szin, String marke, int evjarat) {
        this.szin = szin;         // Az 'this' kulcsszó a példány változókra hivatkozik
        this.marke = marke;       // A 'marke' attribútum értékét a paraméterrel állítjuk be
        this.evjarat = evjarat;   // Az 'evjarat' attribútum értékét a paraméterrel állítjuk be
    }

    // Metódus, amely elindítja az autót
    void indit() {
        // Kiírja az autó színét és márkáját, amikor elindítjuk
        System.out.println(this.szin + " " + this.marke + " autó elindult.");
    }
}

// Példa az Auto osztály használatára
public class Main {
    public static void main(String[] args) {
        // Létrehozunk egy új Auto objektumot
        Auto myAuto = new Auto("Piros", "Toyota", 2020);
        
        // Elindítjuk az autót
        myAuto.indit();  // Kiírja: "Piros Toyota autó elindult."
    }
}
```


***Objektumok**

Az objektumok az osztály példányai. Minden egyes objektum különálló, és saját állapotát (attribútumait) és viselkedését (metódusait) tartalmazza. Az objektumok segítségével interakcióba léphetünk a program különböző részeivel, és különböző adatokkal dolgozhatunk.

Egy objektumnak a következőképpen kellene kinéznie:

```java
Auto myAuto = new Auto("Piros", "Toyota", 2020);
```
Ebben a példában létrehoztunk egy myAuto nevű objektumot az Auto osztályból, amely piros, Toyota márkájú és 2020-as évjáratú.



***Öröklődés**

Az OOP egyik kulcsfontosságú jellemzője az öröklődés, amely lehetővé teszi, hogy egy osztály örökölje egy másik osztály attribútumait és metódusait. Ez segít a kód újrafelhasználásában és a hierarchikus struktúrák létrehozásában.

```java
class Jarmu {
    void mozgatas() {
        System.out.println("A jármű mozog.");
    }
}

class Bicikli extends Jarmu {
    void kerekpározás() {
        System.out.println("A bicikli kerekpároz.");
    }
}
```

A fenti példában a `Bicikli` osztály örökli a `Jarmu` osztály metódusait. Ez azt jelenti, hogy a `Bicikli` objektum képes a `mozgatas` metódust is használni:

```java
Bicikli myBicikli = new Bicikli();
myBicikli.mozgatas();  // Kiírja: "A jármű mozog."
```


**Polimorfizmus**

A polimorfizmus az OOP egy másik fontos jellemzője, amely lehetővé teszi, hogy az azonos metódusnevet különböző osztályokban eltérően valósítsuk meg. Ez lehetővé teszi a program számára, hogy rugalmasabban kezelje az objektumokat.

```java
class Allat {
    void hangotAd() {
        System.out.println("Az állat hangot ad.");
    }
}

class Kutya extends Allat {
    void hangotAd() {
        System.out.println("A kutya ugat.");
    }
}

class Macska extends Allat {
    void hangotAd() {
        System.out.println("A macska nyávog.");
    }
}
```

A `Kutya` és `Macska` osztályok eltérően implementálják a `hangotAd` metódust. A következő kód példát mutat arra, hogyan használhatjuk őket:

```java
Allat myAllat1 = new Kutya();
Allat myAllat2 = new Macska();

myAllat1.hangotAd();  // Kiírja: "A kutya ugat."
myAllat2.hangotAd();  // Kiírja: "A macska nyávog."
```


**Összegzés**

Az osztályok és objektumok fogalmai fontos játszanak a Java-ban. Az osztályok mint sablonok definiálják az objektumok szerkezetét és viselkedését, ehez képest az objektumok az osztályok példányai, amelyek valós adatokkal és funkciókkal rendelkeznek. Az OOP alapelvei, mint az öröklődés és a polimorfizmus, lehetővé teszik a kód újrafelhasználását, a modularitást, és segítenek a bonyolultabb rendszerek megírásában.


# Következő Lépesek

Próbáltam ennek a résznek valami hangzatos nevet kitalálni, de ezt sikerült. ;)
Ide kerestem neked további oldalakat, amik segíthetnek neked.

[Oracle](https://docs.oracle.com/javase/tutorial/)
[Coursera](https://www.coursera.org/specializations/java-programming)

Itt tovább fejlesztheted eddig megszereztt tudásodat! 



# Kapcsolat

Lehet hogy amit most olvastál, az full kínai volt számodra. Ha bármit nem értessz, vagy elakadtál, akkor írj nekem egy [E-Mailt](jaokoi27@gmail.com)





