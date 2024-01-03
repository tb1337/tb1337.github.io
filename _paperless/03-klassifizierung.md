---
title: "Klassifizierung"
excerpt: "Dokumente klassifizieren, um sie später mit Leichtigkeit wiederzufinden."
permalink: /paperless/klassifizierung/
header:
  image: /assets/images/paperless/03-header.jpg
  caption: >
    Foto von <a href="https://unsplash.com/de/@qwitka?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Maksym Kaharlytskyi</a> auf <a href="https://unsplash.com/de/fotos/aktenschrank-Q9y3LRuuxmg?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
toc: true
toc_sticky: true
---

Ich gehe davon aus, dass du an dieser Stelle bereits eine laufende *paperless-ngx*-Installation zur Verfügung hast. Falls nicht, ist das gar nicht tragisch: ich möchte die folgenden Themen auf dieser Seite etwas mehr veranschaulichen. Nun drücke ich dem Ganzen auch meinen persönlichen Stempel auf, denn ich spreche von *meinen* Erfahrungen - von denen ich hoffe, dass sie dich zumindest einmal inspirieren werden.

## Was macht *paperless-ngx*?

Auf der ersten [Seite](/paperless/einfuehrung/) sprach ich davon, dass *paperless-ngx* ein DMS ist. Toll, man kann damit also seine Dokumente organisieren. Das können Leitz-Ordner auch :satisfied:. Ja, die Arbeit eines DMS beginnt eben mit dem Lagern von Dokumenten, genau wie bei einem Leitz-Ordner.

Das Tolle an einem DMS aber ist, dass es Dokumente eben nicht nur lagern kann. Es kann unter anderem:

* Dokumente klassifizieren (einen Typ festlegen).
* Dokumente nach Absendern ordnen.
* Dokumente markieren (z.B. zur späteren Weiterarbeit).
* Metainformationen bereitstellen.
* Dokumente automatisiert abholen (z.B. vom Scanner, aus Emails).
* Dir sogar mitteilen, in welchem Leitz-Ordner ein Dokument physisch abgeheftet wurde.
* und vieles mehr...

Nun wird es sicher auch Leitz-Ordner-Profis geben, die mit Post-Its und anderen kleinen Helfern ähnliche Features analog umsetzen können und sich daher fragen: wozu brauche ich ein DMS? Ich bin leider nicht so ein Profi und ich arbeite einfach viel lieber digital :sweat_smile:. So habe ich meinen Papierkram nämlich auch außer Haus jederzeit griffbereit in meiner Hosentasche.

**Und so sieht *paperless-ngx* aus, wenn man es zum ersten Mal öffnet:**

[![Bild: Paperless beim ersten Start]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-overview.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-overview.png)

## Klassifizierung

Das Klassifizieren von Dokumenten deutet eigentlich an, dass man einem Dokument einen Typ zuweist. Ich verstehe darunter allerdings den Gesamtprozess des Anheftens von Metainformationen an ein Dokument. Wenn ich also von Klassifizierung spreche, meine ich nicht nur das Zuweisen eines Dokumenttyps, sondern die Zuweisung aller Metainformationen an ein Dokument: Dokumenttyp, Korrespondent, Speicherpfad, Tags etc.

[![Bild: Klassifizierung von Dokumenten]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-classification.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-classification.png)

