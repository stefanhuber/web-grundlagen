# Cascading Stylesheets (CSS)

CSS ist eine Stylesheet-Sprache um die Gestaltung bzw. Formatierung einer Webseite durchzuführen. Jedes HTML-Element kann über CSS-Eigenschaften wie zum Beispiel die Textfarbe, die Schriftgröße oder die Höhe formatiert werden. CSS ist nicht nur auf Webseiten beschränkt sondern kann auch für die Formatierung von Druck bzw. die Sprachausgabe verwendet werden.

CSS-Stylesheets organisieren sich als Ansammlung von CSS-Regeln. Eine CSS-Regel enthält eine Aufzählung von CSS-Eigenschaften und entsprechenden Werten. Über CSS-Selektoren werden CSS-Regeln mit HTML-Elementen verknüpft.

## CSS-Regeln

CSS-Regeln sind die grundlegenden syntaktischen Bausteine um einen CSS-Stylesheet zu definieren. Eine CSS-Regel wird über einen Block von CSS-Eigenschaften und deren zu setzende Werte deklariert. Der Eigenschaftsblock wird über die Klammern `{` und `}` eingeschlossen. Eine CSS-Eigenschaft wird von einem Bezeichner eingeleitet und über `:` vom Wert getrennt. Eine CSS-Eigenschaft muss durch `;` abgeschlossen werden. Die letze CSS-Eigenschaft innerhalb eines Blockes kann ohne `;` abgeschlossen werden.

Beispiel einer CSS-Regel (ohne CSS-Selektor):
```CSS
{
  background-color: red;
  color: blue
}
```

Um CSS-Regeln auf HTML-Elemente im DOM anzuwenden, werden CSS-Selektoren verwendet. CSS-Selektoren werden syntaktisch vor dem Eigenschaftsblock gesetzt. Somit kann der Eigenschaftsblock einer CSS-Regel auf selektierte HTML-Elemente angewendet werden. 

Beispiel einer vollständigen CSS-Regel:
```CSS
a.my-class, #id123 {
  background-color: red;
  color: blue
}
```

## CSS-Stylesheets einbinden

 - Externer Stylesheet: Alle CSS-Regeln werden innerhalb einer eigenen Datei CSS-Datei beschrieben und über das `link-Tag` im HTML-Head eingebunden
 - Interner Stylesheet: Im HTML-Head können innerhalb eines `style-Tags` CSS-Regeln im HTML-Dokument angegeben werden
 - Inline Angabe: Jedes HTML-Element im Dokument kann über das style-Attribut direkt über CSS-Eigenschaften formatiert werden

> Um eine klare Trennung zwischen Inhalt und Gestaltung herzustellen, sollten Stylesheets vorranging extern eingebunden werden. Interne Stylesheets machen Sinn um die Ladezeit zu optimieren, dies sollte aber möglichst nicht manuell durchgeführt werden. Inline Angaben sollten vermieden werden und nur für dynamische Änderungen über JavaScript genutzt werden.

## CSS-Eigenschaften

Über CSS-Eigenschaften kann das Aussehen und die Positionierung bzw. das Layout von HTML-Elementen bestimmt werden. Es gibt eine Vielzahl von unterschiedlichen CSS-Eigenschaften die jeglichen Aspekt des Aussehens bzw. auch des Verhaltens von HTML-Elementen bestimmen.

## Wertangaben für CSS-Eigenschaften

Viele CSS-Eigenschaften verlangen eine Wertangabe als Deklaration (zB `width`, `padding`, `font-size`). Diese Wertangaben bestehen einerseits aus einem `Zahlenwert` und andererseits aus einer `Einheit`. In CSS können Werte in `absoluten` oder `relativen` Einheiten angegeben werden. Generell muss jeder Wert mit Einheit angegeben werden, außer für `0`. Zwischen Wert und Einheit darf sich kein Leerraum befinden (zB `15px`, `5%` oder `55cm`).

### Absolute Wertangaben

| Einheit | Beschreibung |
| --- | --- |
| `cm` | Zentimeter |
| `mm` | Millimeter |
| `in` | Zoll (inches) `1in = 2.54cm` |
| `px` | Ein physischer Pixel (Ausnahme: siehe `viewport`) |
| `pt` | Punkt (point) `1/72 eines Zolls` |
| `pc` | picas `1pc = 12pt` |

