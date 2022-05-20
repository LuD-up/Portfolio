---
title : "Générer un robot.txt automatiquement avec Hugo"
description : "Comment générer et configurer le fichier robots.txt automatiquement avec Hugo"
date : 2022-01-30T17:32:47Z
cover :  cover.png
draft: false
---

![Photo d'un jouet Wall-e sur fond blanc](cover.webp "Photo par Arturo Esparza sur Unsplash")

Pour générer automatiquement un `robots.txt` sous Hugo, il suffit d'ajouter dans le fichier de configuration `config.toml`

```bash
enableRobotsTXT = true
```

Par défaut, Hugo va générer un fichier très basique :

```bash
User-agent: *
```

## Personnaliser le fichier

Vous pouvez personnaliser le template de base, par exemple pour indiquer aux différents moteurs de recherche où se situe notre fichier `sitemap.xml`.

Il faut donc créer un fichier `robots.txt` dans le dossier `/layout/` de votre site avec le code suivant :

```bash
User-agent: * 
Allow: /

Sitemap: {{ "sitemap.xml" | absLangURL }}
```

---

Sources :
- https://gohugo.io/templates/robots/
- https://tangenttechnologies.ca/blog/hugo-robots-and-sitemaps/
