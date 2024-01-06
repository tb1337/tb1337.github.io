---
title: "Papierlos mit iPhone"
excerpt: "iPhones können unser Leben bereichern, auch im privaten Büro sind sie wertvoll."
permalink: /paperless/iphone/
header:
  image: /assets/images/paperless/header.jpg
  caption: >
    Foto von <a href="https://unsplash.com/de/@lucabravo?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Luca Bravo</a> auf <a href="https://unsplash.com/de/fotos/apple-macbook-neben-computermaus-auf-tisch-9l_326FISzk?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
toc: true
toc_sticky: true
scanned_gallery:
  - url: /assets/images/paperless/06-ios-scanned.jpg
    image_path: /assets/images/paperless/06-ios-scanned.jpg
    alt: "Bild: Dokument mit iPhone gescannt"
    title: "Ein Dokument mit dem iPhone gescannt."
  - url: /assets/images/paperless/06-genius-scanned.jpg
    image_path: /assets/images/paperless/06-genius-scanned.jpg
    alt: "Bild: Dokument mit Genius Scan gescannt"
    title: "Ein Dokument mit Genius Scan gescannt."
---

**Disclaimer:** Ich werde hier nur über Apple Produkte berichten. Wenn du sie nicht magst, ist das für mich völlig in Ordnung. Lies einfach nicht weiter. Woran ich nicht interessiert bin sind Hinweise, warum Apple nicht gut ist oder dass Android ja viel besser sei. Spar dir die Zeit und langweile uns beide damit einfach nicht. Ich bin seit fast einem Jahrzehnt weg von Android, und das bleibt so. Danke :sunglasses:.
{:  .notice--danger}

## Das Smartphone als Werkzeug

Wir haben annähernd alle ein Smartphone in der Tasche und ich persönlich habe zu Social Media und Mobile Games eine Meinung. Die ist gar nicht gut, sparen wir das also besser aus. In meinen Augen wäre es einfach eine Verschwendung, das Smartphone nur für sowas zu nutzen: denn das ist alles, aber nicht smart.

Überleg mal. Du hast einen Computer in der Tasche, der mit einigen Laptops konkurrieren kann. Er hat sämtliche Verbindungsmöglichkeiten an Bord, eine Kamera, Sensorik und kann, mit den richtigen Apps ausgestattet, richtig viel Arbeit richtig schnell erledigen. Das ist ein Schweizer Taschenmesser ohne Schneidwerkzeug, aber vielleicht sind Smartphones in Zukunft ja mit einem schnittfähigen Laser ausgestattet. Wenn ich es mir recht überlege: nein, lieber nicht :grin:.

### Motivation

Alle Pflichten des Lebens haben eine Gemeinsamkeit, da spielt es auch gar keine Rolle, ob es der Papierkram oder regelmäßiges Sporttreiben ist: du machst keine Freudensprünge, wenn du sie erledigen *musst*. Ich bin ein Mensch, der gern alle äußeren Umstände abwägt, die mich davon abhalten könnten, etwas zu tun - um sie dann als Ausreden zu nutzen. 

> Heute ist Regen angesagt?
> Oh, wie schade, dann kann ich wohl keine Jogging-Tour machen.

Kommt dir bekannt vor? :laughing:

Kommen wir zurück zu unserem Papierkram. Eine mögliche Barriere war in meinem Fall die Tatsache, dass ich eine Abneigung gegenüber Drucker/Multifunktionsgeräte in meinem Haushalt habe. Die Vorstellung mit meinem Drucker andauernd irgendwelche Post einscannen zu müssen, hat mich genervt. Ich finde Drucker und insbesondere ihre Software völlig unintuitiv und veraltet, obendrein gibt es Bloatware und Tracker von den Herstellern ohne Ende. Nein danke. Da spielt es auch keine Rolle, ob Canon, HP, Epson oder sonstwas drauf steht. Es wäre doch schön, wenn mein iPhone bloß vernünftig scannen könnte... wie war das mit dem Schweizer Taschenmesser?

### Digitales Handwerk

