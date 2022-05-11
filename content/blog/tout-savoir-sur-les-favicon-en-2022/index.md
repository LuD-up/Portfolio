---
title : "Tout savoir sur les favicons en 2022"
description : "Tutoriel sur l'implémentation des différents favicons essentiels en 2022 pour la majorité des navigateurs, moteurs de recherche, plateformes mobile etc."
date : 2022-01-22T15:10:40Z
draft: true
---

Au cours de la refonte de mon site, j’ai eu beaucoup de mal à trouver des sources récentes sur ce point.

J’aime n’inclure que ce qui est vraiment nécessaire dans mes projets. Je suis donc parti en quête d’informations pour bien comprendre l’état de la gestion des favicons à ce jour et voici mes conclusions.

## Version courte

Vous aurez juste besoin de 6 versions en PNG de votre favicon à intégrer au header de votre site :

```HTML
<!-- Tous les navigateurs -->
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16.png">

<!-- Pour Google -->
<link rel="icon" type="image/png" sizes="48x48" href="favicon-48.png">
<link rel="icon" type="image/png" sizes="192x192" href="favicon-192.png">

<!-- Pour Apple -->
<link rel="apple-touch-icon" type="image/png" sizes="180x180" href="favicon-180.png">
<link rel="apple-touch-icon" type="image/png" sizes="167x167" href="favicon-167.png">
```

---

## Version longue

### Qu’est-ce qu’un favicon ?

Un favicon (contraction anglaise des mots favorite et icon) est une image utilisée à de nombreux endroits : dans les onglets du navigateur, les résultats des moteurs de recherche...

Pour afficher un favicon sur votre site il suffit d’ajouter un `<link>` dans votre `<head>` comme ceci :

```HTML
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16x16.png">
```

* L’attribut `<rel>` doit avoir la valeur `icon` pour faire comprendre au navigateur qu’il s’agit d’un favicon.
* L’attribut `<type>` doit indiquer le format de votre image.
* L’attribut `<size>` est important pour différencier les différentes tailles pouvant être utilisées.
* Enfin, le `<href>` sert à indiquer le chemin à suivre pour trouver l’image.

### 🌍 Favicon pour les navigateurs web modernes

Les navigateurs affichent un favicon dans les onglets, dans la barre d'adresse et dans la liste des favoris. Pour tous ces éléments, les icônes sont affichées en 16x16 pixels. Sur les ordinateurs modernes (particulièrement les Mac) et les smartphones dotés d'écrans avec une plus grande résolution, vous avez besoin de doubler la taille de l’image à 32x32 pixels.

```HTML
<!-- Pour tous les navigateurs -->
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16x16.png">
```

### 🤖 Google

