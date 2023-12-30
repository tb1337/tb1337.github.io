---
title: "Das Setup"
excerpt: "Ein Leitfaden, wie man sein Leben papierlos und smart organisieren kann."
permalink: /guides/paperless/setup/
toc: true
toc_sticky: true
---

Viele Wege führen nach Rom, zumindest aber benötigst du eine Komponente: ein Gerät, auf dem Services betrieben werden können. Hier setzt *paperless-ngx* nur wenige Grenzen. Ich habe mich für die containerisierte Variante mit Docker[^1] entschieden, die Docker Bridge läuft auf meinem Synology NAS [^2]. Dieser Leitfaden beschränkt sich auf die Verwendung von **Docker**.

[^1]: Containermanager, [docker.com](https://www.docker.com)
[^2]: Network Attached Storage, [Synology Webseite](https://www.synology.com/de-de)

**Info:** Bitte beachte, dass ein paar Vorkenntnisse notwendig sind. Grundsätzlich ist aber jeder in der Lage, ein papierloses Büro zu betreiben, wenn er sich in die Materie einarbeitet und Englisch beherrscht.
{:  .notice--info}

## paperless-ngx

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

Bewusst verzichte ich auf den Einsatz einer relationalen Datenbank, wie z.B. PostgreSQL. Ich möchte mein papierloses Büro einfach nicht von einer Datenbank abhängig machen, denn diese benötigt auch Wartung, Backups, etc. Ein weiterer Vorteil ist, dass sich eine *sqlite*-Datei sehr viel einfacher backuppen lässt :sunglasses:.

**Warnung**: Wenn du dich mit Datenbanken nicht gut auskennst, rate ich dringend dazu, ebenfalls auf deren Einsatz zu verzichten! Bei falscher Handhabung droht Datenverlust; und genau das muss vermieden werden. Es gibt absolut keinen großen Vorteil durch ihren Einsatz, da *paperless-ngx* keine horrenden Datenmengen speichert. Meine *sqlite*-Datenbank ist gerade einmal 14 MB[^4] groß.
{:  .notice--warning}

[^4]: mit über 3000 Dokumenten am 30.12.2023