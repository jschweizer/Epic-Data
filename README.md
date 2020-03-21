# Epic-Data
Eine dezentrale, hoch skalierbare, offene Plattform für die Aggregation, Verarbeitung und Veröffentlichung von verifizierten gesellschaftlich relevanten Daten. 

**Ziel**: Existierende Datenquellen, Analyse und Visualisierungswerkzeuge verknüpfen. Dabei die Authentizität der Daten und Qualität der Analyse garantieren. Daten sind frei öffentlich verfügbar.

## Eigenschaften
* Dezentrale Datenerfassung
* Verifizierte Daten
* Offenes Dateiformat
* Keine Abhängigkeit von zentralen Servern
* Beliebig skalierbar
* Weiterleitung in Echtzeit
* Krisensicher, da unabhängig von einzelnen Knoten
* Offen zugänglich (Open Data)
* Analyse Knoten können frei eingebunden werden (z.B. von Universitäten, RKI, etc.)
* Beliebige Visualisierungstools können frei auf Daten zugreifen.

## Herausforderung
Gesellschaftlich relevante Daten fallen oft über das ganze Land, ja sogar die ganze Welt verteilt an (COVID-19, CO2 Ausstoß, etc.). Probleme:
* Erfassung und Weiterleitung der Daten ist mühselig, langsam und uneinheitlich.
* Es existieren keine einheitlichen Datenformate.
* Verifizierte Datensätze sind schlecht zugänglich.
* Oftmals werden (wenn überhaupt) nur Zusammenfassungen veröffentlicht.
Entscheidungsträgern (Regierungen auf allen Ebenen, Krankenhäuser, Versorgern, etc.) und der Öffentlichkeit mangelt es an hochwertig aufbereiteten, aktuellen, viele Perspektiven abdeckenden Informationen. Nur wenige Stakeholder sind an der Informationskette beteiligt. Viel Potential bleibt auf der Strecke, weil keine Möglichkeit zur Partizipation besteht.

Die Komponenten einer Lösung:

## Open Data Pool
Die Grundlage ist ein frei zugänglicher offener Datenpool. Dieser Pool ist dezentral organisiert. Es gibt keine zentralen Server. Jeder Teilnehmer (PC mit Netzzugang) stellt ein Knoten dar. Jeder Knoten hält seine eigenen Daten vorrätig und kopiert externe Daten, die er verarbeitet (Redundanz). Das Open Source Projekt IPFS (Interplanetary File System) bietet eine solide Grundlage.

Jeder Knoten hat einen öffentlichen Schlüssel (https://de.wikipedia.org/wiki/Public-Key-Infrastruktur) über den er identifiziert werden kann.

## Datenquellen
Der Pool ist für alle offen zugänglich (schreiben und lesen). Publizierte Daten müssen mit dem eigenen privaten Schlüssel signiert werden. So kann Authentizität garantiert werden (siehe Zertifikation).

*Beispiel*: Krankenhäuser, die anonymisierte (!) Krankenberichte publizieren.

## Zertifikation
Zertifizierende Knoten sind spezielle Datenquellen. Sie publizieren Listen von zertifizierten öffentlichen Schlüsseln.

*Beispiel*: Gesundheitsämter publizieren die öffentlichen Schlüssel aller ihnen zugeordneten medizinischen Einrichtungen. So können an COVID-19 relevanten Daten interessierte Dritte sicherstellen, dass nur verifizierte Krankendaten verarbeitet werden.

## Web of Trust
Auf oberster Ebene stehen Regierungen, die verifizierte Listen von Gesundheitsämtern publizieren. Der öffentliche Schlüssel der Regierung kann auf der offiziellen Website der Regierung veröffentlich werden. So kann jeder an Open Data Interessierte von einem verifizierten Startpunkt aus beginnen und sich durch den Pool navigieren.

## Aggregation
Interessierte Stellen (RKI, Ämter, Forschungseinrichtungen, technisch versierte Journalisten, etc.) können nun verifizierte Daten zusammenfassen und auswerten. Die Ergebnisse werden ebenfalls im Open Data Pool publiziert. Die Webseiten dieser Organisation veröffentlichen ihre öffentlichen Schlüssel. So kann garantiert werden, dass eine Analyse tatsächlich z.B. vom Robert Koch Institut stammt.

## Visualisierung
Visualisierungswerkzeuge können über den Pool die Ergebnisse von ausgesuchten Aggregatoren abonnieren.

*Beispiele*:
* Eine Smartphone App für das allgemeine Publikum.
* Das Dashboard einer Wochenzeitung, Landrats, Bürgermeister, etc.
* Versorger und Krankenhäuser sind permanent auf dem Laufenden, wobei sie genau die Daten und Perspektiven bekommen, die ihren Aufgaben am besten gerecht werden.

## Technische Umsetzung
* IPFS für den Datenpool
* WolkenKit für die lokale Datenverarbeitung (Caching) in Analyse oder Aggregationsknoten
* JSONLD (linked data) als offenes erweiterbares Dateiformat
* Adapter können legacy Formate in JSONLD konvertieren
* Einfach Web UIs zur manuellen Pflege von Daten
* Adapter binden existierende Analyse Tools (z.B. http://www.aiit.io, http://covidsim.eu) oder Visualisierungen ein
