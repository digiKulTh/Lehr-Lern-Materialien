# Digitale Kulturwerkbank Thüringen@ThULB. 
Hier finden sich die Materialien aus dem Lehrinnovationsprojekt [digitale Kulturwerkstatt Thüringen (digiKulTh)](https://dksm.thulb.uni-jena.de/digikulth/), durchgeführt im Rahmen von [Freiraum2023](https://stiftung-hochschullehre.de/foerderung/freiraum/) der [Stiftung Innovation in der Hochschullehre](https://stiftung-hochschullehre.de/) an der [Thüringer Universitäts- und Landesbibliothek Jena](https://www.thulb.uni-jena.de/home).

## Zielgruppe und Inhalt des Repositoriums
Das Repositorium richtet sich primär an Hochschul-Lehrende im Bereich Kulturgutdigitalisierung und soll Hilfestellung bei der Vorbereitung und Durchführung entsprechender Lehrveranstaltungen bieten. Da museale Standards angewendet und eingehalten werden, ist es auch für den Bereich der Ausbildung an GLAM-Institutionen – etwa bei der Schulung von Volontär:innen – hilfreich. Es besteht sowohl aus Materialien für die Lehrenden als auch für die Lernenden und ist so lizensiert, dass eine Bearbeitung und Veränderung problemlos möglich ist. Es wird zumindest bis zum Ende der Projektlaufzeit im März 2026 beständig erweitert und überarbeitet.

Dieses Repositorium enthält derzeit als nutzbare Ressourcen einen Ordner mit [Handreichungen](https://github.com/digiKulTh/Lehr-Lern-Materialien/tree/main/Handreichungen), die wir im Rahmen des Praxisseminars als PDFs an die Studierenden ausgeben und die uns als Orientierung über die Inhalte dienen. In einem Ordner mit [Lehrendenmaterial](https://github.com/digiKulTh/Lehr-Lern-Materialien/tree/main/Lehrendenmaterial) findet sich etwa eine Checkliste zur Vorbereitung eines digiKulTh-Praxisseminars, ein Verzeichnis der im Rahmen der Objektdigitalisierung eingesetzten Technik sowie eine Vereinbarung über die Nachnutzung der von den Teilnehmenden erzeugten Daten und Metadaten durch die Institution.

### Lehrendenmaterial
1. Warum gibt es dieses Kursangebot, wer ist die Zielgruppe, was sind die Lernziele? <br> => [Einführung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Lehrendenmaterial/Einf%C3%BChrung.md)
2. Was ist bei der **Planung, Durchführung und Nachbereitung** eines Praxisseminar zur Kulturgutdigitalisierung grundsätzlich zu beachten? <br> => *Vorüberlegungen & Beweggründe*, *Mindmap*, [Checkliste Vorbereitung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Lehrendenmaterial/Checkliste%20Vorbereitung.md)
3. Welche **Technik** wird zur Durchführung eines Praxisseminars benötigt? <br> => [digiKulTh-Fototechnik](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Lehrendenmaterial/digiKulTh-Fototechnik.md)
4. Wie kann eine **Schreibanweisung für (Objekt)-Informationen** aussehen? <br> => [Demo-Schreibanweisung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Lehrendenmaterial/Demo-Schreibanweisung.md)
5. Wie könnte eine Vorlage zur **Übertragung von Nutzungsrechten** von Objektfotodigitalisaten und -metadaten aussehen? <br> => [Vorlage Rechtübertragung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Lehrendenmaterial/Vorlage_Rechte%C3%BCbertragung.md)
6. Welche wesentlichen **Faktoren und Techniken** sind für die **Praxis der Objektfotografie** relevant? <br> => *Handreichung Praxis Objektfotografie*
  
### Studierendenmaterial
1. Über welche **Grundkenntnisse** zur Kulturgutdigitalisierung sollte ich verfügen? 
=> [Ordner Handreichungen](https://github.com/digiKulTh/Lehr-Lern-Materialien/tree/main/Handreichungen)
2. Wie können die **wichtigsten Inhalte in kurzer Zeit** erfasst werden? 
=> in den Handreichungen verlinkte Podcasts [derzeit noch unvollständig]
3. Wie kann ich **mein Wissen prüfen**? 
=> [Quiz Kulturgutdigitalisierung](https://liascript.github.io/course/?https://raw.githubusercontent.com/digiKulTh/Lehr-Lern-Materialien/refs/heads/main/Interaktives/Quiz_Kulturgutdigitalisierung.md)
4. Wie kann ich ein **Foto-Setup aufbauen** ?
=> *Aufbau-Tutorial 1, 2*
6. Wie sollte ich die **Technik einstellen**? 
=> [Checkliste Objektfotografie](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md), *Tutorial 3* 
7. Wie kann man mit dem Setup **Objekte fotografieren**?
=> *Workflow-Tutorial*
7. Wie kann ich in digiCult.web **Objektinformationen eintragen**? 
=> *Screencast*

---

## Interne Tipps für die Materialerstellung
- Marcdown-TOC-Generator: https://bitdowntoc.derlin.ch/ (gibt ein Preset für GitHub)
- `&shy;` ist der (unsichtbare) HTML-Code für ein 'weiches' Trennzeichen (nach Bedarf) und etwa in der Tabellenformatierung hilfreich
- https://github.com/BaileyJM02/markdown-to-pdf erlaubt die automatische Generierung von PDFs aus Markdown-Dokumenten in einem Ordner via GitHub-Action. Gut gestaltete PDFs, u. a. mit Kopf- und Fußzeilen, generiert der Editor [MarkText](https://github.com/marktext/marktext).
