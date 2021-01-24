---
title: 
9 Suchmaschinen und Discovery-Systeme Teil 2"
date: 2020-12-11
---
Suchmaschinen und Discovery-Systeme Teil 2

Phu, diese Vorlesung hatte es in sich. Irgendwie hatte ich das erste Mal das Gefühl irgendwie abgehängt zu haben und um 16.30 Uhr fühlte ich mich dann komplett verloren um ehrlich zu sein. In diesem Sinne ein Hoch auf die Aufzeichnung (und die zeitnahe Bereitstellung derer)!

Aber erst mal zurück auf Anfang, der ein Nachtrag zu LIDO beinhaltete. 
Für mich von Bedeutung festzuhalten: LIDO lebt zwar von einem etwas spezielleren, ungewohnteren Konzept, ist aber eigentlich einfach ein XML-Format. Das Transformieren/die Übertragung von einer Datei, die im LIDO-Standard (ereignis-zentriert) vorliegt in einen anderen Metadatenstandard (dokumentenzentriert) mittels Crosswalks ist anspruchsvoll und mit Informationsverlusten behaftet aber nicht per se unmöglich. Die Entitäten-Struktur und somit all diese Verbindungseigenschaften gehen verloren, da LIDO einfach auf einem anderen Konzept basiert.

### Funktion von Suchmaschinen am Beispiel von Solr
In der Vorlesung 6 "Metadaten modellieren und Schnittstellen nutzen Teil 1" wurde Solr bereits kurz angesprochen (Stichworte Suchindex/Volltextsuchmaschine, nicht auf Bibliotheken und Archive spezifiziert, (neben Elasticsearch) Internetstandardtechnologie, Basis für VuFind).

Da die heutige Sitzung im Zeichen des Imports steht: Es empfiehlt sich vor dem eigentlichen importieren von Daten ein Schema festzulegen, das definiert welche Felder und darin dann welche Datentypen akzeptiert werden wollen. Bspw. wird so möglich für das Feld 'Datum' (das z.B. im ISO-Standardformat erfasst werden muss) eine Suchanfrage mit Zeiträumen anstellen zu können. Das würde nicht funktionieren, wenn diese Information als Text gespeichert wäre.

### Kurzer Exkurs zur Frage „Was ist der Unterschied zwischen Suchindex und Datenbank?“
Grundsätzlich unterscheiden sich diese beiden Systeme stark in ihrer Struktur wie die Daten darin vorliegen und gespeichert sind. Für die Gegenüberstellung wird hier als Beispiel Solr als Suchindex und MySQL als Datenbank hinzugezogen. 
In Solr steht ein Dokument wie für sich alleine und ist nicht in ein Beziehungsgeflecht eingebunden. Ausserdem bietet Solr keine persistente Speicherung und funktioniert mittels lexikalischer Suche. Es bietet die Möglichkeit die Verben automatisch auf ihre Grundform zu reduzieren und so auch zu suchen. Hingegen wird keinerlei Konsistenzprüfung durchgeführt. Des Weiteren sind die Daten in Solr statisch. Wenn also ein Dokument aktualisiert werden will, indexiert Solr eine Kopie davon, in welcher dann die Änderungen gespeichert sind. Der ursprüngliche Datensatz wird zwar bei einer Suche nicht als Ergebnis ausgegeben, existiert jedoch immer noch.  
In MySQL sind relationale Datensätze zu finden, die aufeinander verweisen und somit Abfragen möglich sind, die diese Relationen berücksichtigen. Bei der Suche sind boolsche Operatoren erlaubt und es wird grundsätzlich einfach ein Glyphenvergleich gemacht. D.h. MySQL gleicht den Suchterm 1:1 mit den vorliegenden Datensätzen ab und verspricht Transaktionssicherheit. Grosser Unterschied: Die Datensätze sind nicht statisch, sondern veränderlich. 
Datenbanken legen den Schwerpunkt auf konsistente, dauerhaft zu speichernde Daten. Diese „storage-Funktion“ wird auch mit C(reat)R(ead)U(pdate)D(elete) abgekürzt. Ein Suchindex wie Solr hingegen ist für Retrieval und die Suche in grossen Datenbeständen geeignet. Apropos Retrieval…

