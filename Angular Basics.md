# Angular Basics

## Keywords:

- Property Binding
- Decorator
- wildcard

## DOM

Das DOM, oder "Document Object Model", ist ein wichtiger Begriff in der Webentwicklung. Hier ist eine einfache Erklärung, die auch für Programmieranfänger verständlich ist:

Stellen Sie sich das DOM als eine Art Brücke zwischen Ihrem HTML-Code (die Struktur Ihrer Webseite) und dem, was im Webbrowser des Benutzers angezeigt wird, vor. Wenn eine Webseite geladen wird, liest der Browser den HTML-Code und erstellt anhand dieses Codes das DOM.

Das Besondere am DOM ist, dass es Ihre Webseite als eine Art Baumstruktur darstellt, in der jedes Element, jeder Text und jedes Attribut ein "Knoten" im Baum ist. Zum Beispiel ist in HTML der `<body>-Tag` ein Knoten, und alle Elemente darin, wie `<p>`, `<div>`, `<span>`, sind untergeordnete Knoten.

### 1. Interaktivität: 
Durch das DOM können JavaScript und andere Skriptsprachen mit der Webseite interagieren. Wenn Sie beispielsweise ein Element auf Ihrer Webseite ändern möchten (wie das Hinzufügen von Text oder das Ändern der Farbe), können Sie dies über das DOM tun, ohne den ursprünglichen HTML-Code zu ändern.

### 2. Dynamische Änderungen: 
Sie können das Aussehen und Verhalten Ihrer Webseite dynamisch ändern, ohne die Seite neu laden zu müssen. Dies ist die Grundlage für viele interaktive und dynamische Webseiten.

### 3. Ereignishandhabung: 
Das DOM ermöglicht es auch, auf Benutzeraktionen wie Klicks, Tastendruck oder Mausbewegungen zu reagieren und entsprechend zu handeln.

Kurz gesagt, das DOM ist eine programmierbare Repräsentation Ihrer Webseite, die es ermöglicht, die Seite dynamisch zu ändern und mit Benutzeraktionen zu interagieren. Es ist eine Schlüsselkomponente, die moderne, interaktive Webseiten möglich macht.







<br>

# Components

Jede Komponente muss folgendes haben:

- Eine **TypeScript-Klasse** mit Verhaltensweisen wie das Verarbeiten von Benutzereingaben und das Abrufen von Daten von einem Server
- Eine **HTML-Vorlage**, die steuert, was in das DOM gerendert wird
- Ein **CSS-Selektor**, der definiert, wie die Komponente in HTML verwendet wird

```ts
@Component({
  selector: 'app-dashboard',
  standalone: true, // Angular 13+
  imports: [CommonModule], // Standalone
  templateUrl: './dashboard.component.html', 
  styleUrl: './dashboard.component.css' 
})
```

<br>

### Weitere häufige Metadaten in Komponenten
- `standalone: true` — Der empfohlene Ansatz zur Vereinfachung der Autorenerfahrung von Komponenten
- `styles` — Ein String oder ein Array von Strings, das alle CSS-Stile enthält, die auf die Komponente angewendet werden sollen

Mit diesem Wissen hier ist eine aktualisierte Version unserer TodoListItem-Komponente.

<br>

```ts
// todo-list-item.component.ts
@Component({
  standalone: true,
  selector: 'todo-list-item',
  template: `
    <li>(TODO) Read Angular Essentials Guide</li>
  `,
  styles: `
    li {
      color: red;
      font-weight: 300;
    }
  `,
})
export class TodoListItem {
  /* Component behavior is defined in here */
}
```

<br>

### Trennung von HTML und CSS in separate Dateien
Für Teams, die ihre HTML- und/oder CSS-Dateien separat verwalten möchten, bietet Angular zwei zusätzliche Eigenschaften: `templateUrl` und `styleUrl`.

<br>

```ts
// todo-list-item.component.ts
@Component({
  standalone: true,
  selector: 'todo-list-item',
  templateUrl: './todo-list-item.component.html',
  styleUrl: './todo-list-item.component.css',
})
export class TodoListItem {
  /* Component behavior is defined in here */
}
```

```ts
<!-- todo-list-item.component.html -->
<li>(TODO) Read Angular Essentials Guide</li>
```

```ts
// todo-list-item.component.css
li {
  color: red;
  font-weight: 300;
}
```

<br>

### Verwendung einer Komponente
Ein Vorteil der Komponentenarchitektur ist, dass Ihre Anwendung modular ist. Mit anderen Worten, Komponenten können in anderen Komponenten verwendet werden.

Unter Verwendung der vorherigen TodoListItem-Komponente sieht der alternative Ansatz wie folgt aus:

Um eine Komponente zu verwenden, müssen Sie:

1. Die Komponente in die Datei importieren
2. Sie zum `imports`-Array der Komponente hinzufügen
3. Den Selektor der Komponente in der Vorlage verwenden

Hier ist ein Beispiel einer TodoList-Komponente, die die TodoListItem-Komponente von vorher importiert:

<br>

```ts
// todo-list.component.ts
import {TodoListItem} from './todo-list-item.component.ts';
@Component({
  standalone: true,
  imports: [TodoListItem],
  template: `
    <ul>
      <todo-list-item></todo-list-item>
    </ul>
  `,
})
export class TodoList {}
```