Diese Begrifflichkeiten wirst du nun sehr oft lesen, ich möchte nun näher auf sie eingehen. Auch lohnt sich ein Blick in die offizielle [Dokumentation](https://docs.paperless-ngx.com/usage/).

### Was ist ein Dokument?

Ich spreche immer von Dokumenten, doch bislang habe ich nicht erläutert, was genau ich damit meine. Du wirst dir vermutlich denken, dass das ja klar ist. Im Beruf habe ich jedoch beim Digitalisieren der Posteingangsstrecke gemerkt, dass das eben nicht immer so eindeutig ist. Es wird also Zeit für ein bisschen Theorie :see_no_evil:.

#### Fallbeispiel

Nehmen wir einen praktischen Fall: dich erreicht **ein** Brief :envelope:. Enthalten sind **vier** Blatt Papier :page_with_curl:, die wiederum doppelseitig bedruckt sind; die gesamte Sendung besteht also aus **acht** bedruckten Seiten :page_facing_up:. Aus dem Inhalt geht hervor, dass es sich bei sechs Seiten um **zwei** unterschiedliche Rechnungen (A und B) :paperclips: handelt. Die verbliebenen zwei Seiten sind eine Aufstellung von Leistungspositionen, die als Anlage :bar_chart: zu Rechnung B mitgekommen sind.

#### Analyse

Wie du siehst, nimmt das Thema schnell ungeahnte Komplexität an. Was wäre für dich in diesem Beispiel denn nun **ein** Dokument? Aus meiner Sicht gibt es zu dieser Fragestellung erstmal mehrere Antwortmöglichkeiten:

1. Da alle Seiten in einem Brief verpackt waren, handelt es sich um **ein** Dokument (= Sendung).
2. Hier liegen **zwei** Dokumente vor, **eine** Rechnung A und **eine** weitere Rechnung B nebst Anlage.
3. Es handelt sich um **drei** Dokumente, **zwei** Rechnungen A + B und **eine** Anlage.

Alle drei Möglichkeiten sind gangbare Wege, soviel sei dazu gesagt. Jede Person definiert ihr eigenes Ablagesystem und muss es natürlich so strukturieren, dass sie selbst im Bedarfsfall die korrekten Dokumente wiederfinden kann. Ich persönlich halte allerdings **Antwort 2** für die effizienteste Vorgehensweise und setze dies auch selbst so um. Doch warum?

#### Schlussfolgerung

Die erstmal schnellste Methode ist natürlich **Antwort 1**: ich packe den Brief aus, scanne ihn ein und lasse ihn in *paperless-ngx* verschwinden. Das funktioniert sehr gut bis zu dem Tag, an dem ich genau diese eine Rechnung B nebst Anlage wiederfinden muss. Durch die Kapselung mehrerer Rechnungen in ein Dokument wird die Suche nämlich unnötig erschwert. Die Zeit, die ich bei der Klassifizierung also eingespart habe, geht bei der längeren Suche locker dreifach wieder verloren.

Anders verhält es sich mit **Antwort 3**: hier stecke ich sehr viel Zeit in die Klassifizierung von drei Dokumenten und habe dann alles sauber abgelegt. Doch welchen Vorteil habe ich davon, die Anlage von ihrer eigentlichen Rechnung B zu trennen? Wenn der Tag kommt, an dem ich Rechnung B und ihre passende Anlage wiederfinden muss, suche ich nach zwei Dokumenten im System[^1]. Schlimmstenfalls enthält die Rechnung keinen Hinweis darauf, dass ihr eine Anlage beigefügt worden ist, und das hätte die zusätzliche negative Auswirkung, dass wir eine lose Anlage im DMS herumschwirren haben.

[^1]: Seit *paperless-ngx* v2.2.0 gibt es logische Dokumentenverknüpfungen, womit sich Dokumente verbinden lassen. Dies hat Stand 02.01.2024 jedoch weder eine Auswirkung auf die Qualität der Suchergebnisse, noch eine Visualisierung im UI.

Aus diesen Gründen halte ich **Antwort 2** für den effizientesten Weg. Die Sendung wird in ihre zwei Rechnungen A + B aufgegleist und die Anlage zur Rechnung B gepackt. So entstehen in *paperless-ngx* zwei Dokumente mit ihrer jeweils korrekten Klassifizierung. Darüber hinaus ist die Anlage immer direkt mit ihrer Rechnung zusammen auffindbar. Und falls ich einmal nur nach der Anlage suchen muss, kann ich mir sicher sein, dass mich niemand nach der *Rechnungsanlage von Datum XY*, sondern immer nach einer Anlage im Kontext einer bestimmten Rechnung fragen wird.

[![Bild: Dokumenten-Ansicht]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-documents.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-documents.png)

**Info:** Nach all der Theorie wirst du dich bei genauem Hinsehen nun fragen, warum auf dem Bild Rechnungen und Einzelverbindungsnachewise voneinander getrennt sind. Ich halte einen EVN schlichtweg nicht für eine Rechnungsanlage[^2], sondern ein für sich allein stehendes Dokument. Aus der Rechnung ergibt sich für mich auch ohne einen EVN eine Aufgabe: nämlich der Akt der Bezahlung eben dieser.
{:  .notice--info}

[^2]: Hierüber kann man streiten, ich änderte zu dem Thema auch selbst andauernd meine Meinung. Letztendlich habe ich mich aber festgelegt und behalte es so bei.

Hast du andere Erfahrungen gemacht? Lass es mich wissen :grin:.

### Korrespondent

Unter Korrespondenten versteht man den Absender von Dokumenten, die dich erreichen. In der anderen Richtung sind Korrespondenten die Empfänger von Dokumenten, die du verschickst.

![Bild: Korrespondenten]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-correspondent.png)

