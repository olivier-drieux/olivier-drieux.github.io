---
title: MySQL
categories: competences-techniques
hero: /images/competences-techniques/mysql/featured-image.svg
menu:
  sidebar:
    name: MySQL
    identifier: ct-mysql
    parent: competences-techniques
    weight: 4
---

## Présentation
MySQL est un système de gestion de base de données relationnelles, largement utilisé dans le monde professionnel. Cette compétence consiste à maîtriser les différentes fonctionnalités mises à disposition par MySQL, telles que les procédures stockées, les triggers, les vues, les événements, etc. pour stocker, gérer et surveiller les données d'une application.

Dans un contexte professionnel, MySQL est utilisé dans de nombreuses entreprises pour stocker et gérer des données de manière efficace et sécurisée. Par exemple, des sites web de commerce électronique peuvent stocker des informations sur les commandes, les clients et les produits dans une base de données MySQL. Des entreprises de logistique peuvent stocker des informations sur les expéditions, les stocks et les fournisseurs. Des applications de gestion de projet peuvent stocker des informations sur les tâches, les ressources et les échéances.

## Mon expérience
J'ai personnellement eu l'occasion de mettre en œuvre la compétence MySQL dans le cadre de mon alternance. J'ai participé au développement d'une API où les données étaient stockées dans une base de données MySQL. J'ai effectué une migration des données d'une ancienne version de l'application vers la nouvelle version. Pour cela, j'ai formaté les données en utilisant une requête SELECT, puis j'ai extrait ces données dans un fichier avec la commande `mysqldump`. J'ai par la suite simplement importé les données dans la nouvelle base de données avec la commande `mysql < fichier.sql`.

J'ai également créé des procédures stockées pour mettre à jour les données de manière 
automatisée.
```sql
CREATE PROCEDURE get_available_product()
BEGIN
    DECLARE product_id INT;
    START TRANSACTION;
        /* Trouver un produit disponible et assigner l'ID du produit trouvé à la variable product_id */
        SELECT id INTO product_id FROM products WHERE is_available = 1 AND quantity > 0 LIMIT 1
        /* Verrouiller la ligne pour la mise à jour */
        FOR UPDATE;
        /* Marquer le produit comme indisponible */
        UPDATE products SET is_available = 0 WHERE id = product_id;
        /* Renvoyer les données du produit */
        SELECT * FROM products WHERE id = product_id;
    COMMIT WORK;
END
```
Ici, la procédure stockée cherche un produit disponible dans la base de données, l'assigne au client qui en fait la demande, le marque comme indisponible et renvoie les informations sur ce produit.

La procédure stockée offre plusieurs avantages pour la gestion de la base de données. Tout d'abord, grâce à l'utilisation de transactions START et COMMIT, les opérations effectuées dans la procédure stockée sont exécutées de manière atomique, ce qui signifie que toutes les opérations doivent être complétées avec succès ou qu'aucune d'entre elles ne sera appliquée. Cela garantit que les modifications apportées à la base de données sont cohérentes et qu'en cas d'erreur, elles sont annulées.

De plus, cette procédure stockée utilise des verrous pour verrouiller les lignes lors de la lecture et de la mise à jour des données, ce qui garantit que les données ne seront pas modifiées simultanément par d'autres utilisateurs, ce qui peut entraîner des erreurs ou des incohérences dans la base de données.

En outre, les procédures stockées sont exécutées du côté du serveur de base de données et ne nécessitent pas de transfert de données entre le client et le serveur. Cela peut améliorer les performances et la vitesse de traitement.

Enfin, la procédure stockée offre une interface simple pour accéder et gérer les données dans la base de données, ce qui peut aider à simplifier les opérations complexes et améliorer l'efficacité et la cohérence des données stockées.

## Evolution et autocritique
Je considère avoir un niveau de maîtrise satisfaisant en MySQL, mais je suis conscient que je peux encore progresser. En effet, la mise en œuvre de MySQL peut varier en fonction du contexte, et il est important de comprendre les besoins spécifiques de chaque projet pour choisir les fonctionnalités les plus adaptées.

La compétence MySQL est une compétence essentielle dans mon profil professionnel, car elle me permet de gérer efficacement les données de mes applications. Je considère qu'elle est une priorité car elle est largement utilisée dans de nombreux domaines professionnels.

J'ai une bonne vitesse d'acquisition de la compétence, mais je suis conscient que l'apprentissage est un processus continu et que je dois rester à jour avec les nouvelles versions et fonctionnalités de MySQL.

Ma marge de progression dans la compétence MySQL serait de travailler sur des projets plus complexes et de me familiariser avec des outils plus avancés tels que MySQL Workbench. Je pourrais également approfondir mes connaissances sur l'optimisation des requêtes SQL pour améliorer les performances des bases de données.

## Conseils
En recul sur la compétence, je conseille de se familiariser avec l'interface de gestion de base de données MySQL, telle que phpMyAdmin, pour faciliter la gestion et la surveillance des données. Il est également important de comprendre les concepts de base de la gestion de base de données relationnelles, tels que les tables, les clés primaires et étrangères, les index, etc.

## Réalisations liées
- [Pegaseo](/posts/realisations/pegaseo) : réalisation d'une API avec une base de données MySQL
- [OLAU](/posts/realisations/olau) : réalisation d'une API avec une base de données MySQL
- [Théâtre du jour](/posts/realisations/theatre-du-jour) : réalisation d'une API avec une base de données MySQL
- [Battlesquad](/posts/realisations/battlesquad) : réalisation d'un site web avec une base de données MySQL
