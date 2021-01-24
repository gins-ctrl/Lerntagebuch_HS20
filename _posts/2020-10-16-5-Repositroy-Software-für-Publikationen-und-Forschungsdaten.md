---
title: "5 Repository-Software für Publikationen und Forschungsdaten"
date: 2020-10-16
---
ArchivesSpace Teil 2: Praxis


Als Grundkonfiguration galt es ein eigenes Repository in ArchivesSpace (AS) zu erstellen, das dann später im public interface einsehbar sein soll (dafür Checkbox *Publish?* anwählen). Darin galt es eigene Datensätze zu erstellen, respektive anzulegen. Die Übung hat gezeigt, dass für das Handling und das Verständnis der Software die Begrifflichkeiten 'Accession', 'Resource' und 'Archival Objecst' klar sein müssen. (P.S. Auch das Datensätze-anlegen empfanden wir in der Gruppe keineswegs als trivial, denn die vielen Felder lösen auch viele Fragen aus ;))

+ Accession: 
  + Um dem Provenienzprinzip Folge zu leisten ist es vorerst notwendig Informationen zur  Herkunft/zum Erwerb des Bestandes zu erfassen (also was wissen wir über die Entstehung des Bestandes? Wie sind die Materialien ins Archiv gekommen?). Es wird also ein Datensatz für die Bestandeserwerbung erstellt, der dann wiederum mit Ressourcen verknüpft werden kann. Die bei Accession hinterlegten Informationen werden dann den damit verknüpften Ressourcen „vererbt“.

+ Resource: 
  + Mittels Anlegen von einem Ressourcen-Datensatz können dann die Bestände und Materialien selbst erschlossen werden. Dies stellt der zentrale Nachweis auf der obersten Verzeichnungsstufe dar. Eine Ressource kann selbst eine Collection (Bestand) sein, an die wiederum weitere Collections oder aber Archival Objects angehängt werden können.

+ Archival Objects:
  + Sind dementsprechend Nachweise auf den Verzeichnungsstufen unter der Ressource. Die  Erschliessung ist auf verschiedenen Ebenen möglich: Bestand (Fonds), Serie (Series) über die Akte (File) bis hin zum Einzelstück (Item). 

Um eine tiefere Verzeichnungsstufe anlegen zu können, muss die jeweilige Ressource aufgerufen und bearbeitet und über 'Add Child' (oder bei Objekten auf derselben Stufe 'Add Sibling') gewählt werden. Um die Verknüpfung zwischen Accession und einer bereits erstellten Ressource herzustellen muss die gewünschte Accession angewählt werden. Über den Button ‚Spawn‘ und der Auswahl ‚Resource‘ wird das Ausfüllen eines Eingabeformulars gefordert. Wenn aber bereits ein Resource-Datensatz erstellt wurde, kann die Ressource bearbeitet und die Verknüpfung über ‚related Accession‘ hinterlegt werden. Ohne die Schritt-für-Schritt-Anleitung im Script hätten sich mir diese mir etwas umständlich erscheinenden Schritte wahrscheinlich nicht erschlossen - oder sicherlich nicht innert einer nützlichen Frist. 

ArchivesSpace bietet nebst der OAI-PMH Schnittstelle die Möglichkeit Daten in unterschiedlichen Formaten wie EAD, MARCXML oder CSV zu im- und exportieren. Dazu gab es zwei Übungen mit folgendem Erkenntnisgewinn: Das in der letzten Vorlesung kennengelernte Austauschformat EAD klingt in der Theorie toll und es ist weit verbreitetet. Aber bereits bei unserem Mini-Beispiel, bei dem wir Beispieldaten im Format EAD in ArchivesSpace importiert haben, hat sich schnell gezeigt, dass es in der Praxis nicht ganz so einwandfrei funktioniert. Es ploppten Meldungen über nicht ausgefüllte Pflichtfelder oder über- oder unterschrittene Zeichenvorgaben auf – und ganz generell waren die Daten von der ursprünglichen Datei in der importierten Datei nicht an der Stelle, an der sie sein sollten. Darüber hinaus stellte sich der Export einer MARCXML-Datei als verlustbehaftet heraus. Dies liegt daran, dass die vorhin in EAD importierte Datei einer Baumstruktur unterliegt, die im MARCXML nicht wiederzufinden ist. Grund dafür sind die unterschiedlichen Verzeichnungstiefen und –Strukturen in Kombination mit den „Transformationsregeln“ der Software, die die Daten dann „in die andere Form quetschen“. Daten verlustfrei über verschiedene Systeme hinweg auszugeben und einzuspeisen ist und bleibt also herausfordernd aber nicht per se unmöglich. Denn wenn das Zielformat (bspw. DC) mehr Möglichkeiten bietet als das Ausgangsformat (bspw. MARC21), kann eine verlustfreie Konvertierung durchaus funktionieren.

