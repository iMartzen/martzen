---
layout: post
title: "Aliens vielen ons datacenter aan: disaster recovery met een twist"
date: 2024-05-29
image: /assets/img/posts/aliens-attack-disaster-recovery.jpg
categories: [Infrastructure]
tags: [disaster-recovery, resilience, rpo, rto]
---

> “In a shocking turn of events, the AWS us-west-2 datacenter in Oregon fell victim to a targeted invasion by green-skinned extraterrestrial beings.”

Zo begon onze disaster recovery-drill in 2023. Ja, **aliens vielen ons datacenter aan**. En nee: dat is niet alleen voor de grap.

Ik hou van dit soort scenario’s omdat ze iets doen wat “normale” DR-tests vaak niet doen: ze trekken je uit de sleur van checklist-denken. Ineens kijk je niet meer naar *het document*, maar naar *de werkelijkheid*.

## Disaster recovery is meer dan compliance

Natuurlijk: ISO 27001 en SOC 2 willen dat je disaster recovery test. Dat is logisch en nuttig, maar het is ook vooral de ondergrens. Als DR voor je team voelt als “even afvinken”, dan mis je waar het echt om draait.

Voor mij is een DR-drill geen examen maar een diagnose. Het gaat niet om “slagen”, maar om scherper worden: als team én als systeem. Je ontdekt waar herstel nog leunt op handwerk, waar kennis in hoofden zit in plaats van in runbooks, en welke afhankelijkheden je in rustige tijden onderschat. Iedere oefening is een momentopname en tegelijk een kans om de volgende keer rustiger en sneller te herstellen.

En ja: het mag ook gewoon leuk zijn. Humor is soms een verrassend goede manier om stressbestendigheid te oefenen.

## Waarom we creatieve scenario’s kiezen

We kiezen elk jaar een scenario dat nét absurd genoeg is om iedereen wakker te schudden: sneeuwstormen, overstromingen… en dus alien invasions.

Het punt is niet dat aliens realistisch zijn. Het punt is dat **echte incidenten óók zelden netjes binnen je verwachting passen**. Een creatief scenario dwingt je om te reageren op onverwachte frictie: ontbrekende informatie, rare afhankelijkheden, en kleine beslissingen die ineens groot blijken.

## RPO, RTO en onze progressie

Voordat ik met cijfers strooi, eerst dit:

- **RPO (Recovery Point Objective)** is hoeveel data je maximaal wilt kunnen verliezen. Bijvoorbeeld: RPO 50 minuten betekent dat je tot 50 minuten aan veranderingen kwijt kunt raken.

- **RTO (Recovery Time Objective)** is hoe snel je weer operationeel wilt zijn na een incident. Bijvoorbeeld: RTO 16 uur betekent dat het maximaal 16 uur mag duren om weer operationeel te zijn.

Kort gezegd: **RPO gaat over dataverlies**, **RTO gaat over hersteltijd**. En nog één belangrijke nuance: het zijn **doelen**. In een echte ramp wil je er zo dicht mogelijk bij komen, maar je ontwerpt en oefent vooral zodat je niet hoeft te gokken.

Wat mij altijd motiveert: je ziet echte progressie als je drills serieus neemt. Hieronder een overzicht van de afgelopen jaren:

**2021:** RPO 50 minuten, RTO 16 uur  
**2022:** RPO < 1 seconde, RTO 6 uur  
**2023:** RPO < 1 minuut, RTO 2 uur 41 minuten  

Die getallen zijn leuk, maar de échte winst zit eronder: betere voorbereiding, heldere verantwoordelijkheden, minder handwerk, minder afhankelijkheid van losse kennis in hoofden, en een team dat sneller samen kan handelen.

## Herstel in lagen: eerst de kern, dan de helpers, dan de luxe

Het beste herstelplan werkt in mijn optiek met een lagenmodel. Dat klinkt misschien droog, maar in een incident is dit goud waard: het maakt prioriteiten expliciet en voorkomt discussie terwijl de klok tikt.

1. **Kernservices eerst** – wat móét draaien om het platform weer bruikbaar te maken (bijv. de hoofdapplicatie, database, login/auth).
2. **Kritieke ondersteuners daarna** – wat je nodig hebt om weer echt te kunnen leveren (bijv. job queue + workers zoals Sidekiq/Redis, storage, essentiële notificaties).
3. **Niet-kritieke tooling als laatste** – handig en waardevol, maar niet nodig voor de eerste recovery (bijv. interne dashboards, analytics en andere interne tools).

De kracht zit niet alleen in de volgorde, maar in het gesprek dat je ermee afdwingt: waarom hoort iets in laag 1 en niet in laag 2? Als je dat vooraf scherp hebt, herstel je sneller én rustiger.

## Blijven verbeteren

We halen de compliance, en de recovery-tijden zijn goed. Maar dat is geen eindstation.

Als je wilt dat disaster recovery echt een teamding is, moet het zichtbaar en bespreekbaar zijn. Dan wordt paraatheid iets wat je samen onderhoudt, in plaats van iets dat je eens per jaar uit de kast trekt. En het helpt om scherp te blijven op de vragen die er écht toe doen:

- moeten we scenario’s realistischer maken, of juist nog vreemder?  
- welke nieuwe onderdelen moeten mee in de volgende drill?  
- waar is “sneller” nuttig, en waar is “stabieler” belangrijker?  

Voor mij is het antwoord simpel: **blijven oefenen, blijven bijstellen**. Veerkracht is geen status: het is een gewoonte.

## Be prepared (ook voor aliens)

Disaster recovery is niet alleen een protocol. Het is een belofte: aan jezelf en aan je team, dat je voorbereid wilt zijn op de chaos die je niet kunt voorspellen.

En aliens? Kom maar door.

Lees het volledige verhaal voor meer context, extra details over onze progressie en meer alien-details: [Embracing Resilience: HackerOne's Approach to Disaster Recovery](https://www.hackerone.com/blog/embracing-resilience-hackerones-approach-disaster-recovery)