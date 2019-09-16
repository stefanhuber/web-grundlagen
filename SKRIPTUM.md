# Web-Grundlagen

# World Wide Web (WWW)

Das WWW ist ein globales und verteiltes Informationssystem bestehend aus Webseiten und anderen Web-Resourcen (zB Bilder, Videos, etc). Web-Resourcen werden auf Web-Servern bereitgestellt und sind öffentlich abrufbar. Jede Web-Resource (Webseite, Bild, Video, etc) ist über einen Uniform Resource Locator (URL) eindeutig identifiziert und abrufbar. Webseiten sind im WWW über sog. Hyperlinks miteinander verknüpft. Hyperlinks werden ebenfalls über einen URL ausgedrückt. Webseiten können über Web-Browser (auch Web-Clients) geladen und bedient werden.

## Technische Grundlagen

Das technische Fundament für das WWW bildet das Internet. Das Internet ist ein globales Netzwerk (Internet = interconnected network), welches Computer und andere Computer Netzwerke (Intranets) miteinander verknüpft.

### Uniform Resource Locator (URL)

Eine URL ist eine global eindeutige "Adresse" einer Web-Resource. Ein Web-Browser kann über eine URL Web-Resourcen herunterladen und letzlich anzeigen. URL folgend einem vorgegebenen syntaktischen Aufbau:

 - Schema (Scheme): Das Schema gibt den Typ der URL an. Bekannte Schemata sind zB `http`, `https`, `ftp` oder `mailto`. Die Schemaangabe wird mit einem `:` abgeschlossen.
 - Zuständigkeit (Authority): Wesentlicher Bestandteil der Authority ist der `Host`, welcher als Domain-Name oder IP-Adresse angegeben werden kann. Optional kann die Authority eine Benutzerinformation enthalten, welche vor der Host-Angabe steht (Abgeschlossen durch ein `@`). Optional kann auch eine Port-Angabe angebracht werden (Eingeleitet durch einen `:`).
 - Pfad (Path): Der Pfad ist eine hierarchische Angabe einer konkreten Ressource innerhalb einer Authority. Alle Pfadbestandteile werden ähnlich zu einem Dateisystem mittels `/` getrennt.
 - Abfrage (Query): Der Abfrage-Teil (Query-String) wird genutzt um optionale Schlüssel-Wert Paare anzugeben. Ein Query-String wird über ein `?` eingeleitet. Schlüssel-Wert Paare werden jeweils über `&` getrennt. Mit `=` wird jeweils der Schlüssel mit dem zugehörigen Wert verknüpft.
 - Fragment: Fragmente können genutzt werden um Teile eine Ressource zu identifizieren, zB als Anker innerhalb einer Webseite. Fragmente werden über ein `#` eingeleitet.

Beispiel einer URL:
```
          userinfo       host      port
          ┌──┴───┐ ┌──────┴──────┐ ┌┴┐
  https://john.doe@www.example.com:123/forum/questions/?tag=networking&order=newest#top
  └─┬─┘   └───────────┬──────────────┘└───────┬───────┘ └───────────┬─────────────┘ └┬┘
  scheme          authority                  path                 query           fragment
```

### Domain Name System (DNS)

Das Internet basiert auf dem TCP/IP Netzwerk-Stack (Internetprotokollfamilie). Im TCP/IP Netzwerk-Stack werden alle Knoten des Netzwerkes über eine IP-Adresse identifiziert. IP-Adresse sind ähnlich wie Telefonnummern für Menschen schwer einprägsam. DNS ist ein Internet-Dienst welcher, ähnlich zu einem Telefonbuch, Klarnamen zu IP-Adressen verwaltet und abrufbar macht.

[//]: # (TODO: richtige IP-Adressen suchen zu den Beispielen)
Auszug aus der Datenbank eines DNS-Servers:
```
wikipedia.org        185.102.12.2
fh-kufstein.ac.at    85.234.32.2
```

Der Web-Browser nimmt in der Adresszeile einen URL engegeben, welcher unter anderem auch einen Domain-Namen enthält. Der Web-Browser würde im ersten Schritt einen DNS-Server anfragen um die IP-Adresse des entsprechenden Domain-Namen zu erhalten.

### HTTP-Protokoll



### Web-Browser

## W3C und Standardisierung

# Web-Technologien

# HTML



## Glossar

| Begriff | Beschreibung  |
| --- | --- |
| Webseite/Website | Mit einer Website werden alle einzelnen Webseiten, welche unter einem gemeinsamten Domänennamen veröffentlicht sind, bezeichnet. Eine Webseite ist dabei, über eine URL eindeutig identifizierte Web-Resource. |
| Pseudoelement | Pseudoelemente sind (über CSS-Selektor) identifizierbare Bestandteile eines normalen HTML-Elements. Beispiele: <ul><li>`::selection` gibt den Text an, welcher von der Benutzerin zB mit der Maus selektiert wurde</li><li>`::first-line` gibt die erste Zeile Text innerhalb eines Paragraphen an</li></ul>  |
|  |  |
|  |  |