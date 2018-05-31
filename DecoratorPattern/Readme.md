# Decorator Pattern

### Wozu dient das Decorator Pattern?

Das Decorator Pattern verhindert die "Klassenexplosion". Was ist 
hier gemeint? Das Decorator Pattern fügt einem Object dynamisch 
erweiterungen hinzu, anstatt tausende einzelne Klassen zu haben.

Betrachten wir mal als Beispiel ein Restaurant.

Das Restaurant xy bietet als Hauptspeisen Schnitzel, Burger, Tofu 
und Steak an, als Beilage gibt es entweder Pommes, Reis, Salat oder
Kartoffeln. Jetzt könnte man für jede einzele Kombination eine Klasse
erstellen zB. SchnitzelMitPommes, SchnitzelMitSalat, BurgerMitPommes, ...
Dies würde aber schnell in einer unübersichtlichen Anzahl an Klassen enden.

Abhilfe bietet hier das Decorator Pattern, es ermöglicht einem ein
Hauptgericht mit Beilage zusammen zu stellen ohne, dass man hierfür
für jede möglichkeit eine eigene klasse benötigt.



### Wie funktionert das Observer Pattern?

Zu erst brauchen wir eine abstracte Klasse Gericht, welche dann Beilage
und Hauptgericht zusammenfasst. Danach erstellen wir die einzelnen Klassen 
der Hauptgerichte welche von der Hauptklassse Gericht erbt. Dann erstellen
wir die abstracte Klasse Beilage, von der Klasse beilage erben dann die
Unterklassen wie zum Beispiel Pommes oder Salat.

Wenn man jetzt den Preis seines Gerichts wissen möchte muss man nur die
cost() Methode des "obersten" Objekts aufrufen, welches dann seinen Preis
und den Preis der aller Attribute zurück liefert.

### UML

### Code