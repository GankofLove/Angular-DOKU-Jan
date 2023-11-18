# Angular Basics


<br>

## Components

Bausteine, die wiederverwertbar sind. Angular = Modulare Software Architketur

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


## Verwendung einer Component
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

<br>

## Services (shared)
Stellen Sytem, Modul oder Komponentenweit geteilte Logik bereit. BSP: HTTP Requests, Kommunikation zwischen Komponenten.

geteilter/wiederverwendbarer Code der zw. komponenten oder anderen services. BSP: Requests

Verschiedene Komponenten können sich via Dependecy Injection bedienen.

Stellt Daten zur Verfügung um austausch zu ermöglichen. Backbone der App.

<br>

## Direktives (ngIf, ngFour, ngSwitch)
In Angular sind strukturelle Direktiven eine leistungsfähige Art von Direktiven, die dazu verwendet werden, das Layout eines HTML-Templates zu ändern, indem Elemente hinzugefügt, entfernt oder manipuliert werden. Sie verändern die Struktur des DOM (Document Object Model).

### `*ngIf`
Diese Direktive wird verwendet, um ein Element basierend auf einer Bedingung ein- oder auszublenden. Wenn die Bedingung wahr ist, wird das Element im DOM gerendert; wenn sie falsch ist, wird das Element aus dem DOM entfernt.

### `*ngFor`:

*ngFor ist eine Schleifen-Direktive, die verwendet wird, um eine Liste von Elementen zu wiederholen. Sie wird typischerweise verwendet, um Arrays oder Objekte in der Template-View durchzulaufen.

### `*ngSwitch`, `*ngSwitchCase`, `*ngSwitchDefault`:

Diese Gruppe von Direktiven arbeitet ähnlich wie eine Switch-Anweisung in vielen Programmiersprachen. *ngSwitch legt den Ausdruck fest, *ngSwitchCase definiert die Fälle, und *ngSwitchDefault wird angezeigt, wenn kein Fall zutrifft.

```html
<div [ngSwitch]="condition">
  <div *ngSwitchCase="'case1'">Fall 1</div>
  <div *ngSwitchCase="'case2'">Fall 2</div>
  <div *ngSwitchDefault>Standardfall</div>
</div>
```
Diese Direktiven sind besonders nützlich, um dynamische Interfaces zu erstellen, die auf die Daten und die Logik der Komponente reagieren. Sie sind ein zentraler Bestandteil von Angulars deklarativem Ansatz zur UI-Gestaltung.

## Pipes
formatierungshilfen im HTML. BSP: Währungen anzeigen (€, $, ...)

## Exports
Welche Teile dürfen von anderen Komponenten verwendet werden? (privat, public)

<br>

## Router

<br>

## ngOnInit
Die `ngOnInit`-Methode wird ausgeführt, nachdem Angular alle Eingabeproperties der Komponente mit ihren Anfangswerten initialisiert hat. Die `ngOnInit`-Methode einer Komponente wird genau einmal ausgeführt.

Dieser Schritt erfolgt, bevor das eigene Template der Komponente initialisiert wird. Dies bedeutet, dass Sie den Zustand der Komponente basierend auf ihren anfänglichen Eingabewerten aktualisieren können.

<br>

## ngOnChanges
Die `ngOnChanges`-Methode wird ausgeführt, nachdem sich irgendeine der Eingabeproperties der Komponente geändert hat.

Dieser Schritt erfolgt, bevor das eigene Template der Komponente überprüft wird. Dies bedeutet, dass Sie den Zustand der Komponente basierend auf ihren aktuellen Eingabewerten aktualisieren können.

Während der Initialisierung wird die erste `ngOnChanges`-Ausführung vor `ngOnInit` durchgeführt.

<br>

### Reactive Forms