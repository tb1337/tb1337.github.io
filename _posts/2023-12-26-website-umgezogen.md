---
title: "Meine Webseite ist umgezogen"
header:
  image: /assets/images/posts/2023-12-26-header.jpg
  caption: >
    Foto von <a href="https://unsplash.com/de/@freiburgermax?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Max Langelott</a> auf <a href="https://unsplash.com/de/fotos/silhouette-von-kranwagen-d3_cFMe97Ec?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
  
categories:
  - Website
tags:
  - news
---

Ich habe mich entschlossen, meine Webseite auf GitHub Pages umzuziehen und neu aufzubauen. Bislang habe ich sie selbst in meiner heimischen Infrastruktur gehostet, aufgrund zunehmender Sicherheitsrisiken kommt das aber nicht mehr für mich in Frage. 

Zwischenzeitlich habe ich mit einem VPS experimentiert, aber auch hier muss man laufend dran bleiben, um Sicherheitsrisiken im Keim zu ersticken. Das ist für mich auf Dauer leider keine Option, da die Webseite einfach nur ein kleines Projekt für Nebenbei ist und im Alltag vermutlich häufig viel zu kurz kommt.

## Gründe

- Keine Schwachstellen, die Aufmerksamkeit erfordern
- Kein PHP oder WordPress
- Keine Datenbank
- Webseite ist Open Source:
  - Theme: [minimal-mistakes@GitHub](https://github.com/mmistakes/minimal-mistakes)
  - Source: [tb1337.github.io@GitHub](https://github.com/tb1337/tb1337.github.io)

## Warum GitHub Pages?

Anfangs war mein Plan, eine kleine Webseite mit dem Python Django Framework aufzubauen. Das ist aber mit Kanonen auf Spatzen geschossen gemessen an dem, was ich mit der Webseite wirklich vorhabe. Auch wenn mir die Vorstellung eines Docker-Projekts mit CI/CD Pipeline sehr gefällt, idealerweise mit Live-Fakten meines Zuhauses :smile:.

Wie jedoch eingangs erwähnt, kommt die Pflege einfach häufig zu kurz. Und genau deshalb finde ich diese Möglichkeit sehr ansprechend: ein Einfallstor in meine private Infrastruktur, schlimmer noch Zugriff auf den Core meines Smart Home, ist somit schlichtweg nicht möglich. Die so eingesparte Zeit stecke ich dann lieber in meine öffentlichen Python Projekte.