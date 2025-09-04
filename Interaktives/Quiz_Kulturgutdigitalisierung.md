<!--
author:   Michael Markert
email:    michael.markert@uni-jena.de
version:  0.9
language: de
comment:  Quiz Kulturgutdigitalisierung. Fragen aus allen Bereichen rund um Digitalisierungsprojekte an GLAM-Einrichtungen.

script:   https://cdnjs.cloudflare.com/ajax/libs/Sortable/1.14.0/Sortable.min.js

@dragdroporder
<div style="width: 100%; max-width: 600px; padding: 20px; border: 1px solid rgb(var(--color-highlight)); border-radius: 8px;">
  <div class="choices-container" style="display: flex; flex-direction: column; gap: 10px;" id="quiz-@0">
  </div>
  <div class="feedback" style="margin-top: 20px; font-size:2em; font-weight: bold; text-align: center;">🤔</div>
</div>

<script>
  void setTimeout(() => {
    (function(){
        const quizId = '@0';
        const container = document.querySelector(`#quiz-${quizId}`);

        const feedback = container.nextElementSibling;
        const correctAnswers = '@2'.split('|');

        const initialOrder = '@1'.split('|');
        container.innerHTML = initialOrder.map(item => 
          `<div class="choice lia-code lia-code--inline" style="padding: 10px; border-radius: 4px; cursor: move; user-select: none;">${item}</div>`
        ).join('');
        
        new Sortable(container, {
          animation: 150,
          onEnd: function() {
            const choices = Array.from(container.querySelectorAll('.choice'));
            const currentOrder = choices.map(choice => choice.textContent.trim());
            
            const isCorrect = currentOrder.length === correctAnswers.length && 
                             currentOrder.every((answer, index) => answer === correctAnswers[index]);
            
            if (isCorrect) {
              feedback.textContent = "✅";
            } else {
              feedback.textContent = "❌";
            }
          }
        });
        
    })();
  }, 100);
</script>
@end

-->

# Quiz Kulturgutdigitalisierung (Beta)

Dieses Quiz deckt Fragestellungen aus allen Lernzielbereichen des Praxisseminars "Vom Ding zum Datensatz. Kulturgut handhaben, erschließen und digitalisieren" ab. 

Die im Quellcode jeweils vor den Fragen vermerkten Lernziele entsprechen der Übersicht unter https://github.com/digiKulTh/Lehr-Lern-Materialien#lernziele.

Alle Fragen sind Multiple-Choice-Fragen, außer es ist dahinter ein anderer Fragetyp vermerkt. Die Antwort wird nur dann als richtig gewertet, wenn alle Haken korrekt gesetzt sind.

Durch Klicken auf `Prüfen` werden die Antworten abgeglichen, der Haken daneben gibt die korrekte Lösung vor, sollte man nicht darauf kommen.

