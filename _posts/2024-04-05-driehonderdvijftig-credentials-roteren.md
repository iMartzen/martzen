---
layout: post
title: "350 credentials roteren: waarom ik dit elk jaar wil blijven doen"
date: 2024-04-05
image: /assets/img/posts/driehonderdvijftig-credentials-roteren.jpg
categories: [Security, Infrastructure]
tags: [credential-rotation, secrets-management, vault, incident-response, automation, best-practices]
---

**350 credentials.** Elk jaar (meestal rond september) roteren we ze allemaal: wachtwoorden, service tokens, SSH-keys en andere secrets die, als ze lekken, direct impact kunnen hebben.

Ik schrijf dit op mijn persoonlijke blog omdat dit soort werk vaak onzichtbaar is, terwijl het voor mij juist laat zien hoe je als team met risico omgaat. Ik schreef eerder een uitgebreidere versie met meer details en best practices. Die link staat onderaan. Hier deel ik vooral mijn eigen blik op waarom ik dit belangrijk blijf vinden.

## Waarom dit meer is dan compliance

Je kunt credential rotation doen omdat een framework het vraagt. Maar voor mij is het vooral een simpele realiteit: geheimen lekken ooit. Niet altijd door een “hack”, soms door logs, screenshots, laptops, third parties, misconfiguraties, of een token dat te lang blijft bestaan.

Regelmatig roteren verkleint dan het probleem van “permanente toegang” naar “een beperkt tijdvenster”. Dat geeft mij rust, omdat je het ergste scenario alvast kleiner maakt.

## We denken in lagen: impact bepaalt prioriteit

Niet elk secret is even gevaarlijk. Daarom helpt het om te categoriseren op impact:

- **A Kritiek:** direct bruikbaar vanaf internet, zonder extra barrières.
- **B Belangrijk:** toegang met extra drempels (zoals tweede factor of netwerkbeperking), maar nog steeds gevoelig.
- **C Lager risico:** vervelend als het lekt, maar meestal minder directe of minder grote impact.

Dit systeem is niet perfect, maar het helpt enorm bij keuzes. Je voorkomt dat alles “even urgent” wordt.

## Wanneer roteren?

Drie momenten zijn typisch belangrijk:

1. **Jaarlijks (bulk-rotation):** alles een keer grondig doorlopen en opschonen.
2. **Bij vertrek van medewerkers:** vooral als iemand toegang had tot A/B-secrets.
3. **Na signalen van een incident:** bij twijfel roteer ik liever te vroeg dan te laat.

## Automatiseren waar het kan

Handmatig honderden secrets roteren is vragen om fouten. Daarom helpt een combinatie van centrale opslag (bijv. een secrets manager zoals Vault), automatisering voor het grootste deel, en duidelijke instructies voor de uitzonderingen.

De kern blijft voor mij: maak de veilige route de makkelijke route.

## Tot slot

Credential rotation is niet glamoureus, maar wel één van de meest praktische manieren om risico structureel te verlagen. Niet omdat het “moet”, maar omdat het werkt.

Meer context en details (de lange versie): [The Importance of Credential Rotations: Best Practices for Security and Data Protection](https://www.hackerone.com/blog/importance-credential-rotations-best-practices-security-and-data-protection)
