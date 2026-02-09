---
layout: post
title: "91% accurate geautomatiseerde routing in exposure management"
date: 2025-12-11 10:00:00 +0000
categories: [Security]
tags: [hackerone, ai, automation, exposure-management]
---

Bij HackerOne heb ik een interessant probleem opgelost: Hoe route je security rapporten automatisch naar het juiste team, zonder handmatig werk?

## Het probleem

Elke security organisatie kent de "triage queue" problematiek. Voordat een vulnerability gerepareerd kan worden, moet het eerst de juiste persoon bereiken. Bij ons betekende dat: een Security Duty Engineer die elk rapport leest, bepaalt naar welk van onze 47+ product areas het hoort, en de juiste GitLab labels opzoekt.

Dit proces was:

- **Traag**: Rapporten bleven in onze queue tot een mens ze bekeek
- **Inconsistent**: Verschillende engineers routeerden vergelijkbare bugs naar verschillende teams
- **Handmatig**: Waardevolle tijd ging naar administratieve taken

## De oplossing

Ik heb een confidence-based automation gebouwd met Hai (onze AI security agent). Het resultaat: **91% accuracy** bij een 90% confidence threshold, en **64% van alle rapporten** worden nu automatisch gerouteerd.

### Hoe werkt het?

1. **Analyze**: Hai leest de titel en beschrijving
2. **Predict**: Matcht content tegen onze "Routing Map"
3. **Score**: Kent een confidence score toe (0-100%)
4. **Act**: Bij ≥90% confidence → automatisch escaleren naar GitLab

## Waarom is dit belangrijk?

- ✅ **Snellere remediation**: Rapporten bereiken de juiste persoon binnen één minuut
- ✅ **Minder handwerk**: Twee derde van de queue wordt automatisch afgehandeld
- ✅ **Hogere kwaliteit**: Consistente routing vermindert reroutes

Nieuwsgierig naar de technische details, de architectuur en hoe je dit zelf kunt bouwen?

**[Lees het volledige artikel op de HackerOne blog →](https://www.hackerone.com/blog/accurate-routing-exposure-management)**

In het artikel ga ik dieper in op:

- De volledige Hai Play architectuur
- Hoe we de 90% threshold hebben gevalideerd
- Onze "PPR Lane Tracker" voor visibility
- Code voorbeelden en JSON responses
- Praktische tips om je eigen routing automation te bouwen

---

_Dit artikel is oorspronkelijk gepubliceerd op het HackerOne blog als ["Customer Zero"](https://www.hackerone.com/blog/accurate-routing-exposure-management) - we testen onze eigen platform capabilities voordat ze naar klanten gaan._
