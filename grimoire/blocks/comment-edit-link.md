# Documentation du bloc `core/comment-edit-link`

Ce document présente les attributs et les fonctionnalités du bloc **`core/comment-edit-link`** dans WordPress Gutenberg. Ce bloc affiche un lien permettant d’éditer un commentaire dans le tableau de bord WordPress. Ce lien n'est visible que pour les utilisateurs ayant la capacité d’éditer des commentaires.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `linkTarget`        | `string`   | `_self`               | Définit la cible du lien d'édition du commentaire (ex: `_self`, `_blank`).     |
| `textAlign`         | `string`   |                       | Permet de définir l'alignement du texte du lien d'édition.                    |

---

## Contexte utilisé

- **`commentId`** : Ce bloc utilise le contexte `commentId`, ce qui permet d’afficher un lien spécifique pour un commentaire particulier.

---

## Supports (Fonctionnalités prises en charge)

### **Couleurs**
- **`color`** :
  - **link** : Permet de définir la couleur du lien d'édition.
  - **gradients** : Permet de définir des dégradés de couleurs pour le lien.
  - **text** : Pas de support pour la couleur du texte (désactivé).
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background` et `link`.

### **Espacement**
- **`spacing`** :
  - **margin** : Permet de définir des marges extérieures pour le lien d’édition.
  - **padding** : Permet de définir des espacements intérieurs pour le lien.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `margin` et `padding`.

### **Typographie**
- **`typography`** :
  - **fontSize** : Permet de définir la taille de la police pour le lien d’édition.
  - **lineHeight** : Permet de définir la hauteur de ligne du lien.
  - **__experimentalFontFamily** : Permet de définir la famille de police du lien.
  - **__experimentalFontWeight** : Permet de définir le poids de la police du lien.
  - **__experimentalFontStyle** : Permet de définir le style de la police du lien (ex: `italic`).
  - **__experimentalTextTransform** : Permet de définir la transformation du texte (ex: `uppercase`).
  - **__experimentalTextDecoration** : Permet de définir la décoration du texte (ex: `underline`).
  - **__experimentalLetterSpacing** : Permet de définir l’espacement des lettres.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `fontSize`.

### **Bordures**
- **`__experimentalBorder`** :
  - **radius** : Permet de définir le rayon des coins du lien d’édition.
  - **color** : Permet de définir la couleur de la bordure du lien.
  - **width** : Permet de définir la largeur de la bordure du lien.
  - **style** : Permet de définir le style de la bordure du lien (ex: `solid`, `dashed`).

### **Interactivité**
- **`interactivity`** :
  - **clientNavigation** : Permet de naviguer sur le client, à savoir sur le même site, lorsque le lien d'édition est cliqué.

### **HTML**
- `html` : Ce bloc ne prend pas en charge l'édition HTML.

---

## Styles

- `style` : Définit le style du bloc dans l'éditeur (`wp-block-comment-edit-link`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comment-edit-link`.* 