> [Start des interaktiven Quiz](https://liascript.github.io/course/?https://raw.githubusercontent.com/digiKulTh/Lehr-Lern-Materialien/refs/heads/main/Interaktives/Quiz_Kulturgutdigitalisierung.md)

## 1. Rahmenbedingungen der Kulturgutdigitalisierung
<!--
@comment
Lernziel: Sie kennen die Relevanz von Kulturgutdigitalisierung, wissen, welche Ziele damit verfolgt werden und welche Arbeitsschritte dafür notwendig sind (1).
@end
-->

Was sind Hauptziele der Kulturgutdigitalisierung?

[[x]] Langzeiterhaltung digitaler Kopien
[[x]] Verbesserung der Zugänglichkeit
[[ ]] Ersatz der physischen Objekte
[[x]] Unterstützung der Forschung
[[ ]] Kosteneinsparung in der Verwaltung

Welche Arbeitsschritte sind für die Kulturgutdigitalisierung notwendig?

[[x]] Objektauswahl und -vorbereitung
[[ ]] Verkaufsvorbereitung
[[x]] Fotografische Dokumentation
[[x]] Metadatenerfassung
[[x]] Qualitätskontrolle

## 2. Sammlungsmanagement
<!--
@comment
Lernziel: Sie haben ein Verständnis für die grundlegende Struktur musealen Sammlungsmanagements als Verschränkung physischer (z. B. Handling, Konservierung) und digitaler (z. B. Fotografie, Erschließung) Aspekte (2).
@end
-->

Welche Aussagen zur Struktur des musealen Sammlungsmanagements sind korrekt?

[[ ]] Digitale Aspekte haben die physischen weitgehend ersetzt
[[x]] Digitales Sammlungsmanagement setzt physisches Sammlungsmanagement voraus 
[[ ]] Physische und digitale Verwaltung erfolgen völlig getrennt
[[x]] Physische und digitale Aspekte sind eng miteinander verschränkt
[[ ]] Nur große Museen benötigen digitales Sammlungsmanagement

Was bedeutet die Abkürzung DAM?

[[ ]] Digital Archive Master
[[x]] Digital Asset Management
[[ ]] Dog Assasinates Man (Mathcore Band)
[[ ]] Digital Archive Management

Welche Bereiche umfasst das physische Sammlungsmanagement?

[[x]] Objekthandling und Transport
[[ ]] Digitale Bildbearbeitung
[[x]] Konservatorische Betreuung
[[ ]] Ausstellungsentwicklung
[[x]] Klimatische Überwachung
[[x]] Verpackung

Welche Bereiche umfasst das digitale Sammlungsmanagement?

[[x]] Digitale Objektdokumentation
[[x]] Metadatenverwaltung
[[ ]] Restaurierung
[[x]] Rechteverwaltung
[[x]] Digitale Langzeitarchivierung
[[ ]] Integrated Pest Management (IPM)

## 3. Rechtliche Aspekte
<!--
@comment
Lernziel: Sie kennen zentrale rechtliche Aspekte von Sammlungsdigitalisierung im Bereich Urheber- und Persönlichkeitsrecht (1).
@end
-->

Welche rechtlichen Aspekte müssen bei der Sammlungsdigitalisierung beachtet werden?

[[x]] Urheberrecht
[[x]] Persönlichkeitsrecht
[[ ]] Vereinsrecht
[[x]] Datenschutzrecht
[[ ]] Steuerrecht

Bei welchen Objekten ist besondere rechtliche Vorsicht geboten?

[[x]] Zeitgenössische Kunstwerke
[[x]] Fotografien von Personen
[[ ]] Objekte vor 1900
[[x]] Personenbezogene Dokumente

> vgl. [Handreichung Rechtliche Aspekte](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Rechtliche%20Aspekte.md)

## 4. Lizenzmodelle
<!--
@comment
Lernziel: Sie kennen Lizenzmodelle für die Publikation von (Meta-)Daten (1) und können deren Eigenschaften beschreiben (2).
@end
-->

Was sind wichtige Eigenschaften von CC-Lizenzen?

[[x]] Modularer Aufbau der Lizenzbausteine
[[x]] Internationale Gültigkeit
[[x]] Maschinelle Lesbarkeit
[[ ]] Kostenpflichtige Nutzung
[[ ]] Zeitliche Begrenzung

Ordnen Sie die folgenden CC-Lizenzen von offen (oben) nach geschlossen (unten) (Drag-and-Drop-Quiz).

@dragdroporder(@uid,CC-BY-SA|CC0|CC-BY-NC-ND|CC-BY-ND,CC0|CC-BY-SA|CC-BY-ND|CC-BY-NC-ND)

> vgl. [Handreichung Rechtliche Aspekte](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Rechtliche%20Aspekte.md)

## 5. Ethische Herausforderungen
<!--
@comment
Lernziel: Sie kennen ethische Herausforderungen der Kulturgutdigitalisierung insbesondere im weiteren Anwendungsbereich der CARE-Prinzipien (sensible Objekte) (1).
@end
-->

Bei welchen Objektkategorien ist besondere ethische Sensibilität erforderlich?

[[x]] Menschliche Überreste
[[ ]] Thüringer Alltagsgegenstände des 20. Jahrhunderts
[[x]] Ritualgegenstände indigener Völker
[[ ]] Münzen und Medaillen
[[x]] Objekte aus kolonialem Kontext

Was sind wichtige ethische Maßnahmen bei der digitalen Präsentation sensibler Objekte?

[[x]] Respektvolle Bildauswahl
[[ ]] Allgemeine Freigabe für die Öffentlichkeitsarbeit, etwa für Social-Media-Kampagnen
[[x]] Kontextualisierende Beschreibungen
[[ ]] Kommerzielle Verwertung
[[x]] Einbindung relevanter Gemeinschaften
[[x]] Zugangsbeschränkungen für besonders sensible Inhalte

> vgl. [Handreichung Ethische Dimensionen](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Ethische%20Dimensionen.md)

## 6. Nachnutzung von Sammlungsdaten
<!--
@comment
Lernziel: Sie kennen Formen der Nachnutzung von Sammlungsdaten in Forschung, Lehre und Vermittlung (1).
@end
-->

Was sind wichtige Formen der Nachnutzung digitalisierter Sammlungen?

[[x]] Wissenschaftliche Forschungsprojekte
[[x]] Digitale Ausstellungen
[[x]] Machine Learning und KI-Training
[[ ]] Ersatz für Originalobjekte nach Versteigerung
[[x]] Lehrmaterialien für Schule und Universität
[[x]] Vermittlungsarbeit

Wer sind typische Nutzer:innen digitalisierter Sammlungen?

[[x]] Wissenschaftler:innen
[[x]] Studierende
[[x]] Museumspädagog:innen
[[x]] Künstler:innen
[[x]] Museumspersonal

Welche technischen Voraussetzungen erleichtern die Nachnutzung von Sammlungsdaten?

[[x]] Ausreichende Bildauflösung von Digitalisaten
[[ ]] Kostenpflichtige Zugänge
[[x]] Strukturierte Metadaten 
[[x]] Stabile Links auf Datenbestände (URIs)
[[ ]] Fehlende Schnittstellendokumentation

## 7. Expertise und Ansprechpartner
<!--
@comment
Lernziel: Sie haben einen Überblick über relevante Expertisefelder für den Gesamtprozess und können relevante Ansprechpartner benennen (2).
@end
-->

In welchen Bereichen ist spezialisiertes Fachwissen in einem Digitalisierungsprojekt nötig?

[[x]] Objekthandling und Konservierung
[[x]] Digitale Fotografie
[[ ]] Museumspädagogik
[[x]] Metadatenstandards
[[x]] Rechtliche Aspekte

Welche Expertisen sind für Digitalisierungsprojekte relevant?

[[x]] Restaurator:innen
[[x]] Fotograf:innen
[[x]] Museolog:innen
[[x]] IT-Spezialist:innen
[[ ]] Marketingexpert:innen
[[x]] Fachwissenschaftler:innen

## 8. Objekthandling
<!--
@comment
Lernziel: Sie haben Grundkenntnisse im Handling von Objekten, d. h. kennen die Merkmale geeigneter Handschuhe, Verpackungsmaterialien, Depotmöbel und Räumlichkeiten (1).
Lernziel: Sie kennen häufig auftretende Substanzen, Zustände und Bedingungen, die den Objekten oder ihnen selbst bei Exposition schaden können (1).
@end
-->

Welche Handschuhe sind für welche Objekte geeignet?

[[x]] Baumwollhandschuhe für unempfindliche Objekte (nach entsprechender Beurteilung durch Fachpersonal)
[[ ]] Fleece-Fäustlinge für Metallobjekte
[[ ]] Fingerlose Handschuhe für besseres Gefühl
[[x]] Nitrilhandschuhe für chemisch sensible Objekte

Welche Umweltbedingungen können Objekten schaden?

[[x]] Sonnenlicht
[[x]] Hohe Luftfeuchtigkeit
[[ ]] Dunkelheit
[[x]] Starke Temperaturschwankungen
[[x]] Schädlingsbefall
[[ ]] Dauerhafte Temparaturen zwischen 15 und 20 Grad

Was ist bei der Verpackung von Objekten zu beachten?

[[x]] Säurefreie Materialien verwenden
[[x]] Ausreichende Polsterung
[[ ]] Obstkisten und Stiegen sind zu bevorzugen
[[x]] Luftzirkulation ermöglichen
[[x]] Objektspezifische Anforderungen beachten
[[ ]] Möglichst luftdicht verpacken

Welche Anforderungen gelten für Depoträume?

[[x]] Klimakontrolle
[[x]] Lichtschutz
[[ ]] Tägliches Stoßlüften
[[x]] Schädlingsmonitoring
[[ ]] Essen und Trinken stehen am Arbeitsplatz
[[x]] Zugang nur für eingewiesene Personen

> vgl. [Handreichung Handhabung von Museumsobjekten](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Handhabung%20von%20Museumsobjekten.md)

## 9. Konservierung und Integrated Pest Management (IPM)
<!--
@comment
Lernziel: Sie kennen die Möglichkeiten der Anbringung von Inventarnummern sowie grundlegende Konservierungstechniken und das Konzept des Integrated Pest Management (IPM) (1).
@end
-->

Welche Aussagen zum Integrated Pest Management (IPM) sind korrekt?

[[x]] Ist ein ganzheitlicher Ansatz zur Schädlingsprävention
[[x]] Regelmäßige Kontrollen sind ein zentraler Bestandteil
[[ ]] Ist nur für Naturkundemuseen relevant
[[x]] Umfasst präventive und reaktive Maßnahmen
[[x]] Sollte in allen Sammlungen mit organischen Materialien angewendet werden

Welche Methoden der Inventarnummeranbringung sind geeignet?

[[x]] Beschriftung mit säurefreier Tusche auf Lackschicht
[[ ]] Direktes Beschriften von Holzobjekten mit dem Kugelschreiber
[[x]] Direktes Beschriften mit Bleistift rückseitig auf Zeichungen und Drucken
[[ ]] Aufkleben von Post-Its an Objektunter- oder -rückseite
[[x]] Anhängen von säurefreien Etiketten mittels Baumwollfaden

> vgl. [Handreichung Depoträume und Lagerung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Depotraeume%20%26%20Lagerung.md)

## 10. Datenmanagement und FAIR
<!--
@comment
Sie haben Grundkenntnisse über Datenmanagement und kennen die FAIR-Prinzipien (1).
@end
-->

Wie sollten Digitalisate abgelegt werden?

[[ ]] Nur auf einem USB-Stick in meiner Schreibtischschublade
[[x]] Mit einem Backup an einem anderen Ort
[[ ]] In einem Ordner "Alle Bilder", benannt "Bild1", "Bild2", "Bild3"
[[x]] Auf einem Netzlaufwerk der jeweiligen Institution
[[x]] So, dass sie auch nach vielen Jahren noch wiedergefunden und zugeordnet werden können

Wofür steht das Akronym FAIR?

[[x]] Findable (auffindbar)
[[ ]] Fast (schnell)
[[ ]] Annotated (annotiert)
[[x]] Accessible (zugänglich)
[[ ]] International (international)
[[x]] Interoperable (interoperabel)
[[x]] Reusable (nachnutzbar)
[[ ]] Representative (repräsentativ)

> vgl. [Handreichung Ethische Dimensionen](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Ethische%20Dimensionen.md)

## 11. Sammlungsdatenbanken und Erfassung
<!--
@comment
Lernziel: Sie wissen, welche Metadaten sie bei der Digitalisierung von Kulturgut erheben sollten und wie dies in einer Erfassungsmaske zu geschehen hat (2).
@end
-->

Welche grundlegenden Metadaten sollten erfasst werden?

[[x]] Eindeutige Inventarnummer
[[x]] Objektbezeichnung und Objektart
[[ ]] Beliebtheit bei Personal und Besucher:innen
[[ ]] Objektfarbe(n)
[[x]] Datierung (z. B. Herstellungszeit und/oder Ankauf)
[[x]] Standort
[[ ]] Aktueller Versicherungswert

Was muss bei der Datenerfassung beachtet werden?

[[x]] Einheitliche Terminologie
[[ ]] Kreative Datumsformate ("Jänner des Jahres '24")
[[x]] Vollständigkeit der Pflichtfelder
[[x]] Verwendung kontrollierter Vokabulare 
[[ ]] Nichtssagender Objekttitel ("Vase")

> vgl. [Handreichung Inventarisierung](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Handreichung%20Inventarisierung.md)

## 12. Datennutzung für Forschung und Lehre
<!--
@comment
Lernziel: Sie verstehen die Relevanz strukturierter Daten für die Arbeit mit Sammlungen und die Nutzung von Sammlungsdaten für Forschung, Lehre und Vermittlung (2).
@end
-->

Welche Vorteile bieten strukturierte Sammlungsdaten?

[[x]] Systematische Auswertungsmöglichkeiten
[[x]] Vergleichbarkeit zwischen Sammlungen
[[ ]] Ersatz physischer Sammlungen
[[x]] Automatisierte Analysemöglichkeiten
[[ ]] Vereinfachte Verkaufsprozesse

Was ist eine PID (single choice)?

[[ ]] Ein Datenaustauschformat (portable interoperable data)
[[ ]] Ein 3D-Datenformat (product image 3D)
[[x]] Die eindeutige Benennung einer digitalen Ressource (persistent identifier)
[[ ]] Eine Lizenzangabe (public international domain)

Wie können digitalisierte Sammlungen in der Lehre eingesetzt werden?

[[x]] Zur Erstellung virtueller Vermittlungsformate
[[x]] In digitalen Seminarmaterialien
[[ ]] Als Ersatz für Präsenzveranstaltungen
[[x]] Für Lehrforschungsprojekte

## 13. Digitale Objektfotografie
<!--
@comment
Lernziel: Sie kennen relevante Ausrüstung zur Objektfotografie sowie wichtige Kamera- und Objektivparameter (1).
Lernziel: Sie können die Elemente und Merkmale eines Arbeitsplatzes für Objektfotografie beschreiben (2).
Lernziel: Sie kennen wesentliche Schritte der digitalen Entwicklung und des Datenexports (1).
@end
-->

Welche Parameter sind bei der Objektfotografie wichtig?

[[x]] Blende
[[ ]] Tageszeit
[[x]] ISO-Wert
[[x]] Belichtungszeit
[[x]] Weißabgleich

Was gehört zu einem professionellen Digitalisierungsarbeitsplatz?

[[x]] Farbtreue Displays
[[x]] Standardisierte Beleuchtung
[[x]] Farbkarte mit Maßstab für Weißabgleich und als Größenreferenz
[[x]] Hochauflösende Kamera
[[x]] Hochwertige Objektive
[[x]] Hintergrundsystem

Was muss bei der Aufnahmesituation beachtet werden?

[[x]] Neutraler, reflexionsarmer Hintergrund
[[ ]] Kreative Bildgestaltung
[[x]] Gleichmäßige, schattenfreie Ausleuchtung
[[ ]] Belichtungskorrektur immer auf -3
[[x]] Maßstab und Farbkeil im Bild
[[x]] Verwacklungsfreie Aufnahme

Welche Schritte gehören zur digitalen Entwicklung von Objektfotografien?

[[x]] RAW-Entwicklung
[[x]] Kontrolle des Weißabgleichs und Farbraums
[[ ]] Künstlerische Bildbearbeitung
[[ ]] Export als GIF
[[x]] Export als TIFF

> vgl. [Checkliste Objektfotografie](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md)

## 14. Qualitätssicherung der Digitalisierung
<!--
@comment
Lernziel: Sie können wesentliche Qualitätskriterien für Objektfotografien benennen (1) und vorgelegte Digitalisate entsprechend einschätzen (2).
@end
-->

Welche technischen Mindestanforderungen gelten für Digitalisate?

[[x]] Mindestens 6000x4000 Pixel (24 Megapixel) 
[[x]] TIFF-Format als Archivformat
[[ ]] Farbraum: 8 Bit Graustufen
[[x]] Mehrere Ansichten pro Objekt
[[ ]] Maximale Dateikomprimierung

Was sollte bei der Qualitätskontrolle von Digitalisaten geprüft werden?

[[x]] Schärfe der Aufnahme
[[x]] Korrekte Belichtung
[[ ]] Dramatische Ausleuchtung
[[x]] Farbtreue
[[x]] Vollständigkeit der Ansichten

Welche Informationen müssen in den Metadaten der Digitalisate hinterlegt sein?

[[x]] Technische Metadaten (EXIF)
[[x]] Bildurheber:in
[[ ]] Privatadresse der Bildurheber:in
[[x]] Lizenz

> vgl. [Checkliste Objektfotografie](https://github.com/digiKulTh/Lehr-Lern-Materialien/blob/main/Handreichungen/Checkliste%20Objektfotografie.md)

## Ende

🎉🎆
Du hast es geschafft und bist hoffentlich zufrieden mit Deinen Antworten!
💪🥳
