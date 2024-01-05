---
title: "Setup"
excerpt: "Zeit für den digitalen Wandel: ein neues papierloses Büro aufsetzen."
permalink: /paperless/setup/
header:
  image: /assets/images/paperless/header.jpg
  caption: >
    Foto von <a href="https://unsplash.com/de/@lucabravo?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Luca Bravo</a> auf <a href="https://unsplash.com/de/fotos/apple-macbook-neben-computermaus-auf-tisch-9l_326FISzk?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
toc: true
toc_sticky: true
---

Viele Wege führen nach Rom, zumindest aber benötigst du eine Komponente: ein Gerät, auf dem Services betrieben werden können. Hier setzt *paperless-ngx* nur wenige Grenzen. Ich habe mich für die containerisierte Variante mit Docker[^1] entschieden, die Docker Bridge läuft auf meinem Synology NAS[^2]. Dieser Leitfaden beschränkt sich auf die Verwendung von **Docker**.

[^1]: Containermanager, [docker.com](https://www.docker.com)
[^2]: Network Attached Storage, [Synology Webseite](https://www.synology.com/de-de)

**Info:** Bitte beachte, dass ein paar Vorkenntnisse notwendig sind. Grundsätzlich ist aber jeder in der Lage, ein papierloses Büro zu betreiben, wenn er sich in die Materie einarbeitet und Englisch beherrscht.
{:  .notice--info}

## Vorbereitung

Wichtigste Informationsquelle für die folgenden Inhalte ist [die Webseite von *paperless-ngx*](https://docs.paperless-ngx.com).

### Setup

Ich empfehle stets die Verwendung von **docker compose**[^3], da es die Handhabung von Containern enorm erleichtert. Praktischerweise liefern die Macher von *paperless-ngx* bereits diverse Beispiel-Setups mit, welche [hier](https://github.com/paperless-ngx/paperless-ngx/tree/dev/docker/compose) zur Verfügung stehen.

[^3]: Mehr Infos auf [docker-compose](https://github.com/docker/compose)

Meine Installation besteht aus den folgenden Komponenten:

```yaml
# ...
services:
  broker:
    image: redis:7
    # ...
  webserver:
    image: paperlessngx/paperless-ngx:latest
    # ...
  gotenberg:
    image: gotenberg/gotenberg:7.8
    # ...
  tika:
    image: ghcr.io/paperless-ngx/tika:latest
    # ...
# ...
```

Bewusst verzichte ich auf den Einsatz einer relationalen Datenbank, wie z.B. PostgreSQL. Ich möchte mein papierloses Büro einfach nicht von einer Datenbank abhängig machen, denn diese benötigt auch Wartung, Backups, etc. Ein weiterer Vorteil ist, dass sich eine *sqlite*-Datei sehr viel einfacher backuppen lässt :sunglasses:. Solltest du eine *MySQL*-Datenbank verwenden wollen, gibt es noch weitere Dinge zu [beachten](https://docs.paperless-ngx.com/advanced_usage/#mysql-caveats).

**Warnung**: Wenn du dich mit Datenbanken nicht gut auskennst, rate ich dringend dazu, ebenfalls auf deren Einsatz zu verzichten! Bei falscher Handhabung droht Datenverlust; und genau das muss vermieden werden. Es gibt absolut keinen großen Vorteil durch ihren Einsatz, da *paperless-ngx* keine horrenden Datenmengen speichert. Meine *sqlite*-Datenbank ist gerade einmal 14 MB[^4] groß.
{:  .notice--warning}

[^4]: mit über 3000 Dokumenten am 30.12.2023

**Gotenberg** und **Tika** sind optionale Bestandteile der *paperless-ngx*-Installation. Sie werden benötigt, um *Office*- und Email-Dateien verarbeiten zu können. Ich nutze diese Services zwar extrem sporadisch, Haben ist aber besser als Brauchen. [Hier](https://docs.paperless-ngx.com/configuration/#optional-services) findest du weitergehende Erläuterungen dazu.

### Konfiguration

Meine *docker compose*-Konfiguration ist natürlich auf meine Bedürfnisse zugeschnitten. Hier ein kleiner Einblick in den *paperless-ngx*-Container. Alle Ordner sind frei zugänglich auf dem Dateisystem meines Servers, *docker Volumes* nutze ich nicht:

```yaml
# ...
volumes:
  - ./data:/usr/src/paperless/data
  - ./media:/usr/src/paperless/media
  - ./export:/usr/src/paperless/export
  - ./consume:/usr/src/paperless/consume
  - ./hooks:/usr/src/paperless/scripts
  - ./trash:/usr/src/paperless/trash
environment:
  PAPERLESS_REDIS: redis://broker:6379
  PAPERLESS_TIKA_ENABLED: 1
  PAPERLESS_TIKA_GOTENBERG_ENDPOINT: http://gotenberg:3000
  PAPERLESS_TIKA_ENDPOINT: http://tika:9998
  PAPERLESS_TASK_WORKERS: 2
  PAPERLESS_THREADS_PER_WORKER: 2
  PAPERLESS_PRE_CONSUME_SCRIPT: /usr/src/paperless/scripts/PRE_CONSUME.sh
  PAPERLESS_POST_CONSUME_SCRIPT: /usr/src/paperless/scripts/POST_CONSUME.sh
  PAPERLESS_TRASH_DIR: /usr/src/paperless/trash

  PAPERLESS_URL: # vertraulich
  PAPERLESS_TRUSTED_PROXIES: # vertraulich
  PAPERLESS_USE_X_FORWARD_HOST: true
  PAPERLESS_USE_X_FORWARD_PORT: true
  PAPERLESS_PROXY_SSL_HEADER: ["HTTP_X_FORWARDED_PROTO", "https"]
  PAPERLESS_SECRET_KEY: # vertraulich

  PAPERLESS_ENABLE_UPDATE_CHECK: true
  PAPERLESS_OCR_LANGUAGES: deu
  PAPERLESS_OCR_LANGUAGE: deu
  PAPERLESS_FILENAME_FORMAT: {owner_username}/{created}_{correspondent}_{document_type}_{title}

  # QR Code Scanner
  PAPERLESS_CONSUMER_ENABLE_BARCODES: true
  PAPERLESS_CONSUMER_ENABLE_ASN_BARCODE: true
  PAPERLESS_CONSUMER_BARCODE_SCANNER: ZXING
# ...
```

Alle Optionen sind detailliert [hier](https://docs.paperless-ngx.com/configuration/#docker) dokumentiert, jedes Detail kann und sollte nachgelesen werden. Für Vorschläge zu meiner Konfiguration bin ich jederzeit zu haben, nimm einfach Kontakt mit mir auf!

**Erläuterungen:**
* Wie eingangs erwähnt, behalte ich mir den Zugriff auf alle Daten über das Dateisystem vor. Das erleichtert Backups ungemein.
* Ich verwende Custom Scripts, um Aktionen vor und nach dem Konsumieren von Dokumenten auszuführen.
* Der Papierkorb ist aktiviert. Sollte nicht passieren, aber falls ich mal etwas lösche, ist es nicht sofort verloren.
* *paperless-ngx* läuft in meinem Homelab innerhalb eines *Traefik*[^5]-Dockernetzwerks, ist also geproxied.
* Beim `PAPERLESS_FILENAME_FORMAT` wird für jeden Eigentümer ein eigener Ordner angelegt. *paperless-ngx* ist mandantenfähig, ein bisschen :wink:. Für den Privathaushalt mit mehreren Personen reicht es vollkommen.
* Der Barcode-Scanner ist aktiviert. Für eine bessere Erkennung von kleinen QR Codes auf Dokumenten verwende ich `ZXING`. Ein anderer Paperless-User, *Marvin Gaube*, hat einen interessanten [Artikel](https://margau.net/posts/2023-04-16-paperless-ngx-asn/) darüber verfasst.

[^5]: Traefik ist ein Reverse Proxy, [traefik.io](https://doc.traefik.io/traefik/)

## Fazit

Es gibt viele Details, über die man seine *paperless-ngx*-Installation für den persönlichen Gebrauch optimieren kann. Das hängt immer sehr vom eigenen Use-Case, aber auch der eingesetzten Technik ab.

Auf die oben angesprochenen Custom Scripts gehe ich im weiteren Verlauf detaillierter ein. Das ist ein extrem mächtiges Tool, womit sich allerhand Schandtaten realisieren lassen :grin:. Stichwort: eigene Regelwerke, Validierung und Nachhalten dieser.