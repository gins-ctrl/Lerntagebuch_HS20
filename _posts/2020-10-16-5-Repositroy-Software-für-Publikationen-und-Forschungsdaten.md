---
title: "5 Repository-Software für Publikationen und Forschungsdaten"
date: 2020-10-16
---
inkl. ArchivesSpace Teil 2 
 
Obschon wir die Bedienung von ArchivesSpace (AS) bereits am Ende der letzten Vorlesung begonnen haben, wird der gesamte praktische Teil in diesem Post „verarbeitet“. 

Als Grundkonfiguration galt es ein eigenes Repository in ArchivesSpace zu erstellen. Hier für uns wichtig zu beachten: das Anwählen der Checkbox *Publish?* wird – soll das Repository später dann im public interface einsehbar sein – vorausgesetzt. Danach galt es eigene Datensätze zu erstellen, die dann in eben genanntem public interface zu sehen sein sollen. In AS können ausschliesslich die Sprachen Englisch, Spanisch, Französisch und Japanisch konfiguriert werden, weshalb für das Handling der Software das Verständnis der englischen Begriffe wie Accession, Resource und Archival Objects unabdingbar ist. 

+ Accession: 
  + Um dem Provenienzprinzip Folge zu leisten ist es vorerst notwendig Informationen zur  Herkunft/zum Erwerb (wie sind sie entstanden? wie sind die Materialien ins Archiv gekommen? Welche „Stationen“ durchliefen sie?) des Bestandes zu erfassen. Es wird also ein Datensatz für die Erwerbung erstellt, der dann wiederum mit Resourcen verknüpft werden kann. Die hier hinterlegten Informationen werden dann der damit verknüpften Resource „vererbt“.

+ Resource: 
  + Mittels Anlegen von einem Resourcen-Datensatz können die Bestände und Materialien genauer erschlossen werden. Dies stellt der zentrale Nachweis auf der obersten Verzeichnungsstufe dar. Eine Resource kann selbst eine Collection sein, an die wiederum eine weitere Collection oder aber Archival Objects angehängt werden können.

+ Archival Objects:
  + sind dementsprechend Nachweise auf den Verzeichnungsstufen unter der Ressource. Die  Erschliessung ist auf der Ebene Bestand (Fonds), Serie (Series) über die Akte (File) bis hin zum Einzelstück (Item) möglich. 

Um eine tiefere Verzeichnungsstufe anlegen zu können, muss die jeweilige Ressource aufgerufen und bearbeitet und über „Add Child“ (oder bei Objekten auf derselben Stufe „Add Sibling“) gewählt werden.

Um die Verknüpfung zwischen Accession und einer bereits erstellten Resource herzustellen muss die gewünschte Accession angewählt werden. Über den Button ‚Spawn‘ und der Auswahl ‚Resource‘ wird das Ausfüllen eines Eingabeformulars gefordert. Wenn aber bereits ein Resource-Datensatz erstellt wurde, kann die Ressource bearbeitet und die Verknüpfung über ‚related Accession‘ hinterlegt werden. 

ArchivesSpace bietet nebst der OAI-PMH Schnittstelle die Möglichkeit Daten in unterschiedlichen Formaten wie EAD, MARCXML oder CSV zu im- und exportieren. Dazu gab es zwei Übungen mit folgendem Erkenntnisgewinn: Das in der letzten Vorlesung kennengelernte Austauschformat EAD klingt in der Theorie toll! Es ist weit verbreitetet aber bereits bei unserem Mini-Beispiel, bei dem wir Beispieldaten im Format EAD in ArchivesSpace importiert haben, hat sich schnell gezeigt, dass es in der Praxis nicht ganz so einwandfrei funktioniert. Es ploppten Meldungen über nicht ausgefüllte Pflichtfelder oder über- oder unterschrittene Zeichenvorgaben auf – und ganz generell waren die Daten von der ursprünglichen Datei in der importierten Datei nicht an der Stelle, an der sie sein sollten. Darüber hinaus stellte sich der Export einer MARCXML-Datei als verlustbehaftet heraus. Dies liegt daran, dass die vorhin in EAD importierte Datei einer Baumstruktur unterliegt, die im MARCXML nicht wiederzufinden ist. Diese unterschiedlichen Verzeichnungstiefen und –Strukturen sind in Verbindung mit den „Transformationsregeln“ der Software, die die Daten dann „in die andere Form quetschen“, Grund dafür.