### Relative Wertangaben

Relative Wertangaben orientieren sich anhand einer anderen Wertangabe (zB Viewport, font-size des aktuellen HTML-Elements). Relative Wertangaben haben den Vorteil, dass sie sich besser anpassen auf unterschiedliche Ausgabemedien.

| Einheit | Beschreibung |
| --- | --- |
| `em` | Relativ zur `font-size` des HTML-Elements (`2em` würde bedeuten 2x so groß wie die aktuelle `font-size`) |
| `rem` | Relativ zur `font-size` des Wurzel HTML-Elements (`2rem` würde bedeuten 2x so groß wie die definierte `font-size` im `html` Element) |
| `vw` | Relativ zu `1%` der Viewport-Breite |
| `vh` | Relativ zu `1%` der Viewport-Höhe |
| `%` | Definiert den Wert relativ zum Elternelement |

Es sind noch weitere Einheiten definiert, welche jedoch eher selten genutzt werden: `ex`, `ch`, `vmin`, `vmax`.

## CSS-Selektoren

Mit CSS-Selektoren können HTML-Elemente im DOM eindeutig identifiziert werden. Somit kann der Eigenschaftsblock einer CSS-Regel auf selektierte HTML-Elemente angewendet werden. CSS-Selektoren werden auch in Zusammenhang mit JavaScript verwendet um HTML-Elemente zu selektieren und dynamisch zu verändern.

Es gibt unterschiedliche Formen von Selektoren:
 - Einfache Selektoren: Element-Selektor, Class-Selektor oder ID-Selektor
 - Attribut Selektor: Basierend auf einem oder mehreren HTML-Attributen
 - Pseudoklassen: HTML-Elemente können auf Basis eines bestimmten Zustands oder einer spezifischen Positionierung selektiert werden.
 - Pseudoelemente: Selektion eines Teiles eines HTML-Elementes.
 - Kombinatoren: Einzelne Selektoren können über Kombinatoren verknüpft werden.

### Einfache Selektoren

| Bezeichnung |  Syntax Beispiel | Beschreibung | 
| --- | --- | --- |
| ID-Selektor | `#sample-id` | HTML-Elemente können das Attribut `id` setzen, welches einen eindeutigen Wert für das gesamte HTML-Dokument haben muss. Über den ID-Selektor kann ein HTML-Element mit der entsprechenden ID selektiert werden. |
| Class-Selektor | `.sample-class` | Es können beliebige Klassen definiert werden, welche in HTML-Elementen im Class-Attribut gesetzt werden. Über den Class-Selektor können alle HTML-Elemente selektiert werden, welche die entsprechende Klasse gesetzt haben. |
| Element-Selektor | `div` | HTML-Elemente können über den entsprechenden Bezeichner (Tagname) selektiert werden. |
| Universal-Selektor | `*` | Als "Joker" kann der sog. Universal-Selektor verwendet werden, welcher alle HTML-Elemente selektiert. |

### Attribut Selektoren

| Syntax Beispiel | Beschreibung |
| --- | --- |
| `[attr]` | HTML-Elemente können Attribute setzen. Mit dem einfachen Attribut Selektor werden alle HTML Elemente ausgewählt, welche das Attribut gesetzt haben, egal mit welchem Wert. |
| `[attr=„value“]` | Eine Erweiterung des einfachen Attribut Selektors wird durch die Angabe eines Wertes mit `=` durchgeführt. Somit werden nur HTML-Elemente ausgewählt, welche ein Attribut mit genau dem entsprechenden Wert aufweisen. |
| `[attr~=„value“]` | Alle HTML-Elemente in denen unter anderem der Attributwert `value` auftritt. |
| `[attr^=„value“]` | Alle HTML-Elemente in denen der Arttributwert mit `value` startet. |
| `[attr$=„value“]` | Alle HTML-Elemente in denen der Arttributwert mit `value` endet. |
| `[attr*=„value“]` | Alle HTML-Elemente in denen der Arttributwert den Teilstring `value` enthält. |

### Pseudoklassen