Auch spannend (und bedenklich): ArchivesSpace unterschlägt nützliche Informationen! Zwar wird ausgegeben, dass der Import funktioniert hat – ein Blick in die Logdatei zeigt jedoch dass dem gar nicht so ist. Die Fehlermeldung geht irgendwo jenseits der AS-Untiefen verloren. Ausserdem dürfte, wie oben schon angedeutet, an der Usability von ArchivesSpace gerne noch ein wenig geschraubt werden. Denn allein das Ausfindigmachen der Option ‚Import‘, bzw. ‚Export‘ ist bei weitem nicht intuitiv. 

Weiterer „Fun Fact“: bei ArchivesSpace gibt’s keine kostenlose online-Hilfe, die für alle gleichermassen nutzbar ist. Diese steht nur zahlenden Mitglieder zur Verfügung – dasselbe mit dem Benutzerhandbuch. Entspricht also nicht wirklich dem Verständnis von „open“.

## Marktüberblick Archivsysteme
+ ArchivesSpace wird vor allem in den USA durch eine grosse Community gestützt und genutzt
+ [Access to Memory (AtoM)](https://www.accesstomemory.org) ist eine weitere Open-Source Lösung 
+ In der Schweiz marktführend sind die Systeme [scope.Archiv](http://www.scope.ch) und [CMISTAR](https://www.cmiag.ch/cmistar)
  (Die Visualisierung von Digitalisaten wird oftmals mit einer zusätzlichen Software-Lösung angegangen. Beispiel: e-Pics-Plattform der ETH Zürich, die auch meine Praktikumsstelle (Fotostiftung Schweiz) verwendet)

## Bibliotheks- und Archivsoftware im Vergleich
Bibliotheken setzen den Fokus auf die Vermittlung von Medien und legen viel Wert auf die Interaktion mit den Benutzer'innen. Bei öffentlichen Biblios stehen eher Veranstaltungs- und Content-Management und die optische Ausgestaltung der Werkzeuge und Systeme im Mittelpunkt. Bei wissenschaftlichen Biblios eher die Erschliessung und das e-Ressourcen-Management. Die Darstellungsweise ist also eher neutral und etwas nüchterner. Archive dagegen basieren bezüglich der Erfassung und Abbildung ihrer Bestände auf dem Provenienzprinzip, was sich natürlich auch auf die Software-Anforderungen auswirkt: Bibliothekssoftware soll medienzentriert sein und arbeitet hauptsächlich mit dem Metadatenformat MARCXML, Archivsoftware soll sich an den Findmitteln und der meist hierarchischen Bestandesstrukturen orientieren und nutzt das Metadatenformat EAD (und vielleicht bald RiC).

## Repository-Software für Publikationen und Forschungsdaten
Das Wichtigste in Kürze:
+ Open Access: freier Zugang zu ForschungsPUBLIKATIONEN 
+ Open Data: Verzeichnis von ForschungsDATEN 
+ Forschungsdaten: Während der Forschung erhobene Daten
+ Forschungsinformation: Informationen über die Forschenden selbst, Forschungsfinanzierung, Patente etc.
+ Forschungsberichterstattung: Grundlage dafür sind Forschungsinformations(-systeme), kurz FIS
+ Best Practice Beispiel: Zenodo (kostenlos, Versionisierung, ID-Vergabe,…)
+ ORCID: Zusammenschluss von Verlagen und Institutionen mit dem Ziel international eine ID für Forschende umzusetzen (wie die DOI für Dokumente)

#### Wir lernen DSpace…
…als Software für Publikationen und Forschungsdaten (in der Demo Version) kennen, die mit dem Metadatenstandard Qualified Dublin Core arbeitet. DSpace bietet dateibasierte Importe und die Schnittstellen SWORD (publizieren in DSpace auf anderen Webseiten) und OAI-PMH (externe Systemen können auf Metadaten, die in DSpace abgelegt sind zugreifen). Die Erweiterung für die Verwaltung von Forschungsinformationen ist dann DSpace-CRIS. Ausserdem relevante (Open Source) Systeme in D/A/CH: Eprints, Fedora / Islandora, Invenio, MyCoRe, OPUS.
