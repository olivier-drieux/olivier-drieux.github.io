---
title: Battlesquad
hero: /images/realisations/battlesquad/featured-image.png
theme: Toha
description: Réalisation Battlesquad
menu:
    sidebar:
        name: Battlesquad
        identifier: rea-battlesquad
        parent: realisations
        weight: 2
---

## Battlesquad : promouvoir la compétition en ligne

**Grand passionnés de jeux-vidéo et de compétitions**, mon ami et moi avons décidé de créer en 2019 **l'association à but non lucratif Battlesquad**. Nous avons voulu mettre en place une **plateforme en ligne** pour organiser des **tournois de jeux vidéo** et promouvoir la **compétition entre joueurs**.
L'un des principaux enjeux de ce projet était de proposer une solution **innovante** et **fonctionnelle** pour les **organisateurs de tournois** et les **joueurs**, afin d'attirer l'attention des utilisateurs potentiels et générer de l'engagement. Cependant, il existait des risques liés à la **concurrence**, car de nombreux autres **sites web** proposaient déjà des fonctionnalités similaires, ce qui pouvait rendre difficile la différenciation de notre projet. Par ailleurs, le développement d'un **site web** peut s'avérer **complexe** et nécessiter des **ressources importantes** en termes de temps et de budget, ce qui pouvait également compromettre le succès du projet. Enfin, la **sécurité** et la **protection des données personnelles** des utilisateurs constituaient un enjeu majeur pour la crédibilité et la confiance des utilisateurs dans notre projet.

Dans le projet Battlesquad, différents acteurs étaient impliqués, tels que les **organisateurs de tournois**, les **joueurs**, les **partenaires** et les **sponsors**. Les organisateurs de tournois avaient pour mission de **planifier** et de **gérer les compétitions**, tandis que les joueurs participaient aux tournois et contribuaient à l'**engagement** de la plateforme. Les partenaires et les sponsors, quant à eux, soutenaient financièrement et matériellement le projet en fournissant des lots pour les tournois ou en aidant à la promotion de la plateforme.

## Les résultats impressionnants de notre expérience et de notre expertise

Dans un premier temps, nous avons travaillé sur la création de **maquettes** pour le **site web**, en réfléchissant à toutes les **fonctionnalités** que nous souhaitions inclure pour rendre le site **pratique** pour les **organisateurs de tournois** et **facile à utiliser** pour les **joueurs**.

Nous avons ensuite défini la **base de données** en créant un **diagramme**, afin de garantir que toutes les fonctionnalités seraient correctement intégrées. Nous avons mis toutes ces informations dans un **cahier des charges** pour en garder une trace.

<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; margin: 30px;">
  <img onclick="window.open('/images/realisations/battlesquad/diag-bdd.png')" src="/images/realisations/battlesquad/diag-bdd.png" width="40%" style="align-self: center; cursor: pointer;" alt="Diagramme de base de données" title="Cliquer pour zoomer" />
  <i>Diagramme de base de données</i>
</div>