Pseudoklassen werden mit einem führenden `:` angegeben. Es gibt eine Vielzahl von Pseudoklassen, im folgenden soll ein Auszug von häufig vorkommenden gegeben werden:

| Syntax Beispiel | Beschreibung |
| --- | --- |
| `:hover` | Das HTML-Element über dem der Mauszeiger liegt. |
| `:checked` | Checkbox, Radio-Button oder Selection-Option welche aktiviert ist. |
| `p:first` | Das erste Vorkommen eines `p-Tag` im HTML-Dokument |
| `p:first-child` | Das erste `p-Tag` welches ein Kindelementist. |
| `input:focus` | Ein `input-Tag` (zB Textfeld) auf dem der Fokus liegt. |
| `:empty` | Ein HTML-Element, welches keine Kindelemente hat. |
| `:not(p)` | Jesed HTML-Element, dass kein `p-Tag` ist. |

### Pseudoelemente

Pseudoelemente werden mit zwei führenden `:` angegeben.

| Syntax Beispiel | Beschreibung |
| --- | --- |
| `::after` | Kann genutzt werden um Inhalte nach einem HTML-Element über CSS einzufügen. Der Inhalt sollte vorrangig stilistische Gründe haben. |
| `::before` | Ähnlich zu `::after` fügt `::before` Inhlate vor einem HTML-Element ein. |
| `::first-letter` | Selektiert den ersten Buchstaben innerhalb eines Textes. |
| `::first-line` | Selektiert die erste Zeile eines Textes. |
| `::selection` | Spezifiziert genau den Text, welcher selektiert wurde (zB mit der Maus). |

### Kombinatoren

Mit Kombinatoren können CSS-Selektoren verknüpft werden. Im folgenden sind `A` und `B` Platzhalter für beliebige CSS-Selektoren:

| Bezeichnung | Syntax Beispiel | Beschreibung |
| --- | --- | --- |
| Nachkommenkombinator | `A B` oder `A >> B` | Alle Nachkommen von `A`, welche `B` entsprechen. Die Nachkommen müssen nicht direkte Kinder sein sondern können auch Enkelkinder sein. |
| Direkter Nachkommenkombinator | `A > B` | Alle direkte Nachkommen von `A` (nur Kinder). |
| Geschwisterkombinator | `A ~ B` | Alle Geschwister von `A` (auf gleicher Ebene), welche `B` entsprechen |
| Angrenzender Geschwisterkombinator | `A + B` | `B` ist direkt (auf gleicher Ebene) das nächste Geschwister von `A` |
| Gruppierung | `A, B` | `A` und `B` ist jeweils eine unabhängige Gruppe von CSS-Selektoren, welche innerhalb einer CSS-Regel auftreten.

## CSS Box-Modell

Jedes HTML-Element wird im Web-Browser anhand des Box-Modell als eine rechteckige "Box" repräsentiert. Das Box-Modell findet bei Block-Elementen vollständige Anwendung und bei Inline-Elementen in eingeschränkter Form. Das Box-Modell definiert die 4 Bereiche `Content`, `Padding`, `Border` und `Margin`, welche in Kombination die Abmessungen eines HTML-Elements berechnen.

 - `Content Box`: Der Inhaltsbereich wird definiert durch die CSS-Eigenschaften `width` und `height`.
 - `Padding Box`: Padding ist der Innenabstand zwischen Inhalt und Rahmen (CSS-Eigenschaft `padding`).
 - `Border Box`: Der Rahmen liegt zwischen Innenabstand und Außenabstand (CSS-Eigenschaften, welche mit dem Prefix `border` beginnen).
 - `Margin Box`: Margin ist der Außenabstand, welcher zwischen Rahmen und anderen HTML-Elementen in der Umgebung definiert ist (CSS-Eigenschaft: `margin`). 

![CSS Box-Modell](../images/014-box-model.png "CSS Box-Modell")

## Kaskade

Unterschiedliche CSS-Selektoren können das selbe HTML-Element bestimmen. Definierte CSS-Regeln können dadurch kollidieren und CSS-Eigenschaften können unterschiedlich definiert werden. Zum Beispiel könnte eine Regel die Schriftfarbe für Überschriften als blau definieren und eine andere Regel die Schriftfarbe als rot definieren. CSS definiert deshalb einen Kaskadierungs-Algorithmus um zu bestimmen, welche CSS-Selektoren und dadurch CSS-Regeln/CSS-Eigenschaften priorisiert werden.

