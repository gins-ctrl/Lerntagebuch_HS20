---
title: "2 Marc, 21, in Dublin oder so"
date: 2020-09-27
---

Die zweite Vorlesung war für mich etwas frustrierend, da mich technische Schwierigkeiten vom Motiviertsein und Vorwärtskommen abhielten. 
Zu Beginn wurde auf die neue Möglichkeit von virtuellen Gruppenarbeiten mit Teilgruppensitzungen via dem von der FHGR eingesetzten Tool ‚Webex‘ hingewiesen. So sind wir nicht mehr gezwungen uns über eine andere Anwendung mit den anderen Gruppenmitglieder’innen kurzzuschliessen, sondern können das direkt in Webex machen. Ausserdem können wir bei Problemen oder Fragen bei den Übungen Unterstützung anfordern und die Dozierenden können die Kontrolle über unseren Desktop, respektive unsere virtuelle Maschine übernehmen und so auf eine gewinnbringende Art und Weise Hilfestellung leisten. 

## Tipps und Hinweise zu den Lerntagebüchern 
Hier vor allem erwähnens- und für die eigene Lerntagebuch-Umsetzung wissenswert: Bilder können unterschiedlich in GitHub Pages eingebunden werden. 
+ Die vollständige URL vom jeweiligen Bild angeben (Idealfall)
+ Einen separaten Ordner im eigenen Repository erstellen, in welchem die Bilder abgelegt sind. Das Ordner-Anlegen ist auf der GitHub Oberfläche jedoch nicht möglich, weshalb es ein Geheimtipp bedarf: Über den Button *Add File* >> *Create new file* wählen. Da kann dann der gewünschte Ordnername definiert werden. Dann gilt es nach dem Ordnername ein / zu machen – so wird ein Ordner kreiert, in das noch eine Datei (bspw. eine Textdatei endend auf .txt) gespeichert werden muss, die dann später wieder gelöscht werden kann. Hauptsache der Ordner ist erstellt – check. 
+ Relativer Pfad unter der Bedingung, dass eine Variable genutzt wird. Tolle Notiz – habe ich aber während der Vorlesung nicht wirklich verstanden. Ich habe meine Notizen noch mit folgenden, sehr grundlegenden Erklärungen aus einer [Lehrveranstaltung am Institut für Digital Humanities der Uni Köln](https://lehre.idh.uni-koeln.de/lehrveranstaltungen/wisem19/basissysteme-der-informationsverarbeitung-1-bsi-2/web-technologien/html-1/relative-vs-absolute-pfade/) ergänzt:
  + Ein Pfad besteht aus:  einer Laufwerks- oder Datenträgerbezeichnung, einer Liste von Verzeichnissen, also Ordner und Unterordner und einem Dateinamen
  + Absoluter Pfad:  „Absolute Pfade beinhalten die vollständige Position einer Datei und sind somit unmissverständlich zu finden.“ Ausgangspunkt ist die oberste Ebene der  Datenstruktur des Computers. Wenn ein Bild im Netz online verfügbar ist, kann die absolute URL des Bildes verwendet werden.
  + Relativer Pfad = „Relative Pfade beschreiben die Position einer Datei relativ zu der Datei oder dem Ordner, in dem man sich gerade befindet. Damit sind sie komplett unabhängig von der Datenstruktur des Computersystems, auf dem sie sich befinden.“ Wenn ein Bild sich lokal innerhalb des eigenen Projekts befindet, sollte ein relativer Pfad verwendet werden. So können präventiv Fehler vermieden werden. Das Bild bleibt erreichbar, solange das Bild mit der HTML-Datei im gleichen Ordner liegt - auch wenn sich sonst etwas an der Ordnerstruktur ändert.
Das würde für die Datei ‚beispielbild.jpg‘ im Ordner ‚Images‘ so aussehen: 
```![]({{site.baseurl}}/images/beispielbild.jpg)``` (was mir zu kryptisch ist ;))

## Wieso Git(Hub) nützlich ist
Git ist eine Software zur Versionskontrolle. Wichtig ist, dass Git nicht ausschliesslich ein Werkzeug für die Softwareentwicklung, sondern vielmehr für die Zusammenarbeit in Projekten nützlich ist. Zeitgleiches, kollaboratives Arbeiten an Textdateien jeglicher Art (Code, Tabellen, etc.) auf mehreren Rechnern und das Nachvollziehbarmachen jeder Änderung (inkl. Eruierung wer was wann geändert hat), machen Git so erfolgreich. Um ein Git Repository im Web öffentlich zu machen, muss Git auf einem Webserver installiert sein. Eine andere Möglichkeit ist die Nutzung einer Plattform, wie GitHub eine ist. 

