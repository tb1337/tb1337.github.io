---
title: "Einführung"
excerpt: "Ein Leitfaden, wie man sein Leben papierlos und smart organisieren kann."
permalink: /paperless/einfuehrung/
header:
  image: /assets/images/paperless/01-header.jpg
  caption: >
    Foto von <a href="https://unsplash.com/de/@lucabravo?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Luca Bravo</a> auf <a href="https://unsplash.com/de/fotos/apple-macbook-neben-computermaus-auf-tisch-9l_326FISzk?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
toc: true
toc_sticky: true
---

Papierkram. Jeder von uns hat ihn, jeder muss ihn bewältigen, rechtzeitig auf Ereignisse reagieren, Schriftgut ablegen - und irgendwann im Bedarfsfall wiederfinden. Einige haben sich hierfür ein straffes Ordnersystem ausgedacht, andere feuern ihre Dokumente in irgendeine Kiste. Die Ablageregeln, die man sich hierfür aufgestellt hat, geraten mit den Jahren möglicherweise in Vergessenheit und bestimmte Dokumenttypen lagern dann an mehreren Stellen - der Worst Case ist eingetreten.

## Lösungsansätze

Nacheinander probierte ich verschiedene Lösungsansätze aus und entwickelte so mit der Zeit meine heutige Lösung.

### Ablage nach Datum

Da ich mich 2016 noch nicht mit privaten DMS[^1] auskannte bzw. mir mein Use-Case noch nicht bewusst war, entwickelte ich ein einfacheres Ablagesystem in meinen Ordnern. Hierbei heftete ich jedes Dokument einfach nach Datum ab und beschriftete die Ordner mit Zeiträumen.

[^1]: Document Management System, [Wikipedia](https://de.wikipedia.org/wiki/Dokumentenmanagement)

Mann, kam ich mir clever vor. :sunglasses: Bis der Tag kam, an ich einen bestimmten Brief von der Krankenkasse gesucht habe. Natürlich wusste ich nicht mehr, wann genau ich ihn erhalten hatte: ich blätterte also jeden Ordner durch, bis ich den Brief schließlich gefunden hatte.

### Erste Gehversuche: ecoDMS

Über meinen Freund Ben habe ich von [ecoDMS](https://www.ecodms.de/de/) erfahren. Das DMS besteht aus einem **Server**, der die Dokumente erkennt, klassifiziert und speichert, sowie einem **Client**. Über diesen kann man dann Dokumente suchen, mit Metainformationen versehen und einfach damit arbeiten. Cool - da ich einen Server zuhause stehen hatte, passte das wie die Faust aufs Auge und meine Dokumente wären immer verfügbar für mich.

Man steckt bei *ecoDMS* sehr viel Zeit in die Konfiguration, überlegt sich Strukturen, Dokumenttypen, Datenfelder, etc. Außerdem musste man der Erkennungssoftware beibringen, *wie* Dokumente klassifiziert werden sollen. Über einen praktischen Editor konnte man Bereiche auf einem Dokument auswählen, in denen bspw. immer eine Kundennummer auftauchte. Wahnsinn :grin:!

Bis Absender von Dokumenten halt mal ihr Brieflayout ändern. Ich musste leider feststellen, dass das ziemlich oft passiert. Dann begann nämlich jedes Mal das große Herumgefummel und *ecoDMS* wurde für mich einfach nur noch lästig und fühlte sich so **gar nicht smart** an. Der lästige Windows-FAT-Client und die schlechten Mobile- und Web-Zugriffsmöglichkeiten rundeten das negative Erlebnis ab.

### Die Lösung: paperless-ngx

Anfang 2021 dann der große, medienwirksame Newcomer: [paperless-ng](https://github.com/jonaswinkler/paperless-ng) - Open Source, ausführbar in vielen privaten Umgebungen, rein webbasierter Zugriff, alles über REST API.

Als im August 2021 das **Aus** von *paperless-ng* verkündet wurde, machte sich bei mir Enttäuschung breit. Ich hatte schließlich mein *ecoDMS* damit abgelöst. Im März 2022 dann die Kehrtwende: ich war offensichtlich nicht der einzige Fan von *paperless-ng*. Das Projekte wurde geforkt und ging an den Start als:

**[paperless-ngx](https://github.com/paperless-ngx/paperless-ngx)**

Jeder hat seine Präferenzen, ich favorisiere ganz klar den digitalen Weg: wenig bis gar kein Papier im Aktenschrank. Das passt einfach zu meinem Lifestyle. Auf den folgenden Seiten gehe ich näher auf meine Vorgehensweise mit *paperless-ngx* ein, die sich komplett mühelos in den Alltag integrieren lässt.