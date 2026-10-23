Wochenplaner
Eine kleine Website, um am Einkaufstag die Gerichte für die kommende Woche auszuwählen und daraus automatisch eine Einkaufsliste zu erzeugen. Sie ist für die Bedienung am Handy gebaut und kommt ohne Server, Build-Schritt oder externe Bibliotheken aus: Die gesamte Seite steckt in einer einzigen Datei (index.html).
Funktionen
Auswahl: Gerichte mit + und − auswählen, wie oft sie gegessen werden sollen (maximal 14 Portionen pro Gericht). Filter für Standard (schnell), Mittag zum Vorbereiten und Abendessen. Pro Gericht gibt es eine Kurzbeschreibung und eine aufklappbare Zutatenliste.
Einkaufsliste: Wird aus der Auswahl berechnet, nach Supermarktbereichen sortiert und zusammengezählt. Positionen lassen sich abhaken. Mengen in g und ml werden auf 10 aufgerundet, alle anderen Einheiten auf ganze Zahlen.
Neues Gericht: Eigene Gerichte mit Name, Art, Zeit, Kurzbeschreibung und Zutaten hinzufügen. Selbst angelegte Gerichte lassen sich wieder löschen.
Hell- und Dunkelmodus: Die Seite folgt der Einstellung des Geräts.
Mitgelieferte Gerichte
Die Rezepte sind vegetarisch, überwiegend pflanzlich (einige mit Ei), reich an Gemüse und Hülsenfrüchten und sparsam mit gesättigten Fetten und Zucker. Alle Mengen gelten für eine Person. Nährwerte werden nicht berechnet. Salz und Pfeffer werden als vorhanden vorausgesetzt.
Eigene Gerichte hinzufügen
Im Tab Neues Gericht werden die Zutaten für eine Portion eingetragen, eine Zutat pro Zeile im Format Menge Einheit Zutat:
200 g Linsen
2 Stk Zwiebel
1 EL Olivenöl
Kommas als Dezimaltrennzeichen sind erlaubt (0,5 Stk Zitrone).
Heißt eine Zutat genauso wie eine bekannte Zutat (Groß- und Kleinschreibung egal), wird sie dem passenden Supermarktbereich zugeordnet. Unbekannte Zutaten landen unter Sonstiges.
Gleiche Zutaten mit gleicher Einheit werden in der Einkaufsliste zusammengezählt. Verwende deshalb immer dieselbe Einheit (z. B. immer g, nicht mal g und mal kg).
Datenspeicherung
Auswahl, abgehakte Positionen und eigene Gerichte werden gespeichert:
Bei Nutzung über Claude: im privaten Bereich des eigenen Kontos, also auf allen Geräten verfügbar.
Bei Nutzung auf einem anderen Hosting (z. B. GitHub Pages): nur im Browser des jeweiligen Geräts (localStorage). Das Löschen der Browserdaten oder ein Gerätewechsel führt zum Verlust.
Veröffentlichen mit GitHub Pages
Neues Repository auf GitHub anlegen.
Die Datei als index.html hochladen (Add file → Upload files) und mit Commit changes bestätigen.
Unter Settings → Pages bei Branch main und / (root) wählen und speichern.
Nach ein bis zwei Minuten ist die Seite unter https://<benutzername>.github.io/<repository>/ erreichbar.
Mitgelieferte Gerichte ändern
Die Gerichte stehen am Anfang des Skripts in index.html im Array D. Jeder Eintrag hat das Format:
["Name", Art, Minuten, "Kurzbeschreibung", [["Zutat", Menge pro Portion], ...]]
Art ist 0 (Standard), 1 (Mittag zum Vorbereiten) oder 2 (Abendessen). Zutaten müssen im Objekt IG (Einheit und Supermarktbereich) vorkommen. Neue Zutaten dort ergänzen.
Technik
Reines HTML, CSS und JavaScript in einer Datei, keine Abhängigkeiten. Layout mit Rücksicht auf Handy-Displays, inklusive Safe-Area-Abständen.
