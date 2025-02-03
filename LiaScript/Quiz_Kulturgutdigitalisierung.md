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

Die jeweils vor den Fragen vermerkten Lernziele entsprechen der Übersicht unter https://github.com/digiKulTh/Lehr-Lern-Materialien#lernziele und werden nach Finalisierung des Quizzes entfernt.

Alle Fragen sind Multiple-Choice-Fragen, außer es ist dahinter ein anderer Fragetyp vermerkt.

Durch Klicken auf `Prüfen` werden die Antworten abgeglichen, der Haken daneben gibt die korrekte Lösung vor, sollte man nicht darauf kommen.

## Rahmenbedingungen der Kulturgutdigitalisierung
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
[[x]] Fotografische Dokumentation
[[x]] Metadatenerfassung
[[x]] Qualitätskontrolle
[[ ]] Verkaufsvorbereitung

## Sammlungsmanagement
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

## Rechtliche Aspekte
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

## Lizenzmodelle
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

## Ethische Herausforderungen
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

## Nachnutzung von Sammlungsdaten
<!--
@comment
Lernziel: Sie kennen Formen der Nachnutzung von Sammlungsdaten in Forschung, Lehre und Vermittlung (1).
@end
-->

Was sind wichtige Formen der Nachnutzung digitalisierter Sammlungen?

[[x]] Wissenschaftliche Forschungsprojekte
[[x]] Digitale Ausstellungen
[[x]] Machine Learning und KI-Training
[[ ]] Verkauf der Originalobjekte
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

## Expertise und Ansprechpartner
<!--
@comment
Lernziel: Sie haben einen Überblick über relevante Expertisefelder für den Gesamtprozess und können relevante Ansprechpartner benennen (2).
@end
-->

In welchen Bereichen ist spezialisiertes Fachwissen in einem Digitalisierungsprojekt nötig?

[[x]] Objekthandling und Konservierung
[[x]] Digitale Fotografie
[[x]] Metadatenstandards
[[x]] Rechtliche Aspekte
[[ ]] Verkaufsstrategie

Welche Expertisen sind für Digitalisierungsprojekte relevant?

[[x]] Restaurator:innen
[[x]] Fotograf:innen
[[x]] Museolog:innen
[[x]] IT-Spezialist:innen
[[ ]] Marketingexpert:innen
[[x]] Fachwissenschaftler:innen

## Objekthandling
<!--
@comment
Lernziel: Sie haben Grundkenntnisse im Handling von Objekten, d. h. kennen die Merkmale geeigneter Handschuhe, Verpackungsmaterialien, Depotmöbel und Räumlichkeiten (1).
Lernziel: Sie kennen häufig auftretende Substanzen, Zustände und Bedingungen, die den Objekten oder ihnen selbst bei Exposition schaden können (1).
@end
-->

Welche Handschuhe sind für welche Objekte geeignet?

[[x]] Baumwollhandschuhe für unempfindliche Objekte
[[ ]] Fleece-Fäustlinge für Metallobjekte
[[ ]] Fingerlose Handschuhe für besseres Gefühl
[[x]] Nitrilhandschuhe für chemisch sensible Objekte

Welche Bedingungen können Objekten schaden?

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
[[x]] Verschlossener Zugang

## Konservierung und IPM
<!--
@comment
Lernziel: Sie kennen die Möglichkeiten der Anbringung von Inventarnummern sowie grundlegende Konservierungstechniken und das Konzept des Integrated Pest Management (IPM) (1).
@end
-->

Welche Aussagen zum Integrated Pest Management (IPM) sind korrekt?

[[x]] Es ist ein ganzheitlicher Ansatz zur Schädlingsprävention
[[x]] Regelmäßige Kontrollen sind ein zentraler Bestandteil
[[ ]] Es ist nur für Naturkundemuseen relevant
[[x]] Es umfasst präventive und reaktive Maßnahmen
[[x]] Sollte in allen Sammlungen mit organischen Materialien angewendet werden.

