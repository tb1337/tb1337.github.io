---
title: "Workflow"
excerpt: "Briefe, Faxe, Emails und digitale Dokumente im Alltag meistern."
permalink: /paperless/workflow/
toc: true
toc_sticky: true
---

Nachdem wir auf den letzten Seiten unser gemeinsames Verständnis zum papierlosen Büro abgeglichen und geschärft haben, wird es Zeit, auf den stinknormalen Alltag zu sprechen zu kommen. Auch *paperless-ngx* wird uns nicht zu Freudensprüngen verleiten, wenn es darum geht, sich um den Papierkram zu kümmern - auch wenn ich diese Illusion gern aufrecht erhalten hätte. Der Unterschied liegt schlicht und ergreifend darin, dass die vierteljährlichen *Ich mache Ablage und räume meine Leitz-Ordner auf*-Sonntage durch ein digitalisiertes Büro einfach wegfallen.

Auch in der offiziellen [Dokumentation](https://docs.paperless-ngx.com/usage/#usage-recommended-workflow) findest du wertvolle Hinweise darauf, wie man *paperless-ngx* nutzen könnte. Du wirst feststellen, dass meine Erläuterungen in einigen Punkten damit übereinstimmen. Nicht etwa weil ich abschreibe, sondern weil die Architektur der Software uns hier einen Weg bereits vorgeebnet hat. Mit welcher Besohlung du diesen Weg gehst, kannst du dir selbst aussuchen - wie bisher auch, sprechen wir nun weiter über mein Schuhwerk.

## Arbeitsablauf

Sehen wir uns einmal den typischen Ablauf mit *paperless-ngx* an, wenn uns im Alltag neue Dokumente erreichen. Hierbei spielt es im Übrigen überhaupt keine Rolle, auf welchem Wege sie das tun; sei es per Post, per Email, als Download aus einer App, oder per Fa... nein, das blöde Wort mit x am Ende ist keine Erwähnung wert :clown_face:.

[![Bild: Ablaufdiagramm]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/04-workflow.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/04-workflow.png)

### Barcodes und ASN[^1]

[^1]: Archive Serial Number, bzw. eindeutige Seriennummer eines Dokuments in deinem Haushalt. Idealerweise fortlaufend.

Dieses Thema spielt bereits beim Scannen eine größere Rolle, weshalb ich an dieser Stelle kurz darauf eingehen möchte. 

**Anm. d. Red.:** Barcodes und ASN sind komplett optional. Du musst das nicht benutzen, wenn du nicht möchtest. Es kann die Handhabung deines papierlosen Büros in einigen Situationen jedoch vereinfachen, weshalb es sich auf jeden Fall lohnt, einen Blick auf das Feature zu werfen.
{:  .notice--primary}

#### Grundsätzliches zu Barcodes

*paperless-ngx* kommt mit einem eingebauten Barcode-Scanner, welcher zwei tolle Funktionen bereitstellt:

1. **Splitting**: solltest du viele Dokumente auf einem Stapel haben und diesen auf einmal einscannen, können anhand von Trennblättern mit Barcode die einzelnen Dokumente erkannt werden.
2. **ASN Erkennung**: Barcodes oder QR Codes können eine ASN[^1] kodiert bekommen, welche von *paperless-ngx* erkannt und an das Dokument angefügt wird.

[Hier](https://docs.paperless-ngx.com/advanced_usage/#barcodes) kannst du etwas über das Barcode-Feature von *paperless-ngx* in der offiziellen Dokumentation nachlesen, und [hier](https://docs.paperless-ngx.com/configuration/#barcodes) alles über ihre Konfiguration.

#### Warum ich mit ASN arbeite

*paperless-ngx* und Leitz-Ordner koexistieren in meinem papierlosen Büro, auch wenn das auf den ersten Blick ein Widerspruch ist. Ich <u>arbeite</u> nur mit den digitalen Abbildern meiner Dokumente, d.h. ich suche und finde sie im DMS, setze Todo-Tags und behalte meinen Posteingang im Blick. Im Leitz-Ordner <u>lagern</u> die Originale, die ich aufbewahren muss oder will. Den fasse ich ansonsten nur an, um weitere Dokumente einzulagern. Dieser Fakt macht für mich den eindeutigen Unterschied.

ASN sind ein kleiner Helfer, um mich bei meinem *dualen System* zu unterstützen. Ich sehe in *paperless-ngx* auf einen Blick, dass ein Dokument als physisches Original existiert und auf den zweiten Blick, in welchem Leitz-Ordner es lagert. Sollte ich ein Original benötigen, kann ich direkt im richtigen Ordner auf die richtige Seite blättern, da die ASN mir verrät, wo im Ordner sich das Dokument befindet (oder zumindest befinden sollte :grin:). Beispiel gefällig?

[![Bild: ASN]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/04-asn.png)]({{ site.url }}{{ site.baseurl }}/assets/images/paperless/04-asn.png)

Das System bietet sehr charmante Suchmöglichkeiten nach Dokumenten mit ASN, und zeigt diese unter dem Dokumenten-Datum gleich an. Dass ein Dokument eine ASN hat, verrät mir, dass ein Original dazu existieren muss. Die ASN selbst verrät mir, wo das Dokument abgeheftet sein muss. Meine Leitz-Ordner sind beschriftet mit dem Nummernbereich der ASNs, die sie enthalten, z.B. *1000 - 1499*. Innerhalb des Ordners sind die Dokumente nach ASN aufsteigend abgeheftet, d.h. Dokument *1499* finde ich ganz vorne, während die *1000* ganz hinten liegt. Einfach, oder?

**Profi-Tipp:** Es ist nicht nur möglich, vom digitalen Abbild auf ein Original zu schließen. Die abgehefteten Dokumente beklebe ich mit einem QR Code, in den die ASN einkodiert ist. Scanne ich mit meinem iPhone diesen QR Code, öffnet sich *paperless-ngx* im Browser und zeigt mir die digitale Version des Dokuments an. Dazu später mehr.
{:  .notice--info}

### Scannen

Wie über dem Schaubild am Anfang dieser Seite erwähnt, erreichen uns Dokumente mittlerweile über alle möglichen Kanäle. Ich präferiere natürlich den digitalen Weg, denn z.B. ein Email-Anhang oder App-Download ist blitzschnell an *paperless-ngx* übergeben. Hierfür musst du nicht einmal das Handy aus der Hand legen. Aus diesem Grund achte ich auch bei Vertragsabschluss mit Serviceanbietern darauf, dass diese schon selbst digital unterwegs sind. Eine monatliche Rechnung für den Internetanschluss per Post ist für mich ein absolutes Tabu. Das hat auch weniger politisch-motivierte grüne Gründe, es passt schlichtweg nicht zu meinem Lifestyle.

Gerade bei Behörden erfreut sich der Postweg allerdings nach wie vor größter Beliebtheit. In solchen Fällen musst du nach dem Öffnen des Briefs deinen Scanner bemühen. Hier empfiehlt sich ebenfalls das Smartphone, denn es gibt eine richtig gute Scanner-App in den App Stores: **[Genius Scan](https://thegrizzlylabs.com/genius-scan/)**.

**Info**: 2018 gab es die App als Einmalkauf für 8,99 EUR, heute bietet sie nur noch ein monatliches Abo an. Du benötigst das Abo nicht zwingend, denn in erster Linie willst du Dokumente scannen. Im Abo enthalten ist ein automatischer Export, auch möglich in Richtung *paperless-ngx*. Als iPhone User bist du allerdings mit Shortcuts[^2] gesegnet: nutze sie :sunglasses:. Dazu später mehr.
{:  .notice--info}

[^2]: Die Kurzbefehle-App auf iPhones, iPad und Macs von Apple.

### Konsumieren

Die größte und umfangreichste Komponente von *paperless-ngx* ist vermutlich der <u>Document Consumer</u>, er ist Herz und Gehirn des ganzen DMS. Und das geht auch gar nicht anders, denn er stellt sämtliche Funktionalitäten zur Dokumentenverarbeitung, OCR, Fehlerbehandlung, Erkennung von Metainformationen, automatischer Klassifizierung und letztlich auch Archivierung bereit.

