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

**MySQL** est un système de gestion de base de données relationnelles, largement utilisé dans le monde professionnel. Cette compétence consiste à maîtriser les différentes fonctionnalités mises à disposition par **MySQL**, telles que les **procédures stockées**, les **triggers**, les **vues**, les **événements**, etc. pour stocker, gérer et surveiller les données d'une application.

Dans un contexte professionnel, **MySQL** est utilisé dans de nombreuses entreprises pour stocker et gérer des données de manière efficace et sécurisée. Par exemple, des sites web de commerce électronique peuvent stocker des informations sur les commandes, les clients et les produits dans une base de données **MySQL**. Des entreprises de logistique peuvent stocker des informations sur les expéditions, les stocks et les fournisseurs. Des applications de gestion de projet peuvent stocker des informations sur les tâches, les ressources et les échéances.

Il est important de noter que la mise en œuvre de **MySQL** peut varier en fonction des spécificités du projet et des contraintes techniques ou organisationnelles. Par exemple, l'utilisation de **MySQL** dans un environnement de haute disponibilité nécessitera des connaissances approfondies sur la **réplication** et la **gestion des pannes**. Il est donc crucial d'adapter son approche en fonction du contexte et des besoins de chaque situation.

## Mon expérience

J'ai personnellement eu l'occasion de mettre en œuvre la compétence **MySQL** dans le cadre de mon **alternance**. J'ai participé au développement d'une **API** où les données étaient stockées dans une base de données MySQL. J'ai effectué une **migration des données** d'une ancienne version de l'application vers la nouvelle version. Pour cela, j'ai formaté les données en utilisant une requête **SELECT**, puis j'ai extrait ces données dans un fichier avec la commande `mysqldump`. J'ai par la suite simplement importé les données dans la nouvelle base de données avec la commande `mysql < fichier.sql`.

J'ai également créé des **procédures stockées** pour mettre à jour les données de manière automatisée.
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

**Ici, la procédure stockée** cherche un produit disponible dans la base de données, l'assigne au client qui en fait la demande, le marque comme indisponible et renvoie les informations sur ce produit.

La **procédure stockée** offre plusieurs avantages pour la gestion de la base de données. Tout d'abord, grâce à l'utilisation de transactions **START** et **COMMIT**, les opérations effectuées dans la procédure stockée sont exécutées de manière atomique, ce qui signifie que toutes les opérations doivent être complétées avec succès ou qu'aucune d'entre elles ne sera appliquée. Cela garantit que les modifications apportées à la base de données sont cohérentes et qu'en cas d'erreur, elles sont annulées.

De plus, cette procédure stockée utilise des **verrous** pour verrouiller les lignes lors de la lecture et de la mise à jour des données, ce qui garantit que les données ne seront pas modifiées simultanément par d'autres utilisateurs, ce qui peut entraîner des erreurs ou des incohérences dans la base de données.

En outre, les procédures stockées sont exécutées du côté du **serveur de base de données** et ne nécessitent pas de transfert de données entre le client et le serveur. Cela peut améliorer les performances et la vitesse de traitement.

Enfin, la procédure stockée offre une **interface simple** pour accéder et gérer les données dans la base de données, ce qui peut aider à simplifier les opérations complexes et améliorer l'efficacité et la cohérence des données stockées.

## Développement et perspectives d'amélioration

Je considère avoir un niveau de maîtrise **satisfaisant** en **MySQL**, mais je suis conscient de la nécessité de **progresser**. La mise en œuvre de MySQL varie selon le contexte, et il est crucial de comprendre les **besoins spécifiques** de chaque projet pour choisir les fonctionnalités adaptées, comme la **réplication** et la **gestion des pannes** dans un environnement de **haute disponibilité**.

MySQL est **essentiel** dans mon profil professionnel, car il me permet de **gérer efficacement** les données de mes applications. L'apprentissage est un **processus continu** et je dois rester à jour avec les **nouvelles versions** et **fonctionnalités**.

Ma **marge de progression** inclut de travailler sur des **projets plus complexes**, de me familiariser avec des **outils avancés** et d'approfondir mes connaissances sur l’**optimisation des requêtes SQL**. Dans mon **projet professionnel**, j’aspire à devenir un **expert en ingénierie des bases de données**, capable de concevoir et d’optimiser des systèmes de gestion de données **performants** et **fiables**.

Pour atteindre cet objectif, je compte suivre une **formation en ligne** sur les aspects avancés de MySQL et je prévois de me former sur d’autres **systèmes de gestion de bases de données** pour élargir mes compétences.

La compétence MySQL occupe une **place importante** dans mon métier actuel d’**ingénieur en développement logiciel**, car elle me permet de concevoir et de développer des applications **performantes** et **fiables**. En tant qu’expert en ingénierie des bases de données, cette compétence est **cruciale** pour mon **succès professionnel** et ma capacité à apporter de la **valeur** aux projets sur lesquels je travaille.

## Conseils

- **Maîtrisez les bases** : Assurez-vous de bien comprendre les concepts fondamentaux de MySQL, tels que les tables, les clés primaires et étrangères, les index et les jointures. Ces connaissances solides vous permettront de créer des bases de données bien structurées et performantes.
    
- **Apprenez les bonnes pratiques** : Familiarisez-vous avec les bonnes pratiques en matière de conception et de gestion des bases de données, comme la normalisation, l'optimisation des requêtes et la gestion des transactions. Cela vous aidera à développer des applications plus efficaces et évitera des problèmes potentiels à l'avenir.
    
- **Automatisez et sécurisez** : Apprenez à utiliser les fonctionnalités avancées de MySQL, telles que les procédures stockées, les triggers et les événements, pour automatiser les tâches récurrentes et renforcer la sécurité et l'intégrité des données.
    
- **Pratiquez et expérimentez** : Travaillez sur des projets variés et confrontez-vous à des problématiques différentes pour acquérir de l'expérience et développer votre compréhension de MySQL. N'hésitez pas à expérimenter et à apprendre de vos erreurs pour améliorer vos compétences.

## Réalisations liées

- [Pegaseo](/posts/realisations/pegaseo) : réalisation d'une API avec une base de données MySQL.
- [Théâtre du jour](/posts/realisations/theatre-du-jour) : réalisation d'une API avec une base de données MySQL.
- [Battlesquad](/posts/realisations/battlesquad) : réalisation d'un site web avec une base de données MySQL.
