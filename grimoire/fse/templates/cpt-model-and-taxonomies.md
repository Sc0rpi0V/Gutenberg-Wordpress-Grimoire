# Les Modèles des Custom Post Types (CPT) et des Taxonomies dans WordPress

## Introduction

Lorsque vous déclarez de nouveaux Custom Post Types (CPT) dans WordPress, vous gagnez un contrôle total sur les types de contenu que vous pouvez créer. Vous aurez ainsi accès à de nouveaux menus dans l'interface d'administration de WordPress. Par exemple, si vous déclarez un CPT **Portfolio**, vos nouveaux contenus seront accessibles via une URL dédiée, comme `monsite.fr/portfolio`. En plus de cela, vous pourrez définir un modèle de page spécifique pour chaque CPT, ce qui vous permet de personnaliser la mise en page des contenus.

---

## Déclarer un Custom Post Type (CPT)

### Méthode PHP

La déclaration d'un CPT se fait généralement en trois étapes :

1. **Déclarer les libellés** qui apparaîtront dans l'interface d'administration.
2. **Définir les paramètres** du CPT dans un tableau `$args`.
3. **Déclarer le CPT** via la fonction `register_post_type()`.

Cette fonction accepte deux paramètres :

- Le **slug** du CPT, qui sera aussi l'URL par défaut.
- Le tableau de paramètres `$args` que vous avez défini précédemment.

Une fois le CPT déclaré, vous devrez vous rendre dans l'interface de WordPress, sous **Réglages > Permaliens**, puis cliquer sur **"Enregistrer les modifications"** sans modifier quoi que ce soit.

---

## CPT par archives vs CPT hiérarchiques

- **CPT avec archives** : Si vous souhaitez que votre CPT se comporte comme un blog, vous devez définir le paramètre `has_archive` à `true`.
- **CPT hiérarchiques** : Si vous avez besoin de créer une structure de pages parentes et enfants, comme pour une documentation, vous devez définir `has_archive` à `false` et `hierarchical` à `true`.

---

## L'importance du paramètre `show_in_rest`

Il est essentiel de définir le paramètre `show_in_rest` à `true`, sinon l'éditeur Gutenberg ne pourra pas se charger correctement pour votre CPT. Gutenberg utilise l'API REST de WordPress pour enregistrer les données de la publication.

---

## Changer l'URL d’un CPT

L'URL d'un CPT sera, par défaut, le slug que vous définissez via la fonction `register_post_type()`. Par exemple, pour un **Portfolio**, l'URL serait `monsite.fr/portfolio`. Si vous souhaitez changer cette URL après coup, vous devez utiliser le paramètre `rewrite` dans le tableau `$args` lors de la déclaration du CPT.

---

## Déclarer un CPT via ACF

Si vous utilisez **Advanced Custom Fields (ACF)**, vous pouvez déclarer un CPT en cochant l'option **"Configuration avancée"**. Cela vous permettra d'accéder à toutes les options disponibles pour un CPT, telles que les libellés, l'URL, la hiérarchie, et l'icône. Avec ACF, les informations de déclaration du CPT sont enregistrées dans la base de données, au lieu de le faire directement en PHP.

---

## Taxonomies Personnalisées

Les taxonomies permettent de classer les publications de manière logique. WordPress offre deux taxonomies par défaut : les **catégories** et les **étiquettes**.

- **Catégories** : Liste fixe d'éléments choisis à l'avance, permettant une navigation fluide.
- **Étiquettes** : Champ libre où l'on peut saisir n'importe quelle valeur pour mettre en avant des thématiques spécifiques.

### Déclarer une taxonomie pour notre CPT

Pour créer une taxonomie personnalisée pour un CPT, comme par exemple une taxonomie **"Types de projets"** pour un Portfolio, vous pouvez déclarer cette taxonomie en PHP en ajoutant un bout de code après la déclaration du CPT. Utilisez la fonction `register_taxonomy()` qui prend trois paramètres :

1. **Slug de la taxonomie** (utilisé dans l'URL).
2. **Slug du CPT auquel la rattacher**.
3. **Tableau des paramètres** définis pour cette taxonomie.

Si vous souhaitez que votre taxonomie fonctionne comme des **catégories**, définissez `hierarchical` à `true`.

---

## Créer les modèles de pages pour votre CPT

### Structure des modèles

Pour afficher les archives et les pages individuelles de votre CPT, vous devez créer des fichiers modèles spécifiques dans votre thème. La hiérarchie des templates de WordPress nous permet de créer des fichiers :

- **archive-<slug>.html** pour afficher la liste des éléments d'un CPT.
- **single-<slug>.html** pour afficher un seul élément de ce CPT.

Dans cet exemple, pour un **Portfolio**, vous devez créer les fichiers suivants dans le dossier **templates** de votre thème :
- **archive-portfolio.html** : pour afficher la liste des projets.
- **single-portfolio.html** : pour afficher un seul projet.

### Le modèle d'archives

Commencez par ajouter un **header**, un **groupe**, et un **footer**. Passez le groupe en `<main>` et ajoutez un **titre de niveau 1** suivi d'une **boucle de requête**. Cette boucle héritera de la requête principale de la page. Dans le bloc « modèle de publication », choisissez un affichage en **3 colonnes** et réduisez l'espacement entre les blocs. Conservez uniquement les images mises en avant.

### Le modèle single

Pour le modèle **single**, il est assez simple : ajoutez le **titre de la publication**, l’**image mise en avant**, et le **contenu de l’article**.

À côté du titre, vous pouvez ajouter un bloc « **Type de projet** » dans une **rangée**, ce bloc affichera les types de projets assignés à cet élément. Ce bloc est lié à la taxonomie personnalisée **"Types de projets"** que vous avez créée via `register_taxonomy()`.

---

## Ajouter votre CPT au menu

N'oubliez pas d'ajouter une entrée dans le menu principal pour le **Portfolio**. Allez dans **Apparence > Éditeur > Navigation** et ajoutez un lien personnalisé vers le Portfolio. Cependant, WordPress ne liste pas par défaut les archives des CPT, vous devrez donc créer un lien personnalisé vers l'archive de votre CPT (par exemple, `monsite.fr/portfolio`).

---

## Le modèle pour la taxonomie

Enfin, il reste un dernier détail à régler : si vous cliquez sur un **type de projet** dans une page single, vous serez redirigé vers l'archive classique du blog. Ce n'est pas ce que nous souhaitons. Nous allons donc créer un modèle spécifique pour notre taxonomie.

- Créez un fichier **taxonomy-<slug>.html** dans le dossier **templates** de votre thème. Par exemple, pour une taxonomie "Type de projet", créez **taxonomy-type-projets.html**.
- Dans ce fichier, remplacez le titre par un bloc **"Titre d'archive"** afin que le titre de la page affiche le type de projet cliqué.

Vous n'aurez plus besoin de modifier la boucle de requête, car elle est automatiquement gérée par WordPress pour afficher les bonnes publications selon la taxonomie sélectionnée.

---

## Conclusion

En résumé, en déclarant un **Custom Post Type (CPT)** et une **taxonomie personnalisée**, vous avez la possibilité de créer des structures de contenu totalement personnalisées dans WordPress. Vous pouvez également créer des modèles dédiés pour l'affichage de vos CPT et de vos taxonomies, en utilisant la hiérarchie de modèles de WordPress pour adapter les pages d'archives et les pages de contenu unique à vos besoins spécifiques.