Für CSS gelten folgende Faktoren um die Priorität von CSS-Eigenschaften festzulegen:
 - Wichtigkeit: Für eine CSS-Eigenschaft kann durch Angabe des Schlüsselwortes `!important` die Priorität so gesetzt werden, dass alles andere überschrieben wird.
 - Spezifität: Diese wird anhand eines numerischen Wertes gemesen.
 - Reihenfolge: Letztlich wird die Reihenfolge in der CSS-Stylesheet Definition herangezogen. Bei gleicher Spezifität wird die Definition, welche als letze definiert wurde, verwendet.

### Spezifitätsberechnung von CSS-Selektoren

CSS-Eigenschaften innerhalb von CSS-Regeln mit höherer Spezifität überschreiben CSS-Eigenschaften innerhalb von CSS-Regelen mit niederer Spezifität.

Die Spezifität errechnet sich anhand numerischer Werte, welche für unterschiedliche CSS-Selektoren bzw. Angaben vergeben werden. Kombinatoren haben **keinen Einfluss** auf die Spezifität. Folgende Regeln werden verwendet um die Spezifität zu errechnen:

| Wert | Beschreibung |
| --- | --- |
| 1000 | Falls eine CSS-Eigenschaft im `style-Attribut` des HTML-Elements angegeben wird. |
| 100 | Für jeden ID-Selektor wird 100 vergeben. |
| 10 | Für Class-, Attribut- oder Pseudoklassen Selektoren wird jeweils 10 vergeben. |
| 1 | Für Element- bzw. Pseudoelement Selektoren wird jeweils 1 vergeben. |

### Beispiele für Spezifitätsberechnungen

| CSS-Selektor | 1000 | 100 | 10 | 1 | Summe |
| --- | --- | --- | --- | --- | --- |
| `h1` | 0 | 0 | 0 | 1 | 0001 |
| `p a::first-letter` | 0 | 0 | 0 | 3 | 0003 |
| `#exm p.class1` | 0 | 1 | 1 | 1 | 0111 |
| `.class1 > .class2` | 0 | 0 | 2 | 0 | 0020 |

## Vererbung

Das HTML-Dokument besteht aus einer Hierarchie von HTML-Elementen. Gewisse CSS-Eigenschaften werden vererbt. Das bedeutet, dass gewisse CSS-Eigenschaften, welche für ein Elternelement gesetzt werden an allen Kinder und Enkelkinder auch gesetzt werden.

Beispiele für CSS-Eigenschaften welche vererbt werden sind: `color`, `font-family`, `font-weight`, `text-align`. Beispiele für CSS-Eigenschaften welche nicht vererbt werden sind: `margin`, `padding`, `width`, `height`, `position`.

> Die genauen Vererbungsregeln von einzelnen CSS-Eigenschaften werden im W3C-Standard definiert. Für das tägliche Arbeiten mit CSS entsteht schnell eine Intuition dafür, welche CSS-Eigenschaften vererben und welche nicht.

Im folgenden Beispiel soll das Konzept der Vererbung demonstriert werden. Dabei ist eine kleiner HTML Ausschnitt definiert. Auf dem HTML-Element `section` wird ein Padding von `15px` bzw. eine Schriftfarbe `red` definiert. Das Padding wird dabei nur auf `section` angewandt, die Schriftfarbe jedoch auch auf `h1`, `p` und `strong`. Padding ist eine CSS-Eigenschaft, welche nicht vererbt wird, die Schriftfarbe ist jedoch eine CSS-Eigenschaft, welche vererbt wird. Durch die explizite Angabe der Schriftfarbe `blue` auf `strong` wird `red` überschrieben.

Beispiel HTML:
```html
<section>
  <h1>Eine Überschrift</h1>
  <p>Ein <strong>Beispieltext</strong> innerhalb eines Paragraphen</p>
</section>
```

Beispiel CSS:
```css
section {
  padding:15px;
  color: red;
}
strong {
  color: blue;
}
```
