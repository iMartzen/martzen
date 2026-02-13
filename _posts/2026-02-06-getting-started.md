---
layout: post
title: "Aan de slag met Jekyll en Obsidian"
date: 2026-02-06 15:30:00 +0000
image: /assets/img/posts/getting-started.jpg
categories: [Programming]
tags: [jekyll, obsidian, setup, tutorial]
---

Ik gebruik [Obsidian](https://obsidian.md/) als editor voor mijn blogposts en [Jekyll](https://jekyllrb.com/) om de site te genereren. In dit artikel leg ik uit hoe je die twee combineert tot een prettige schrijfworkflow.

## Waarom deze combinatie?

Er zijn genoeg opties om een blog te draaien van: WordPress, Ghost, Hugo etc. maar ik wilde iets dat aan drie voorwaarden voldoet:

1. **Lokale markdown bestanden** als bron van waarheid, geen database
2. **Een fijne schrijfervaring** met autocomplete, linking en preview
3. **Gratis hosting** via [GitHub Pages](https://pages.github.com/)

[Obsidian](https://obsidian.md/) geeft je een krachtige markdown editor met features als backlinks, graph view, en templates. [Jekyll](https://jekyllrb.com/) neemt diezelfde markdown bestanden en bouwt er een statische website van. Omdat alles plain text is, heb je volledige controle en kun je alles in Git bijhouden.

## Vereisten

Voordat je begint, heb je het volgende nodig:

- **Ruby** (≥ 3.0) — Jekyll draait op Ruby. Installeer het via [rbenv](https://github.com/rbenv/rbenv) of [Homebrew](https://brew.sh/): `brew install ruby`
- **Bundler** — Ruby's dependency manager: `gem install bundler`
- **Jekyll** — `gem install jekyll`
- **Obsidian** — gratis te downloaden op [obsidian.md](https://obsidian.md/)
- **Git** — voor versiebeheer en deployment

## Project opzetten

### Jekyll installeren

```bash
# Maak een nieuw Jekyll project
jekyll new mijn-blog
cd mijn-blog

# Of clone een bestaand theme, zoals Chirpy
git clone https://github.com/cotes2020/jekyll-theme-chirpy.git mijn-blog
cd mijn-blog
bundle install
```

> Ik gebruik het [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) theme. Het heeft ingebouwde dark mode, zoekfunctionaliteit, en een overzichtelijke layout.
{: .prompt-info }

### Obsidian vault koppelen

Open Obsidian en kies **Open folder as vault**. Selecteer je Jekyll projectmap (bijvoorbeeld `mijn-blog`). Obsidian opent nu je hele project als vault, inclusief de `_posts` folder.

Je kunt ook alleen de `_posts` map als vault openen als je de rest van het project niet in Obsidian wilt zien.

## Workflow

Mijn dagelijkse workflow ziet er zo uit:

1. Open Obsidian en maak een nieuw bestand in `_posts/`
2. Gebruik het template (zie hieronder) voor de juiste front matter
3. Schrijf de post in markdown
4. Preview met `bundle exec jekyll serve --livereload`
5. Commit en push naar GitHub

### Lokaal testen

```bash
bundle exec jekyll serve --livereload --port 4000
```

Jekyll draait nu op `http://localhost:4000`. Bij elke wijziging die je opslaat in Obsidian, wordt de site automatisch opnieuw gebouwd.

## Obsidian template voor blogposts

Dit is misschien wel de handigste tip: maak een template in Obsidian zodat je niet elke keer de [front matter](https://jekyllrb.com/docs/front-matter/) handmatig hoeft te typen.

### Template instellen

1. Maak een map `_templates` aan in je project (of een andere naam)
2. Ga in Obsidian naar **Settings → Core plugins → Templates** en zet het aan
3. Stel de **Template folder location** in op `_templates`
4. Maak een nieuw bestand `_templates/blog-post.md` aan met deze inhoud:

{% raw %}
```markdown
---
layout: post
title: ""
date: {{date}} {{time}}
image:
categories: []
tags: []
---

```
{% endraw %}

### Template gebruiken

Als je een nieuwe post wilt schrijven:

1. Maak een nieuw bestand aan in `_posts/` met het juiste naamformaat: `YYYY-MM-DD-titel-van-je-post.md`
2. Open het bestand en gebruik **Ctrl/Cmd + P** → zoek naar **Templates: Insert template**
3. Selecteer `blog-post` en de front matter wordt automatisch ingevuld, inclusief de huidige datum en tijd

> Het naamformaat `YYYY-MM-DD-titel.md` is verplicht voor Jekyll. Zonder de datum in de bestandsnaam wordt je post niet herkend.
{: .prompt-warning }

## Handige Obsidian instellingen voor Jekyll

Een paar instellingen die ik aanraad als je Obsidian met Jekyll gebruikt:

| Instelling | Waar | Waarde |
| --- | --- | --- |
| Default location for new notes | Settings → Files & Links | `_posts` |
| New link format | Settings → Files & Links | Relative path |
| Use Wikilinks | Settings → Files & Links | **Uit** (Jekyll snapt geen `[[links]]`) |
| Strict line breaks | Settings → Editor | **Aan** |

Door **Wikilinks uit te zetten** maakt Obsidian standaard markdown links aan (`[tekst](url)`) in plaats van `[[wiki-style]]` links. Dat scheelt weer converteren achteraf.

## Deployen naar GitHub Pages

Als je site klaar is, push je alles naar een GitHub repository. GitHub Pages bouwt automatisch je Jekyll site:

```bash
git add .
git commit -m "Nieuwe post toegevoegd"
git push origin main
```

Als je een custom domain wilt, voeg dan een `CNAME` bestand toe aan je project root met je domeinnaam. Meer info hierover vind je in de [GitHub Pages documentatie](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Meer lezen

- [Jekyll documentatie](https://jekyllrb.com/docs/) — alles over configuratie, themes en plugins
- [Obsidian Help](https://help.obsidian.md/) — officiële documentatie
- [Chirpy theme wiki](https://github.com/cotes2020/jekyll-theme-chirpy/wiki) — specifieke instructies voor dit theme
- [Markdown Guide](https://www.markdownguide.org/) — handige referentie voor markdown syntax
- [GitHub Pages docs](https://docs.github.com/en/pages) — hosting en deployment

---

Met deze setup heb je een snelle, gratis blog waar je volledige controle over hebt. Geen CMS, geen database, gewoon markdown bestanden en Git. 📝
