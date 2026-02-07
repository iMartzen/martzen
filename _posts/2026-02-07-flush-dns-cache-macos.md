---
layout: post
title: "DNS Cache legen op macOS"
date: 2026-02-07 10:00:00 +0000
categories: [macos, terminal]
tags: [dns, cache, zsh, alias, productiviteit]
---

Heb je wel eens problemen gehad met je netwerk op macOS waarbij websites niet laden, terwijl je internet prima werkt? Dan moet je waarschijnlijk je DNS cache legen. Ik liep hier steeds tegenaan en werd het zat om elke keer het commando te googelen.

## Het commando

```bash
sudo dscacheutil -flushcache && sudo killall -HUP mDNSResponder
```

Dit doet twee dingen:

1. **`dscacheutil -flushcache`** - maakt de DNS cache leeg
2. **`killall -HUP mDNSResponder`** - herstart de DNS responder service

De `&&` zorgt ervoor dat het tweede commando alleen wordt uitgevoerd als het eerste succesvol is.

## Wanneer heb je dit nodig

- websites laden niet, maar internet werkt wel
- na het wijzigen van DNS servers
- bij het testen van lokale ontwikkelomgeving met custom domains
- rare netwerkproblemen na het loskoppelen van een VPN

## Makkelijk maken met een alias

Ik leerde dit commando van een collega tijdens het troubleshooten van een lokale ontwikkelomgeving. Nadat ik het voor de derde keer die week had ingetypt, wist ik dat ik een alias nodig had.

Voeg dit toe aan je `~/.zshrc`:

```bash
alias flush="sudo dscacheutil -flushcache && sudo killall -HUP mDNSResponder"
```

Herlaad vervolgens je shell:

```bash
source ~/.zshrc
```

Nu kun je elke keer dat je DNS moet legen, gewoon typen:

```bash
flush
```

Voer je wachtwoord in, en klaar. Simpel, makkelijk te onthouden, en voorkomt dat je dat lange commando moet onthouden (of googelen).

## Pro tip

Voeg `echo "DNS cache geleegd!"` aan het einde toe om een bevestiging te krijgen:

```bash
alias flush="sudo dscacheutil -flushcache && sudo killall -HUP mDNSResponder && echo 'DNS cache geleegd!'"
```

Dat is het! Een kleine alias die het leven net iets makkelijker maakt.