Les moteurs de recherche comme Google affichent également un favicon à côté des résultats de recherche. Alors que DuckDuckGo utilise la même icône que les navigateurs (16x16 ou 32x32 pixels), Google affiche une icône légèrement plus grande de 48x48 pixels. En fait, [Google déclare explicitement](https://developers.google.com/search/docs/advanced/appearance/favicon-in-search) qu'il ne prend plus en compte les icônes en 16x16.  Google accepte toute icône de taille 48x48 ou des multiples de celle-ci.

C'est également la taille par défaut des icônes des applications sur l'écran d'accueil d'Android. Ainsi, lorsque les utilisateurs souhaitent épingler votre site Web comme raccourci sur leur écran d'accueil Android, vous devez également fournir des icônes en multiples de 48x48. Je recommande d'en fournir une en 48x48 et une en 192x192, qui est [la taille pour les appareils Android ayant une plus grande résolution](https://material.io/design/iconography/product-icons.html#grid-and-keyline-shapes).

```HTML
<!-- Pour Google et Chrome -->
<link rel="icon" type="image/png" sizes="48x48" href="favicon-48x48.png">
<link rel="icon" type="image/png" sizes="192x192" href="favicon-192x192.png">
```

### 🍏 Apple

Sur l'iPhone et l'iPad, les utilisateurs peuvent épingler un site web sur leur écran d'accueil (comme sur Android) où il apparaîtra comme l'icône d'une application native. Apple utilise des tailles différentes pour ses icônes :

* Pour l'iPhone, elles doivent être des multiples de 60x60. Comme tous les iPhone sont équipés d'écrans Retina depuis de nombreuses années, il suffit de fournir une icône en 180x180.
* Sur l'iPad, la taille des icônes des applications est de 83,5x83,5 ([sérieusement](https://developer.apple.com/design/human-interface-guidelines/ios/icons-and-images/app-icon/)). Mais comme tous les iPad ont des écrans Retina depuis plus de 10 ans maintenant, il est suffisant (et recommandé) de ne fournir qu'une icône de 167x167 pixels.

Apple étant Apple, ils ont encore une chose à dire sur les favicons : pour que Safari reconnaisse correctement vos icônes d'écran d'accueil, elles doivent être marquées avec `rel="apple-touch-icon"` au lieu de `rel="icon"`.

**Attention :** l’attribut `rel=“apple-touch-icon-precomposed”` est obsolète depuis la sortie d’iOS 7 en 2013.

```HTML
<!-- Pour iPad -->
<link rel="apple-touch-icon" type="image/png" sizes="167x167" href="favicon-167x167.png">
    
<!-- Pour iPhone -->
<link rel="apple-touch-icon" type="image/png" sizes="180x180" href="favicon-180x180.png">
```

**Note :** Depuis la sortie de Safari 12 en 2018, [l’utilisation de mask-icon n’est plus nécessaire](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/pinnedTabs/pinnedTabs.html), et supporte maintenant l’utilisation de favicons de manière classique.

### Microsoft

Avec l’arrivée de Windows 8 en 2012, Microsoft voulait démocratiser l’usage de “tuiles” pour afficher les applications, et il fallait donc s’adapter à ce besoin. Aujourd’hui, avec Windows 11 (et Windows 10 avant lui) Microsoft est revenu à quelque chose de plus classique.

De plus, Internet Explorer étant mort et enterré (remplacé par Edge), vous n’avez plus besoin de supporter aucun format spécifique à Microsoft (tile.png, tile-wide.png…).

### Le format ICO

Autrefois, les navigateurs recherchaient un fichier nommé favicon.ico dans votre répertoire racine. Ce n'est plus nécessaire car tous les navigateurs modernes supportent le format PNG pour ce type de fichier.

### Le format SVG

En théorie, avec le format SVG, un seul fichier couvrirait tous les cas d'utilisation. Mais [le SVG n'est pas pris en charge par tous les navigateurs](https://caniuse.com/?search=icon.svg) (surtout Safari) et d’autres services peuvent ne pas le prendre en compte non plus (moteurs de recherche, les plateformes de médias sociaux, les écrans d'accueil Android et iOS, etc.).

Au final, vous aurez toujours besoin de fournir des PNG en plusieurs tailles et il y a peu d'avantages à fournir un SVG en plus.

### Le fichier Web Manifest

La plupart des générateurs de favicons en ligne, ainsi que le fameux HTML5 Boilerplate ajoutent un fichier `*.webmanifest` à votre configuration, mais vous n’en avez probablement pas besoin.

{{< figure src="illustration-home-screen-icon.webp" title="Illustration par Velove Branding House sur Dribbble" alt="Illustation d'une icone sur la page d'accueil d'un smartphone" >}}

Les fichiers Web Manifest sont destinés aux PWA ([Progressive Web App](https://fr.wikipedia.org/wiki/Progressive_web_app)). Cette technologie lancée en 2015 par Google permet aux sites Web qui se comporter comme des applications natives sur mobile. Cependant, seul Android le prend en charge, [Apple ne semblant pas avoir la volonté d’implémenter](https://www.informatiquenews.fr/apple-naime-decidement-pas-les-pwa-71503) cette technologie sur iOS. Pour la plupart des sites web, l’intérêt est donc limité.

**EDIT :** Apple semble enfin décidé à avancer dans le bon sens avec la [publication de la beta iOS 15.4](https://firt.dev/ios-15.4b) qui va dans le sens d'une adoption des PWA, on espère donc voir l'implémentation arriver en même temps qu'iOS 16 !

## Conclusion

Comme vous pouvez le voir, de nombreuses options n'ont pas besoin d'être intégrées à l'heure où vous lisez ces lignes et vous pouvez vous contenter du strict nécessaire pour couvrir la grande majorité des cas.