---
layout: post
title: "Vogel-spotter: een BirdWeather dashboard met FastAPI en Docker"
date: 2026-02-13 08:00:00 +0000
image: /assets/img/posts/vogel-spotter-birdweather-dashboard.jpg
categories: [IoT]
tags: [birdweather, fastapi, docker, ansible, javascript, vogels, iot, python]
---

Ik wilde een simpele manier om te zien welke vogels er bij mijn BirdWeather-station langskomen. Niet via de BirdWeather-app zelf, maar op een eigen dashboard dat ik op een tablet in de keuken kan zetten. Dat werd [vogel-spotter](https://github.com/iMartzen/vogel-spotter).

## Wat het doet

Vogel-spotter is een webapplicatie die twee dingen laat zien:

1. **Recente waarnemingen** — welke vogels zijn er het afgelopen uur gedetecteerd?
2. **Top 25** — welke soorten komen het vaakst voor op dit station?

Dat is het. Geen statistieken-overkill, geen grafieken met 47 assen. Gewoon: wat zit er nu in de tuin?

De app draait live op [tuin.uitvogelpassie.nl](https://tuin.uitvogelpassie.nl/).

## De stack

De keuzes zijn bewust simpel gehouden:

| Component | Technologie |
|-----------|-------------|
| Backend | FastAPI (Python) |
| Frontend | Vanilla JavaScript (SPA) |
| Webserver | Nginx |
| Containerisatie | Docker + Docker Compose |
| HTTPS | https-portal (Let's Encrypt) |
| Deployment | Ansible playbook |

Geen framework voor de frontend, geen ORM voor de backend. De FastAPI-backend haalt data op van de [BirdWeather API](https://www.birdweather.com/), verwerkt het, en serveert het via twee endpoints.

## API endpoints

De backend heeft twee routes:

- **`/api/detections`** — geeft recente vogelwaarnemingen van het afgelopen uur terug
- **`/api/top25`** — retourneert de top 25 meest waargenomen soorten op het station

De frontend pollt deze endpoints en rendert de data dynamisch. Een refresh-knop zorgt dat je handmatig kunt updaten zonder de pagina te herladen.

## Opzetten

De makkelijkste manier is Docker:

```bash
git clone https://github.com/iMartzen/vogel-spotter.git
cd vogel-spotter
./run.sh
```

Het `run.sh` script regelt de rest. Je hebt alleen een `.env` bestand nodig met je station ID:

```text
STATION_ID=1
```

Vervang `1` met het ID van je eigen BirdWeather-station.

> Geen eigen server? Je kunt vogel-spotter ook deployen op [Vercel](https://vercel.com/) — er zit een kant-en-klare configuratie bij.
{: .prompt-tip }

## Server deployment met Ansible

Voor een "echte" deployment op een server zit er een Ansible playbook bij. Dat is handig als je het op een VPS of een Raspberry Pi wilt draaien zonder elke keer handmatig te SSH'en.

Het playbook regelt:

- Docker installatie
- Repository clonen
- Containers starten
- HTTPS certificaten via Let's Encrypt

Eén commando en je station draait.

## Features die het fijn maken

Een paar kleine dingen die het dagelijks gebruik prettiger maken:

- **Dark mode** — voor 's avonds of in omgevingen met weinig licht
- **Responsive design** — werkt op telefoon, tablet en desktop
- **Tweetalig** — Nederlands en Engels

Geen van deze features is spectaculair op zich, maar samen maken ze het verschil tussen "een project dat werkt" en "een project dat je daadwerkelijk gebruikt".

## Inspiratie

Het project is geïnspireerd door [luistervink.nl](https://www.luistervink.nl/), dat zich richt op het monitoren en analyseren van vogelgeluiden. Vogel-spotter pakt dat idee en maakt er een persoonlijk dashboard van, gekoppeld aan je eigen BirdWeather-station.

## Wat ik nog wil toevoegen

Er staan twee dingen op de to-do lijst:

- **Dagelijkse top 10** — welke vogels zijn er vandaag het meest gezien?
- **Maandelijkse statistieken** — trends per soort over een langere periode

Maar eerlijk: in de huidige vorm doet het precies wat ik nodig heb. En dat is misschien wel het belangrijkste bij een hobby-project — weten wanneer het "klaar genoeg" is.

De broncode staat op [GitHub](https://github.com/iMartzen/vogel-spotter) onder MIT-licentie.