Pour le développement, nous avons choisi **PHP** comme **langage de développement** car c'était le langage que nous apprenions à l'école **[IN'TECH](/posts/formations/ingenieur-intech)** à ce moment-là. Nous avons développé l'application sans utiliser de **framework**. Pour compenser cela, nous avons créé un fichier **core.php** qui était appelé par tous les autres fichiers PHP et qui contenait les informations nécessaires pour faire fonctionner une page du site web. Nous avons également implémenté un système de **traduction** en stockant toutes les traductions de texte du site dans un fichier **JSON**, ce qui nous a permis d'obtenir un site **multilingue** en utilisant les valeurs parsées du fichier JSON pour récupérer les chaînes de caractères à afficher.

<details><summary><strong>Cliquer pour voir un exemple de code utilisant la traduction</strong></summary>

Fichier JSON contenant les traductions de la page de tournoi :

```json
{
        ...,
        "tournoi": {
                ...,
                "statut": {
                        "fr": "Statut",
                        "en": "Status"
                },
                ...,
        },
        ...
}
```

Fichier `core.php` contenant le code pour récupérer les traductions :

```php
...

$file = file_get_contents("../../../sources/traductions.json");
$traductions = json_decode($file);

...
```

Exemple de code PHP utilisant la traduction :

```php

...

$tournoiTrad = $traductions->tournoi;

...

<div class="text-muted font-weight-bolder text-couleur">
        <?php
        if (isset($tournoiTrad->statut)) {
                echo $tournoiTrad->statut->$langue;
        } else {
                echo "Statut";
        }
        ?>
</div>

...
```

</details>

<br />

Le projet Battlesquad comprenait plus de **50 pages web**, avec des niveaux d'accès différenciés. Certaines pages n'étaient accessibles qu'**aux utilisateurs connectés**, tandis que d'autres étaient réservées aux **administrateurs du site** et aux **organisateurs de tournois**.

<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; margin: 30px;">
  <img onclick="window.open('/images/realisations/battlesquad/site.png')" src="/images/realisations/battlesquad/site.png" width="40%" style="align-self: center; cursor: pointer;" alt="Capture d'écran de l'accueil du site" title="Cliquer pour zoomer" />
  <i>Capture d'écran de l'accueil du site</i>
</div>

Le projet **Battlesquad** a connu un grand **succès**, avec plus de 50 **tournois organisés** pour plus de **11 000€ de gains** et plus de **10 000 utilisateurs** inscrits.
Le point culminant a été la LAN Fortnite de la **Occitania Gaming Convention** en novembre 2019, avec **2640€ de gains**, et le tournoi en ligne de la **ConfigoMatic CUP** en février 2020 avec **5000€ de gains**.

<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; margin: 30px;">
  <img onclick="window.open('/images/realisations/battlesquad/ogc.jpg')" src="/images/realisations/battlesquad/ogc.jpg" width="40%" style="align-self: center; cursor: pointer;" alt="Image de la Occitania Gaming Convention en novembre 2019" title="Cliquer pour zoomer" />
  <i>Image de la Occitania Gaming Convention en novembre 2019</i>
</div>

Cependant, malgré les résultats positifs obtenus lors des **tournois organisés** et de l'augmentation de la communauté, l'association **Battlesquad** et son **site web** ont malheureusement été fermés aujourd'hui.

## Rétrospective : retour sur notre aventure avec Battlesquad

En rétrospective, le projet **Battlesquad** était une **initiative intéressante** visant à promouvoir et partager le **savoir-faire** dans le domaine de la **compétition de jeux vidéo**. Les **objectifs** étaient clairs, et l'enjeu était pertinent. Cependant, il y a eu des **difficultés à maintenir** le projet à long terme, malgré les résultats positifs obtenus lors des **tournois organisés** et l'augmentation de la **communauté**. Une **planification à long terme** pour gérer ces **risques** et assurer la **viabilité** du projet aurait été bénéfique.

Il est important de souligner que même si le projet **Battlesquad** est terminé, les **leçons** et **connaissances** acquises grâce à cette **expérience** peuvent être appliquées à de **futurs projets** dans le domaine de la **compétition de jeux vidéo**.

L'utilisation d'un **framework** comme **[Symfony](/posts/competences-techniques/symfony)** ou **Laravel** aurait été plus simple et plus efficace pour le développement du site web **Battlesquad**. Ces frameworks offrent des **fonctionnalités préconstruites** pour faciliter la gestion de la **sécurité**, de la **base de données** et la **maintenance**. De plus, ils permettent une meilleure **évolutivité** en étant conçus pour être **modulaires** et ajouter de nouvelles **fonctionnalités**. L'utilisation d'un framework aurait donc permis une meilleure gestion des fonctionnalités de base, une meilleure évolutivité et une maintenance plus facile à long terme du site web.

Malgré la fermeture de l'association **Battlesquad** et de son site web, l'**expérience** acquise par les acteurs impliqués dans ce projet peut être utilisée pour développer de **nouveaux projets** dans le domaine de la **compétition de jeux vidéo**. Les **organisateurs de tournois**, les **joueurs** et les **partenaires** peuvent poursuivre leur engagement dans d'autres initiatives similaires, en mettant à profit les **compétences** et les **connaissances** acquises lors de leur participation au projet Battlesquad.

## Compétences liées

- [MySQL](/posts/competences-techniques/mysql) : la base de données de l'application a été développée avec MySQL.
- [Adaptabilité](/posts/competences-humaines/adaptabilite) : adaptation aux demandes des utilisateurs et aux mises à jour des jeux-vidéos.
- [Autonomie](/posts/competences-humaines/autonomie) : développement du projet sur mon temps libre.
- [Gestion de projet](/posts/competences-humaines/gestion-de-projet) : gestion de la partie développement de l'application tout en participant aux négociations clients et à la gestion des tournois.
- [Travail en équipe](/posts/competences-humaines/travail-en-equipe) : partage des développements de l'application avec mon ami.
