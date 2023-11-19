# Projekt „Arbeitsboard“:

Speziell in der agilen Arbeitsweise sind Arbeitsboards sehr beliebt, um transparent das aktuelle Geschehen darzustellen. Grundsätzlich eignen sich für solche Darstellungen viele verschiedene Tabellen – es muss nur eine Art „Status“ geben.

Ziel des Projekts ist, eine Web-Plattform (in Angular oder React) prototypisch zu implementieren, um beispielsweise Aufgaben (oder Tickets, Ideen, …) in Abhängigkeit ihres Status zu visualisieren. So kann es beispielsweise drei Spalten „Offen“, „In Arbeit“ und „Erledigt“ geben und alle zugehörigen Aufgaben werden in der jeweiligen Spalte angezeigt. Da es unterschiedliche Anwendungsfälle für diese Darstellungsform gibt, wäre es ideal, wenn auch die Spalten selbst dynamisch erzeugt werden (bspw. festgelegt in der Datenbank / Konfiguration wird mittels REST abgerufen) und nicht statisch vordefiniert sind.

Je nach Zeit und Fortschreiten des Projekts, kann das Arbeitsboard um nützliche weitere Funktionen ergänzt werden. Beispielsweise, dass Aufgaben von der einen Spalte in die nächste verschoben werden können und somit sich ihr Status ändert (Request an das Backend, Änderung in der Datenbank). Oder dass bei Klick auf eine Aufgabe weitere Details angezeigt werden, die in der Übersicht noch nicht ausreichend dargestellt werden konnten (Priorität, Kategorie, zugeordnete Person, Sollerledigungsdatum, etc.).

Das Frontend kommuniziert mit deinem Backend idealerweise über REST (im JSON-Format), sodass dein Backend mit unserer REST-Schnittstelle dann möglichst einfach ausgetauscht werden könnte.

Wenn noch Zeit für weitere Features bleibt, können wir uns diesbezüglich gerne abstimmen.

Liebe Grüße

Christof Feischl

