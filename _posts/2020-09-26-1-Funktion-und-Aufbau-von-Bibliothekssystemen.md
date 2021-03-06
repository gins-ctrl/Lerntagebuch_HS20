---
title: "1 Funktion und Aufbau von Bibliothekssystemen 1/2"
date: 2020-09-26
---
Shell we start?

## Einführung
Da ich die vergangenen Semesterferien 80% als Praktikantin mit Arbeiten verbrachte (und ich einfach nicht wahrhaben wollte, dass das neue Semester bereits wieder losgeht) habe ich mich null auf die kommenden Module vorbereitet. So war es auch mit BAIN, das bei meiner Vertiefungsrichtung Archivierung sinnvollerweise zu den Pflichtmodulen zählt. Also sehr dürftiger Einstieg meinerseits – zu unserem Glück nicht auch „dozierenderseits“: Das Modul scheint gut strukturiert, organisiert und mit motivierten und sehr engagierten Dozenten unter einem guten Stern zu stehen. Also, shell we start?

Kurzer Einschub bevors an die Lehrinhalte der ersten Vorlesung geht: _„Für mich und das Modul Bibliotheks- und Archivinformatik-Modul heisst das konkret: meine Blogartikel jeweils möglichst nach der jeweiligen Vorlesung schreiben“_ Regina Eicher, die gute Vorsätze brechende. Wenigstens habe ich ausnahmsweise eine gute Erklärung dafür, denn ich muss nebst anderen Deadlines noch den Praktikumsbericht (fertig) schreiben…
Also erstes Learning: Frau schreibe die Blogartikel ~~möglichst nach~~ direkt nach der jeweiligen Vorlesung. 

## Technische Grundlagen
Die Modulinhalte sind mittels einer CodiMD-Installation einseh-, und von allen, die den entsprechenden Link kennen, auch veränderbar. Da das Modul einerseits ausschliesslich online stattfindet und es andererseits auch Informatikthemen beinhaltet, scheint es mir eine sehr sinnvolle Lösung die Modulinhalte so zu vermitteln und auch gleich eine geeignete Plattform für kollaboratives Arbeiten zu haben. Die Bedienung scheint mir sehr intuitiv zu sein und ganz nebenbei lerne ich noch MarkDown. Auch die gut dokumentierten [Funktionen und Hilfestellungen zu CodiMD ](https://codimd.web.cern.ch/features) stimmen mich sehr optimistisch, dass ich soweit damit zurechtkomme.

![Modulüberblick](https://pad.gwdg.de/uploads/upload_4710561903c2b829c76a62df6232af74.png)

Für mich wichtig: 
+ [Koha](https://koha-community.org/about/): erstes open source Bibliothekssystem an dessen Entwicklung eine weltweite Gemeinschaft arbeitet, 
+ [ArchivesSpace](https://archivesspace.org/about/mission): quelloffene, webbasierte Archiv-Software – sozusagen von Archiven für Archive entwickelt und 
+ [DSpace](https://duraspace.org/dspace/about/): eine quelloffene Software für digitale Repositorys.

Wir sollten also am Ende des Moduls Kenntnisse darüber haben, wie wir über - respektive aus - diesen 3 Repository Software über Schnittstellen die jeweiligen Metadaten zusammenführen und mittels Crosswalks dann am Ende MARC21 erhalten. 
Ich belasse es an dieser Stelle mit dieser rudimentären Beschreibung und erhoffe mir dann am Ende des Kurses die Zusammenhänge zu verstehen und nicht nur Begriffe zu lesen, die ich nicht wirklich zuordnen kann.

## Arbeitsumgebung und die liebe Shell
Daraufhin ging es an die Einrichtung unserer Arbeitsumgebung: verschiedene Übungen und Aufträge können wir auf einer virtuellen Maschine, die wir mittels VPN-Verbindung mit dem Rechnerzentrum der FHGR zur Verfügung haben, ausführen ohne „etwas kaputt zu machen“ oder unzählige Programme auf unserem eigenen, lokalen Rechner installieren zu müssen. Dies kenne ich bereits aus vorherigen Modulen. Der verwendete Webserver läuft auf Linux, respektive Ubuntu (Version 20.04 LTS  (wichtig für Recherchen, da es viele verschiedene Versionen gibt)) – weshalb ich mich wieder mit einer wunderschönen (Ironie!) grafischen Oberfläche, der Kommandozeile, auseinandersetzen „darf“. Dank der guten Anleitung in den Unterlagen, klappte die Installation der Programme etc. auf Anhieb. Das Durcharbeiten der beiden Kapitel der „Library Carpentry Lesson zur Unix Shell“ (Themen: Navigieren und mit Dateien und Verzeichnissen in der Shell arbeiten) waren für mich elementarer Bestandteil um da wieder etwas Shell-Luft schnuppern zu können. Das Durcharbeiten des Tutorials hat sogar noch bisschen Spass gemacht – und meine Notizen und Screenshots, die ich, weise wie ich bereits geworden bin, dabei gemacht habe, helfen mir auch später mich einzudenken und die Shell und die Systematik zu verstehen. Befehle wie pwd, cd, ls oder mkdir sind mir von ARIS noch geläufig. Hingegen neu (weil noch nie gehört oder gut verdrängt) waren mir cat, head, tail oder auch less. Angewöhnen sollte ich mir unbedingt die Arbeit mit den Pfeiltasten, um bereits verwendete Befehle wieder aufzurufen im Verlauf. Ebenfalls sehr wichtig: Copy-Paste funktioniert nicht in allen Terminals mit den gewohnten Tastenkombinationen CTRL + C, resp. V, sondern es Bedarf zusätzlich dem Einsatz der Shift-Taste. Es gibt da noch mehrere Möglichkeiten, wie Rechtsklick, oder die Tastenkombination STRG + SHIFT + C, resp. V oder beim "pasten" SHIFT + EINFÜGEN/INSERT. 

## Blog mit GitHub Pages
Das „Aufsetzen“ des vorliegenden Blogs hat mich ziemlich viel Zeit und Nerven gekostet, obwohl uns an sich eine gute Anleitung von den Dozierenden zur Verfügung stand. Im Nachhinein kann ich hier nur sagen: warten lohnt sich ;) denn ich habe mich wie verrückt auf die Suche nach den möglichen Fehlern gemacht um herauszufinden warum meine Posts nicht angezeigt werden und der Blog so überhaupt nicht aussieht wie er sollte. Verrücktsein hat sich dann nicht gelohnt, denn nach ca. 30 Minuten war einfach alles an der gewünschten Stelle. Zuhören hätte sich eher gelohnt, denn später kam mir in den Sinn, dass eine kurze zeitliche Verzögerung in der Vorlesung bereits angekündigt wurde… 
