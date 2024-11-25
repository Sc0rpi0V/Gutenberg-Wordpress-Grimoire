# Les Atomes

## Introduction

Cette première partie peut sembler un peu complexe à appréhender. À première vue, on pourrait penser que les blocs sont les atomes de ce système. Cependant, il existe un niveau encore plus fondamental : les **éléments primitifs**.

---

## Les Atomes dans un Bloc : Exemple avec le Bloc Image

Prenons un exemple concret : le **bloc image** dans l'éditeur de contenu de WordPress. 

- [Bloc Image](/grimoire/img/atomes-blocs-gutenberg-2048x1330.jpg.avif)

### Description du Bloc Image

Ce bloc permet d’ajouter une image, mais il est composé de plusieurs sous-éléments. En l’occurrence :
1. **L’image elle-même** : l’élément visuel principal.
2. **La légende** : un texte facultatif qui accompagne l’image, souvent situé en dessous.

### Illustration

Le bloc image est un bon exemple pour comprendre cette distinction. Voici une représentation typique :
- Une image est insérée dans le contenu.
- Une légende décrivant l’image peut être ajoutée.

Ces deux éléments (l’image et la légende) sont les véritables **atomes** qui composent ce bloc.

---

## Les Légendes : Un Exemple d’Élément Primitif

Les légendes ne se limitent pas uniquement au bloc image. On peut également les retrouver dans d’autres blocs, comme :
- Les **galeries** : chaque image peut avoir une légende.
- Les **tableaux** : des textes explicatifs sous les tableaux.

### Personnalisation Globale des Légendes

Dans le **Full Site Editing (FSE)** de WordPress, il est possible de styliser ces légendes de manière globale, directement depuis l’éditeur de styles. Par exemple, on peut définir :
- La couleur des légendes.
- La police et le style appliqués.

#### Illustration

Dans l’éditeur de styles globaux, il existe une section spécifique dédiée aux éléments primitifs, permettant cette personnalisation.

- [Styles globaux Editeur](/grimoire/img/reglage-legendes-fse.jpg.avif)

---

## Les Boutons : Un Autre Exemple d’Élément Primitif

Les boutons constituent un autre exemple pertinent d’élément primitif. 

### Présence des Boutons dans Différents Blocs

Bien qu’ils soient souvent associés au **bloc « Boutons »**, les boutons apparaissent également dans d'autres contextes, comme :
- Les blocs de **recherche**.
- Le **bloc fichier**, permettant le téléchargement d’un document.

#### Illustration

Les boutons ne sont pas exclusifs à un seul bloc. On peut les retrouver dans plusieurs endroits de l’éditeur, renforçant leur statut d’élément réutilisable.

-[Boutons présents dans différents blocs](/grimoire/img/boutons-atomes-dans-blocs-gutenberg.jpg.avif)

### Personnalisation des Boutons dans le FSE

Dans l’éditeur de styles globaux, on peut définir des règles pour les boutons de manière indépendante, sans passer par un bloc spécifique. Par exemple :
- Modifier leur couleur.
- Ajuster leur bordure ou leur typographie.

---

## Ce que Sont les Atomes

Pour simplifier, on peut dire que les **atomes** sont des **éléments primitifs**. Ils sont encore plus basiques que les blocs eux-mêmes. En termes techniques, ces atomes sont souvent représentés par des balises HTML telles que :
- `<img>` pour les images.
- `<caption>` pour les légendes.
- `<a>` pour les liens.

---

## À Retenir

1. Les **atomes** sont des éléments fondamentaux qui composent les blocs.
2. Ces éléments peuvent être configurés de manière **indépendante des blocs** dans l’éditeur d’apparence de WordPress.
3. Cette distinction est particulièrement utile dans le contexte du **Full Site Editing (FSE)**, où la personnalisation globale des styles devient possible.

