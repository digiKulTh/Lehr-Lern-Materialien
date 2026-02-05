# Projektmanagement in der Kulturgutdigitalisierung

Michael Markert

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

AG Minimaldatensatz: Minimaldatensatz-Empfehlung für Museen und Sammlungen v1.0.1. 2024, URL: http://www.minimaldatensatz.de/ (letzer Zugriff 05/02/2025).

Deutsche Digitale Bibliothek: Homepage, 2025, URL: https://www.deutsche-digitale-bibliothek.de/ (letzer Zugriff 05/02/2025).

Europeana: Homepage, 2025, URL: https://www.europeana.eu/ (letzer Zugriff 05/02/2025).

Knaus, Gudrun: Leitfaden für digitales Sammlungsmanagement an Kunstmuseen. Heidelberg 2019, URL: https://archiv.ub.uni-heidelberg.de/artdok/6413/ (letzer Zugriff 06/02/2025).

Wikimedia: Commons:Structured data, 2025, URL: <https://commons.wikimedia.org/wiki/Commons:Structured_data> (letzer Zugriff 06/02/2025).

Wikipedia: Gaussian Splatting, 2025, URL: <https://de.wikipedia.org/wiki/Gaussian_Splatting> (letzer Zugriff 06/02/2025).