Auch spannend (und bedenklich): ArchivesSpace unterschlägt bei einem fehlgeschlagenen Import nützliche Informationen.. Zwar wird ausgegeben, dass der Import funktioniert hat – wird jedoch ein Blick in die Logdatei geworfen, stellt man fest, dass dem gar nicht so ist. Diese Fehlermeldung geht irgendwo jenseits der AS-Untiefen verloren. Ausserdem dürfe an der Usability von ArchivesSpace gerne noch ein wenig geschraubt werden. Denn das Ausfindigmachen der Option ‚Import‘, bzw. ‚Export‘ ist bei weitem nicht intuitiv. 

Weiterer „Fun Fact“: bei ArchivesSpace gibt’s keine kostenlose online-Hilfe, die für alle gleichermassen nutzbar ist. Diese steht nur zahlenden Mitglieder zur Verfügung – dasselbe mit dem Benutzerhandbuch. Entspricht also nicht wirklich unserem Verständnis von „open“.

## Marktüberblick Archivsysteme
+ ArchivesSpace wird vor allem in den USA durch eine grosse Community gestützt und genutzt
+ Acess to Memory ist eine weitere Open-Source Lösung 
+ Scope.Archiv und CMISTAR sind in der Schweiz marktführende Systeme 
+ (Die Visualisierung von Digitalisaten wird oftmals mit einer zusätzlichen Software-Lösung angegangen, so bspw. die e-Pics-Plattform der ETH Zürich (,die ich auch in meinem Praktikum in der Fotostiftung Schweiz kennenlernen durfte))

## Bibliotheks- und Archivsoftware im Vergleich
Um die Unterschiede zu verstehen, ist es nützlich sich die grundlegenden Unterschiede zu vergegenwärtigen. Zum einen ist da die Bibliothek, die für die Vermittlung von Medien, die in grösseren Auflagen erscheinen und in der Regel keine Unikate sind, verantwortlich. Da wiederum soll die Differenzierung von öffentlicher (Veranstaltungs- und Content-Management, optische Ausgestaltung) und wissenschaftlicher Bibliothek (v.a. Erschliessung und e-Ressourcen-Management, neutrale, nüchterne Darstellung) gemacht werden. Bibliotheken also als medienzentrierte und stark mit den Benutzer’innen interagierende Institution im Vergleich zu Archiven, die grossen Wert auf die Erfassung und Abbildung der Provenienz ihrer meist unikaler Archivalien legen. Hier soll sich die Software also dementsprechend an den Findmitteln und nicht wie bei der Bibliothek an den Medien orientieren. 

## Repository-Software für Publikationen und Forschungsdaten
Da es mich weniger interessiert und ich wieder zu viel schreibe, das Wichtigste in Kürze:
Open Access: freier Zugang zu PUBLIKATIONEN 
Open Data: Verzeichnis von FORSCHUNGSDATEN 
Forschungsinformation: Informationen über die Forschenden selbst, Forschungsfinanzierung, Patente,
Forschungsberichterstattung: Grundlage dafür sind Forschungsinformations(-systeme)
+ Best Practice Beispiel: Zenodo (kostenlos, Versionisierung, ID-Vergabe,…)
+ ORCID: Zusammenschluss von Verlagen und Institutionen mit dem Ziel international eine ID für Forschende umzusetzen (wie die DOI für Dokumente)

#### Wir lernen DSpace…
…als Software für Publikationen und Forschungsdaten (in der Demo Version) kennen. Die Erweiterung für die Verwaltung von Forschungsinformationen ist dann DSpace-CRIS.
Aus Zeichenmangel (und Zeitmangel während der Vorlesung) gehe ich auf die Konfiguration und die Übungen mit DSpace im nächsten Beitrag ein…