## Übung
Als Übung sollten wir uns mittels Teilgruppensitzungen in Webex austauschen können und den Link zu unserem Lerntagebuch ergänzen. Bei mir hat leider bereits das Beitreten in eine Teilgruppensitzung nicht funktioniert. Ich nutze die Webex-App, da dies von der FHGR empfohlen wurde. Die meisten von meiner Mitstudent’innen nutzen die Browser-Version und hatten keine Probleme. Da mich das Einloggen in den VPN der FHGR aber so oder so immer vom Internet trennt, funktionierte wenigstens die Teilgruppensitzung nach einem erneuten Einwählen in Webex. Danke lieber Neustart-Trick 77. Glücklicherweise habe ich noch einen zweiten Rechner, bei dem die Verbindung nicht immer gekappt wird alsbald ich den VPN ins Churer Rechnerzentrum lege. Die Zeit für die Übung inkl. Pause habe ich trotzdem mit Fehlersuchen verbracht und war deshalb etwas entnervt. Am Ende der technischen Strapazen habe ich auch glatt vergessen, was Inhalt der eigentlichen Übung war. Dies habe ich dann beim Lerntagebuch von [Lea Bächli](https://leabaechli.github.io/bain/lektion2/) nachgelesen (ein Hoch auf die Leaschen Ausführungen ;)). Also ich hätte das offizielle Dokument mit dem Link zum Lerntagebuch ergänzen sollen. Dies mittels "fork", "clone", "commit" und "pull request". Hier der Konjunktiv, da dies glücklicherweise der Dozent für mich erledigt hat. Ich habe dann noch [recherchiert](https://www.dev-insider.de/was-ist-ein-fork-a-745969/) und immerhin gelernt was Fork, Branch und merge bedeutet, yay!
+ Fork: (Gabelung, Abspaltung) Von einem Ursprungsprojekt spaltet sich ein neues Projekt ab, indem der quelloffene Code kopiert, das Projekt umbenennt und unabhängig vom eigentlichen „Mutterprojekt“ weiterentwickelt und verändert wird.
+ Branch: Funktioniert vom Prinzip her gleich, jedoch wird die „Abzweigung“ oftmals wieder mit dem Hauptentwicklungszweig zusammengeführt und bleibt ein Teil des Projekts. „Ein Branch trägt also zur Weiterentwicklung des ursprünglichen Projekts bei, während ein Fork ein gänzlich neues Projekt beginnt.“
+ Merge: bedeutet verschmelzen, zusammenführen – also geforkte/gegabelte Seiten wieder zusammenführen und so separate Änderungen kombinieren können. 

## Funktion und Aufbau von Bibliothekssystemen Teil 1 – MARC21 & Dublin Core
MARC21 und Dublin Core sind international verbreitete Metadatenstandards, denen ich bereits in anderen Modulen in der Theorie begegnet bin. Auch das Bibliothekssystem Koha, welches wir später noch kennen lernen, und viele andere grossen Bibliothekssoftware basieren auf MARC21 oder unterstützen es zumindest als Austauschformat. Der von uns vorgenommene Vergleich der beiden Metadatenstandards hat ergeben, dass 
+ MARC21 von vielen Kontrollfeldern und Zahlencodes lebt, die es zu verstehen gilt
+ Mit MARC21 werden hingegen auch mehr Informationen geliefert als bei Dublin Core (DC)
+ In DC sind aussagekräftigere Namespaces (und nicht Codes) zu finden,
+ das ganze kommt schlanker daher und wirkt darum auch übersichtlicher und ist besser von Menschen lesbar

Fazit: MARC21 ist zwar mühsam, es lohnt sich aber wegen der Vermeidung von Informationsverlust (da mehr Informationen ausgeliefert werden) damit zu arbeiten.

## Koha
Koha war ja bereits auf der Modulübersicht zu sehen. Es handelt sich um ein weltweites Open Source Projekt und ist eher als Bibliotheksmanagement-System und nicht als Katalog-Software zu verstehen, respektive nutzen. Die Installation verlief wegen des sehr detaillierten [Tutorials von Stephan Tetzel](https://zefanjas.de/wie-man-koha-installiert-und-fuer-schulen-einrichtet-teil-1/) gut. Weiteres ist darüber im nächsten Post zu lesen...
