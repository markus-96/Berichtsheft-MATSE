Diese LaTeX-Vorlage ist dafür gedacht, um ein Berichtsheft zu führen beziehungsweise Ausbildungsnachweise strukturiert zu führen.

Es ist möglich, einzelne Monatsberichte als Report oder alle Monatsberichte in einem Berichtsheft zu kompilieren.

# Ordnerstruktur
```
+--- Ausbildungsnachweis Nr 1                   <-- Ordner des ersten Ausbildungsnachweis
|   +--- Ausbildungsbericht_gebunden.tex        <-- Datei für das gebundene Berichtsheft
|   +--- Ausbildungsnachweis.pdf                <-- Ausbildungsnachweis als pdf
|   +--- Ausbildungsnachweis.tex                <-- Ausbildungsnachweis: main-Dokument
|   +--- bericht.tex                            <-- Ausbildungsnachweis: Text des Berichts
|   +--- document_info.tex                      <-- Ausbildungsnachweis: Eckdaten
|   +--- tables.tex                             <-- Ausbildungsnachweis: Daten für die Tabellen
+--- Berichtsheft_gebunden.pdf                  <-- Berichtsheft mit allen Ausbildungsnachweisen
+--- Berichtsheft_gebunden.tex                  <-- Berichtsheft: main-Dokument
+--- document_info.tex                          <-- Berichtsheft: Eckdaten
+--- LICENSE
+--- titlepage.tex                              <-- Berichtsheft: Titelseite
```

Für jeden Ausbildungsnachweis, also jeden Monat, muss ein neuer Ordner angelegt werden. Der fünfzehnte 
Ausbildungsnachweis muss zum Beispiel in den Ordner `Ausbildungsnachweis Nr 15` abgelegt werden. Hierzu 
legt man sich am Besten einen Vorlagen-Ornder `Ausbildungsnachweis Nr` an, der die wichtigsten Dateien 
enthält.

# vorgesehene Arbeitsweise
Nach dem Kopieren dieses Repositories sollten folgende Schritte unternommen werden: 
 - Umbenennen des Ordners `Ausbildungsnachweis Nr 1` in `Ausbildungsnachweis Nr`
 - in der Datei `Ausbildungsnachweis Nr/document_info.tex` folgende Punkte wie folgt ändern:
   ```
    \renewcommand{\Vorname}{Max}                <-- richtiger Vorname
    \renewcommand{\Nachname}{Mustermann}        <-- richtiger Nachname
    \renewcommand{\Monat}{August}               <-- löschen
    \renewcommand{\Jahr}{2023}
    \renewcommand{\Betreuer}{Ulrich Höbel}      <-- richtiger Betreuer
    \renewcommand{\Institut}{Intitut f. Super-MATSEs} <-- richtiges Institut
    \renewcommand{\Datum}{31.08.2023}           <-- löschen
    \renewcommand{\BerichtNr}{1}                <-- löschen
   ```
 - in der Datei `document_info.tex` alles anpassen, wie oben.

## monatlicher Ausbildungsbericht:
 - Ordner `Ausbildungsnachweis Nr` kopieren und die Nummer anpassen
 - in der Datei `tables.tex` die einzelnen Tage eintragen, an denen man krank, im Urlaub, ... war
 - in der Datei `bericht.tex` den Tätigkeitsbericht verfassen
 - in der Datei `document_info.tex` die Nummer des Berichts, den Monat, das Jahr und das Datum anpassen
 - mittels der Datei `Ausbildungsnachweis.tex` die pdf kompilieren

## Berichtsheft
Möchte man alle Berichte zusammen in einem Buch als pdf kompilieren, zum Beispiel am Ende der Ausbildung,
geht man wie folgt vor:
 - in der Datei `document_info.tex` gegebenenfalls das Datum anpassen
 - in der Datei `Berichtsheft_gebunden.tex` in die Liste `\readlist*\Berichte{1,2}` alle Berichte hinzufügen,
   die in das Berichtsheft aufgenommen werden sollen
 - mittels der Datei `Berichtsheft_gebunden.tex` die pdf kompilieren
