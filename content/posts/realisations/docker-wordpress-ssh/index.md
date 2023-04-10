---
title: 'Créer et déployer un site WordPress en SSH avec Docker'
tags: []
categories: realisations
hero: /images/realisations/docker-wordpress-ssh/featured-image.svg
---

# Présentation

Le projet consiste à créer une image de conteneur Docker pour faciliter le déploiement et les tests de fonctionnalités sur des sites web WordPress en environnement local. Cette image regroupe toutes les dépendances nécessaires pour exécuter un site WordPress, comme le serveur web Apache, la base de données, WP-CLI et WordPress lui-même, ainsi que des modèles WordPress préinstallés. Cela permet de limiter les coûts et les risques liés aux déploiements en production.

# Objectifs, contexte, enjeu, risques

L'objectif principal de ce projet est de simplifier les tests de fonctionnalités sur des sites web WordPress en utilisant une image de conteneur Docker en environnement local. Cela permettra de disposer d'une solution flexible pour s'adapter aux besoins spécifiques de chaque projet en termes de versions de WordPress et de PHP, ainsi que les paramètres de base de données. En effectuant les tests localement, il est possible d'économiser des coûts et des risques liés aux déploiements en production, ainsi que de limiter les coûts et les risques liés aux déploiements en production. Les risques incluent les erreurs de configuration lors de l'utilisation de l'image de conteneur, les problèmes liés à la gestion des modèles WordPress, les problèmes liés à la configuration des ports et à l'utilisation de WP-CLI.

# Etapes

- Configuration des variables d'environnement : le fichier de variables d'environnement .env contient de nombreuses variables qui doivent être configurées correctement pour que le conteneur fonctionne correctement. Il faut spécifier les informations de base de données, les noms d'utilisateur et les mots de passe, ainsi que les versions de WordPress et de PHP souhaitées.

- Gestion des modèles WordPress : avant de déployer le conteneur, il est nécessaire d'installer les modèles WordPress dans le dossier config/templates. Les modèles doivent être installés avant de construire l'image de conteneur, et il faut reconstruire l'image pour ajouter un nouveau modèle.

- Construction de l'image de conteneur : le Dockerfile utilisé pour construire l'image de conteneur est assez complexe. Il reprend l'image WordPress officielle en spécifiant les versions de WordPress et de PHP souhaitées, il installe également les paquets openssh-server et mariadb-server pour créer un serveur SSH et permettre à WP-CLI de communiquer avec la base de données.

- Configuration des ports : il y a deux ports à configurer, un pour le serveur HTTP et un pour le serveur SSH. Il est important de s'assurer que ces ports sont libres sur l'hôte et qu'ils ne sont pas utilisés par d'autres applications en cours d'exécution.

- Utilisation de WP-CLI : WP-CLI est un outil en ligne de commande pour gérer les sites WordPress. Il est utilisé pour installer WordPress et les modèles, configurer les paramètres de base de données et effectuer des opérations courantes telles que la mise à jour des plugins et des thèmes. Les utilisateurs doivent être familiarisés avec cet outil pour utiliser pleinement cette image de conteneur.

# Acteurs

Les acteurs principaux seraient les développeurs et les administrateurs qui utilisent cette image de conteneur pour déployer et tester des sites web WordPress en environnement local.

# Résultats

Les résultats attendus étaient la simplification des processus de déploiement et de test de fonctionnalités sur des sites web WordPress, une flexibilité accrue pour s'adapter aux besoins spécifiques de chaque projet, et des économies de coûts et de risques liés aux déploiements en production. Les résultats obtenus ont confirmé ces attentes, en offrant une solution efficace pour faciliter les tests de fonctionnalités sur des sites web WordPress en utilisant une image de conteneur Docker en environnement local.

# Lendemains

Il est important de maintenir et mettre à jour régulièrement l'image de conteneur pour assurer son bon fonctionnement, surveiller les logs pour détecter les erreurs et problèmes potentiels, et rester à jour sur les mises à jour de WordPress et des composants utilisés pour assurer la compatibilité et la sécurité de l'image de conteneur.

# Mon regard critique

Globalement, l'utilisation d'une image de conteneur Docker pour les tests de fonctionnalités sur des sites web WordPress est une excellente idée qui permet de simplifier les processus de déploiement et de test, d'augmenter la flexibilité pour s'adapter aux besoins spécifiques de chaque projet, et d'économiser des coûts et des risques liés aux déploiements en production. Cependant, il est important de noter que la maintenance de l'image de conteneur et la surveillance des logs et des mises à jour de sécurité sont nécessaires pour s'assurer que l'image de conteneur fonctionne correctement et en toute sécurité. Il est également important de noter que les utilisateurs doivent être familiarisés avec les outils tels que WP-CLI pour utiliser pleinement cette image de conteneur.

# Quelques images
![Docker WordPress](/images/realisations/docker-wordpress-ssh/buildssh-login.png)