---
layout: post
title: "Praktisch printen met PLA"
date: 2026-02-11 10:00:00 +0000
image: /assets/img/posts/praktisch-printen-met-pla.jpg
categories: [3D Printing]
tags: [3d-printing, pla, cad, design, maker]
---

Ik print het liefst met PLA, en vooral dingen die gewoon nuttig zijn: kleine onderdelen die een irritatie wegnemen of iets netter maken. Geen decoratie (oké, soms een beetje), geen cosplay-helmen, maar prints die je elke dag pakt zonder erbij na te denken. Hieronder staat mijn aanpak, inclusief een concreet voorbeeld.

## Waarom PLA

Voor utility prints is PLA voor mij de default:

- **Makkelijk te printen** — weinig warping, meestal geen enclosure nodig (al heb ik die wel)
- **Prima voor binnen** — sterk genoeg voor holders, clips en organizers
- **Voorspelbaar resultaat** — wat je ontwerpt, is meestal ook wat je krijgt

De grote beperking is hitte: PLA wordt zacht als het warm wordt. Dus liever niet in een hete auto of pal naast een radiator. Ik heb ooit tijdens een hittegolf een Raspberry Pi uit een licht vervormde case mogen “redden”. Lesson learned. 😅

## Mijn designregels

Na genoeg mislukte prints (en net-te-krappe passtukjes) ben ik uitgekomen op een paar regels die bijna altijd werken:

1. **Hou het simpel** — minder supports = meer kans dat het in één keer lukt  
2. **Maak stresspunten dikker** — clip- en ophangpunten krijgen minstens **2 mm** wand  
3. **Rond hoeken af** — sterker dan scherpe hoeken én fijner in gebruik  
4. **Gebruik chamfers i.p.v. supports** — een **45° afschuining** aan de onderkant scheelt veel cleanup  

Voor clips geldt extra: maak ze dikker dan je intuïtie zegt. PLA is stijf en breekt sneller dan het buigt. Als flexibiliteit belangrijk is, werkt een schroefje vaak beter, of een snap-fit met wat extra speling.

## Workflow: van idee naar print

Mijn proces is bijna altijd hetzelfde:

1. **Meet het echte object** — schuifmaat erbij: hygrometer, silica-zakje, én de ruimte in de kast  
2. **Ontwerp parametrisch** — zet maten als variabelen in je CAD, zodat je snel corrigeert als je 0,5 mm mis zit  
3. **Draft print** — snelle testprint met lage infill om de passing te checken  
4. **Final print** — pas aan waar nodig en print de definitieve versie  

Die draft print bespaart serieus tijd. Niets zo pijnlijk als een perfecte print die nét niet past.

## Handige gewoontes

- **Label je prints** — ik zet datum en versienummer aan de onderkant, direct in het model. Scheelt later speuren.  
- **Blijf parametrisch werken** — als “hygrometer_breedte” een variabele is, kun je hetzelfde ontwerp hergebruiken voor een ander model.  
- **Bouw een maat-bibliotheek** — ik heb een notitie met standaardmaten die ik vaak nodig heb: sensoren, kabeldoorvoeren, schroefmaten.  

## Checklist voor utility prints

- [ ] Past het écht? (meet twee keer, print één keer)
- [ ] Geen scherpe randen die kunnen prikken
- [ ] Functionele delen zijn dik genoeg (clips, hooks)
- [ ] Ventilatiegaten waar nodig
- [ ] Niet bedoeld voor hitte of direct zonlicht
- [ ] Eerst een draft print gedaan voor de passing
