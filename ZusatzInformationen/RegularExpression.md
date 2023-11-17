# Regular Expressions


## Links

Links zum Thema Regular Expressions (RegEx), erklärungen dazu im Kurs:

- Online Tools: <br>
https://regexr.com/ <br>
https://regex101.com/

- Lernspiele: <br>
https://regexlearn.com/learn/regex101 <br>
https://regexone.com/

- Challenges: <br>
https://regexcrossword.com/ <br>
https://alf.nu/RegexGolf?world=regex&level=r00

<br>

Regular Expressions, oft als "RegEx" abgekürzt, sind eine **Methode zur Suche, Analyse und Manipulation von Texten durch Beschreibung von Mustern.** Sie sind in vielen Programmiersprachen und Tools verfügbar und bieten eine flexible Art, mit Zeichenketten umzugehen. Hier ist eine grundlegende Erklärung der Komponenten und Funktionsweise von RegEx:

## Grundlagen der Regular Expressions

### Grundlegende Zeichen
- **Literalzeichen**: Normale Zeichen wie Buchstaben und Zahlen entsprechen sich selbst.
- **Metazeichen**: Zeichen wie `.` (Punkt), `*` (Stern), `+` (Plus) und `?` (Fragezeichen) haben spezielle Bedeutungen.

### Metazeichen
- **`.`**: Steht für jedes Zeichen außer einem Zeilenumbruch.
- **`*`, `+`, `?`**: Quantifizierer, die angeben, wie oft ein Element vorkommen soll. `*` steht für 0 oder mehr, `+` für 1 oder mehr und `?` für 0 oder 1.
- **`^`, `$`**: Anker, die den Anfang (`^`) und das Ende (`$`) einer Zeile markieren.

### Zeichenklassen
- Ermöglichen das Matchen einer Gruppe von Zeichen. Zum Beispiel `[abc]` trifft auf jeden Buchstaben `a`, `b` oder `c` zu.
- **`\d`**, **`\w`**, **`\s`**: Stehen für digitale Ziffern, Wortzeichen und Leerzeichen. Ihre Großbuchstaben-Varianten (`\D`, `\W`, `\S`) verhalten sich entgegengesetzt.

### Gruppen und Bereichsspezifikation
- **Klammern** (`()`): Gruppieren Teile des Ausdrucks und können zum Extrahieren von Teilzeichenketten verwendet werden.
- **Alternativen** (`|`): Bedeuten "oder" und erlauben das Matchen von einem von mehreren Mustern.

### Escape-Zeichen
- Ein Backslash (`\`) wird verwendet, um spezielle Zeichen zu "entwerten" (z.B. `.` um einen Punkt zu matchen).

### Gierig vs. Faul
- RegEx-Muster sind standardmäßig "gierig", was bedeutet, dass sie versuchen, das längstmögliche Match zu finden. Durch Hinzufügen eines `?` nach einem Quantifizierer wird das Verhalten "faul" oder "minimal", d.h., es sucht das kürzestmögliche Match.

### Beispiel
- Das Muster `\d{2,4}` würde nach einer Zahlenfolge suchen, die mindestens 2 und höchstens 4 Ziffern lang ist.

<br>

Reguläre Ausdrücke sind extrem mächtig und können von sehr einfach bis sehr komplex reichen. Sie sind ein unverzichtbares Werkzeug in der Softwareentwicklung, besonders wenn es um die Verarbeitung von Texten geht.