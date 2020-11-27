---
title: "6 Metadaten modellieren und Schnittstellen nutzen Teil 1"
date: 2020-10-30
---
SRU, OAI-PMH, Z39.50 & XSLT und Crosswalks. Aha. Okay. Also, hää? 

Tag Nr. 6 steht im Zeichen des Übertragens und Konvertierens. Laut Titel und Modulbeschreibung gar der Metadatenmodellierung – wir arbeiten aber mit XSLT und MarcEdit und wenden somit keine Programmiersprache an (was mir auch recht ist ;)). Aber der Reihe nach:
Die neue Modulübersicht zeigt, dass es jetzt mittels OAI-PMH-Schnittstelle(n) ums Herunterladen der Metadaten aus den verschiedenen Systemen geht: Aus Koha werden die Daten im Format MARC21-XML, aus ArchivesSpace in EAD und aus DSpace in Dublin Core ‚geharvestet‘, was so viel wie ernten oder abgrasen bedeutet. (Da sich metha als OAI Harvester nicht reibungslos einsetzen lässt und etwas „hakelig“ ist, wird in dieser Lehreinheit nun VuFindHarvest eingesetzt). Die verschiedenen Formate sollen daraufhin mit MarcEdit in ein einheitliches Format, nämlich MARC21-XML gebracht werden. Eigentlich könnte bereits mit MarcEdit direkt geharvestet werden. Der Einsatz von mehreren Tools soll aber beim Verständnis der Schritte helfen und aufzeigen was da genau passiert. (By the way: MARCXML ist dasselbe wie MARC21-XML!!!)

![Aktualisierter Modulüberblick](https://pad.gwdg.de/uploads/upload_19a6e70e127583b4c50e24282bf7e3fd.png)

Auch auf dem Schaubild und Thema zukünftiger Lehreinheiten: 
Die Daten sollen als nächstes in ein Discovery-System geladen werden. In unserem Beispiel wäre das Vufind, das mit einer eigenen Software und mit Solr als Basis arbeitet.  Solr wiederum ist ein Suchindex, respektive eine Volltextsuchmaschine, die weit verbreitet eingesetzt wird. Es handelt sich dabei also nicht um eine auf Bibliotheken und Archive spezifizierte sondern um eine Internetstandardtechnologie.


## 3 wichtige Übertragungsprotokolle im Archiv- und Bibliotheksbereich
+ Die Z39.50 Schnittstelle von der Library of Congress: ist die älteste Variante, die aber noch immer genutzt wird und oft mit dem moderneren SRU ergänzt wird. Hierfür ist eine spezielle Software nötig. 
+ SRU (Search/Retrieve via URL): ist ebenfalls von der Library of Congress, wird auch breit angewendet und funktioniert sehr ähnlich wie das Urgestein Z39.50. SRU ist wie Z39.50 gut für Live-Abfragen oder gezielte Datenabrufe mit vielen Parametern
+ Und die bereits bekannte OAI-PMH (Open Archives Initiative Protocol for Metadata Harvesting), die ebenfalls weit verbreitet ist. OAI-PMH ist bei grösseren Datenabzügen und regelmässigen Aktualisierungen stark und kann (wie SRU auch) ohne zusätzliche Software genutzt werden. 

### Metadaten mit VuFindHarvest über OAI-PMH Schnittstelle harvesten
Um diese Übung vollbringen zu können, muss vorerst sichergestellt werden, dass die Endpoints der Systeme, die wir anzapfen wollen, verfügbar sind. Das bedeutet konkret hier so viel wie ArchivesSpace (AS) im Terminal starten (check) und das Tool VuFindHarvest installieren (check). 

Für das eigentliche Harvesting heisst das nun mittels der öffentlichen Schnittstelle OAI-PMH und den nun verfügbaren Endpoints die Metadaten aus Koha, AS und DSpace laden. Dafür ist es wichtig, die Formate richtig zu benamseln – und zwar so: im MarcXML aus Koha, oai_ead für AS und oai_dc für DSpace. Bei DSpace muss ausserdem Set com_10673_1 angegeben werden. Es empfiehlt sich ausserdem die Daten in verschiedenen Ordnern abzulegen. Das sieht dann unter Verwendung des abgeänderten Beispielbefehls so aus:

BILD NOCH EINFÜGEN

### Konvertierung: XSLT Crosswalks mit MarcEdit
Unter Crosswalk versteht man hier in diesem Zusammenhang das Konvertieren von einem Metadatenstandard (bspw. MARC21) in einen anderen (Dublin Core). In einem Crosswalk stehen verschiedene Regeln für die Zuordnung, respektive Veränderung der Elemente und Daten – vergleichbar mit einer Karte, die über eine andere gelegt und so abgeglichen wird (Mapping). Ziel ist es dies verlustfrei tun zu können. Realität ist eher, dass Inhalte und Zusammenhänge den verschiedenen Strukturen der Standards geschuldet, verloren gehen. Crosswalks werden oftmals mit XSLT gemacht, was als eine Programmiersprache für das Transformieren von XML-Dokumenten zu verstehen ist. 

Die Installation von MarcEdit in der Shell funktionierte ebenfalls einwandfrei und das Programm ist nun in meiner virtuellen Maschine im Startmenü zu finden. Bei MarcEdit handelt es sich um eine zwar gratis nutzbare Software, sie ist aber nicht Open Source. Wir arbeiten damit, da sie die für die Arbeit mit MARC21 am meisten genutzte Software ist und beispielsweise für die Datenbearbeitung ausserhalb von Systemen wie Alma oder Aleph Einsatz findet.
Die Übung, bei der MarcEdit angewendet wurde, war etwas demotivierend und holprig.. (Zum Glück funktioniert es in den Teilgruppensitzungen dann doch immer bei jemandem irgendwie ;))

Für mich als Learning: 
+ Bei ArchivesSpace ist ein Zwischenschritt notwendig um vom Format EAD in MARC-XML zu kommen. Es gilt also zuerst die EAD-Daten in MARC und daraus dann MARC-XML zu „machen“.  Dies erklärt dann auch, weshalb in den Metadatenordnern (, die ja eben bestenfalls pro System einzeln angelegt wurden) bei Koha die Datensätze nur 1x vorhanden sind (weil ja keine Konvertierung nötig war, da die Daten bereits in MARC-XML vorliegen), bei DSpace 2x (da sie einmal im ursprünglichen Dublin Core und dann im Zielformat MARC-XML vorliegen) und bei ArchivesSpace schlussendlich 3x vorliegen (da die Metadaten in den Formaten EAD, MARC und MARC-XML vorhanden sind). 

Für die nächste Lehreinheit wird die [Installation von OpenRefine](https://openrefine.org/download.html) und das Durcharbeiten von den [Lehrmaterialien](https://librarycarpentry.org/lc-marcedit/01-introduction/index.html) dazu vorausgesetzt. Das habe ich beides mit einiger Überwindung und Startschwierigkeiten bei der Installation erledigt :)
