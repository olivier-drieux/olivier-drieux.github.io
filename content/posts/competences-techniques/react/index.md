---
title: React
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

Bien que React soit une bibliothèque **polyvalente** et **adaptative**, la manière dont elle est utilisée peut varier en fonction du contexte et des spécificités du projet. Dans certaines situations, il peut être nécessaire de combiner React avec d'autres outils ou bibliothèques pour répondre à des besoins spécifiques, comme la gestion d'état avec Redux ou le **routage** avec React Router.

<div style="display: flex; flex-direction: column; align-items: center; justify-content: center; margin: 30px;">
  <img onclick="window.open('https://insights.stackoverflow.com/survey/2021#most-popular-technologies-webframe-prof')" src="/images/competences-techniques/react/survey.png" width="30%" style="align-self: center; cursor: pointer;" alt="React est la librairie la plus populaire parmi les professionnels en 2021" title="Cliquer pour zoomer" />
  <i>React est la librairie la plus populaire parmi les professionnels en 2021</i>
</div>

Dans un contexte professionnel, la maîtrise de React est un **atout majeur** pour les développeurs travaillant sur des projets web. En effet, eact est une bibliothèque essentielle pour les développeurs professionnels qui cherchent à créer des **applications web modernes**, **performantes** et **évolutives**, utilisée par de nombreuses **grandes entreprises** telles que **Facebook**, **Instagram**, **Netflix**, **Airbnb**, **Uber**, **Dropbox** et bien d'autres.

Une actualité récente en ce qui concerne React est la sortie de **React v18**, qui introduit une nouvelle fonctionnalité appelée **React Server Components**. Il s'agit d'une évolution majeure pour la création d'applications web **côté serveur avec React**, permettant de générer des composants React côté serveur de manière **asynchrone**, améliorant ainsi la **performance** et l'**expérience utilisateur**.

## Mon expérience

Pendant mon apprentissage en entreprise, j’ai créé un système de **pagination automatique** pour les pages qui affichent des informations dynamiques de l’application. Cette réalisation a permis d'améliorer significativement la performance et l'ergonomie de l'application Pegaseo. Grâce à ma compétence en **React**, j'ai su résoudre ce problème et contribuer efficacement à la réussite du projet.

<details><summary><strong>Cliquer pour voir le code</strong></summary>

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

</details>

Le code ci-dessus est un [**hook React personnalisé**](https://fr.reactjs.org/docs/hooks-intro.html) qui permet, grâce aux options données avec le paramètres `props`, de définir une requête [react-query](https://react-query.tanstack.com/) et de laisser au hook la **résponsabilité** de gérer la **pagination** de la page. Le hook renvoie un object contenant le résultat de la requête, les métadonnées de la pagination et un élément de pagination React. Il est important de noter que le hook utilise une **fonction de [debounce](https://www.techtarget.com/whatis/definition/debouncing#:~:text=Debouncing%20is%20removing%20unwanted%20input,hardware%20switches%2C%20programs%20and%20websites.)** pour éviter de mettre à jour la pagination trop souvent, ce qui permet d'éviter des requêtes inutiles.
Ce hook permet de **simplifier** le code des composants qui l'utilisent et de **réduire** le nombre de lignes de code. Il permet également de **centraliser** la logique de pagination dans un seul endroit, ce qui facilite la **maintenance** et la **réutilisation** du code.

## Développement et perspectives d'amélioration

Grâce à ma forte motivation et à ma curiosité constante pour les nouvelles technologies, j'ai pu rapidement acquérir et monter en compétences sur React. Cela m'a permis d'atteindre aujourd'hui un niveau de **maîtrise avancé**, me rendant autonome dans le développement et la mise en place de l'architecture d'applications web avec React.

Cependant, je reste toujours à l'affût des **dernières tendances** et des **nouvelles fonctionnalités** pour continuer à me perfectionner. Ma marge de progression en React consiste notamment à approfondir mes connaissances en matière de **performance**, en utilisant des fonctionnalités récentes telles que "**suspense**" ou "**lazy loading**". Je suis également intéressé par l'utilisation de **bibliothèques tierces** comme **Redux** ou **Next.js** pour améliorer la gestion de l'état de l'application et la mise en place de routes.

À moyen terme, je vise à devenir un **expert en React**, capable de concevoir et d'implémenter des applications complexes et performantes. Pour y parvenir, je prévois de suivre des **formations en ligne** et de participer à des **conférences** et **ateliers** sur React.

Dans mon poste actuel, la maîtrise de React est une compétence clé et une priorité pour réussir dans mes responsabilités de développeur. Les projets sur lesquels je travaille dépendent fortement de la qualité et de l'efficacité des applications web que je développe, et la maîtrise de React est essentielle pour atteindre ces objectifs. Par conséquent, l'amélioration continue de ma compétence en React reste une priorité pour moi, afin de contribuer au succès de mes projets et de mon équipe.

## Conseils

- **Commencez petit** : lorsque vous commencez à apprendre React, il est important de commencer par des projets simples avant de passer à des projets plus complexes. Cela vous permettra de mieux comprendre les concepts fondamentaux et de consolider vos connaissances.

- **Expérimentez** : n'ayez pas peur d'expérimenter avec les différentes fonctionnalités de React. Essayez de nouvelles choses, testez de nouvelles approches et apprenez de vos erreurs.

- **Soyez patient** : l'apprentissage de React peut être difficile et prendre du temps. Il est important de rester patient et persévérant pour progresser.

- **Restez à jour** : React est une technologie en constante évolution. Il est important de rester informé des dernières fonctionnalités et des meilleures pratiques pour continuer à améliorer vos compétences.

- **Pratiquez régulièrement** : la pratique régulière est essentielle pour maintenir et améliorer vos compétences en React. Trouvez des projets personnels ou des projets open-source auxquels vous pouvez contribuer pour vous exercer.

- **Apprenez à travailler en équipe** : dans le monde professionnel, il est souvent nécessaire de travailler en équipe. Apprenez à collaborer avec d'autres développeurs en utilisant des outils de gestion de code tels que Git, et pratiquez les bonnes pratiques de communication pour travailler efficacement en équipe.


## Réalisations liées

- [Pegaseo](/posts/realisations/pegaseo) : réalisation d'une application web