In *paperless-ngx* können wir uns Korrespondenten als virtuelle Schubladen vorstellen, in denen alle Dokumente einer Person oder Firma abgelegt sind. Mit nur einem Klick finden wir alle Dokumente, die einem bestimmten Korrespondenten zugeordnet sind.

### Dokumenttyp

Mit dem Dokumenttyp legst du fest, um was für eine Art Dokument es sich handelt. Hier kann man beliebig granular werden, doch Simplizität schlägt aus meiner Sicht Komplexität. Die Klassifizierung von Dokumenten zu einem Dokumenttyp erfolgt nach Regeln, die wir uns selbst ausdenken und auferlegen müssen. Es sollte uns also auf einen Blick klar sein, was für ein Dokument vor uns liegt und welcher Dokumenttyp das sein könnte.

**Warnung:** Ertappst du dich selbst dabei, wie du immer wieder zwischen mehreren Dokumenttypen schwankst, gebe ich dir einen guten Rat: konsolidiere sie. Wenn selbst du dir als Mensch unsicher bist, wie soll dann *paperless-ngx* den korrekten Dokumenttyp automatisiert für dich erkennen?
{:  .notice--warning}

Sehen wir uns alle Dokumente an, die wir im Laufe der Zeit erhalten, kristallisieren sich ein paar Dokumenttypen deutlich heraus.

**In meinem Fall sind das diese hier:**

Dokumenttyp | Beschreibung
:-------- |:--------
Bescheid | Bescheide von Behörden, z.B. Steuerbescheide, Bewilligungen, etc.
Dokument | Abstrakter Typ für Dokumente, die keinem Typ eindeutig zuordbar sind.
Kontoauszug | Der Name ist Programm, egal ob Girokonto, ETF-Sparplan, Depot.
Korrespondenz | Allgemeine Schriftwechsel, auf die eine Antwort folgen soll, z.B. Beschwerde beim Internetanbieter.
Kündigung | Kündigungen und Kündigungsbestätigungen von Verträgen aller Art.
Lohnabrechnung | Hiermit werden alle monatlichen Lohnzettel klassifiziert.
LSt-Bescheinigung | Lohnsteuerbescheinigungen kommen in der Regel 1x im Jahr, sind aber wichtig genug für einen eigenen Typ.
NK-Abrechnung | Lange habe ich Nebenkostenabrechnungen einfach als *Rechnung* klassifiziert, zur schnelleren Auffindbarkeit habe ich aber dann einen eigenen Dokumenttyp erstellt.
Rechnung | Enthält alle Rechnungen, z.B. vom Internetanbieter, Mobilfunk, Käufe mit Garantie, etc.
Spendennachweis | Ich spende jedes Jahr, die Quittungen erhalten diesen Dokumenttyp.
Spesenabrechnung | Beruflich bin ich viel unterwegs und dieser Dokumenttyp enthält die Abrechnungen gegenüber meiner Arbeitgeberin, wie auch ihre Antworten darauf.
SV-Mitteilung | Bestimmt für Sozialversicherungsmitteilungen, An- und Abmeldungen.
Vertrag | Komplexer Dokumenttyp, enthält Verträge aller Art. Auch Versicherungspolicen und Vertragsänderungsmitteilungen.
Zeitnachweis | Lohnabrechnungen und Zeitnachweise klassifiziere ich getrennt voneinander. Enthält auch Zeitnachweise für Freelancer-Tätigkeiten.
Zertifikat | Nachweise über Schulungen, Weiterbildungen und Seminare.
Zeugnis | Dokumenttyp für Schul-, Ausbildungs- und Arbeitszeugnisse.

### Tagging

Die einen lieben sie, die anderen hassen sie, und die übrigen 80% nutzen sie nicht: Tags. Auch ich selbst habe mich lange vor dem Einsatz von Tags gesträubt, weil es Dingen eine Komplexität verleihen kann, die schnell unüberschaubar ist. Denn zu jedem Tag gibt es eine Story: wann nutze ich ihn? Wann muss er wieder entfernt werden? Was sagt er aus? Hier sind uns überhaupt keine Grenzen gesetzt.