Welche Methoden der Inventarnummeranbringung sind geeignet?

[[x]] Beschriftung mit säurefreier Tusche auf Lackschicht
[[ ]] Direktes Beschriften von Holzobjekten mit dem Kugelschreiber
[[x]] Direktes Beschriften mit Bleistift rückseitig auf Zeichungen und Drucken
[[ ]] Aufkleben von Post-Its an Objektunter- oder -rückseite
[[x]] Anhängen von säurefreien Etiketten

## Metadaten und Datenmanagement
<!--
@comment
Lernziel: Sie haben Grundkenntnisse in den Bereichen Metadaten, Datenmanagement und Linked Open Data (FAIR, LIDO) (1).
@end
-->

Wofür steht das Akronym FAIR?

[[x]] Findable (auffindbar)
[[ ]] Fast (schnell)
[[ ]] Annotated (annotiert)
[[x]] Accessible (zugänglich)
[[ ]] International (international)
[[x]] Interoperable (interoperabel)
[[x]] Reusable (nachnutzbar)
[[ ]] Representative (repräsentativ)

Was sind wichtige Metadatenstandards im Museumsbereich?

[[x]] LIDO
[[x]] Dublin Core
[[ ]] HTML5
[[x]] CIDOC CRM
[[ ]] PNG Format

## Sammlungsdatenbanken und Erfassung
<!--
@comment
Lernziel: Sie kennen verbreitete Erfassungssysteme, Thesauri/Vokabulare sowie Datenformate (1).
Lernziel: Sie wissen, welche Metadaten sie bei der Digitalisierung von Kulturgut erheben sollten und wie dies in einer Erfassungsmaske zu geschehen hat (2).
@end
-->

Welche Eigenschaften haben verbreitete Erfassungssysteme?

[[x]] Hierarchische Datenstrukturen
[[x]] Standardisierte Eingabemasken
[[ ]] Word-basierte Oberfläche
[[x]] Thesaurusanbindung
[[x]] Exportfunktionen
[[ ]] Automatische Objektbewertung

Welche grundlegenden Metadaten sollten erfasst werden?

[[x]] Eindeutige Inventarnummer
[[x]] Objektbezeichnung und Objektart
[[ ]] Beliebtheit bei Personal und Besucher:innen
[[ ]] Farbe
[[x]] mindestens ein Datum, etwa zu Herstellungszeit oder Ankauf
[[x]] Standort
[[ ]] Aktueller Versicherungswert

Was muss bei der Datenerfassung beachtet werden?

[[x]] Einheitliche Terminologie
[[ ]] Kreative Datumsformate ("Jänner des Jahres '24")
[[x]] Vollständigkeit der Pflichtfelder
[[x]] Verwendung kontrollierter Vokabulare 
[[ ]] Nichtssagender Objekttitel ("Vase")

## Datennutzung für Forschung und Lehre
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

Wie können digitalisierte Sammlungen in der Lehre eingesetzt werden?

[[x]] Zur Erstellung virtueller Vermittlungsformate
[[x]] In digitalen Seminarmaterialien
[[ ]] Als Ersatz von Präsenzveranstaltungen
[[x]] Für Lehrforschungsprojekte

## Digitale Objektfotografie
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

## Qualitätssicherung der Digitalisierung
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

Was ist bei der Qualitätskontrolle von Digitalisaten wichtig?

[[x]] Schärfe der Aufnahme
[[x]] Korrekte Belichtung
[[x]] Farbtreue
[[x]] Vollständigkeit der Ansichten

Welche Informationen müssen in den Metadaten der Digitalisate hinterlegt sein?

[[x]] Technische Metadaten (EXIF)
[[x]] Bildurheber:in
[[ ]] Privatadresse der Bildurheber:in
[[x]] Lizenz

## Ende

🎉🎆
Du hast es geschafft und bist hoffentlich zufrieden mit Deinen Antworten!
💪🥳
