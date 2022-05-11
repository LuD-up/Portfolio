---
title: "Plausible, l'outil d'analyse de trafic qui respecte la vie privée"
description: "Découvrez comment remplacer Google Analytics par Plausible, un outil d'analyse de trafic de site web open source qui respecte la vie privée."
date: 2020-10-03T17:00:00Z
draft: false
---

Difficile de parler d'outils d'analyse de trafic pour les sites web sans mentionner Google Analytics, qui cumule à lui seul [80%  du marché](https://fr.wikipedia.org/wiki/Google_Analytics) dans ce domaine.

Pour faire simple, un outil d'analyse de trafic sert aux administrateurs des différents sites que vous consultez à savoir qui vous êtes, sur quelles pages vous vous rendez, pour combien de temps etc. De nombreuses données sont donc collectées pour pouvoir donner une vue d'ensemble du parcours des utilisateurs.

Cependant, de nombreux problèmes sont à souligner concernant Google Analytics :

**Surdimensionné**  
Google Analytics vous donne tout un tas de données extrêmement pointues, mais tout cela augmente drastiquement la complexité du service, et il est souvent difficile de s'y retrouver. De plus ces données sont peut-être utiles à un département marketing, mais pas au commun des mortels.

**Temps de chargement**  
Pour collecter autant de données, le script de Google pèse lourd ! 45.7KB en plus à télécharger pour chaque utilisateur, et pour chaque page de votre site.

**Précision**  
De nombreux navigateurs bloquent l'accès à Google Analytics (Safari, Brave, [uBlock Origin](https://ublockorigin.com/), la précision des données fournies par le service sont donc à remettre en question car les utilisateurs de ces services n'apparaîtrons pas dans vos statistiques.

**Cookies et RGPD**  
L'utilisation du service de Google vous oblige à afficher une bannière qui informe vos utilisateurs du dépôt de cookies sur leurs ordinateurs, et la collecte de données personnelles.

**Format propriétaire**  
Vous ne pouvez pas savoir ce qu'il se passe en utilisant le script sur votre site, vous devez faire confiance à Google.

**Vie privée**  
Google partage vos données au plus offrant. C'est même son business model. 

## Quelles alternatives ?

[Matomo](https://fr.matomo.org/) (anciennement Piwik) était jusqu'à peu l'une des seules alternatives open source à Google, mais il ne corrige que les deux derniers points soulevé ci-dessus, de plus, il nécessite d'avoir un serveur dédié pour l'installer, ce qui ajoute en complexité.

## Présentation de Plausible

[Plausible.io](https://plausible.io/) est un outil d'analyse d'audience pour vos sites web qui corrige de nombreux problèmes comparé à ses concurrents.

![Tableau de bord de Plausible.io](plausible-preview.jpg)

**Légèreté**  
Le script de Plausible est 45 fois plus petit (moins d'1KB) que celui de Google. Votre site est donc plus rapide à charger.

**Respect de votre vie privée**  
Plausible ne récolte aucune donnée personnelle et respecte la RGPD. Vous n'avez donc pas besoin d'ajouter une bannière demandant d'accepter des Cookies.

**Open Source**  
Étant un logiciel open source, vous pouvez consulter, et contribuer au code sur leur [dépôt Github](https://github.com/plausible/analytics).

**Simple d'utilisation**  
Contrairement à Google Analytics qui vous propose une infinité de sous sections et filtres à mettre en place, Plausible mise sur la simplicité avec un tableau de bord sur une page, où toutes les données pertinentes sont regroupées.

**Autres fonctionnalités**  
Ils y a déjà quelques fonctionnalités qui peuvent être très utiles comme [l'intégration de Google Search Console](https://docs.plausible.io/google-search-console-integration), [la planification d'objectifs](https://docs.plausible.io/goal-conversions), ou [la notification par mail](https://docs.plausible.io/email-reports) chaque semaine de vos audiences. Le logiciel étant encore jeune, d'autres fonctionnalités sont à prévoir !

**Transparence et éthique**  
L'équipe derrière ce logiciel est très transparente et à cheval sur l'éthique. Ils détaillent par exemple sur leur blog [15 techniques marketing auxquelles ils ont dit non](https://plausible.io/blog/best-marketing-practices), et ont  mis en accès libre leur tableau de bord, que [vous pouvez consulter ici](https://plausible.io/plausible.io).

### Le prix

Une période d'essai de 30 jours est proposée afin de se familiariser avec le produit et savoir si vous voulez passer le cap. Au delà des 30 jours gratuits il faudra payer en fonction du nombre de pages vues par mois. Consultez le [tableau des prix](https://plausible.io/#pricing) pour en savoir plus.

### Un développement actif

L'auto-hébergement est actuellement en développement. L'équipe de Plausible ayant besoin de testeurs pour faire avancer le projet, [n'hésitez pas à l'essayer](https://plausible.io/blog/self-hosted-web-analytics-beta) !  
Les deux co-fondateurs ont d'ailleurs discuté d'une potentielle version sans JavaScript, vous pouvez [écouter le podcast de ChangeLog](https://changelog.com/podcast/396) (en anglais) pour en savoir plus.

Si vous voulez vous tenir au courant des futures évolutions vous pouvez consulter [leur roadmap](https://plausible.nolt.io/roadmap).

## Conclusion

Un nouveau produit pour remplacer des services des GAFAM est toujours une bonne nouvelle !

Ici, avec Plausible, une alternative est donc possible, et celle-ci est très agréable à utiliser au quotidien. Une attention particulière sur le design et l'expérience utilisateur à été faite et c'est un plaisir de voir émerger ce genre d'outil dans le monde du libre.

Dites moi ce que vous en pensez, et si vous comptez l'utiliser sur vos sites, votre avis m'intéresse !