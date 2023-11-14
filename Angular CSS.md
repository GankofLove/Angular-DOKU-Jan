## CSS Selektoren

![ng1](./assets/ng%201.png)



Ein CSS-Selektor ist der erste Teil einer CSS-Regel. Es handelt sich um ein Muster aus Elementen und anderen Begriffen, die dem Browser mitteilen, welche HTML-Elemente ausgewählt werden sollen, um die CSS-Eigenschaftswerte innerhalb der Regel auf diese anzuwenden. Die Elemente, die vom Selektor ausgewählt werden, werden als **Subjekt des Selektors** bezeichnet.

Einige Codebeispiele mit hervorgehobenem h1.
In anderen Artikeln sind Ihnen vielleicht einige verschiedene Selektoren begegnet, und Sie haben gelernt, dass es Selektoren gibt, die das Dokument auf unterschiedliche Weise ansprechen — zum Beispiel durch die Auswahl eines Elements wie h1 oder einer Klasse wie .special.

In CSS werden Selektoren in der CSS-Selektoren-Spezifikation definiert; wie jeder andere Teil von CSS müssen sie von Browsern unterstützt werden, um zu funktionieren. Die meisten Selektoren, auf die Sie stoßen werden, sind in der Level-3-Selektoren-Spezifikation und der Level-4-Selektoren-Spezifikation definiert, die beide ausgereifte Spezifikationen sind, daher finden Sie eine hervorragende Browserunterstützung für diese Sselektoren.

![css selektor](./assets/css%20selektor.png)

<br>

## CSS Selektor-Listen

Wenn mehr als ein Element dieselben CSS-Stile verwendet, können die einzelnen Selektoren zu einer Selektorliste zusammengefasst werden, so dass die Regel auf alle einzelnen Selektoren angewendet wird. Zum Beispiel, wenn ich denselben CSS-Stil für ein h1-Element und auch für eine Klasse .special habe, könnte ich dies als zwei separate Regeln schreiben.

```CSS
h1 {
  color: blue;
}

.special {
  color: blue;
}
```

wird zu:

```CSS
h1, .special {
  color: blue;
}
```

<br>

## Arten von Selektoren
Es gibt einige verschiedene Gruppierungen von Selektoren, und zu wissen, welche Art von Selektor Sie benötigen könnten, wird Ihnen helfen, das richtige Werkzeug für die Aufgabe zu finden. In den Unterartikeln dieses Artikels werden wir uns die verschiedenen Gruppen von Selektoren genauer ansehen.

### Typ-, Klassen- und ID-Selektoren
**Typ-Selektoren** zielen auf ein HTML-Element ab, wie zum Beispiel ein `<h1>`:


```css
h1 {
}
```
**Klassen-Selektoren** zielen auf ein Element ab, das einen spezifischen Wert für sein Klassenattribut hat:

```CSS
.box {
}
```
**ID-Selektoren** zielen auf ein Element ab, das einen spezifischen Wert für sein ID-Attribut hat:


```CSS
#unique {
}
```

<br>

## Pseudo-Klassen und Pseudo-Elemente
Diese Gruppe von Selektoren umfasst Pseudo-Klassen, die bestimmte Zustände eines Elements gestalten. Die Pseudo-Klasse :hover zum Beispiel wählt ein Element nur dann aus, wenn es mit dem Mauszeiger überfahren wird:


```CSS
a:hover {
}
```
Es beinhaltet auch Pseudo-Elemente, die einen bestimmten Teil eines Elements auswählen, anstatt des Elements selbst. Zum Beispiel wählt ::first-line immer die erste Zeile Text innerhalb eines Elements aus (ein <p> im untenstehenden Fall), so als ob ein <span> um die erste formatierte Zeile gewickelt und dann ausgewählt wurde.


```CSS
p::first-line {
}
```
<br>

## Kombinatoren
Die letzte Gruppe von Selektoren kombiniert andere Selektoren, um Elemente innerhalb unserer Dokumente anzusprechen. Das Folgende wählt zum Beispiel Absätze aus, die direkte Kinder von <article>-Elementen sind, unter Verwendung des Kind-Kombinators (>):


```CSS
article > p {
}
```

<br>

## Zusammenfassung
In diesem Artikel haben wir CSS-Selektoren vorgestellt, mit denen Sie gezielt bestimmte HTML-Elemente ansprechen können. Als Nächstes werden wir uns die Typ-, Klassen- und ID-Selektoren genauer ansehen.

Für eine vollständige Liste der Selektoren siehe unsere Referenz zu CSS-Selektoren. 