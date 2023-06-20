# htl_jobboerse_api

HTL Jobbörse API
Allgemeine Hinweise
Alle Aufgaben sollen so umgesetzt werden, dass die Seite nicht neu geladen werden muss!
Achtung: Nur in einer Testumgebung:
Sollte es zu einer Fehlermeldung wie Access to XMLHttpRequest at
'https://jobboerse.htl-braunau.at/htl_job_api.php?cmd=getcpylist' from origin
'null' has been blocked by CORS policy: No 'Access-Control-Allow-Origin'
header is present on the requested resource kommen, muss die Chrome-Extension
Moesif Origin & CORS Changer installiert und aktiviert werden
Alternativ kann auch https://corsproxy.io/ verwendet werden (besser).
API der HTL Jobbörse
Die Jobbörse auf der Website der HTL Braunau kommuniziert über eine API mit dem Backend zur Verwaltung
der Firmen und deren Jobs. Die Daten werden im JSON Format zur Verfügung gestellt: https://jobboerse.htlbraunau.at/htl_job_api.php
Über den GET-Parameter cmd können verschiedene Anfragen gestellt werden.
Anzahl der Unternehmen
?cmd=getcpysize liefert die Anzahl der Firmen in der Datenbank
{
"cmd": "getcpysize",
"size": "771"
}
Auflistung von Unternehmen
?cmd=getcpylist liefert die Liste von Unternehmen (alphabetisch nach Firmenname)
&count=3 schränkt die Anzahl der Unternehmen auf eine bestimmte Zahl ein
&from=3 Offset der Unternehmen
&maxage=100 zeigt nur Unternehmen an, die Jobs eingetragen haben, die nicht älter als
100 Tage sind
Detailansicht eines Unternehmens
?cmd=getcpysingle&company_id=292 liefert die Details eines Unternehmens einer bestimmten
company_id (inklusive Bildpfad für das Logo)
Auslistung der Jobs
?cmd=getlist liefert eine Liste von Jobs (neuere Jobs zuerst)
&maxage=300 schränkt die Liste der Jobs so ein, dass sie maximal 300 Tage alt sein dürfen
&company_id=129 die Jobs eines Unternehmens mit einer bestimmten company_id
&count=3 schränkt die Anzahl der Jobs auf eine bestimmte Zahl ein
&from=3 Offset der Jobs
Detailansicht eines Jobs
?cmd=getsingle&offer_id=2450 liefert die Details eines Jobs mit einer bestimmten offer_id
Aufgabenstellung
1. Unternehmensliste
Erstelle eine Datei index.html , die eine Liste der ersten 10 Unternehmen und deren wichtigsten Daten
anzeigt:
Firmenname
Anschrift
Anzahl der Jobs
Zeige nur Firmen an, die Jobs haben, die nicht älter als 300 Tage sind.
2. Unternehmensliste mit Paginierung
Erweitere die Aufgabe 1 so, dass es einen Button Weiter und Zurück gibt, mit denen die Unternehmen
um jeweils 10 Einträge weiter- und zurück geschalten werden können.
Erweitere die Navigation um eine Anzeige der Seiten:
Zurück 1 2 3 4 Weiter
3. Anzeigen der Informationen eines bestimmten Unternehmens
Erweitere das Beispiel so, dass bei Klick auf ein Unternehmen die Firmendetails inklusive Logo übersichtlich
dargestellt werden.
4. Anzeigen der Jobs eines bestimmten Unternehmens
Erweitere die Aufgabe 3 so, dass unterhalb der Firmeninformationen alle Jobs des Unternehmens in Form
einer Liste angezeigt werden, die nicht älter als 300 Tage sind.
Erstellen einen Button Zur Unternehmensliste , das auf die Darstellung von Aufgabe 2
(Unternehmensliste) umschaltet.
5. Detailansicht eines Jobs
Erweitere die Aufgabe 4 so, dass bei Klick auf einen Job alle Details inklusive Link zum Job-PDF angezeigt
werden.
Erstelle einen Button Alle Jobs des Unternehmens , das wieder die Liste aus Aufgabe 4 des jeweiligen
Unternehmens anzeigt.
Beispielseite
(Die Icons sind nicht notwendig:)
