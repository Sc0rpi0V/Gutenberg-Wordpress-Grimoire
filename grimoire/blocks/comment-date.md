# Documentation du bloc `core/comment-date`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/comment-date`** dans WordPress Gutenberg. Ce bloc permet d'afficher la date à laquelle un commentaire a été publié.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `format`            | `string`   |                       | Permet de définir le format d'affichage de la date du commentaire.            |
| `isLink`            | `boolean`  | `true`                | Définit si la date du commentaire doit être un lien.                          |

---

## Contexte utilisé

- **`commentId`** : Ce bloc utilise le contexte `commentId`, ce qui permet d'afficher la date d'un commentaire spécifique.

---

## Supports (Fonctionnalités prises en charge)

### **Couleurs**
- **`color`** :
  - **gradients** : Permet de définir des dégradés de couleurs pour le texte.
  - **link** : Permet de définir la couleur du lien pour la date du commentaire.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background`, `text`, et `link`.

### **Typographie**
- **`typography`** :
  - **fontSize** : Permet de définir la taille de la police du texte de la date.
  - **lineHeight** : Permet de définir la hauteur de ligne pour la date.
  - **__experimentalFontFamily** : Permet de définir la famille de police.
  - **__experimentalFontWeight** : Permet de définir le poids de la police.
  - **__experimentalFontStyle** : Permet de définir le style de la police (ex : `italic`).
  - **__experimentalTextTransform** : Permet de définir la transformation du texte (ex : `uppercase`).
  - **__experimentalTextDecoration** : Permet de définir la décoration du texte (ex : `underline`).
  - **__experimentalLetterSpacing** : Permet de définir l'espacement des lettres.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `fontSize`.

### **Bordures**
- **`__experimentalBorder`** :
  - **radius** : Permet de définir le rayon des coins du bloc.
  - **color** : Permet de définir la couleur de la bordure du bloc.
  - **width** : Permet de définir la largeur de la bordure du bloc.
  - **style** : Permet de définir le style de la bordure (ex : `solid`, `dashed`).
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `radius`, `color`, `width` et `style`.

### **Espacement**
- **`spacing`** :
  - **margin** : Permet de définir des marges extérieures pour le bloc.
  - **padding** : Permet de définir un espacement intérieur pour le bloc.

### **HTML**
- `html` : Ce bloc ne prend pas en charge l'édition HTML.

---

## Styles

- `style` : Définit le style dans l'éditeur (`wp-block-comment-date`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comment-date`.* 
