---
title: "5 Repository-Software für Publikationen und Forschungsdaten"
date: 2020-10-16
---
inkl. ArchivesSpace Teil 2 
 
Obschon wir die Bedienung von ArchivesSpace (AS) bereits am Ende der letzten Vorlesung begonnen haben, folgt hier der gesamte praktische Teil. 

Als Grundkonfiguration galt es ein eigenes Repository in ArchivesSpace zu erstellen. Hier für uns wichtig zu beachten: das Anwählen der Checkbox *Publish?* wird – soll das Repository später dann im public interface einsehbar sein – vorausgesetzt. Danach galt es eigene Datensätze zu erstellen, die dann in eben genanntem public interface zu sehen sein sollen. In AS können ausschliesslich die Sprachen Englisch, Spanisch, Französisch und Japanisch konfiguriert werden, weshalb für das Handling der Software das Verständnis der (in meinem Falle) englischen Begriffe wie 'Accession', 'Resource' und 'Archival Objecst' unabdingbar ist. 

+ Accession: 
  + Um dem Provenienzprinzip Folge zu leisten ist es vorerst notwendig Informationen zur  Herkunft/zum Erwerb des Bestandes zu erfassen (also wie ist der Bestand  entstanden? Wie sind die Materialien ins Archiv gekommen? Welche „Stationen“ durchliefen sie?). Es wird also ein Datensatz für die Bestandeserwerbung erstellt, der dann wiederum mit Ressourcen verknüpft werden kann. Die bei Accession hinterlegten Informationen werden dann den damit verknüpften Resosurcen „vererbt“.

+ Resource: 
  + Mittels Anlegen von einem Ressourcen-Datensatz können dann die Bestände und Materialien selbst erschlossen werden. Dies stellt der zentrale Nachweis auf der obersten Verzeichnungsstufe dar. Eine Ressource kann selbst eine Collection (Bestand) sein, an die wiederum weitere Collections oder aber Archival Objects angehängt werden können.

+ Archival Objects:
  + Sind dementsprechend Nachweise auf den Verzeichnungsstufen unter der Ressource. Die  Erschliessung ist auf verschiedenen Ebenen möglich: Bestand (Fonds), Serie (Series) über die Akte (File) bis hin zum Einzelstück (Item). 

Um eine tiefere Verzeichnungsstufe anlegen zu können, muss die jeweilige Ressource aufgerufen und bearbeitet und über „Add Child“ (oder bei Objekten auf derselben Stufe „Add Sibling“) gewählt werden. Um die Verknüpfung zwischen Accession und einer bereits erstellten Ressource herzustellen muss die gewünschte Accession angewählt werden. Über den Button ‚Spawn‘ und der Auswahl ‚Resource‘ wird das Ausfüllen eines Eingabeformulars gefordert. Wenn aber bereits ein Resource-Datensatz erstellt wurde, kann die Ressource bearbeitet und die Verknüpfung über ‚related Accession‘ hinterlegt werden. Ohne die Schritt-für-Schritt-Anleitung im Script hätten sich mir diese mir etwas umständlich erscheinende Schritte wahrscheinlich nicht erschlossen - oder sicherlich nicht innert einer nützlichen Frist. 

ArchivesSpace bietet nebst der OAI-PMH Schnittstelle die Möglichkeit Daten in unterschiedlichen Formaten wie EAD, MARCXML oder CSV zu im- und exportieren. Dazu gab es zwei Übungen mit folgendem Erkenntnisgewinn: Das in der letzten Vorlesung kennengelernte Austauschformat EAD klingt in der Theorie toll und es ist weit verbreitetet. Aber bereits bei unserem Mini-Beispiel, bei dem wir Beispieldaten im Format EAD in ArchivesSpace importiert haben, hat sich schnell gezeigt, dass es in der Praxis nicht ganz so einwandfrei funktioniert. Es ploppten Meldungen über nicht ausgefüllte Pflichtfelder oder über- oder unterschrittene Zeichenvorgaben auf – und ganz generell waren die Daten von der ursprünglichen Datei in der importierten Datei nicht an der Stelle, an der sie sein sollten. Darüber hinaus stellte sich der Export einer MARCXML-Datei als verlustbehaftet heraus. Dies liegt daran, dass die vorhin in EAD importierte Datei einer Baumstruktur unterliegt, die im MARCXML nicht wiederzufinden ist. Grund dafür sind die unterschiedlichen Verzeichnungstiefen und –Strukturen in Kombination mit den „Transformationsregeln“ der Software, die die Daten dann „in die andere Form pressen“. Daten verlustfrei über verschiedene Systeme hinweg auszugeben und einzuspeisen ist und bleibt also herausfordernd.

Auch spannend (und bedenklich): ArchivesSpace unterschlägt bei einem fehlgeschlagenen Import nützliche Informationen.. Zwar wird ausgegeben, dass der Import funktioniert hat – wird jedoch ein Blick in die Logdatei geworfen, stellt man fest, dass dem gar nicht so ist. Diese Fehlermeldung geht irgendwo jenseits der AS-Untiefen verloren. Ausserdem dürfte, wie oben schon angedeutet, an der Usability von ArchivesSpace gerne noch ein wenig geschraubt werden. Denn allein das Ausfindigmachen der Option ‚Import‘, bzw. ‚Export‘ ist bei weitem nicht intuitiv. 

Weiterer „Fun Fact“: bei ArchivesSpace gibt’s keine kostenlose online-Hilfe, die für alle gleichermassen nutzbar ist. Diese steht nur zahlenden Mitglieder zur Verfügung – dasselbe mit dem Benutzerhandbuch. Entspricht also nicht wirklich dem Verständnis von „open“.

## Marktüberblick Archivsysteme
+ ArchivesSpace wird vor allem in den USA durch eine grosse Community gestützt und genutzt
+ Acess to Memory (AtoM) ist eine weitere Open-Source Lösung 
+ In der Schweiz marktführend sind die Systeme Scope.Archiv und CMISTAR
+ (Die Visualisierung von Digitalisaten wird oftmals mit einer zusätzlichen Software-Lösung angegangen, so bspw. die e-Pics-Plattform der ETH Zürich (, die auch meine Praktikumsstelle (Fotostiftung Schweiz) verwendet))

## Bibliotheks- und Archivsoftware im Vergleich
Bibliotheken setzen den Fokus auf die Vermittlung von Medien und legen viel Wert auf die Interaktion mit den Benutzer'innen. Bei öffentlichen Biblios stehen eher Veranstaltungs- und Content-Management und die optische Ausgestaltung der Werkzeuge und Systeme im Mittelpunkt. Bei wissenschaftlichen Biblios eher die Erschliessung und das e-Ressourcen-Management. Die Darstellungsweise ist also eher neutral und etwas nüchterner. Archive dagegen basieren bezüglich der Erfassung und Abbildung ihrer Bestände auf dem Provenienzprinzip, was sich natürlich auch in der Software zeigt. Diese soll also nicht so medienzentriert wie bei Bibliotheken sein, sondern sich an den Findmitteln und der meist hierarchischen Bestandesstrukturen orientieren.

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

