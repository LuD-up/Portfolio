---
title: "Générer les balises Open Graph avec Hugo"
description: "Guide pour générer automatiquement les balises Open Graph sur son site web ou son blog avec Hugo."
date: 2022-02-03T13:10:40Z
draft: true
---

{{< figure src="img-test.webp" title="Redesign de Mastodon pour iOS" alt="Oe" >}}

Open Graph est implémenté de base dans Hugo. Il suffit d'ajouter dans le head du site

## Open Graph 

```GO
{{ template "_internal/opengraph.html" . }}
```

## Twitter Cards

```GO
{{ template "_internal/twitter_cards.html" . }}
```

{{< figure src="img-test-2.webp" alt="Salut" >}}

**Attention :** Si comme moi vous utilisez des images au format WEBP sur votre site, il faudra fournir une image au format PNG ou JPG pour qu'Open Graph et Twitter Cards l'affiche.

Source :
- https://www.hackification.io/software-development/hugo/html/open-graph-tags/
- https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/opengraph.html
- https://gohugo.io/templates/internal/

---


First Hugo looks in your post front matter for an images value (images: [""])
Then Hugo searchs for image page resources with feature, cover or thumbnail in their name. These are images files under a directory that matches the post (e.g. content\posts\first-post)
If not images are found, Hugo looks for images (images: [""]) in your site config
If no image if found, then an image-less Twitter summary card is used instead of summary_large_image


https://erinjeong.com/posts/metatags-hugo/


I migrated my blog to Hugo in February and I currently host this blog on Netlify. I love it so far - it’s simple, fast, and snappy. However, the theme I chose didn’t have built-in meta tags for social.

Setting meta tags is important so you can define what assets are used to generate summary views in social shares.

You can add the following tags into your base HTML file in the <header> tag.

In the baseof.hmtl file, here’s how I defined $title
    {{ $title := print .Title " - " .Site.Title }} 
    {{ if .IsHome }}{{ $title = .Site.Title }}{{ end }}
{{ $title := print .Title " - " .Site.Title }} = sets page title to include .Title (post title) + “-” + .Site.Title (site title).

Open Graph / Facebook and Twitter meta tags
    <!-- Open Graph / Facebook -->
    <meta property="og:title" content= "{{ $title }}" >
    {{ if .Summary }}<meta property="og:description" content="{{ .Summary }}">{{ else }}<meta property="og:description" content="{{ $.Site.Params.Description }}">{{ end }}
    {{ if .Param "feature_image" }}<meta property="og:image" content="{{ .Param "feature_image" | absURL }}">{{ else }}<meta property="og:image" content="{{ $.Site.Params.Avatar | absURL }}">{{ end }}
    <meta property="og:url" content="{{ .Permalink }}">

    <!-- Twitter -->
    <meta property="twitter:card" content="summary_large_image">
    <meta property="twitter:title" content= "{{ $title }}" >
    {{ if .Summary }}<meta property="twitter:description" content="{{ .Summary }}">{{ else }}<meta property="og:description" content="{{ $.Site.Params.Description }}">{{ end }}
    {{ if .Param "feature_image" }}<meta property="twitter:image" content="{{ .Param "feature_image" | absURL }}">{{ else }}<meta property="og:image" content="{{ $.Site.Params.Avatar | absURL }}">{{ end }}
    <meta property="twitter:url" content="{{ .Permalink }}">
Add avatar, description, author in the config.toml file.

title = "your blog title"

[params]
  avatar = "/image/filename.png"
  description = "set description"
  author = "your name"
Notes
The title, summary, and feature_iamge are from each post’s front matter. If they’re not defined in the post, they will return empty.
In config.toml, the avatar specifies the default image. This will be used for the main website and when no feature_image is set in the post.
In config.toml, the descripton specifies the default description. This will be used for the main website and when no description is defined. I recommend always setting the description in your post.
To validate it’s working as intended in localhost, simply Right Click > View Page Source to see if the meta tags are populating correctly.
To validate it’s working in production, you can try sharing in social media or use validator tools like MetaTags.io or Twitter.
For Twitter, there are 4 different card types: summary_large_image, summary, app, player. Read more here. summary_large_image and summary are relevant for us here. Select the one that works better for you.


- -
Thanks for reading! If this was helpful or if you have any questions, feel free to shoot me a note at @erinejeong. 👋