Der rasche Blick in die VuFind-Dokumentation, die Erklärungen der VuFind-Felder bietet, liess mich gekoppelt mit der kleinen Übung (Suche in VuFind vs. Suche in Solr) die Funktionsweise eines Rankings besser verstehen. So sind im Solr Index Schema mehrere unterschiedliche Felder für das Datum 'Titel' beschrieben. Der Titel kommt normalerweise aus dem MARC-Feld 245a. Die weiteren Titel-Felder dienen schlussendlich einer besseren Ranking-Funktion. Ist bspw. der Suchterm im Haupttitel, wird dies stärker gewichtet als wenn der im Feld 'alternate titel' auftaucht. Ausserdem resultiert bei einer exakten Übereinstimmung von Suchterm und Titel ein höheres Ranking, als wenn nur ein Teil des Titels übereinstimmt. Die Übung verlangte eine Suche in VuFind und dieselbe Suche in Solr (plus da die Logdatei im Terminal ansehen). Die Umsetzung in der Gruppe ging etwas schleppend voran, denn die Darstellung der Logdatei auf dem geteilten Bildschirm einer Kommilitonin war munzig plus nährte das technische Erscheinungsbild meine Überforderung. Erst die Tatsache, dass darin die Multiplikationsfaktoren für die Berechnung der Gewichtung ersichtlich sind, holte mich etwas aus meinem Schockzustand ;) 

![Ranking]({{site.baseurl}}/assets/9_ranking.png)

## Die verheerende Datenintegration
Ziel der (mich aus der Bahn werfenden) Übung war es, die mit MarcEdit und OpenRefine konvertierten (und somit alle in MARCXML vorliegenden) Daten aus verschiedenen Systemen (Koha, ArchivesSpace, DSpace und DOAJ) in VuFind zu importieren. Um die Ergebnisse besser zu sehen, sollten wir die Testdaten mit folgenden (einzeln einzugebenden) Befehlen löschen: 
```
/usr/local/vufind/solr.sh stop
rm -rf $VUFIND_HOME/solr/vufind/biblio/index $VUFIND_HOME/solr/vufind/biblio/spell*
/usr/local/vufind/solr.sh start
```
Leider hat dies bei mir nicht funktioniert und die leere Suchanfrage in VuFind gab immer noch 250 Datensätze aus. Und nach erneutem Versuchen endeten jegliche Suchanfragen in einer Error-Meldung. Mit Hilfe des Befehls ```ls –al /usr/local/vufind``` wurde wenigstens sichtbar, dass bei der Installation von VuFind etwas schief lief. Vielleicht wäre die Lösung des Problems naheliegend und total simpel, jedoch habe ich entschieden es dabei zu belassen. Die Teilgruppensitzung fangen ja solche Schwierigkeiten zumindest für die Zeit während der Vorlesung auf. Apropos: Die Aufgabe des Datenimports hat mich und meine Gruppe etwas überfordert, die Aufzeichnung konnte das aber beheben (ich verstehe jetzt alle notwendigen Schritte, die Probleme und Lösungsvorschläge – ich werde hier jedoch nicht weiter darauf eingehen). 

## Wie sieht ein perfekter Katalog aus?
Die Gruppendiskussion darüber brachte folgende Aspekte hervor: 
+ Ein perfekter Katalog ist illusorisch, denn dieser ist abhängig vom Fachgebiet, den Nutzer’innen, den Ressourcen, dem Know-How,… 
+ Nützlich wären Funktionen wie Merkliste, erweiterte Suche, Ausgabe der Daten in verschiedene Metadatenstandards, keine Dubletten aber auch kein Informationsverlust 
Da wäre es sicherlich spannend gewesen die Meinung der Dozierenden dazu zu hören - oder vielleicht hat mir hier einfach bisschen eine Zusammenfassung dieser kurzen Diskussion gefehlt.

Meine Gruppe hat zudem die Frage nach der Relevanz beschäftigt. Wie kommt diese jeweils konkret zustande? Und wie hilfreich wäre es diese Relevanzbeurteilung der Treffer für die Nutzenden (bspw. durch Sterne) sichtbar zu machen? (Ich persönlich empfand das bei der Recherche in der Buchhandlung beim Bibliografien als sehr gewinnbringend – vor allem bei viiiielen Treffern. Aber auch hier spielt die Erwartungshaltung an die Suche und der/die Endnutzende eine grosse Rolle.) 

Moral der Geschichte: 
Thema Relevanz hats mir angetan (weil im Fach Information Retrieval viel zu theoretisch und mit meinem Alltag verknüpfbar), mein VuFind und ich sind auf Kriegsfuss und den Marktüberblick Discovery-Systeme verschiebe ich auf den nächsten Beitrag. 
