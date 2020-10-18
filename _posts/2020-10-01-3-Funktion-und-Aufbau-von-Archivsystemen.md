---
title: "3 Funktion und Aufbau von Archivsystemen"
date: 2020-10-02
---
Kohala in the house

Bevor es an die Lehrinhalte geht hier vorab noch einige relevante Kommentare und Hinweise seitens der Dozierenden…

### … GitHöbb und Gitläbb
Während der letzten Vorlesung kamen wir auf GitHub und GitLab zu sprechen. Ich habe mich da nur ein wenig über den Grundgedanken von Git, respektive GitHub, welches ja für das vorliegende Lerntagebuch Anwendung findet, informiert. Nun sind die Unterschiede in der dritten Vorlesung nochmals aufgegriffen worden, weshalb ich für mich eine Aufstellung einiger Anhaltspunkte gemacht habe:

**GitHub**
+ lebt von einer enorm hohen Nutzerzahl, wurde von Microsoft aufgekauft,
+ hat etwas mehr Beschränkungen bei der kostenlosen Version (bspw. Zulassung von nur 3 Entwicklern in einem privaten Repository) und
+ ist auf einem Webserver installiert.

**GitLab**
+ ist noch eigenständig,
+ ermöglicht kostenlos das Hosting des eigenen Servers (läuft lokal),
+ hat eine etwas übersichtlichere Benutzeroberfläche und
+ die Skalierung des User Interfaces lässt auch eine benutzerfreundliche Ansicht auf mobilen Endgeräten zu.

Sonst noch gut zu wissen: 
+[Zitat:](https://www.ionos.de/digitalguide/websites/web-entwicklung/gitlab-vs-github/) von einem Artikel von IONOS (Hosting-Unternehmen) „Da GitHub und GitLab beide auf Git basieren, ist eine Migration von einer Plattform auf die andere ohne größere Probleme möglich.“   
+ Auf GitHub sowie auf GitLab findet sich Open Source Software – aber nur GitLab ist selbst Open Source (in der Community Edition)

### … Namespaces
Diese sind jeweils im „Wurzelelement“ in der XML-Datei zuhause und dienen der Unterscheidung von gleichlautenden Elementnamen, die im selben Dokument mehrmals verwendet werden. Normalerweise handelt es sich bei dem Namespace um eine URI wie z.B. http://www.w3.org/1999/xhtml. Um nicht immer die ganze URI ausschreiben zu müssen, kann ein Platzhalter für die URI verwendet werden. Dieser kann mittels einem Kürzel abgekürzt und so gekennzeichnet werden. Das Kürzel kann von Dokument zu Dokument variieren, der Namespace hingegen nicht – dieser muss für ein XML-Format gleich bleiben. Die Metapher, dass Namespaces wie die Vorwahl einer Telefonnummer funktionieren, finde ich sehr passend. Untenstehend das Beispiel aus der Vorlesung um dies noch zu veranschaulichen:
> Dublin Core-Beispiel dc:title:
>
> Namespace: http://purl.org/dc/elements/1.1/
>
> Namespace-Kürzel: dc
>
> Elementname: title
>
> Qualifizierter Elementname: dc:title


## Teil 2 von Koha(la)
(Kohala, deshalb weil mich gerade Verniedlichung etwas freundlicher gegenüber Informatik stimmt) 

Die Installation hat, wie bereits im vorherigen Blogbeitrag beschrieben, einwandfrei funktioniert. Hurray! Ich war danach wohl etwas übereifrig, denn ich habe die Übungen, die während der heutigen Vorlesung in Teilgruppensitzungen gelöst werden sollten, bereits gemacht. Dabei bin ich jedoch über die Suche im NEBIS-Katalog gestoplert, die keine Ergebnisse ausgeben wollte. Die Erklärung dazu folgt…

Als erste Übung galt es einen vereinfachten Bibliotheksworkflow zu durchleben. Es sollte ein Buch erfasst und ein Benutzer angelegt werden, der dann an der „Theke“ eben jenes Buch ausleihen und ohne es gelesen zu haben wieder zurückgeben will (?! ;)). Das habe ich sowohl in meinem übermässig starken Flow bereits alleine als auch mit meiner Gruppe dann während der Vorlesung gemeinsam gemacht. Die Koha-Benutzeroberfläche empfinde ich als sehr übersichtlich und die Bedienung ist sogar für mich als Nicht-Bibliotheks-Tier sehr intuitiv. Nachstehend einige unserer im Plenum gesammelten Notizen und Anmerkungen zu diesem Mini-workflow:

