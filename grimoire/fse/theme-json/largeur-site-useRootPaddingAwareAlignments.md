# Largeur du site et useRootPaddingAwareAlignments

Nous allons commencer à remplir notre fichier `theme.json` en abordant la section de mise en page nommée **layout**. Deux étapes sont à prévoir :
1. Configurer les différentes largeurs de notre site ;
2. Activer une option pour que nos sections occupent toute la largeur de l’écran.

Nous allons nous concentrer sur la rubrique **settings > layout**, ainsi que sur une propriété au nom bien singulier : `useRootPaddingAwareAlignments`.

## Configurer la largeur du site

### Quelle est la largeur d’un site ?

Avant l’époque du responsive web design, la réponse était simple : 960px, car c’était une valeur qui se divisait facilement pour faire des colonnes. Aujourd’hui, avec le responsive web design, un site n’a pas de largeur prédéfinie : il est fluide. Cela dit, il est quand même utile de définir une largeur maximale.

Les sections s'étirent à l’infini, mais le contenu à l’intérieur a une limite afin de garantir une bonne lisibilité. Par exemple, sur le site de Gravity Forms, l’inspecteur du navigateur montre que la largeur maximale du site est de 1140px. 

Cependant, les articles du blog ont une largeur plus étroite, environ 880px, afin de respecter les règles typographiques concernant la lisibilité.

WordPress vous permet de définir deux largeurs de contenu :
- **contentSize** : pour vos contenus (pages simples, articles du blog) ;
- **wideSize** : pour toutes vos mises en pages avancées et landing pages.

Il est généralement conseillé de choisir une **contentSize** de manière à ce qu’une ligne de texte contienne entre 45 et 80 caractères. Cela dépendra aussi de la taille de la police définie pour les textes. Dans l’éditeur, vous aurez accès aux largeurs via le menu « Alignement », que ce soit pour les paragraphes, images, ou groupes.

---

## La pleine largeur pour les sections

Dans un design moderne, il est courant d’avoir des sections qui occupent toute la largeur de l’écran. Cependant, un petit problème peut survenir.

Lorsque vous insérez un bloc **Groupe**, vous pouvez le mettre en pleine largeur pour que sa couleur de fond occupe tout l’écran. Vous pouvez utiliser la barre d’outils au-dessus du bloc pour définir la largeur. Cependant, il peut rester des bandes blanches sur les côtés, ce qui n’est pas l'effet recherché.

Cela est dû aux marges de sécurité ajoutées par WordPress pour garantir un bon rendu sur les appareils mobiles. On peut l'observer dans le CSS généré par la page via l’inspecteur du navigateur.

Heureusement, WordPress offre la propriété **useRootPaddingAwareAlignments**, qui permet de résoudre ce problème.

### Fonctionnement de **useRootPaddingAwareAlignments**

En coulisses, WordPress adapte le CSS en ajoutant la classe `.has-global-padding` aux groupes. Cette classe déclare les marges internes, tandis que le `body` ne possède plus de marges. Cela permet de garantir que les sections occupent bien toute la largeur disponible.

---

## Options spécifiques de largeur pour les groupes

Lorsque vous insérez un bloc **Groupe** dans l’éditeur, des options de mise en page spécifiques apparaissent :

- La première option, activée par défaut, permet de contraindre le contenu à une largeur définie. En la désactivant, le contenu peut occuper toute la largeur du bloc. Cette option est utile pour les designs où le contenu doit occuper toute la largeur d’une section.
- La seconde option permet de surcharger les largeurs standard et étendues uniquement pour les éléments enfants de ce bloc.

Ces deux options offrent une flexibilité pour des cas particuliers, mais si vous souhaitez éviter de complexifier l’éditeur inutilement, des propriétés peuvent être ajoutées dans le `theme.json` pour désactiver ces menus.

### Propriétés dans `theme.json` :
- **allowCustomContentAndWideSize** : Désactive la possibilité de définir des largeurs standard et étendues personnalisées pour ce groupe ;
- **allowEditing** : Désactive toutes les options de mise en page.

Si vous souhaitez uniquement garder l’option pour mettre le contenu en pleine largeur, désactivez uniquement les largeurs personnalisées.

