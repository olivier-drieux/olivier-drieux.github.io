---
title: Docker
categories: competences-techniques
hero: /images/competences-techniques/docker/icon.svg
menu:
  sidebar:
    name: Docker
    identifier: ct-docker
    parent: competences-techniques
    weight: 5
---

## Présentation

Docker est une technologie de conteneurisation de logiciels qui permet de créer des environnements d'exécution isolés et portables. Les conteneurs Docker encapsulent toutes les dépendances logicielles nécessaires à l'exécution d'une application, ce qui facilite le déploiement de celle-ci sur différents environnements, tels que des machines locales, des serveurs cloud ou des conteneurs d'orchestration.

Cette compétence a été particulièrement mise en avant par la pandémie de Covid-19, qui a contraint de nombreuses entreprises à revoir leur organisation en termes de travail à distance et de collaboration en ligne. De plus en plus d'entreprises ont donc recours à des conteneurs Docker pour déployer des applications rapidement et facilement sur plusieurs machines ou environnements de développement.

## Mon expérience

Au cours de mon alternance, j'ai pu mettre en pratique mes compétences en Docker en créant plusieurs images pour faciliter le développement et le déploiement de projets. Pour rendre la maintenance des images plus simple et pour faciliter la connexion entre les différents conteneurs, j'utilise généralement Docker Compose.

Par exemple, j'ai créé une image Docker pour la base de données MySQL et Phpmyadmin, ce qui a permis d'automatiser et de simplifier la création de bases de données pour les différents projets.

<details><summary><strong>Cliquer pour voir le code</strong></summary>

```yaml
version: '3.1'

# Définition des services nécessaires pour l'application
services:
    # Service pour la base de données MariaDB
    db:
        image: mariadb # Utilise l'image Docker de MariaDB
        restart: always # Redémarre le service en cas de problème
        environment:
            MARIADB_ROOT_PASSWORD: password # Définit le mot de passe root de la base de données
        volumes:
            - db_data:/var/lib/mysql # Montre le volume pour stocker les données de la base de données

    # Service pour l'interface de gestion de la base de données via PHPMyAdmin
    phpmyadmin:
        image: phpmyadmin # Utilise l'image Docker de PHPMyAdmin
        restart: always # Redémarre le service en cas de problème
        ports:
            - 8080:80 # Redirige le port 8080 du host vers le port 80 du conteneur
        environment:
            - PMA_ARBITRARY=1 # Autorise la connexion à n'importe quelle base de données
            - PMA_HOST=db # Définit le host où se trouve la base de données (ici, le service "db")
            - PMA_USER=root # Définit le nom d'utilisateur pour se connecter à la base de données
            - PMA_PASSWORD=password # Définit le mot de passe pour se connecter à la base de données

# Définition du volume nécessaire pour stocker les données de la base de données
volumes:
    db_data:
```

</details>

Le code ci-dessus est utilisé pour créer deux conteneurs différents : un pour la base de données et un autre pour l'interface graphique Phpmyadmin. Ces deux conteneurs sont liés afin de permettre une connexion facile entre la base de données et l'interface graphique. Les données de la base de données sont stockées dans un volume, ce qui permet d'éviter toute perte de données en cas de suppression du conteneur.

J'ai également créé une image Docker pour tester le [déploiement automatique d'un site WordPress en SSH](/posts/realisations/docker-wordpress-ssh) avec WP-CLI en local. Cette image nous a permis de gagner un temps précieux en testant notre code de déploiement automatique directement sur notre machine plutôt que sur un serveur distant.

## Evolution et autocritique

Je considère avoir un niveau de maîtrise [initié](/posts/niveau-competences) de cette compétence, car j'ai une bonne compréhension de Docker et de son fonctionnement, mais il y a encore beaucoup de fonctionnalités et d'optimisations que je dois explorer pour améliorer mon utilisation de cette technologie.

Ma marge de progression réside principalement dans la contextualisation de la compétence, car Docker ne fonctionne pas toujours dans tous les cas. Il est important de comprendre les besoins spécifiques de chaque projet pour déterminer si Docker est la meilleure solution.

Pour moi, la compétence Docker est essentielle pour mon profil car elle permet de gérer efficacement les applications et les services. Je suis capable d'acquérir rapidement de nouvelles compétences, mais j'estime qu'il faut du temps et de la pratique pour maîtriser pleinement Docker.

## Conseils

- Prenez le temps de comprendre les concepts fondamentaux de Docker avant de vous lancer dans des projets plus complexes. En ayant une bonne compréhension de base, vous serez en mesure de construire des images Docker efficaces et de les intégrer facilement dans vos projets.

- Utilisez des outils tels que Docker Compose pour simplifier la création et la gestion de vos images Docker. Cela vous permettra de gagner du temps et de vous concentrer sur le développement de vos applications plutôt que sur la gestion de l'infrastructure.

- Assurez-vous de bien documenter vos images Docker et les processus de déploiement associés. Cela facilitera la collaboration avec les membres de l'équipe et vous aidera à maintenir des images Docker cohérentes et fiables au fil du temps.

## Réalisations liées

- [Docker WordPress SSH](/posts/realisations/docker-wordpress-ssh) : réalisation d'une image Docker pour le déploiement automatique d'un site WordPress en SSH avec WP-CLI en local.
- [OLAU](/posts/realisations/olau) : réalisation d'une image Docker pour la base de données MySQL et Phpmyadmin.
