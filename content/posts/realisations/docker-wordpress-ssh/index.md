---
title: Docker WordPress SSH
categories: realisations
hero: /images/realisations/docker-wordpress-ssh/featured-image.svg
menu:
    sidebar:
        name: Docker WordPress SSH
        identifier: rea-docker-wordpress-ssh
        parent: realisations
        weight: 5
---

# Créer et déployer un site WordPress en SSH avec Docker
Le **déploiement** et les **tests de fonctionnalités** sur des **sites web WordPress** peuvent être une tâche fastidieuse et risquée, surtout en **production**. Pour simplifier ce processus, il est possible d'utiliser une **image de conteneur Docker**. Dans cet article, nous allons présenter la réalisation d'un projet qui utilise une image de conteneur Docker pour les tests de fonctionnalités sur des sites web WordPress en **environnement local**.

L'objectif principal de ce projet était de simplifier les **tests de fonctionnalités** sur des **sites web WordPress** en utilisant une **image de conteneur Docker** en **environnement local**. Cette approche permet de disposer d'une solution **flexible** pour s'adapter aux besoins spécifiques de chaque projet en termes de versions de WordPress et de PHP, ainsi que les **paramètres de base de données**. En effectuant les **tests localement**, il est possible d'économiser des **coûts** et des **risques** liés aux déploiements en **production**.

# Réalisation d'un projet Docker pour des déploiements WordPress sans effort
Le projet consistait à créer une **image de conteneur Docker** regroupant toutes les **dépendances** nécessaires pour exécuter un site WordPress, comme le **serveur web Apache**, la **base de données**, WP-CLI et WordPress lui-même, ainsi que des **modèles WordPress** préinstallés.

La première étape a consisté à **configurer les variables d'environnement**, notamment les **informations de base de données**, les **noms d'utilisateur** et les **mots de passe**, ainsi que les **versions de WordPress et de PHP** souhaitées. Ensuite, nous avons installé les **modèles WordPress** dans le dossier **config/templates** avant de déployer le conteneur. Les modèles doivent être installés avant de construire l'image de conteneur, et il faut **reconstruire l'image pour ajouter un nouveau modèle**.

La **construction de l'image de conteneur** a été effectuée en utilisant un **Dockerfile complexe** qui reprend l'image WordPress officielle en spécifiant les versions de WordPress et de PHP souhaitées. Il installe également les paquets **openssh-server** et **mariadb-server** pour créer un **serveur SSH** et permettre à WP-CLI de communiquer avec la base de données.

La **configuration des ports** a été effectuée pour le serveur HTTP et le serveur SSH, en s'assurant qu'ils étaient libres sur l'hôte et qu'ils n'étaient pas utilisés par d'autres applications en cours d'exécution.

Enfin, l'utilisation de **WP-CLI** a été nécessaire pour installer WordPress et les modèles, configurer les **paramètres de base de données** et effectuer des opérations courantes telles que la **mise à jour des plugins et des thèmes**. Les utilisateurs doivent être familiarisés avec cet outil pour utiliser pleinement cette image de conteneur.

<div style="display: flex; flex-direction: row; align-items: center; justify-content: center; gap: 30px;">
    <div style="display: flex; flex-direction: column; align-items: center; justify-content: center; width: 40%">
        <img onclick="window.open('/images/realisations/docker-wordpress-ssh/buildssh-login.png')" src="/images/realisations/docker-wordpress-ssh/buildssh-login.png" style="align-self: center; cursor: pointer;" alt="Construction de l'image Docker et connexion au serveur SSH" title="Cliquer pour zoomer" />
        <i>Construction de l'image Docker et connexion au serveur SSH</i>
    </div>
    <div style="display: flex; flex-direction: column; align-items: center; justify-content: center; width: 40%">
        <img onclick="window.open('/images/realisations/docker-wordpress-ssh/wp-dlapache.png')" src="/images/realisations/docker-wordpress-ssh/wp-dlapache.png" style="align-self: center; cursor: pointer;" alt="Déploiement d'un site WordPress avec WP-CLI et accès en localhost" title="Cliquer pour zoomer" />
        <i>Déploiement d'un site WordPress avec WP-CLI et accès en localhost</i>
    </div>
</div>

## Rétrospective : Comment nous avons simplifié les tests WordPress grâce à Docker
Les résultats obtenus ont confirmé les attentes, en offrant une solution efficace pour faciliter les tests de fonctionnalités sur des sites web **WordPress** en utilisant une image de conteneur **Docker** en environnement local. Les avantages incluent la simplification des processus de déploiement et de test, une **flexibilité** accrue pour s'adapter aux besoins spécifiques de chaque projet, et la réduction des **coûts** et des **risques** liés aux déploiements en production.

En utilisant cette image de conteneur Docker, nous avons pu créer des environnements de test rapidement et facilement, avec des versions spécifiques de WordPress et de PHP, ainsi que les paramètres de base de données nécessaires pour chaque projet. De plus, en testant localement, nous avons pu détecter et corriger les **erreurs** plus rapidement et éviter les problèmes en production.

## Compétences liées
- [Docker](/posts/competences-techniques/docker) : création d'une image de conteneur Docker.
- [MySQL](/posts/competences-techniques/mysql) : création d'une base de données pour WordPress.
- [Adaptabilité](/posts/competences-humaines/adaptabilite) : formation sur l'utilisation de Docker.
