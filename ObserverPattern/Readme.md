# Observer Pattern

### Wozu dient das Observer Pattern?

Das Observer Pattern dient als "Newsletter", der Sinn des Observer 
Pattern ist, dass alle abhängigen Objekte benachrichtigt werden,
wenn sich der Zustand eines bestimmten Objektes ändert.

Angenommen wir haben auf Amazon einen Gegenstand gefunden der
uns gefällt, doch leider ist er ausverkauft. Da wir den Gegenstand
unbedingt haben wollen melden wir uns über den "Notify Me" Button
an um informiert zu werden, sobald der Gegenstand wieder zur
Verfügung steht.

Diese Benachrichtigung funktioniert mittels eines Observer Patterns.



### Wie funktionert das Observer Pattern?

Hierfür verwendet man ein Objekt names Observable, dieses Objekt
behinhaltet die Gewünschten Daten, in unserem Fall die Information
ob der Gegenstand wieder verfügbar ist, und eine Liste mit allen
Interessenten (alle die "Notify Me" gedrückt haben).

Die Interessenten die dann die Daten vom Observer haben wollen
können sich dann jederzeit beim Observable registrieren, quasi
wie ein Newsletter (in unserem fall mittels dem "Notify Me" Button).

### UML

![Decorator UML-Diagramm](DecoratorPattern.png "Decorator")

### Code

Als erstes müssen zwei abstrakte Klassen erstellt werden:

* Die Gericht Klasse mit der abstrakten methode cost()
* Die Beilage Klasse die eine Subklasse von Geraenk ist

```java

public abstract class Gericht{
	public abstract double preis();
}

public abstract class Beilage extends Gericht{
    protected Gericht gericht;
}
```

Dann werden die eigentlichen Gerichte und Beilagen implementiert

```java

public class Schnitzel extends Gericht{
    @override
	public double preis(){
		return 7.90;
	}
}

public class Steak extends Gericht{
    @override
	public double preis(){
		return 19.90;
	}
}


public class Pommes extends Beilage{
	private Gericht gericht;

	public Pommes(Gericht gericht){
		this.gericht = gericht;
	}

    @override
	public double preis(){
		return this.gericht.cost() + 1.20;
	}
}

public class Reis extends Beilage{
	private Gericht gericht;

	public Pommes(Gericht gericht){
		this.gericht = gericht;
	}

    @override
	public double preis(){
		return this.gericht.cost() + 2.20;
	}
}
```

Letztens können die verschiedenen Gerichte erstellt werden

```java

public class Main{
	public static void main(String[] args){
		Gericht gericht = new Pommes(new Schnitzel());
		Gericht gericht = new Reis(new Reis(new Steak()));
	}
}
```