+ Medientyp als wichtiges Merkmal, da bspw. die Ausleihkonditionen davon abhängen können
+ Wenn ein Titel per Suchfeld gesucht wird, ist da der exakte Titel einzugeben, ansonsten wird es nicht gefunden. Also wenn „Harry Potter“ gesucht ist, reicht „Harry“ nicht. Der Discovery-Teil von Koha ist also nicht erste Sahne, weshalb es in der Praxis oft mit anderen Discovery-Systemen (wie VuFind, das wir dann noch später behandeln, eines ist) verwendet wird um dieses Problem zu entschärfen.
+ Bei der Bucherfassung ist etwas Konzentration gefordert, da der Standard MARC21 bekanntlich etwas unübersichtlich ist – also Augen auf bei der Dateneingabe und all den Feldern.. Da ist die Schnellaufnahme zu empfehlen, da die etwas abgespeckt und einfach zu überblicken ist.

Die zweite Übung umfasste einen Datenimport. Wir spielten ein Beispiel durch, bei dem es um eine halbautomatische Erfassung mittels einer Schnittstelle ging. So muss nicht selbst katalogisiert werden, sondern das Katalogisat wird über die Schnittstelle in den eigenen Katalog „kopiert“.
+ Die hier verwendete Z.39.50 Schnittstelle ist relativ alt und wird hauptsächlich für das Durchführen einer Art Metasuche genutzt – ist jedoch eher für einzelne Datenabfragen geeignet (wieso dies so ist, ist Thema in einer späteren Vorlesung).
+ Für den Datenimport muss ein Server eingerichtet werden. Als ich die Übung vorgängig machte, war da noch der NEBIS-Katalog aufgeführt. Der Portzugriff von meiner virtuellen Maschine aus wurde aber vom Netzwerk der FHGR aus Sicherheitsgründen gesperrt, sodass ich nicht auf den Server zugreifen konnte – was auch die Erklärung für meine erfolglose Suche ist :)

Dann noch ein Datenexport, der über die Schnittstelle OAI-PMH, was so viel wie *Open Archives Initiative Protocol for Metadata Harvesting* bedeutet. Diese Schnittstelle erlaubt es, dass einmalig der gesamte Datensatz heruntergeladen und danach jeweils die Änderungen in regelmässigen Abständen und völlig automatisiert abgerufen werden können. Aber auch dies wird dann in einer anderen Vorlesung noch vertieft behandelt…

Zurück zur Übung, die im Aktivieren der OAI-PMH-Schnittstelle in Koha und dem Überprüfen, ob die von uns erstellen Datensätze so abrufbar sind (Spoiler: ja, waren sie), bestand. Haupterkenntnis daraus: Koha macht intern alles mit MARC21  aber über die Schnittstelle können die von uns katalogisierten Medien in verschiedenen Formaten angezeigt werden (DC, MARC21, MARCXML)

## Marktüberblick Bibliothekssysteme
Da ich schon viel getippt, gelesen, geübt und gelernt habe, der Überblick in der Vorlesung aus zeitlichen Gründen eher kurz ausfiel und ich die verschiedenen Bibliothekssysteme nicht per se mit eigenen praktischen Erfahrungen verbinden kann, lebt der Marktüberblick Bibliothekssysteme nicht von Ausführlichkeit:
+ [Hier](https://americanlibrariesmagazine.org/wp-content/uploads/2020/04/charts-for-2020-Library-Systems-Report.pdf) die von Marshall Breeding veröffentlichte Statistik-zusammenfassende Tabelle über Bibliothekssysteme, die internationale Entwicklungen erahnen lässt.
+ Swiss Library Service Plattform (kurz SLSP) als kommender Ersatz von Alma
+ FOLIO ist die grösste Open-Source-Alternative, die noch in der Entwicklung steckt
+ Vergleich Alma und Koha: da will ich mich noch etwas einlesen und werde spätestens im hoffentlich etwas ruhigeren Januar noch ergänzen :snowflake:

Diese manuellen Bedienungen schätze ich als Nicht-Bibliotheks-Mensch sehr. Und gleich als Überleitung zur nächsten Vorlesung: die Installation von ArchivesSpace 2.8.0. hat super funktioniert und ist abgeschlossen. JUUHU!

