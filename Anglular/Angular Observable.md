# Angular Observables

Observables werden verwendet um "asynchronous" Tasks auzu führen oder das arbeiten mit asynchornen Daten zu ermöglichen.

Javascript ist eine **single threaded** Programmiersprache. Das bedeutet, dass der bestehende Code Zeile für Zeile ausgeführt wird. Mit der hilfe von Observables/async/Promises können Task quasi paralell bzw. im Hintergrund ausgeführt werden.


* asynchronous = Eine asynchrone Operation ist ein Vorgang in der Programmierung, bei dem eine Aufgabe ausgeführt wird, ohne dass der ausführende Thread (der Hauptablauf des Programms) darauf warten muss, dass die Aufgabe abgeschlossen wird. Das bedeutet, dass das Programm andere Operationen weiter ausführen kann, während die asynchrone Aufgabe im Hintergrund läuft.

### Beispiel: 
Wenn man zb einen HTTP Request an einen Server schickt, dauert dies meistens etwas länger. In diesem Fall würde JavaScrit (weil: single threaded) warten, bis der Code der Zeile fertig ausgeführt wird. Der restliche Code würde sich also verzögern, was nicht erwünscht ist. 

**async Code ist also "non blocking".**

Um dieses Tool in Angular zu verwenden, verwendet man Observables und Promises.

<br>

## Promises

* Promises = Es ist eine Art Container für einen Wert, der noch nicht bekannt ist, aber irgendwann in der Zukunft festgelegt wird. Promises werden verwendet, um mit asynchronen Operationen wie Netzwerkanfragen, Dateizugriffen oder zeitintensiven Berechnungen umzugehen. 

### Beispiel:
Wir machen einen Request an eine Datenbank mit dem Request, alle User in der Datenbank an zu zeigen. Sagen wir 1 mio User. Dieser Vorgang wird etwas dauern. Die Priomise gibt, wenn der Vorgang abgeschlossen ist, alle bestehenden Users wieder. Mit der `.then()` Methode, kann man angeben, was passieren soll, wenn die Promise erfüllt oder abgelehnt worden ist. Man kann mehrere `.then()` Methoden aneinander reihen, um sequenzielle asynchrone Operationen zu erstellen. Jeder .then()-Aufruf gibt eine neue Promise zurück, was das Zusammenfügen mehrerer asynchroner Vorgänge erleichtert.

Mit der `.catch()`-Methode einer Promise kann man Fehler behandeln, die in irgendeinem Teil der Promise-Kette auftreten. Dies hilft, einen sauberen und lesbaren Code zu schreiben, der Fehler effektiv handhabt.

---

* **Sind die gewünschten Daten verfügbar, werden diese immer geliefert, auch wenn diese nicht verwendet werden. **

---

<br>

## Callback Function

 Eine Callback-Funktion ist eine Funktion, die einer anderen Funktion als Argument übergeben wird und zu einem späteren Zeitpunkt aufgerufen wird. Dieser Mechanismus ermöglicht es, mit Ereignissen oder asynchronen Operationen wie Netzwerkanfragen, Dateioperationen oder zeitverzögerten Aktionen zu arbeiten.

 Um die Komplexität von Callbacks zu reduzieren, wurden in neueren JavaScript-Versionen Promises und das Async/Await-Muster eingeführt. Diese bieten eine sauberere und verständlichere Syntax für die Handhabung asynchroner Operationen.

<br>

## Observable

### Beispiel:
Selbes Szenario (1mio Useres Request). Mit der verwendung von Observables, werden die Daten **gestreamt**. Es wird also nicht gewartet, bis alle Daten verfügbar sind um dann alle aufeinmal anzuzeigen. Alle Daten werden "in kleinen Happen" geladen.

---

* **Sind die gewünschten Daten verfügbar, werden diese NUR DANN geliefert, wenn diese auch verwendet werden.**

---

Observables sind ein Feature von RxJs Framework und nicht native von JavaScript/Angular im Gegensatz zu Promises, welche nativ in JavaScript inkludiert sind.

<br>

## RxJS

= Reactive Extension library for JavaScript

Besteht aus zwei Hauptkomponenten:

1. Observable (Streamt die Daten)
2. Observer (Konsumiert die Daten)

Damit der Observer die Daten empfangen kann, muss er den Observable **subscriben**. In anderen Worten: Der Observer ist der Subscriber des Observable!  

```ts
// app.component.ts

// imports ...
import { Observabel } from 'rxjs';

// @component ...

expoert class AppComponent{
title = 'AngularObservable';

myObservable = new Observable((observser) => {
    console.log('Observable starts')
    
    // emiiting Data step by step (streamed)
    observer.next("1")
    observer.netx("2")
    observer.netx("3")
    observer.netx("4")
    observer.netx("5")

    // man könnte alternativ, die daten zb nach einer gewissen zeit streamen:
    setTimeout(()=>{observer.sex("1")}, 1000) // 1sec
    setTimeout(()=>{observer.sex("1")}, 2000) // 2sec..
    setTimeout(()=>{observer.sex("1")}, 3000)
    setTimeout(()=>{observer.sex("1")}, 4000)
    setTimeout(()=>{observer.sex("1")}, 5000)
});

ngOnInit(){
    // callback Functions
    this.myObservable.subscribe((val) => {
        console.log(val);
    });
}
}
```