Tagging ist prima: bei *paperless-ngx* kann man einem Dokument damit einen Kontext verleihen, oder sogar mehrere. Ähnlich wie bei Korrespondenten kann man Tags wie virtuelle Schubladen verstehen, in denen Dokumente liegen. Sie eignen sich erstklassig, um Dokumenten eine Thematik zuzuweisen, die über viele Korrespondenten und Dokumenttypen verteilt ist (z.B. Kfz) - oder einfach nur als Status Indikator.

[![Bild: Tagging]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-tagging.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-tagging.png)

Damit es jedoch nicht zu komplex wird, beschränke ich mich auf einige wenige, dafür eindeutige Tags.

Tag | Beschreibung
:-------- |:--------
Augang | Das Dokument ist ein Ausgangsdokument, wurde also von mir initiert.
Kfz | Verträgen, Rechnungen, etc. verleihe ich mit diesem Tag einen Kfz-Kontext. So kann ich schnell sämtliche Unterlagen zu meinen Autos wiederfinden.
Neu | Hierbei handelt es sich um meinen Posteingangs-Tag. Alle Dokumente mit diesem Tag haben den Status **neu**.
Problem | Dieser Tag wird von meinen Bots[^3] verwendet, wenn ich an einem Dokument noch etwas nacharbeiten muss. Darauf gehe ich später detailliert ein.
Steuer | Dokumente mit diesem Tag werden von mir für die nächste Steuererklärung benötigt.
Todo | Das sind Dokumente, mit denen ich zu einem späteren Zeitpunkt noch etwas vorhabe, oder bei denen ich noch auf eine Antwort warte.
Wichtig | Extrem wichtige Dokumente, die ich schnell wiederfinden muss, wenn ich sie brauche.

[^3]: Mit der [PyPaperless](https://github.com/tb1337/paperless-api) Python Library habe ich kleinere Workflows erstellt, die meine Klassifizierungs-Regeln überwachen.

### Speicherpfade

*paperless-ngx* bietet noch eine weitere Möglichkeit, Schubladen zu erschaffen. Nicht dass wir davon nicht schon bereits einige hätten :sweat:. In diesem Fall handelt es sich um echte Ordner im Dateisystem, in denen die echten PDF-Dateien dann abgelegt werden, die du im DMS abspeicherst. Das ist natürlich ein reines Kosmetik-Feature und bietet Vorteile für Backups, oder wenn man all seine Dokumente bspw. zusätzlich bei einem Cloud-Anbieter speichern möchte.

[![Bild: Speicherpfade]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-storage-paths.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-storage-paths.png)

Ich nutze zwar die physischen Dateiordner nicht, Speicherpfade stellen für mich allerdings ein zusätzliches Klassifizierungsmerkmal dar. So existiert nicht nur für jedes meiner Autos ein echter Dateiordner mit allen Dokumenten drin, meine Bots[^3] wissen hierdurch sogar, um welches Auto es sich handelt. So spare ich mir für jedes Auto einen eigenen Tag anzulegen, denn viele Speicherpfade sind aus meiner Sicht weniger störend, als viele Tags.

## Erkennungs-Algorithmen

Die Klassifizierung ist der Prozess, bei dem man Dokumenten jeweils Korrespondenten, Dokumenttyp, Tags und ggf. einen Speicherpfad zuweist. Das muss man glücklicherweise nicht jedes Mal komplett per Hand machen, *paperless-ngx* wird mit einigen Erkennungsalgorithmen ausgeliefert. Darüber kannst du [hier](https://docs.paperless-ngx.com/advanced_usage/#matching) mehr lesen. Falls die automatische Erkennung nicht zum gewünschten Ergebnis führt, kann man natürlich selbst den korrekten Wert einstellen. Im Falle der Auto-Erkennung lernt *paperless-ngx* dann von deiner Entscheidung und macht es mit ein bisschen Glück direkt beim nächsten Mal richtig.

[![Bild: Erkennungs-Algorithmen]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-matching-algorithms.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/03-matching-algorithms.png)

Ich nutze die **Auto-Erkennung**, wann immer ich bei einem Klassifizierungsmerkmal genügend Dokumente erwarte; ein Model muss schließlich mit genug Daten trainiert werden. Das kann man auf dem Bild übrigens bei *Rechnungen* erkennen.