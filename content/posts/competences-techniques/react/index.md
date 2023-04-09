---
title: React
date: 2023-01-01
tags: ["react","javascript","typescript","web","application web"]
categories: competences-techniques
hero: /images/competences-techniques/react/featured-image.png
menu:
  sidebar:
    name: React
    identifier: ct-react
    parent: competences-techniques
    weight: 2
---

## Présentation
React est une bibliothèque **JavaScript** **open-source** développée par **Facebook** qui permet de construire des **interfaces utilisateur interactives** pour les **applications web**. Utilisant une approche **déclarative**, elle permet aux développeurs de créer des **composants réutilisables** qui peuvent être facilement **manipulés** et mis à jour en temps réel, sans avoir à se soucier de la **gestion du DOM**. Cette approche facilite la **collaboration** entre les différents membres de l'équipe de développement et permet un **développement plus rapide** et plus **efficace**. De plus, React offre des **performances élevées** grâce à sa capacité à mettre à jour dynamiquement les composants sans recharger la page entière, ce qui rend l'application plus **rapide** et plus **fluide** pour les utilisateurs. Enfin, React est soutenu par une **communauté très active** et offre de nombreux **outils** et **bibliothèques tiers** pour faciliter le développement.

<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; margin: 30px;">
  <img onclick="window.open('https://insights.stackoverflow.com/survey/2021#most-popular-technologies-webframe-prof')" src="/images/competences-techniques/react/survey.png" width="30%" style="align-self: center; cursor: pointer;" alt="React est la librairie la plus populaire parmi les professionnels en 2021" title="Cliquer pour zoomer" />
  <i>React est la librairie la plus populaire parmi les professionnels en 2021</i>
</div>

Dans un contexte professionnel, la maîtrise de React est un **atout majeur** pour les développeurs travaillant sur des projets web. En effet, eact est une bibliothèque essentielle pour les développeurs professionnels qui cherchent à créer des **applications web modernes**, **performantes** et **évolutives**, utilisée par de nombreuses **grandes entreprises** telles que **Facebook**, **Instagram**, **Netflix**, **Airbnb**, **Uber**, **Dropbox** et bien d'autres.

Une actualité récente met en avant l'importance de React dans le monde professionnel. En **mars 2021**, **Netflix** a publié un article sur son blog, expliquant comment ils ont amélioré la **performance** de leur application web grâce à React. Ils ont notamment utilisé une technique appelée "**suspense**" pour améliorer le **temps de chargement** de leur page d'accueil, qui a permis d'augmenter le **taux de conversion** des utilisateurs.

## Réalisation
J'ai eu l'opportunité de mettre en pratique mes compétences en React lors de mon alternance chez **Linkweb**. J'ai participé au développement d'une application web nommée ["Pegaseo"](/posts/realisations/pegaseo), développée entièrement avec React. J'ai commencé le projet avec peu de connaissances dans cette bibliothèque, mais j'ai rapidement monté en compétences et j'ai pu être **opérationnel** pour le projet en peu de temps.

Pendant mon **apprentissage en entreprise**, j'ai créé un **système de pagination automatique** pour les pages qui affichent des **informations dynamiques** de l'application.
```tsx
export default function usePagination<TData = unknown>(props: IUsePaginationProps<TData>): IUsePaginationReturn<TData> {
    // Use of react hooks
    const [meta, setMeta] = React.useState<Partial<IMeta>>({
        page: props.initialPage ?? 1,
        itemsPerPage: props.itemsPerPage ?? undefined,
        pageCount: 1,
    });

    // Define a debounced meta setter
    const debouncedSetMeta = debounce(setMeta, 300);

    // Use of react-query hooks
    // Define the query options with the meta
    const queryOptions = props.queryOptions(meta);
    // Use of custom react-query hook to query the data
    const queryResult = useQuery<TData>({
        ...queryOptions,
        onSuccess: response => {
            // Call the onSuccess callback if defined
            queryOptions.onSuccess && queryOptions.onSuccess(response);
            // Set the meta if defined
            undefined !== response.meta && debouncedSetMeta(response.meta);
        },
    });

    // Create the pagination element
    const paginationElement = React.useMemo(() => (
        undefined !== meta.pageCount && 1 < meta.pageCount ? (
            <Pagination
                pageCount={meta.pageCount}
                cssx={{ alignSelf: 'center' }}
                onPageChange={(_, page) => debouncedSetMeta(current => ({ ...current, page }))}
            />
        ) : null
    ), [debouncedSetMeta, meta.pageCount]);

    return { queryResult, meta, paginationElement };
}
```
Ce code est un [**hook React personnalisé**](https://fr.reactjs.org/docs/hooks-intro.html) qui permet, grâce aux options données avec le paramètres `props`, de définir une requête [react-query](https://react-query.tanstack.com/) et de laisser au hook la **résponsabilité** de gérer la **pagination** de la page. Le hook renvoie un object contenant le résultat de la requête, les métadonnées de la pagination et un élément de pagination React. Il est important de noter que le hook utilise une **fonction de [debounce](https://www.techtarget.com/whatis/definition/debouncing#:~:text=Debouncing%20is%20removing%20unwanted%20input,hardware%20switches%2C%20programs%20and%20websites.)** pour éviter de mettre à jour la pagination trop souvent, ce qui permet d'éviter des requêtes inutiles.
Ce hook permet de **simplifier** le code des composants qui l'utilisent et de **réduire** le nombre de lignes de code. Il permet également de **centraliser** la logique de pagination dans un seul endroit, ce qui facilite la **maintenance** et la **réutilisation** du code.

## Evolution et autocritique
Je suis aujourd'hui **autonome** sur le développement de l'application avec React et je participe à la **mise en place de l'architecture** de l'application. J'ai également travaillé sur d'autres projets utilisant cette bibliothèque, ce qui me permet d'affirmer mon niveau de **maîtrise avancé**.

Ma **marge de progression** en React est de continuer à **approfondir** mes **connaissances** en matière de **performance**, notamment en utilisant les dernières **fonctionnalités** telles que **"suspense"** ou **"lazy loading"**. Je suis également intéressé par l'utilisation de **bibliothèques tierces** telles que **Redux** ou **Next.js** pour améliorer la **gestion de l'état** de l'application et la mise en place de **routes**.

La maîtrise de React est **essentielle** dans mon profil de développeur et constitue une compétence de **haut niveau** de **priorité** pour moi. Je souhaite continuer à l'**approfondir** et à l'appliquer sur de nouveaux projets passionnants.

En ce qui concerne ma **vitesse d'acquisition** de cette compétence, j'ai pu apprendre et monter en compétences rapidement grâce à une **forte motivation** et une **curiosité constante** pour les nouvelles technologies. Cependant, je reste toujours à l'affût des **dernières tendances** et des **nouvelles fonctionnalités** afin de continuer à me perfectionner.

## Conseils
Pour réussir dans l'apprentissage de la compétence React, il est important de **commencer petit**, d'**expérimenter**, de faire **preuve de patience**, de **rester à jour** et de **pratiquer régulièrement**. Il est également important d'apprendre à **travailler en équipe** pour collaborer efficacement avec d'autres développeurs.

## Réalisation liée
- [Pegaseo](/posts/realisations/pegaseo) : réalisation d'une application web