Natürlich hat ein iPhone eine ausgefeilte Scanner-Funktion direkt an Bord, aber [Genius Scan](https://tbsch.de/paperless/workflow/#scannen) ist einfach besser. Ich habe absichtlich ein altes Firmenlogo auf dem Papier sichtbar gelassen, da es das Unternehmen eh nicht mehr gibt - auch hier siehst du den qualitativen Unterschied extrem deutlich. Beide Aufnahmen entstanden im Schwarzweiß-Modus beim Scannen.

{% include gallery id="scanned_gallery" layout="half" caption="Genius Scan bereitet das Ergebnis sehr detailliert auf." %}

**Info**: Über Geschmackssinn lässt sich nicht streiten. Mir gefällt das zweite Ergebnis besser, da *Genius Scan* vielfältige Methoden zur Aufbereitung des Scan-Ergebnisses einsetzt. Dicke schwarze Balken am Rand verschwinden, Schrift und Logo sind klar und es führt Begradigungen in hohem Maße aus. So lässt sich nur noch erahnen, dass ich das Blatt absichtlich zerknickt habe.
{:  .notice--info}

## Dokumente teilen

Nun sind wir an einem Punkt angelangt, an dem jedes Dokument digital verfügbar ist: egal ob ein Postbrief, ein Emailanhang oder App Download. Nun geht es wieder um meine persönlichen Erfahrungen, vielleicht bewertest du meine Herausforderungen ja komplett anders.

### FTP und WebDAV

In den Beschreibungen zum [Workflow](https://tbsch.de/paperless/workflow/#konsumieren) sagte ich, dass deine Aufgabe darin besteht, *paperless-ngx* mit Dokumenten zu füttern. Für mich war von Anfang an klar, dass ich nicht jede Datei einzeln hochladen möchte. Das soll automatisch passieren.

*Genius Scan* bringt diverse automatische Exportmöglichkeiten mit, sodass eingescannte Dokumente direkt an den *Consumption-Ordner* übermittelt werden können. Eine Zeit lang löste ich das über FTP und später WebDAV. Ich machte mich allerdings von den Verbindungsmöglichkeiten von *Genius Scan* abhängig und ertappte mich eines Tages dabei, wie ich ankommende Emails über das Share Sheet mit *Genius Scan* teilte, damit es das Dokument an den *Consumption-Ordner* überstellte. Das war mir nicht smart genug, weil ich nicht nur einen vermeidbaren Umweg über *Genius Scan* gehen, sondern auch einen FTP- bzw. WebDAV-Server betreiben musste.

Eine weitere Herausforderung war, dass ich in meiner *paperless-ngx* Installation die Dokumente von zwei Personen verwalte. Ich brauchte also zusätzlich Mandantenfähigkeit - damals gab es **Verarbeitungsvorlagen** noch nicht.

### Shortcuts

Wie schön wäre es, wenn ich ein Dokument direkt mit *paperless-ngx* teilen könnte, so wie wir das bei Fotos von Messengern gewöhnt sind? Und wie geil wäre es, wenn ich gleichzeitig noch festlegen könnte, für welche Person das Dokument bestimmt ist? Genau hier kommen Shortcuts auf Apple Geräten ins Spiel. Die kann man nämlich komplett an seine Bedürfnisse anpassen.

**Kurzerhand habe ich einen Shortcut mit diesem Flow erstellt:**

1. Eingabe über Share Sheet: Bilder, PDFs, Text, Formatierter Text
2. Abfrage, für welche Person das Dokument bestimmt ist
3. Aufruf des REST API Endpunktes zum Erstellen neuer Dokumente
4. Übermittlung aller geteilten Dokumente

Diesen Shortcut habe ich dann noch im Share Sheet als Favoriten hinterlegt, sodass er nun an prominenter Stelle mit dem Finger ansteuerbar ist:

[![Bild: Dokument teilen mit dem iPhone](/assets/images/paperless/04-share-iphone.png)](/assets/images/paperless/04-share-iphone.png)

Auch überzeugt? Am Ende dieser Seite stelle ich meine Shortcuts zur Verfügung.