# Projektmanagement in der Kulturgutdigitalisierung

Michael Markert

**[PLEASE FIND THE ENGLISH VERSION BELOW](#project-management-in-cultural-property-digitization)**

<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

- [Einleitung](#einleitung)
- [Vorbereitungen](#vorbereitungen)
   * [Projektplanung](#projektplanung)
   * [Einbezug relevanter Stakeholder](#einbezug-relevanter-stakeholder)
   * [Zustand der Sammlung](#zustand-der-sammlung)
      + [Datenebene](#datenebene)
      + [Dingebene](#dingebene)
   * [Ressourcen](#ressourcen)
      + [Raum](#raum)
      + [Technik](#technik)
      + [Personal](#personal)
      + [Budget](#budget)
   * [Rechtslage](#rechtslage)
   * [Arbeitsanweisung](#arbeitsanweisung)
- [Digitalisierungsprozess](#digitalisierungsprozess)
   * [Objekttransport](#objekttransport)
   * [Vorbereitung der Objekte](#vorbereitung-der-objekte)
   * [Inventarisierung und Basisdatenerfassung](#inventarisierung-und-basisdatenerfassung)
   * [Anfertigen von Digitalisaten](#anfertigen-von-digitalisaten)
   * [Hinterlegen von Digitalisat-Metadaten](#hinterlegen-von-digitalisat-metadaten)
   * [Speichern, Derivate, Backup](#speichern-derivate-backup)
- [Projektabschluss](#projektabschluss)
   * [Qualitätsmanagement](#qualitätsmanagement)
   * [Langfristige Datenhaltung](#langfristige-datenhaltung)
   * [Evaluierung und Dokumentation](#evaluierung-und-dokumentation)
   * [Datenpublikation](#datenpublikation)
- [Literatur](#literatur)


## KI-Podcast
> Erstellt mit https://notebooklm.google.com/, geprüft auf inhaltliche Fehler

> https://github.com/user-attachments/assets/48788807-85c3-4b68-a141-b92efe92a024

## Einleitung

Es ist herausfordernd, allgemeine Regeln für Digitalisierungsprojekte im Sammlungs- und Museumsbereich festzulegen. Je nach institutionellen und technischen Rahmenbedigungen sowie Ressourcen, der Digitalisierungskompetenz der Mitarbeitenden und eventuellen externen Dienstleister:innen, sowie natürlich abhängig von den zu digitalisierenden Objekten und ihren Anforderungen können sich die Workflows und eingesetzten Werkzeuge stark unterscheiden. Zudem werden Projekte in zunehmendem Maße und in verschiedenen Phasen mit Machine Learning und Künstlicher Intelligenz unterstützt – so bei der 3D-Bildgebung (z. B. [Gaussian Splatting](https://de.wikipedia.org/wiki/Gaussian_Splatting)), der strukturierten Texterkennung von Inventarkarten, der Verschlagwortung von Bildern und Übersetzung von Inhalten für digitale Ausstellungen.

Obwohl sich der Bereich im stetigen Wandel befindet, gibt es eine Reihe von stabilen Grundprinzipien, die sich aus diesem Kontext ableiten: Sammlungsdigitalisierung soll den Objekten nicht schaden, soll eine hohe Daten- und Metadatenqualität liefern, soll leicht nachnutzbar und lange verfügbar sein, nicht zuletzt, weil die Ressourcen für solche Projekte oft eng begrenzt sind. Dabei ist die Sammlungsarbeit im Physischen nicht von der Arbeit im Digitalen trennbar. Sind Objekte noch gar nicht in einer Sammlungsdatenbank verzeichnet, so müssen sie erst inventarisiert werden, weil sich die Bilder sonst nicht zuordnen lassen. Sind sie fragil oder verschmutzt, so werden wahrscheinlich vor der Digitalisierung Reinigungs- und/oder Restaurierungsarbeiten nötig.

Die folgende Darstellung versucht, alle wesentlichen Aspekte eines generischen Workflows abzudecken und dabei diese physische Dimension im Blick zu behalten. Dabei werden drei Phasen mit mehreren Teilaspekten unterschieden:

| Phase I: Vorbereitungen | Phase II: Digitalisierungsprozess | Phase III: Projektabschluss |
| --- | --- | --- |
| [Projektplanung](#projektplanung) | [Objekttransport](#objekttransport) | [Qualitätsmanagement](#qualitätsmanagement) |
| [Einbezug relevanter Stakeholder](#einbezug-relevanter-stakeholder) | [Vorbereitung der Objekte](#vorbereitung-der-objekte) | [Langfristige Datenhaltung](#langfristige-datenhaltung) |
| [Zustand der Sammlung](#zustand-der-sammlung) | [Inventarisierung und Basisdatenerfassung](#inventarisierung-und-basisdatenerfassung) | [Evaluierung und Dokumentation](#evaluierung-und-dokumentation) |
| [Ressourcen: Raum, Technik, Personal, Budget](#ressourcen) | [Anfertigung von Digitalisaten](#anfertigung-von-digitalisaten) | [Datenpublikation](#datenpublikation) |
| [Rechtslage](#rechtslage) | [Hinterlegen von Digitalisat-Metadaten](#hinterlegen-von-digitalisat-metadaten) |     |
| [Arbeitsanweisung](#arbeitsanweisung) | [Speichern, Derivate, Backup](#speichern-derivate-backup) |     |

---

## Vorbereitungen

### Projektplanung

Ein detaillierter Projektplan sollte erstellt werden, der alle Arbeitsschritte, Verantwortlichkeiten, Meilensteine und Zeitpläne umfasst. Was ist wann, durch wen und auf welche Weise zu tun? Welche Technik wird benötigt? Alle nötigen Arbeitsprozesse sollten erprobt werden, um Aufwand, Zeit- und Personalbedarf realistisch abschätzen und ein Mengengerüst aufstellen zu können. Das Anfertigen von Objektfotografien geht meist sehr schnell, ggf. nötige Prozesse wie Verpackung, Transport, Reinigung und Inventarisierung hingegen benötigen viel Zeit.

### Einbezug relevanter Stakeholder

Digitalisierung ist kein Selbstzweck, sondern soll den Zugang zur Sammlung und damit ihre Nutzbarkeit verbessern. Relevante Stakeholder wie Forschende, Fördermittelgeber:innen oder Nutzer:innen im Bereich Bürgerwissenschaft sollten daher aktiv in den Prozess eingebunden werden. So lässt sich sicherstellen, dass die Ergebnisse den Bedürfnissen der Interessent:innen entsprechen und direkt anwendbar sind. Geprüft werden sollte in diesem Zusammenhang auch, ob mit der Digitalisierung ethische Fragestellungen berührt werden, etwa beim Umgang mit menschlichen Überresten in Präparatesammlungen oder kolonialen Objekten in ethnologischen Beständen. Ggf. sind hier noch Vorarbeiten und Vereinbarungen mit Dritten auf einer ganz anderen Ebene nötig (vgl. [Handreichung Ethische Dimensionen](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Ethische%20Dimensionen.md))

### Zustand der Sammlung

#### Datenebene

Voraussetzung für jede Digitalisierung ist ein Inventar der zu digitalisierenden Objekte, da sich die Digitalisate nur so später einem Objekt über die Inventarnummer eindeutig zuordnen lassen. Auch ist es für eine Abschätzung des Aufwands wichtig zu wissen, wie viele Objekte digitalisiert werden sollen und worum es sich bei einem Objekt eigentlich handelt: Wurde unter einer Inventarnummer ein Konvolut von 10-200 Objekten erfasst und sollen alle einzeln fotografiert werden oder entspricht jede Inventarnummer einem Objekt?

Oft wird während der Digitalisierung (weiter) inventarisiert und erschlossen, was Zeit benötigt und eingeplant werden muss. Je nach Objektbestand können z. B. aufwändige Recherchen zu Urheber:innen nötig werden, falls man Abbildungen etwa von Kunstwerken später rechtssicher veröffentlichen möchte.

#### Dingebene

Während der Digitalisierung werden Objekte angefasst, bewegt, klimatischen Änderungen und meist auch starkem Licht ausgesetzt. Entsprechend ist zu prüfen, ob die Objekte stabil genug für den Digitalisierungsprozess sind. Auch können Objekte beispielsweise durch Schädlings- oder Schimmelbefall in Mitleidenschaft gezogen worden sein. Es sollte im Vorfeld zumindest stichprobenartig daraufhin geprüft werden, da eventuell Konservierungs- und/oder Restaurierungsmaßnahmen erforderlich sind.

Gleichzeitig gehen von Objekten eventuell Gefahren für das Digitalisierungspersonal aus, denn Gefahrstoffe wie Feinstaub, Schimmel, Pestizide und andere Gifte sind in Sammlungen allgegenwärtig. Für den Umgang mit entsprechend belasteten Objekten müssen Schutzmaßnahmen, wie persönliche Schutzausrüstung oder spezielle Reinigungsverfahren, eingeplant werden (vgl. [Handreichung Gefahrstoffe und Arbeitsschutz](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Gefahrstoffe%20und%20Arbeitsschutz.md)).

### Ressourcen

#### Raum

Der Raum für die Digitalisierung sollte ausreichend Platz für Digitalisierungstechnik (Hohlkehle/Lichtzelt, Beleuchtung, Kamera, ...), Stellfläche für die Objekte und das Handling derselben bieten. Er sollte leicht zugänglich sein, um Objekttransporte so risikoarm wie möglich durchführen zu können. Auch sollte auf konstante Klimabedingungen (Temperatur, Luftfeuchtigkeit) geachtet werden, um Schäden zu vermeiden (vgl. [Handreichung Depoträume & Lagerung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Depotraeume%20%26%20Lagerung.md)).

#### Technik

Für das jeweilige Vorhaben ist die entsprechende Technik anzuschaffen oder über einen Dienstleister zu leihen, d. h. sowohl die Hardware (Kamera/Scanner, Beleuchtung, Hintergrundsystem/Lichtzelt, ...) als auch die Software (Fernsteuerung der Kamera (Tethering), Bildbearbeitung, Datenbank, ...) (für unsere Technik vgl. [digiKulTh-Fototechnik](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Lehrendenmaterial/digiKulTh-Fototechnik.md)). Nicht vergessen werden sollte die nötige Infrastruktur – insbesondere ausreichend Steckdosen und eine stabile Internetverbindung im Digitalisierungsraum, da die meisten Museumsdokumentationsssysteme heute als Webservice betrieben werden.

#### Personal

Viele vor allem kleinere Institutionen verfügen über kein Personal dediziert für Digitalisierung oder es wird nur sehr selten digitalisiert, sodass entsprechende Kompetenzen nicht trainiert werden und erhalten bleiben. Falls das entsprechende Know-how fehlt, sollten Schulungen oder die Einbindung externer Expert:innen etwa für Beratungen eingeplant werden, um einen reibungslosen Ablauf und die gewünschte Datenqualität sicherzustellen. Ggf. sind externe Expert:innen auch als Dienstleister:innen für intern nicht zu bewältigende Aufgaben etwa im Bereich Restaurierung und 3D-Digitalisierung vorzusehen.

#### Budget

Neben den Kosten für Digitalisierungstechnik und Softwarelizenzen sowie Personal sollten ggf. auch Ausgaben für Reinigung, Konservierung, Restaurierung, Verpackungsmaterial und Transport eingeplant werden. Für eine Veröffentlichung ist unter Umständen die Einholung von Nutzungslizenzen etwa bei der VG Bild-Kunst nötig (s. a. [nächster Abschnitt](#rechtslage)).

### Rechtslage

Auch wenn nicht immer zu Projektbeginn eine Veröffentlichung von Digitalisaten vorgesehen ist, folgt diese oft nach. Die Klärung eventuell bestehender Urheber- und anderer Rechte (Recht am eigenen Bild, Datenschutz) sollte daher als Teil der Digitalisierungsarbeiten mitgedacht werden. Da bei der Erstellung von Objektdigitalisaten im Regelfall ebenfalls Urheberrechte entstehen, sollten entsprechende vertragliche Regelungen mit dem digitalisierenden Personal vorbereitet werden, die etwa eine Freigabe unter Creative Commons-Lizenz vorsehen (vgl. [Handreichung Rechtliche Aspekte](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Rechtliche%20Aspekte.md)).

### Arbeitsanweisung

Digitalisierung ist ein vielschrittiger Prozess, der oft für einen spezifischen Objektbestand verfeinert und angepasst werden muss. Es sollte daher eine detaillierte Arbeitsanweisung entwickelt werden, die zum Nachschlagen dient und die Übergabe an neues Personal vereinfacht – insbesondere bei komplexen Abläufen wie ggf. nötiger Inventarisierung und der Objektfotografie (vgl. [Objektfotografie-Checkliste](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md)).

---

## Digitalisierungsprozess

### Objekttransport

Ganz gleich ob im Haus oder an einem anderen Ort fotografiert wird, sollten der meist nötige Transport – eventuell gar mit einer Kunstspedition – und eine geeignete Objektverpackung eingeplant werden. Auch wenn es nur über den Flur geht, muss der Weg vorbereitet und das Personal etwa mit Transportwagen ausgestattet sein (vgl. [Handreichung Verpackung & Transport](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Verpackung%C2%A0%26%20Transport.md)).

### Vorbereitung der Objekte

Oft wird ein Digitalisierungsvorhaben mit bestandserhaltenden Maßnahmen verbunden, da Sammlungsobjekte im Grundsatz so wenig wie möglich bewegt und manipuliert werden sollten und daher sinnvoller Weise mehrere Arbeiten gleichzeitig durchgeführt werden. Da Digitalisierungsmaßnahmen nicht selten die erste systematische Arbeit an einem Bestand seit Jahr(zehnt)en sind, stehen oft Reinigung und Umverpackung der Objekte an (vgl. [Handreichung Handhabung von Museumsobjekten](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Handhabung%20von%20Museumsobjekten.md)). Die dafür nötige Zeit im Workflow, das benötigte Material und die Räumlichkeiten – etwa für eine Entfernung von Schimmelsporen unter einem Laborabzug oder die Lagerung von Verpackungsmaterial – sollten mit eingeplant werden.

### Inventarisierung und Basisdatenerfassung

Manchmal werden Bestände digitalisiert, die bisher noch keinen Eingang in die Museumsdokumentation gefunden haben oder deren Datensätze nur rudimentär angelegt sind. Sollen Objekte mit Inventarnummern versehen und Metadaten wie Titel, Hersteller, Entstehungszeitraum, Objektklassifikation, Maße, Materialien, Technik, Standort und Kurzbeschreibung erfasst werden (vgl. [Handreichung Inventarisierung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Inventarisierung.md)), so kann dies je nach Rechercheaufwand ausgesprochen zeitintensiv sein. Die Recherche und zeitliche Einordnung einer Herstellermarke kann durchaus eine Stunde dauern – Zeit, die ggf. Kolleg:innen auf das Objekt zur Weiterbearbeitung warten.

### Anfertigen von Digitalisaten

Abhängig von Objekttyp und Anforderungsprofil – sollen einfache Arbeitsfotos, Restaurierungsdokumentationen oder Publikationsabbildungen entstehen – sind entsprechende technische Rahmenbedinungen herzustellen und zu standardisieren (vgl. [Checkliste Objektfotografie](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md)), um eine gleichbleibende Qualität über Unterbrechungszeiten (Krankheit, Urlaub) und Personalwechsel hinweg sicherzustellen. Entsprechend genau sollte die Arbeitsanweisung ausfallen, zudem ist auf regelmäßige Dokumentation zu achten, um Veränderungen im Workflow sowie die je akutellen Arbeitsstände zentral vorzuhalten. Je nach eingesetzter Technik können die Abläufe sehr komplex und aufwändig sein – insbesondere bei allen Verfahren der 3D-Digitalisierung, die oft eine sehr zeit- und rechenintensive Nachbereitung am Computer erfordern. Auch ggf. nötiger Speicherplatz für hochauflösende Bilder in großer Zahl sollte ebenfalls mitbedacht werden.

### Hinterlegen von Digitalisat-Metadaten

Jedes entstehende Digitalisat verfügt als menschengemachtes Objekt über eigene Metadaten, wie Urheberschaft und Entstehungszeit und im Regelfall haben die Mitarbeiter:innen als Urheber:innen auch entsprechende Rechtsansprüche. Sie müssen daher bei Publikationen um Erlaubnis gebeten werden. Die Digitalisate sollten daher auf Grundlage einer entsprechenden Vereinbarung mit den Urheber:innen mit einer Lizenz (z. B. CC-BY 4.0) für die Nachnutzung inner- und außerhalb der bestandshaltenden Institutionen versehen werden (vgl. [Handreichung Rechtliche Aspekte](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Rechtliche%20Aspekte.md)). Idealerweise werden Urheber:innendaten und Lizenz in der Bilddatei selbst (sog. IPTC-Felder) hinterlegt, damit sie nicht vom Digitalisat getrennt werden können (vgl. [Checkliste Objektfotografie](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md)).

### Speichern, Derivate, Backup

Für bestmögliche Qualität sollte man unkomprimierte Versionen von Bilddaten archivieren (meist TIFF). Für Vorschaubilder in der Erschließungssoftware und auf Webseiten werden immer auch Derivate (JPEG, PNG) benötigt, die je nach Software automatisch oder manuell erzeugt werden. Schon während der Arbeit am Projekt ist darauf zu achten, dass Sicherungskopien der Daten angelegt und idealerweise an einem anderen Ort gelagert werden. Bei Datenverlust etwa durch Hardwareausfall können enorme Mehraufwände entstehen – etwa wenn dadurch noch einmal aufwändige Objekttransporte zum Digitalisierungsarbeitsplatz nötig sind.

>Beispielhafte Objektdigitalisierung am Übersee-Museum Bremen (Link zu Youtube-Video):
>
>[![Digitalsierung am Übersee-Museum Bremen](https://img.youtube.com/vi/nyM1c1GsLi4/mqdefault.jpg)](https://youtu.be/nyM1c1GsLi4)

---

## Projektabschluss

### Qualitätsmanagement

Gerade bei mehrjährigen Projekten und wechselndem Personal sollte immer wieder geprüft werden, ob alle Daten – sowohl bezüglich der Digitalisate als auch der Metadaten – der Arbeitsanweisung entsprechen und die notwendigen Merkmale aufweisen. So kann es passieren, dass Digitalisate nicht korrekt mit den Datensätzen verknüpft werden, weil sich Fehler in Dateinamen eingeschlichen haben (z. B. `00558–01.tiff` (Trennzeichen Gedankenstrich) statt `00558-01.tiff`(Trennzeichen Bindestrich)). Vielleicht wurde auch zwischenzeitlich die Beleuchtung ausgetauscht, aber der Weißabgleich nicht angepasst, sodass ein Farbshift aufgetreten ist, der unbemerkt blieb.

### Langfristige Datenhaltung

Die oft großen Datenmengen aus Digitalisierungsprojekten müssen sicher abgelegt werden, damit sie auch über Projekt- und Vertragsenden hinweg verfügbar bleiben. Eine SSD in der Schreibtischschublade ist keine zuverlässige Datenhaltung! Es sollten mindestens zwei Kopien der Daten an unterschiedlichen Orten bzw. in verschiedenen Gebäuden gelagert und in festen Abständen überprüft werden. Zudem muss durch eine geeignete Dokumentation sichergestellt sein, dass für Dritte auch nach einigen Jahren noch nachvollziehbar ist, worauf sich die Daten beziehen.

### Evaluierung und Dokumentation

Selbst wenn kein formaler Projektbericht etwa durch einen Drittmittelgeber gefordert ist, sollten die Projekterfahrungen in Berichtsform festgehalten werden. Schwerpunkte der Darstellung sind Herausforderungen, Lösungen, Verbesserungsmöglichkeiten und Workflows, um spätere Digitalisierungsprojekte zu unterstützen und reproduzierbare Ergebnisse sicherzustellen. Der Bericht sollte auch den finalen Arbeitsstand festhalten, um bei einer Fortsetzung der Arbeiten am Bestand die Einarbeitungszeit zu verkürzen.

### Datenpublikation

Bei einer Datenpublikation ist darauf zu achten, dass die Datensätze Mindeststandards wie die FAIR-Prinzipien (vgl. [Handreichung Ethische Dimensionen](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Ethische%20Dimensionen.md)) einhalten, um nachnutzbar zu sein und auf Portalen wie der [Deutsche Digitale Bibliothek](https://www.deutsche-digitale-bibliothek.de/) oder [Europeana](https://www.europeana.eu/) veröffentlicht werden zu können – etwa nach der [Minimaldatensatz-Empfehlung für Museen und Sammlungen (v1.0.1)](https://wiki.deutsche-digitale-bibliothek.de/pages/viewpage.action?pageId=120422678). Auch wenn Bilddaten beispielsweise auf Wikimedia Commons mit sehr rudimentären Rumpfdatensätzen veröffentlicht werden können, sollten soweit möglich Zusatzinformationen angelegt werden, um die Auffindbarkeit zu erleichtern und die Nutzung zu befördern (s. [Commons:Structured data](https://commons.wikimedia.org/wiki/Commons:Structured_data)).

---

## Literatur

AG Minimaldatensatz: Minimaldatensatz-Empfehlung für Museen und Sammlungen v1.0.1. 2024, URL: http://www.minimaldatensatz.de/ (letzter Zugriff 05.02.2025).

Deutsche Digitale Bibliothek: Homepage, 2025, URL: https://www.deutsche-digitale-bibliothek.de/ (letzter Zugriff 05.02.2025).

Europeana: Homepage, 2025, URL: https://www.europeana.eu/ (letzter Zugriff 05.02.2025).

Knaus, Gudrun: Leitfaden für digitales Sammlungsmanagement an Kunstmuseen. Heidelberg 2019, URL: https://archiv.ub.uni-heidelberg.de/artdok/6413/ (letzter Zugriff 06.02.2025).

Wikimedia: Commons:Structured data, 2025, URL: <https://commons.wikimedia.org/wiki/Commons:Structured_data> (letzter Zugriff 06.02.2025).

Wikipedia: Gaussian Splatting, 2025, URL: <https://de.wikipedia.org/wiki/Gaussian_Splatting> (letzter Zugriff 06.02.2025).

# Project Management in Cultural Property Digitization

Michael Markert

<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

- [Introduction](#introduction)
- [Preparation](#preparation)
   * [Project planning](#project-planning)
   * [Involving relevant stakeholders](#involving-relevant-stakeholders)
   * [State of the collection](#state-of-the-collection)
      + [Data level](#data-level)
      + [Material level](#material-level)
   * [Resources](#resources)
      + [Room](#room)
      + [Technology](#technology)
      + [Personnel](#personnel)
      + [Budget](#budget)
   * [Legal situation](#legal-situation)
   * [Work instructions](#work-instructions)
- [Digitization Process](#digitization-process)
   * [Transporting objects](#transporting-objects)
   * [Preparing objects](#preparing-objects)
   * [Cataloging and collecting basic data](#cataloging-and-collecting-basic-data)
   * [Making digital copies](#making-digital-copies)
   * [Storing digital copy metadata](#storing-digital-copy-metadata)
   * [Storing, derivatives, backup](#storing,-derivatives,-backup)
- [Project Completion](#project-completion)
   * [Quality management](#quality-management)
   * [Long-term data management](#long-term-data-management)
   * [Evaluation and documentation](#evaluation-and-documentation)
   * [Publishing data](#publishing-data)
- [Appendix: Sources and Literature](#appendix-sources-and-literature)
  
<!-- TOC end -->

## Introduction

Making general rules for digitization projects in the collection and museum sector is a challenge. The workflows and tools used can vary greatly depending on institutional and technical general conditions, resources, the digitization expertise of employees and any external service providers. All the above, of course, depends on the objects to be digitized and their requirements. In addition, projects are increasingly supported in various phases by machine learning and artificial intelligence such as 3D-imaging (e.g., [Gaussian Splatting](https://de.wikipedia.org/wiki/Gaussian_Splatting)), structured text recognition of catalog cards, keywording images and translating content for digital exhibitions.

Although the field is constantly changing, there are a number of stable fundamental principles: collection digitization should not damage objects, should deliver high-quality data and metadata, and be easily reusable and available for a long time; not least because the resources for these types of projects are often limited. Physical collection work cannot be separated from digital work with the collection. If objects are not listed in a collection database, they must first be cataloged because otherwise the images cannot be attributed. If they are fragile or dirty, cleaning and/or restoration work is probably necessary before digitization can proceed.

The following information attempts to cover all the essential aspects of a generic workflow while keeping the physical dimension in mind. It is divided into three phases with several partial aspects:


| Phase I: Preparation | Phase II: Digitization process | Phase III: Project completion |
| --- | --- | --- |
| [Project planning](#project-planning) | [Transporting object](#transporting-object) | [Quality management](#quality-management) |
| [[Involving relevant stakeholders](#[involving-relevant-stakeholders) | [Preparing objects](#preparing-objects) | [[Long-term data management](#[long-term-data-management) |
| [State of the collection](#state-of-the-collection) | [Cataloging and collecting basic data](#cataloging-and -ollecting-basic-data) | [Evaluation and documentation](#evaluation-and-documentation) |
| [Resources: room, technology, personnel, budget](#resources-room-technology-personnel-budget) | [[Making digital copies](#[making-digital-copies) | [Publishing data](#publishing-data) |
| [[Legal situation](#[legal-situation) | [Storing digital copy metadata](#storing-digital-copy-metadata) |     |
| [Work instructions](#work-instructions) | [Storing, derivatives, backup](#[storing-derivatives-backup) |     |

---

## Preparation

### Project planning

Create a detailed project plan that includes all work steps, areas of responsibility, milestones and timelines. What should be done when, by whom, and how? What technology is needed? Try out all the necessary work processes to enable you to realistically estimate expenses, time and personnel requirements and establish a quantity framework. Taking object photographs is usually less time-consuming than necessary processes such as packaging, transport, cleaning and cataloging.

### Involving relevant stakeholders

Digitization is not an end in itself. Instead, it aims to improve access to the collection and, in turn, its usability. Relevant stakeholders such as researchers, funders or users from the field of citizen science should therefore be actively involved in the process. This ensures that the results meet the needs of the people involved and are directly applicable. In this context, check whether ethical issues are affected by digitization, for example when dealing with human remains in collections of preserved biological remains or colonial objects in ethnological holdings. Preliminary work and agreements with third parties at a completely different level might still be necessary here (cf [Handout on Ethical Dimensions](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Ethische%20Dimensionen.md))

### State of the collection

#### Data level

The objects must be cataloged before they are digitized, since the digital copy can later only be clearly attributed to an object via the catalog number. It is also important to know how many objects must be digitized and what an object is before the complexity of the task can be estimated: Was a set of 10-200 items recorded under one catalog number, and should each object be photographed individually or does a catalog number correspond to one item?

The inventory is often refined during digitization; this takes time and needs to be considered for planning. Depending on the inventory of objects, extensive research on authors can be necessary, in case images of works of art are to be legally published later.

#### Material level

During digitization, objects are touched, moved and exposed to climatic changes and (usually) to intense light. Accordingly, check that the objects are stable enough for the digitization process. Objects can also have been affected by pests or mold, for example. Check at least a random sample of objects in advance, since preservation and/or restoration measures may be necessary.

At the same time, objects may pose dangers to the personnel involved in digitization, since hazardous substances such as fine dust, mold, pesticides and other poisons are present everywhere in collections. Include protective measures like personal protective equipment or special cleaning procedures for handling affected objects in the plan (cf. [Handout of Hazardous Substances and Occupational Safety](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Gefahrstoffe%20und%20Arbeitsschutz.md)).

### Resources

#### Room

The room for digitization should provide sufficient space for the digitization technology (infinity cove/light tent, lighting, camera, etc.) and floor area for the objects and for handling them. It should be easily accessible to ensure that objects can be transported as safely as possible. Keep climate conditions (temperature, humidity) stable to avoid damage (cf. [Handout on Storerooms & Storage](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Depotraeume%20%26%20Lagerung.md)).

#### Technology

For each project, the appropriate technology – including the hardware (camera/scanner, lighting, background system/light tent, etc.) and software (remote control of the camera (tethering), image processing, database, etc.) – must either be purchased or leased from a service provider (for our technology, see [digiKulTh-Phototechnik](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Lehrendenmaterial/digiKulTh-Fototechnik.md)). Do not forget the necessary infrastructure, in particular enough electrical outlets and a stable internet connection in the digitization room since most modern museum documentation systems operate as a web service.

#### Personnel

Many institutions, particularly smaller ones, do not have personnel dedicated to digitization. They rarely digitize objects, so they do not train personnel or keep the necessary expertise on hand. If the relevant know-how is not available, include the necessary training or integrate external experts into the plan to ensure a smooth process and the desired data quality. If necessary, plan on external expert service providers for tasks that cannot be managed internally, like restoration and 3D-digitization.

#### Budget

In addition to the costs for digitization technology, software licenses and personnel, include costs for cleaning, preservation, restoration, packaging material and transport in the plan. For a publication, it may be necessary to obtain use licenses: for example, from VG Bild-Kunst (see [next section](#Legal situation)).

### Legal situation

Although the plan at the beginning of a project does not always include the publication of digital images, it is often added later. Whether or not copyrights and other rights (right to one’s own image, data protection) exist should therefore be considered as part of the digitization process. Since copyrights also apply when creating images of objects, the relevant agreements should be concluded with the digitizing personnel and provide for release under a Creative Commons license, for example (cf. [Handout on Legal Aspects](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Rechtliche%20Aspekte.md)).

### Work instructions

Digitization is a multi-step process that often needs to be refined and adjusted for a specific collection. Therefore, develop detailed work instructions as a reference and to simplify the transfer to new personnel – particularly for complex processes such as cataloging, if necessary, and object photography (cf. [Object Photography Checklist](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md)).

---

## Digitization Process

### Transporting objects

Whether photographed in the building or elsewhere, it is usually necessary to plan for transport – possibly with an art freight forwarder – and suitable object packaging. Even if it is only across the hallway, the route must be prepared and the personnel must be equipped with some kind of transport aid (cf. [Handout on Packaging & Transport](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Verpackung%C2%A0%26%20Transport.md)).

### Preparing objects

Digitization projects are often carried out together with conservation measures since collection objects should be moved and handled as little as possible. Since digitization measures are often the first systematic work a collection has experienced in years, the objects must first be cleaned and repackaged (cf. [Handling Museum Objects](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Handhabung%20von%20Museumsobjekten.md)). Include the time required for this, the required material and the rooms in the workflow: for example, for the removal of mold spores under a fume hood or the storage of packaging material.

### Cataloging and collecting basic data

Sometimes holdings that the museum has not yet been documented or whose records are only rudimentary must be digitized. Depending on the research involved, assigning catalog numbers to objects and recording metadata such as the title, manufacturer, development period, object classification, dimensions, materials, technology, location and a short description (cf. [Handout on Cataloging](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Inventarisierung.md)) can be extremely time-consuming. Dating and further research into a manufacturer’s distinguishing mark can easily take an hour – time in which colleagues are waiting to work with the object as well.

### Producing digital copies

Depending on the object type and requirements – simple work photos, restoration documentation or images for publication – it is important to establish and standardize the appropriate technical conditions to ensure consistent quality if the work is interrupted (illness, vacation) and in case of personnel changes. Create precise work instructions and document the work regularly to make changes in the workflow and the current status of the work centrally available. Depending on the technology used, the processes can be very complex and detailed – particularly when it comes to 3D-digitization, which often requires very time-consuming and intensive postprocessing on the computer. Also consider the amount of memory required for large numbers of high-resolution images.

### Storing digital copy metadata

As a man-made object, every digital copy created has its own metadata such as authorship and time of creation. Employees as creators also have corresponding legal claims and therefore, they must be asked for permission to publish. The digital copies should be licensed through an agreement with the authors (e.g., CC-BY 4.0) for subsequent use inside and outside the institutions that maintain the holdings (cf. [Handout on Legal Aspects](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Rechtliche%20Aspekte.md)). Ideally, the author data and license are stored in the image file itself (IPTC fields) to ensure that they cannot be separated from the digital image (cf. [Checklist for Object Photography](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md)).

### Storing, derivatives, backup

For the best possible quality, archive uncompressed versions of image data (usually TIFF format). Derivatives (JPEG, PNG) are always required for preview images in archiving software and on websites. They are generated automatically or manually depending on the software. Remember to create backup copies of the data while working on the project and, ideally, store them in a separate location. Data loss due to hardware failure can cause enormous additional costs if this means that complex object transport to the digitization workstation is necessary again.

Object digitization at the Bremen Overseas Museum (example) (link to YouTube video):

[![Digitization ÜberseeMuseum Bremen](data:image/jpeg;base64,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)](https://youtu.be/nyM1c1GsLi4)

---

## Project Completion

### Quality management

Particularly for projects that take several years and when personnel often changes, at regular intervals check whether all data – both the digital copies and the metadata – correspond to the work instructions and have the necessary features. After all, digital images may not be correctly linked to the data records because errors in file names have occurred (e.g., 00558–01.tiff (separated by em-dash) instead of 00558-01.tiff (separated by hyphen)). Perhaps the lighting has also been replaced in the meantime, but the white balance was not adjusted, leading to an unnoticed color shift.

### Long-term data management

The large amounts of data from digitization projects must be stored securely to ensure that they remain available beyond the end of projects and contracts. An SSD in your desk drawer is not reliable data storage! At least two copies of the data should be stored in separate locations or stored in different buildings and checked at specified intervals. Suitable documentation must also ensure that it is still possible for third parties to understand what the data refers to a few years later.

### Evaluation and documentation

Even if a formal project report is not required by a third-party funder, the experience gained during the project should be recorded in report form. Focus on challenges, solutions, opportunities for improvement and workflows to support future digitization projects and ensure reproducible results. Also include the final work status in the report to reduce orientation time when continuing work on the holdings.

### Publishing data

When publishing data, ensure that the records comply with minimum standards like the FAIR principles (cf. [Handout on Ethical Dimensions](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Ethische%20Dimensionen.md)) to ensure that they can be reused and published on portals such as [German Digital Library](https://www.deutsche-digitale-bibliothek.de/) or [Europeana](https://www.europeana.eu/) in accordance with the [Minimum Record Recommendation for Museums and Collections (v1.01)](https://wiki.deutsche-digitale-bibliothek.de/pages/viewpage.action?pageId=120422678). Although image data can be published on Wikimedia Commons with very rudimentary minimum records, additional information should be created whenever possible to facilitate discoverability and promote use (see [Commons:Structured data](https://commons.wikimedia.org/wiki/Commons:Structured_data)).

---

## Appendix: Sources and Literature

AG Minimaldatensatz: Minimaldatensatz-Empfehlung für Museen und Sammlungen v1.0.1. 2024, URL: [http://www.minimaldatensatz.de/](http://www.minimaldatensatz.de/) (last accessed 05.02.2025).

Deutsche Digitale Bibliothek Homepage, 2025, URL: [https://www.deutsche-digitale-bibliothek.de/](https://www.deutsche-digitale-bibliothek.de/) (last accessed 05.02.2025).

Europeana: Homepage, 2025, URL: [https://www.europeana.eu/](https://www.europeana.eu/) (letzer Zugriff 05.02.2025).

Knaus, Gudrun: Leitfaden für digitales Sammlungsmanagement an Kunstmuseen. Heidelberg 2019, URL: [Leitfaden für digitales Sammlungsmanagement an Kunstmuseen](https://archiv.ub.uni-heidelberg.de/artdok/6413/) (last accessed 06.02.2025).

Sächsische Landesstelle für Museumswesen (ed.) (2020): Handreichungen für die Museumsarbeit. Nr. 3 Objektfotografie im Museum, Chemnitz, URL: https://museumswesen.skd.museum/fileadmin/userfiles/Saechsische_Landesstelle_fuer_Museumswesen/Dateien/HR_Dokumentation_3_Objektfotografie_neu.pdf (last accessed 06.02.2025).

Wikimedia: Commons:Structured data, 2025, URL: [Commons:Structured data - Wikimedia Commons](https://commons.wikimedia.org/wiki/Commons:Structured_data) (last accessed 06.02.2025).

Wikipedia: Gaussian Splatting, 2025, URL: [Gaussian Splatting – Wikipedia](https://de.wikipedia.org/wiki/Gaussian_Splatting) (last accessed 06.02.2025).
