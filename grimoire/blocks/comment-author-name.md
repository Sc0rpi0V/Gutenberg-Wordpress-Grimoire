# Documentation du bloc `core/comment-author-name`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/comment-author-name`** dans WordPress Gutenberg. Ce bloc permet d'afficher le nom de l'auteur d'un commentaire.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `isLink`            | `boolean`  | `true`                | Définit si le nom de l'auteur est un lien cliquable.                         |
| `linkTarget`        | `string`   | `_self`               | Définit la cible du lien (`_self`, `_blank`, etc.).                          |
| `textAlign`         | `string`   |                       | Permet de définir l'alignement du texte (gauche, droite, centré, etc.).      |

---

## Contexte utilisé

- **`commentId`** : Ce bloc utilise le contexte `commentId`, ce qui permet d'afficher le nom de l'auteur d'un commentaire spécifique.

---

## Supports (Fonctionnalités prises en charge)

### **HTML**
- `html` : Ce bloc ne prend pas en charge l'édition HTML.

### **Espacement**
- **`spacing`** :
  - **margin** : Permet de définir des marges autour du nom de l'auteur.
  - **padding** : Permet de définir un espacement intérieur pour le bloc.

### **Couleurs**
- **`color`** :
  - **gradients** : Permet de définir des dégradés de couleurs pour le texte.
  - **link** : Permet de définir la couleur du lien.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background`, `text` et `link`.

### **Typographie**
- **`typography`** :
  - **fontSize** : Permet de définir la taille de la police.
  - **lineHeight** : Permet de définir la hauteur de ligne.
  - **__experimentalFontFamily** : Permet de définir la famille de police.
  - **__experimentalFontWeight** : Permet de définir le poids de la police.
  - **__experimentalFontStyle** : Permet de définir le style de la police (ex : `italic`).
  - **__experimentalTextTransform** : Permet de définir la transformation du texte (ex : `uppercase`).
  - **__experimentalTextDecoration** : Permet de définir la décoration du texte (ex : `underline`).
  - **__experimentalLetterSpacing** : Permet de définir l'espacement des lettres.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `fontSize`.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client.

### **Bordures**
- **`__experimentalBorder`** :
  - **radius** : Permet de définir le rayon des coins du bloc.
  - **color** : Permet de définir la couleur de la bordure du bloc.
  - **width** : Permet de définir la largeur de la bordure du bloc.
  - **style** : Permet de définir le style de la bordure (ex : `solid`, `dashed`).
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `radius`, `color`, `width` et `style`.

---

## Styles

- `style` : Définit le style dans l'éditeur (`wp-block-comment-author-name`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comment-author-name`.* 
