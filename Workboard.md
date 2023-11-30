# Workboard

## About

Mein Abschlussprojekt für die Codersbay. Erstellt wurde die Angabe von einer Firma, in der ich mich nach Abschluss der Ausbildung bewerben möchte.

## Was?

### Angabe der Firma
Speziell in der agilen Arbeitsweise sind Arbeitsboards sehr beliebt, um transparent das aktuelle Geschehen darzustellen. Grundsätzlich eignen sich für solche Darstellungen viele verschiedene Tabellen – es muss nur eine Art „Status“ geben.

Ziel des Projekts ist, eine Web-Plattform (in Angular oder React) prototypisch zu implementieren, um beispielsweise Aufgaben (oder Tickets, Ideen, …) in Abhängigkeit ihres Status zu visualisieren. So kann es beispielsweise drei Spalten „Offen“, „In Arbeit“ und „Erledigt“ geben und alle zugehörigen Aufgaben werden in der jeweiligen Spalte angezeigt. Da es unterschiedliche Anwendungsfälle für diese Darstellungsform gibt, wäre es ideal, wenn auch die Spalten selbst dynamisch erzeugt werden (bspw. festgelegt in der Datenbank / Konfiguration wird mittels REST abgerufen) und nicht statisch vordefiniert sind.

Je nach Zeit und Fortschreiten des Projekts, kann das Arbeitsboard um nützliche weitere Funktionen ergänzt werden. Beispielsweise, dass Aufgaben von der einen Spalte in die nächste verschoben werden können und somit sich ihr Status ändert (Request an das Backend, Änderung in der Datenbank). Oder dass bei Klick auf eine Aufgabe weitere Details angezeigt werden, die in der Übersicht noch nicht ausreichend dargestellt werden konnten (Priorität, Kategorie, zugeordnete Person, Sollerledigungsdatum, etc.).

Das Frontend kommuniziert mit deinem Backend idealerweise über REST (im JSON-Format), sodass dein Backend mit unserer REST-Schnittstelle dann möglichst einfach ausgetauscht werden könnte.

Wenn noch Zeit für weitere Features bleibt, können wir uns diesbezüglich gerne abstimmen.

Liebe Grüße

Christof Feischl

<br>

### Meine Zusammenfassung der Angabe
Ein online Ticket-System/Workboard, welches Fortschrittskontrolle, Übersicht und Organisition über verschiedene Arbeitsabläufe/Arbeitsschritte/Todos/Ideen und speziell für das arbeiten in der agilen Softwareentwickling bereitstellt. 

Mithilfe des Workboards werden Tickets erstellt, welche in der jeweilligen Spalte + zugehörigen Status visuel repräsentiert werden.

Als Vorbild dienen ua. bestehende Konzepte von diversen Anbietern (Github, HubSpot, Solar Winds, Happy Fox, Jira Service Desk, etc.). 


## Wie?

### Technologien:

- MongoDB
- Node.js, NPM 
- REST API (JSON Kommunikation)
- Swagger?? 
- Typescript
- React/Angular (HTML/CSS)
- Angular Material Bibliothek

<br>

## Features

Der Fokus des Projekts liegt klar im Frontend.

- Erstellung/Anzeige von Todos (Tickets) basierend auf den Aufgaben.
- Drag-and-Drop-Funktionalität zum Verschieben von Tickets zwischen den verschiedenen Status-Spalten. 
- Ein Klick auf eine Aufgabe öffnet einen Link, welcher das Ticket im Volbildmodus anzeigt.
- Beim erstellen eines Tickets öffnet sich ein Fesnter mit den Details des Tickets (Priorität, Name/Bezeichnung, Beschreibung, ...)
- Stempel wird bei der Erstellung eines Tickets automatisch angangebracht. Stempel = Änderungsdatum + Autor (Genaues Stempelmuster noch unklar)

### Backend

- Stempel: Titel, Author, Datum, Priorität, 

Das Frontend kommuniziert mit dem Backend über REST (im JSON-Format), sodass das Backend mit der Firmeneigenen REST-Schnittstelle möglichst einfach ausgetauscht werden kann. **(Microservices??)**

- Gateway - Security Hash - Verifizierungs Token (Stichworte: Ozelot Framework, Http Verschlüsselung, etc)
- REST API zur Kommunikation (Endpoints)
- Ticket Anfragen verarbeiten: CRUD
- Dynamische erzeugte Spalten (bspw. festgelegt in der Datenbank / Konfiguration wird mittels REST abgerufen)
- Echtzeit-Aktualisierung des Workboards in der Datenbank
- Filter- und Suchfunktionen über bestehende Tickets
- Stempel wird bei der Erstellung eines Tickets automatisch hinzugefügt. Stempel = Änderungsdatum + Autor (Genaues Stempelmuster noch unklar)

### Optional

- Tickets können privat und öffentlich erstellt werden

<br>

## Brainstorming (Work in Progress)

- welche Features könnten noch hinzugefügt werden, die **speziell** für die agile Softwareentwicklung in kombination zu einem Workboard funktionieren könnten?

### Welche Features werden nicht gegeben sein?

- Mobile First
- Login
- 

### Welche Features könnten noch implementiert werden?

- User-Kommentare zu jedem Ticket
- priority Colour Indikator
- Verschlüsselung der Daten mit hasches
- Mobile Darstellung verbessern


## Fragen


- Wie wird die Abfrage aus dem vorhandenen Backend der BMD aussehen? Damit ich meine Webstie darauf einstellen kann.
--- 
- Wie kann ich neue instanzen einer komponente via button aus einer anderen komponente kreieren
---
