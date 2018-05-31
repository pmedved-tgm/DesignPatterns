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

