# Moodle FlexAccess Plugin-Familie

Willkommen im zentralen Repository der **Moodle FlexAccess Plugin-Familie**. Dieses Repository dient als übergeordnete Dokumentations- und Einstiegsseite für alle zugehörigen Komponenten sowie als zentraler Anlaufpunkt für Fehlerberichte und Feature-Vorschläge.

## Über FlexAccess

**FlexAccess** ermöglicht flexible Zugänge zu Moodle-Kursen, ohne alle Nutzungsszenarien in ein einziges Plugin zu pressen. Die Plugin-Familie trennt Identität, Kurszugang, Aktivierung im Kurs und Administration in vier klar abgegrenzte Komponenten, die gemeinsam ein System bilden.

Typische Einsatzszenarien sind beispielsweise Demonstrationskurse, Vorkurse, Orientierungskurse, Schulklassen, Workshops oder andere Angebote, bei denen Teilnehmende schnell und kontrolliert Zugang erhalten sollen.

Die vier Plugins werden **gemeinsam veröffentlicht**, tragen dieselbe Versionsnummer und sind als zusammengehöriges System konzipiert. Eine Teilinstallation ist daher nicht vorgesehen.

## Enthaltene Plugins

Die FlexAccess-Familie besteht aus vier eigenständigen Moodle-Plugins:

* **[FlexAccess Authentication (auth_flexaccess)](https://github.com/ralferlebach/moodle-auth_flexaccess)**  
  Verwaltet die Identitätsschicht: temporäre Nutzerkonten, Umwandlung in dauerhafte Konten, Magic-Login-Links sowie die zentrale, rate-limitierte Mail-Queue.

* **[FlexAccess Enrolment (enrol_flexaccess)](https://github.com/ralferlebach/moodle-enrol_flexaccess)**  
  Steuert, wer einen Kurs betreten darf und auf welchem Weg. Dazu gehören unter anderem temporärer Zugang, Schnellregistrierung, Magic Login, Gastzugang, Zugangsschlüssel, Kapazitätsgrenzen, Zeitfenster sowie Rollen- und Kohortenbeschränkungen.

* **[FlexAccess Activity (mod_flexaccess)](https://github.com/ralferlebach/moodle-mod_flexaccess)**  
  Stellt innerhalb eines Kurses einen gezielten Aktivierungspunkt bereit, an dem ein temporärer Zugang in ein dauerhaftes Nutzerkonto überführt werden kann, ohne bereits erzielte Lernfortschritte zu verlieren.

* **[FlexAccess Administration (tool_flexaccess)](https://github.com/ralferlebach/moodle-tool_flexaccess)**  
  Bietet die administrative Sicht auf das Gesamtsystem: Nutzer- und Kontenübersicht, Systemstatus, Mail-Queue, Richtlinien, Einladungen, Kampagnen sowie anonyme Zugangslisten mit ausdruckbaren Login-Karten.

## Zusammenspiel der Komponenten

Die Verantwortlichkeiten sind bewusst getrennt:

| Komponente | Aufgabe |
| --- | --- |
| `auth_flexaccess` | Identität und Lebenszyklus der FlexAccess-Konten |
| `enrol_flexaccess` | Kurszugang und Zugangsrichtlinien |
| `mod_flexaccess` | Aktivierung eines temporären Kontos innerhalb des Kurses |
| `tool_flexaccess` | Administration, Monitoring und organisierte Zugangsvergabe |

Dadurch wird dieselbe Regel nicht an mehreren Stellen implementiert: Identität wird zentral durch `auth_flexaccess` behandelt, Zugangsentscheidungen durch `enrol_flexaccess`, die Aktivierung im Kurs durch `mod_flexaccess` und administrative Prozesse durch `tool_flexaccess`.

## Voraussetzungen

Die aktuelle FlexAccess-Familie benötigt:

* **Moodle 4.5 oder neuer**
* alle vier FlexAccess-Plugins in **derselben Version**

Die Plugins sind als gemeinsam zu installierendes Set ausgelegt.

## Installation

Installiere die vier Plugins in die entsprechenden Verzeichnisse deiner Moodle-Installation:

1. `auth_flexaccess` nach `/auth/flexaccess`
2. `enrol_flexaccess` nach `/enrol/flexaccess`
3. `mod_flexaccess` nach `/mod/flexaccess`
4. `tool_flexaccess` nach `/admin/tool/flexaccess`

Führe anschließend das Moodle-Upgrade über die Administrationsoberfläche oder die Kommandozeile aus:

```bash
php admin/cli/upgrade.php
```

> **Wichtig:** Installiere und aktualisiere die vier Plugins gemeinsam. Unterschiedliche FlexAccess-Versionen oder eine unvollständige Installation sind nicht als unterstützter Betriebszustand vorgesehen.

## Zentrale Funktionen

Je nach Konfiguration unterstützt FlexAccess unter anderem:

* temporäre Moodle-Konten mit begrenzter Lebensdauer,
* Schnellregistrierung für neue Nutzerinnen und Nutzer,
* Magic Login über einmalige Links,
* kontrollierten Gastzugang,
* Zugangskennwörter und zeitlich begrenzte Zugänge,
* Kapazitätsgrenzen,
* Richtlinien auf Site-, Kursbereichs- und Kursebene,
* Einladungen und Kampagnenlinks,
* anonyme Zugangslisten für Gruppen,
* ausdruckbare Login-Karten,
* Umwandlung temporärer Konten in dauerhafte Nutzerkonten,
* zentrale Mail-Queue mit Rate Limiting,
* administrative Diagnose- und Reparaturfunktionen.

Die Detaildokumentation der jeweiligen Funktionen befindet sich in den README-Dateien der vier Plugin-Repositories.

## Fehlerberichte & Feature-Vorschläge

Bitte nutze den zentralen Issue-Tracker dieses Dach-Repositories für pluginübergreifende Fehlerberichte, Integrationsprobleme und Feature-Vorschläge.

Fehler oder Erweiterungen, die eindeutig nur eine einzelne Komponente betreffen, können alternativ direkt im jeweiligen Plugin-Repository gemeldet werden.

## Entwicklung

Die vier Plugins werden gemeinsam entwickelt und veröffentlicht. Änderungen an gemeinsamen Schnittstellen oder Datenflüssen sollten daher immer mit Blick auf die gesamte Plugin-Familie geprüft werden.

Die aktuellen Entwicklungsstände befinden sich in den jeweiligen GitHub-Repositories:

* [moodle-auth_flexaccess](https://github.com/ralferlebach/moodle-auth_flexaccess)
* [moodle-enrol_flexaccess](https://github.com/ralferlebach/moodle-enrol_flexaccess)
* [moodle-mod_flexaccess](https://github.com/ralferlebach/moodle-mod_flexaccess)
* [moodle-tool_flexaccess](https://github.com/ralferlebach/moodle-tool_flexaccess)

---

Projekt-Maintainer: [Ralf Erlebach](https://github.com/ralferlebach)
