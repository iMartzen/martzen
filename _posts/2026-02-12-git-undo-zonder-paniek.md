---
layout: post
title: "Git: undo zonder paniek"
date: 2026-02-12 10:00:00 +0000
image: /assets/img/posts/git-undo-zonder-paniek.jpg
categories: [Programming]
tags: [git, terminal, productiviteit, workflow, version-control]
---

Git heeft minstens tien manieren om iets ongedaan te maken. Dat klinkt fijn, maar in de praktijk sta je met zwetende handen te googelen welk commando je nu ook alweer nodig hebt. Hier is de versie die ik zelf gebruik: vier situaties, vier oplossingen.

## Situatie 1: file aangepast, nog niet gecommit

Je hebt een bestand gewijzigd maar wilt terug naar de laatste commit-versie.

```bash
git restore pad/naar/bestand
```

Alles in één keer terugzetten:

```bash
git restore .
```

> Let op: dit gooit je lokale wijzigingen weg. Er is geen undo van de undo.
{: .prompt-warning }

## Situatie 2: ge-staged, maar je wilt het terug

Je hebt `git add` gedaan, maar je wilt het bestand weer uit de staging area halen. De wijzigingen blijven intact.

```bash
git restore --staged pad/naar/bestand
```

## Situatie 3: gecommit, maar nog niet gepusht

De commit is lokaal, niemand anders heeft hem gezien. Je hebt twee opties.

**Commit weg, wijzigingen behouden** (meest veilig):

```bash
git reset --soft HEAD~1
```

Je wijzigingen staan weer in staging. Handig als je commit message niet klopte, of als je nog iets wilt toevoegen.

**Commit én wijzigingen weg** (nucleaire optie):

```bash
git reset --hard HEAD~1
```

> Gebruik `--hard` alleen als je echt zeker weet dat je die changes niet meer nodig hebt.
{: .prompt-danger }

## Situatie 4: al gepusht en gedeeld

Zodra anderen jouw commit hebben, wil je de geschiedenis niet herschrijven. Gebruik `revert` — dat maakt een nieuwe commit die de vorige terugdraait:

```bash
git revert <commit-sha>
```

De history blijft intact en je collega's krijgen geen conflicten.

## Wanneer wat

| Situatie | Commando | History intact? |
|----------|----------|----------------|
| Lokale wijziging weggooien | `git restore` | Ja |
| Unstagen | `git restore --staged` | Ja |
| Lokale commit terugdraaien | `git reset --soft` | Nee |
| Gepushte commit terugdraaien | `git revert` | Ja |

## Altijd eerst checken

Voordat je iets doet, kijk even waar je staat:

```bash
git status -sb
git log --oneline -5
```

Twee seconden werk die je een hoop ellende besparen.

## Pro tip

De vuistregel is simpel:

- **Gepusht?** → `git revert`
- **Niet gepusht?** → `git reset` kan
- **Alleen een file?** → `git restore`

Onthoud die drie en je hoeft nooit meer te googelen.
