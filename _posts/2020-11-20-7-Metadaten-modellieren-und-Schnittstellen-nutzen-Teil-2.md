---
title: "7 Metadaten modellieren und Schnittstellen nutzen Teil 2"
date: 2020-11-20
---
messy data & stressy template

Das neuste Schaubild vom BAIN Modul beinhaltet neu die Erweiterung des Discovery-Systems OpenRefine. Um das sich die 7. Vorlesung und somit auch dieser Blogbeitrag dreht.
![neuster Modulüberblick](https://pad.gwdg.de/uploads/upload_3397b1411b4205df59374eff374e81a8.png)

Doch bevor mit OpenRefine gearbeitet werden kann, gilt es dies natürlich zuerst zu installieren. Das lief nicht per se rund (obwohl es doch sehr einfach klang), weshalb ich kurz auf meine Learnings diesbezüglich eingehe. Der erste, etwas peinliche Punkt: Auf der [Download-Seite](https://openrefine.org/download.html) gilt es selbstverständlich das richtige Kit herunterzuladen. Klingt banal, ist es eigentlich auch – wenn frau dabei nur an die virtuelle Maschine und dessen Betriebssystem, als an Linux, gedacht hätte und nicht wie gewohnt an Windows…*beschämt-zu-Boden-Blick*

Nach dem Download stand ich wie ein Esel vor dem Berg vor folgendem Hinweis:
_"extract, then type ./refine to start. This requires Java to be installed on your computer."_
Ich hatte leider keine Ahnung was mit _"type ./refine"_ gemeint war oder wo ich das genau eingeben sollte. Ich hatte zwar eine solche Datei in meinem Verzeichnis - aber die nächsten Schritte erschlossen sich mir nicht. Ausserdem wusste ich nicht, ob bei unseren virtuellen Maschinen Java installiert ist, respektive wie und wo ich das kontrollieren könnte. Weshalb ich mal [diese Anleitung](https://github.com/OpenRefine/OpenRefine/wiki/Installation-Instructions) von GitHub versucht habe zu befolgen. Da kam ich jedoch auch bald an meine Grenzen. Glücklicherweise wurde all mein Nichtwissen durch die Rückmeldung von Herr Lohmeier beseitigt. In den Ordner, in den OpenRefine entpackt werden soll, mit Rechtsklick „im Terminal öffnen“ wählen, dann _./refine_ eingeben, damit OpenRefine startet und nach ca. 15 Sekunden sollte sich der Browser automatisch öffnen. Falls nicht, kann im Firefox http://localhost:3333 eingeben werden. Et Voilà. Ah, und JAVA haben wir bereits für das Arbeiten mit ArchivesSpace installiert. 
Weiteres Learning: ./ bedeutet soviel wie „in diesem Verzeichnis“ und wird hier verlangt, damit das Terminal weiss, ob die Datei namens 'refine' oder der Befehl ```refine``` gemeint ist. 

### Was ist OpenRefine überhaupt?
OpenRefine ist ein 2010 ins Leben gerufenes Discovery System, das als Desktop-App funktioniert, welches den Webbrowser als grafisches Interface nutzt und sich selbst als _„a power tool for working with messy data“_ beschreibt. OpenRefine ist keine Bibliotheks- oder Archivspezifische Software (wurde aber im Jahr 2020 von sehr vielen Bibliotheken genutzt), sondern ist vielseitig einsetzbar und zählt dementsprechend auch unterschiedliche Anwender’innen und Einsatzbereiche (Semantic Web, Data Science,…). Die Oberfläche ist der einer Tabellenverarbeitungssoftware ähnlich – OpenRefine eignet sich schliesslich auch hervorragend für Daten, die in einfacher tabellarischer Form vorliegen. Komplexe XML-Dateien mit Hierarchien können zwar auch verarbeitet werden, jedoch nur unter Verwendung von zusätzlichen Tools. 

### Was kann OpenRefine (nicht)?
OpenRefine ist geeignet um einen Überblick über Daten zu erhalten, diese zu analysieren, bereinigen (Stichwort Inkonsistenzen beheben), konvertieren und mit weiteren Angaben anzureichern. Wird OpenRefine zusammen mit MarcEdit genutzt, kann es auch für Analyse und Umbau von MARC21 nützlich sein. 
Hier einige AHA-Erlebnisse aus den Lehrmaterialien:
Um Daten zu verändern, kann das Drop-Down-Menü mit verschiedenen Optionen genutzt werden. So werden alle Daten in der angewählten Spalte geändert. Dies ist leider nur für eine einzelne Spalte möglich. Es können also nicht mehrere Spalten auf einmal geändert werden, was ich nicht so praktisch finde, da so einige Klicks und Zwischenschritte nötig sind.
In OpenRefine gibt es einerseits...  
+ die Row-Ansicht: jede Zeile repräsentiert ein einzelnes Record) und 
+ die Records-Ansicht: zu einem bestimmten Record werden alle Zeilen zusammen dargestellt
...die oben links („show as“) gewechselt werden kann. 

Eine der nützlichsten Funktionen in OpenRefine sind Facetten: sie helfen den Überblick zu behalten und die Konsistenz der Daten zu verbessern. In einer Facette können Werte, die in einer Spalte erscheinen, gruppiert werden. So ist das Filtern nach Werten und eine effizientere Bearbeitung mehrerer Datensätze gleichzeitig möglich. Mittels Clustering wiederum ist es möglich, ähnliche aber inkonsistente Daten in einer Spalte zusammenzufassen und diese in bestimmte, dann hoffentlich konsistente Daten zu ändern.

Last but not least: 
GREL (General Refine Expression Language), die Excel-Formeln ähnlich ist, sich aber mehr auf Text denn auf numerische Funktionen konzentriert. In GREL werden zwei Arten von Syntax unterstützt: VALUE.FUNCTION(OPTIONS) oder FUNCTION(VALUE, OPTIONS).

### Von einer CSV-Datei zu einer MARCXML-Datei mit OpenRefine
In der Übung ging es darum eine CSV-Datei in ein MARC-XML Format zu konvertieren – und zwar über den Einsatz von Templating. Es wird also manuell ein Format „geschrieben“, das OpenRefine an sich nicht selbst für den Export kennt. Das Vorgehen ist ähnlich wie bei XSLT Crosswalks, nur dass das “Template” hier direkt bearbeitet werden kann und nicht bereits fest steht, wie beispielsweise bei MarcEdit. In OpenRefine wird aber nicht mit XSLT sondern mit GREL gearbeitet. Untenstehend sind jeweils die Transformationen für die Felder in kursiv in meinen eigenen Worten erklärt.

```
<record>
<leader>     nab a22     uu 4500</leader>
<controlfield tag="001">{{cells['URL'].value.replace('https://doaj.org/article/','').escape('xml')}}</controlfield> 
NOTE: URL wird "zugeschnitten", da der erste Teil hier immer derselbe ist. So wird nur alles nach article/ angezeigt, respektive ausgegeben.
<datafield tag="022" ind1=" " ind2=" ">
    <subfield code="a">{{cells['ISSNs'].value.escape('xml')}}</subfield> 
    NOTE: hier wird nichts verändert und die ISSN wird so ausgegeben = hard codiert
</datafield>
<datafield tag="100" ind1="0" ind2=" ">
    <subfield code="a">{{cells['Authors'].value.split('|')[0].escape('xml')}}</subfield> 
    NOTE: im Feld Autor wird die erste Position (darum eine Null), also der erst genannte Autor von den anderen gesplittet und im Feld 100 eingetragen.
</datafield>
<datafield tag="245" ind1="0" ind2="0">
    <subfield code="a">{{cells["Title"].value.escape('xml')}}</subfield> 
    NOTE: .escape('xml') ersetzt alle Zeichen, die in XML nicht erlaubt sind = schlussendlich alles XML-konform
</datafield>{{
forEach(cells['Authors'].value.split('|').slice(1), v ,' 
<datafield tag="700" ind1="0" ind2=" ">
    <subfield code="a">' + v.escape('xml') + '</subfield>
 NOTE: die restlichen Autoren (ab Position 1) werden hier ins Feld 700 eingetragen (mit slice 1 wird die erste Position wie "ausgeschnitten". Autoren sind durch eine Pipe getrennt.
</datafield>')
}}
</record> 
``` 

Damit überhaupt die richtigen MARC-Felder angepeilt und bearbeitet werden, gilt es die [Feld-Dokumentation der Library of Congress](https://www.loc.gov/marc/bibliographic/) zu nutzen. Hier war ich echt froh, hatte ich in meiner Gruppe eine langjährige Bibliotheksmitarbeiterin, die sich mit all den Codes und Feldern auskannte. Für mich war allein diese Dokumentation etwas überfordernd. 
Learnings: 
-	Hard codiert/hart-kodiert meint, dass keine Platzhalter oder ähnliches vorkommen – der Inhalt wird also einfach übernommen ohne dass daran etwas verändert wird 
-	Alles in geschweiften Klammern ist GREL 

In der nächsten Übung ging es noch um die Ergänzung des Templates. Hier hatten wir als Gruppe jedoch bisschen Schwierigkeiten und Zeitprobleme, da wir am eigenen Leib erfahren haben wie schade es ist, dass die Eingabe im Template-Fenster nicht gespeichert wird, wenn dieses geschlossen wird… Wirklich ärgerlich, wenn kurz nochmal was nachgesehen werden muss und schwups kann nochmals von vorn begonnen werden. 
Mit diesem etwas ernüchterndem Erlebnis war auch die Zeit der Vorlesung um. Die Aufgabe inkl. Zusatzartikel darüber wird bei Gelegenheit noch nachgeholt.
