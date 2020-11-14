---
title: "4 Funktion und Aufbau von Archivsystemen"
date: 2020-10-09
---
Archive im Weltall 

In der 3. Vorlesung (Link noch setzen) wurde die Schnittstelle OAI-PMH bei dem Exkurs „Datenexport und Schnittstellen“ gestreift. Als Folge dessen kamen bereits Fragen nach Sinn und Nutzen davon für eine Bibliothek auf..
Als ein Nebeneffekt, respektive als sekundären Nutzen von OAI-Schnittstellen wird die Möglichkeit genannt, dass damit die eigenen Daten weiterverarbeitet oder abgerufen werden können um sie dann in Discovery-Systemen oder als Metadatengrundlage für Digitalisierungsprozesse einzusetzen. 
Der primäre Nutzen ist aber vielmehr die Bereitstellung von Daten gegen aussen. So können andere Institutionen oder bspw. Bibliotheksverbünde Metadaten aus verschiedenen Bibliotheken über eine Schnittstelle, die einheitlich und vom Tool, respektive von der Institution unabhängig ist, „anzapfen“ um Regionalbibliographien oder auch Themenportale zu erarbeiten. Bei spezialisierten Schnittstellen, wie Z39.50 eine ist (sie mein NEBIS-Beispiel von der Übung Datenimport mit Koha), kann je nach dem der Port gesperrt sein. Diese Hürde ist bei einer OAI-PMH (oder SRU) Schnittstelle merklich kleiner, denn diese holt die Metadaten über Webports, die in Netzwerken selten gesperrt sind. In der Vorlesung „Metadaten modellieren und Schnittstellen nutzen“ (Link dann noch setzen) wird die Thematik sicherlich nochmals aufgegriffen und behandelt. Daraufhin wurde zu FOLIO noch ergänzend erwähnt, dass es aus wirtschaftlichen, politischen und strategischen Aspekten nicht als eine Alma-Alternative in Betracht gezogen wurde. Uuund, auch nochmals gut zu hören waren die Vorteil(e) bei Open Source Software: verschiedene Institutionen und Entwickler können wegen des offenen Quellcodes daran feilen und arbeiten und verschiedene Anbieter können Dienstleistungen und Support dazu anbieten, was auch einem Vendor-Lock-in entgegenwirkt.


## Metadatenstandards in Archiven 
### ISAD(G)
Dem *International Standard Archival Description (General)* sowie dem *International Standard Archival Authority Record for Corporate Bodies, Persons and Families (ISAAR (CPF)* (sorry, aber welche normalsterbliche Person hat sich diese überbordende Bezeichnung ausgedacht !?!) bin ich im Studium bereits mehrere Male begegnet, weshalb ich an dieser Stelle nur die Stichworte mehrstufige Verzeichnung und Provenienzprinzip notiere und auf die folgenden 7 Informationsbereiche hinweise:
Identifikation
Kontext
Inhalt und innere Ordnung
Zugangs- und Benutzungsbedingungen
Sachverwandte Unterlagen
Anmerkungen
Kontrolle

Ausserdem die 6 Pflichtfelder in ISAD(G): 

Signatur, Titel, Provenienz, Entstehungszeitraum, Umfang und Verzeichnungsstufe

#### Problematisch ist in ISAD(G)…
…dass einzelne Objekte ohne die Einbettung in ihren Kontext nicht mehr verständlich sein können, 
dass Archivobjekte nicht mehrfach zugeordnet werden können und
dass der Standard nicht auf digitale Materialien ausgerichtet und stark auf den damals analogen Findmitteln basiert. D.h. Digitalisierung und digitale Langzeitarchivierung sind nicht Teil von ISAD(G). 
(Ich kann mich noch gut an den Besuch im Sozialarchiv Zürich im ersten Teil des Studiums erinnern. Da waren viele – ich inklusive – sehr überrascht, dass die Archive in unserer doch sehr modernen, technischen und digitalen Welt noch mit beiden Beinen im Analogen „feststecken“. Jetzt kann ich mir wenigstens vage vorstellen, wie schwierig nur ein erster Schritt in Richtung eines neuen Standards und neue Systeme und Denkweisen hin sein wird.)

Aktuell ist die Arbeit und Entwicklung von *Records in Contexts* (RIC) und die Generierung von Volltexten mittels Optical Character Recognition (OCR) in progress. Mal sehen wohin damit die Reise führt..

### EAD
EAD bedeutet so viel wie *Encoded Archival Description* und ist ein XML-Standard, den es in verschiedenen Versionen gibt. Wenn ich erneut das Schaubild alias Fahrplan für das Modul betrachte, ist es echt erfreulich, dass mir all die fremden Begriffe gar nicht mehr so fremd sind (WOW)! Aus MARC21-XML, Dublin Core und EAD als Metadatenstandards, sowie dem hieroglyphischen OAI-PMH kann ich mir Stand heute einen Reim machen. Ebenso von Koha, und ab der heutigen Sitzung auch von ArchivesSpace, denn damit geht’s weiter…

## Das Open-Source Archivinformationssystem ArchivesSpace (AS)
Als eine nicht vollständige Auflistung der Funktionen und Eigenschaften von ArchivesSpace sind nachfolgende Punkte zu verstehen: AS verwaltet die Standort- und Bestandesinformationen sowie (u.a. deskriptive) Metadaten der Archivobjekte aber auch von Digitalisaten. Ausserdem verfügt AS über Zugangstools (bspw. Onlinekatalog, Schnittstellen) für die Vermittlung und die Sicherstellung für den Zugang für Nutzer’innen (u.v.m.). Zudem erwähnenswert: Im Archivsystem sind nicht alle Bereiche und Objekte für die Öffentlichkeit und/oder für jede‘n Mitarbeiter‘in einsehbar, was wiederum die Rechteverwaltung komplexer macht. In ArchivesSpace ist die Arbeit mit den Metadatenstandards DACS, ISAD(G) und ISAAR(CPF) sowie Import und Export in EAD, MARCXML und METS möglich. 

Soviel also mal zum Theoretischen. 
Praktisch muss das System natürlich mal installiert (check) und in unserem Fall manuell mittels Eingabe von *archivesspace/archivesspace.sh* im Terminal gestartet werden (check – check). In der Shell flimmern ab dann 'zig Meldungen über den Schirm, was an sich ignoriert werden kann. Die Verfügbarkeit der Software ist hingegen an das Terminal gebunden – es darf also nicht geschlossen werden (im Linux-Kontext werden laufende Programme, die im Hintergrund ausgeführt werden, Daemon genannt). Dann ist es im Browser unter unterschiedlichen Ports verfügbar. 
Für uns wichtig: [staff interface](http://localhost:8080/) und [public interface](http://localhost:8081/)

Da ich die Vorlesung etwas früher verlassen musste und ich somit die Bedienung von ArchivesSpace anhand von Übungen nur am Rande mitbekommen habe, wird dies im nächsten Beitrag thematisiert.

Aus ~~dramaturgischen~~ zeitlichen Gründen sind die Übungen mit AS zu Import und Export wie auch der Marktüberblick über die Archivsysteme Inhalt der nächsten Vorlesung!
…Trommelwirbel…

## To Do`s 
Text „was sich Historiker’innen von Archiven wünschen“ lesen und wegen den bereits wieder aufgebrauchten Zeichen in einen anderen Beitrag schmuggeln…
