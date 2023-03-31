# Ausbildungsbetrieb

FLYERALARM Industrial Print GmbH

# Projektbezeichnung

Implementierung eines neuen Systems zur Erfassung von Versandverpackungen mit Hilfe von Bild- und Sensordaten zur Erfüllung der Novelle des Verpackungsgesetzes

# Projektbeschreibung

#### Zielgruppe und Auftraggeber

Der Auftraggeber ist die Geschäftsleitung und die Zielgruppe sind die Mitarbeiter der Produktion. Als Ansprechpartner bezüglich fachlicher Anforderungen an das Projekt dienen
die unterschiedlichen Fachabteilungen.

#### Ist-Zustand

Der Ist-Zustand besteht aus einer Konsolen-Anwendung, welche die Paketgröße und Anzahl für jeden Auftrag individuell bei Eingang der Daten berechnet. Berücksichtigt werden dabei unzählige Faktoren wie beispielsweise Auflage, Stärke, Größe und Gewicht des Papiers und des Kartons, das Maximalgewicht des Paketdienstleisters und ob ein Rollenkern verwendet werden kann. Diese Berechnung ist auch für jeden Standort unterschiedlich, da nicht alle Kartonagen in jedem Werk verwendet werden. All diese in MSSQL-Datenbanken gespeicherten Informationen und diverse Sonderfälle für verschiedene Produkte müssen regelmäßig manuell gepflegt werden. Durch die Änderung des Verpackungsgesetzes gibt es nun zusätzliche gesetzliche Anforderungen an die Erfassung und Meldung verwendeter Verpackungen, was aktuell durch die unterschiedlichen Berechnungen und Ausnahmen an den Standorten nur schwer abbildbar oder planbar ist. Das manuelle Pflegen der Verpackungsdaten ist nicht mehr praxistauglich.

#### Soll-Konzept

Um von den Erfahrungswerten der verpackenden Mitarbeitenden zu profitieren, sollen die Pakete nach dem Verpacken und kurz vor dem Versand gescannt und somit dem entsprechenden Auftrag zugeordnet werden. Die gesammelten Daten werden mit bekannten Kartonagen-Abmessungen verglichen und in einer Datenbank abgespeichert. So können aus diesen gesammelten Daten einheitliche Verpackungsrichtlinien geschaffen und die Datenmeldung bzgl. des Verpackungsgesetzes erleichtert werden.

#### Projektdurchführung

Zur Erfassung der Versandverpackungen werden Distanzsensoren und eine Kamera eingesetzt. Zur Speicherung der Daten wird eine Datenbank auf einem bestehenden Microsoft SQL-Server 2017 verwendet. Für die Datenbankanbindung wird die ASP .NET Core 6.0 Web API, die Programmiersprache C# und das Entity Framework Core zur Abbildung verwendet. Die API wird mit einer GitLab Pipeline als Docker Container erstellt und automatisiert im Docker Swarm verteilt. Mithilfe von Python und verschiedener Bildverarbeitungs-Bibliotheken werden die Sensor- und Bilddaten ausgelesen. Zur Entwicklung der REST-API und des Sensor- und Bildverarbeitungs-Programms werden die IDEs Visual Studio 2022 und PyCharm Community verwendet. Das kostenlose universale Datenbank-Tool DBeaver Community wird verwendet um die Datenbankeinträge einzusehen.

# Projektumfeld

Die FLYERALARM Industrial Print GmbH ist mit mehr als 2000 Mitarbeiters an acht Standorten in Deutschland vertreten. Neben der Herstellung verschiedenster Druckerzeugnisse werden diese Produkte auch weiterverarbeitet, montiert, konfektioniert und für den Versand vorbereitet. Das  Kerngeschäft der IT-Abteilung ist hierbei das Aufarbeiten der Druckdaten von FLYERALARM, um diese den Mitarbeitern in der Produktion, den Druckmaschinen aber auch der Geschäftsführung zur Verfügung zu stellen.

# Projektphasen mit Zeitplanung

1. Analyse 10h
- Ist-Analyse 2h
- "Make or buy"-Analyse 2h
- Analyse der benötigten Libraries 2h
- Analyse der benötigten Schnittstellen von Fremdsystemen 2h
- Soll-Konzept 2h
2. Entwurf 8h
- Entwurf der Datenbankstruktur 2h
- Entwurf der REST-API 2h
- Entwurf der Datenabfrage und -verarbeitung der Sensoren 4h
3. Implementierung 39h
- Erstellen der Datenbank 4h
- Erstellen der REST-API 9h
    * Datenbankanbindung 2h
    * Routenimplementierung 4h
    * Vergleich gemessener Werte mit bekannten Verpackungen 2h
    * Schnittstellendokumentation mit Swagger 1h
- Platzierung der Sensoren 1h
- Erstellen des Sensor-Abfrage-Workers 9h
    * Abfragen der Sensoren 8h
    * REST-Posts ab API 1h
- Erstellen des Bildverarbeitungs-Workers 8h
    * Aufnahme und Abspeichern des Bildes 1h
    * Erkennen des Kartons im Bild 7h
    * Erkennen wichtiger Informationen aus dem Bild 7h
    * REST-Posts an API 1h
4. Test 5h
- Code-Review 2h
- Schreibtischtests 3h
5. Einführung 6h
- Inbetriebnahme der API und der Sensor-Worker 5h
- Abnahme durch Teamleiter 1h
6. Dokumentation 12h
- Erstellen der Entwicklerdokumentation 4h
- Erstellen der Projektdokumentation 8h

Insgesamt 80h

# Dokumentation zur Projektarbeit

Die Beschreibung der REST-Schnittstellen wird während der Implementierungphase automatisch mit dem Swagger-Framework erstellt. Die Dokumentation der Projektarbeit wird stichpunktartig während der einzelnen Phasen im Projekt vorgenommen. Die Ausformulierung und die Entwicklerdokumentation werden am Ende des Projekts vorgenommen.

# Geplanter Bearbeitungszeitraum

Beginn: 03.10.2022 <br> 
Ende: 11.11.2022

# Anlagen

- keine

# Präsentationsmittel

- Laptop
- Beamer

# Themenbetreuer

Herr Marco Thiergart <br>
E-Mail: marco.thiergart@flyeralarm-industrialprint.com <br>
Telefon: +49 9391 50314902