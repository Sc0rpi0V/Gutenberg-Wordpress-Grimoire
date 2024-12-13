# Documentation du bloc `core/comment-reply-link`

Ce document présente les attributs et les fonctionnalités du bloc **`core/comment-reply-link`** dans WordPress Gutenberg. Ce bloc affiche un lien permettant de répondre à un commentaire. Ce lien est utilisé dans le cadre des discussions sous les commentaires sur un article.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `textAlign`         | `string`   |                       | Permet de définir l'alignement du texte du lien de réponse.                   |

---

## Contexte utilisé

- **`commentId`** : Ce bloc utilise le contexte `commentId`, ce qui permet de créer un lien spécifique permettant de répondre à un commentaire donné.

---

## Supports (Fonctionnalités prises en charge)

### **Couleurs**
- **`color`** :
  - **link** : Permet de définir la couleur du lien de réponse.
  - **gradients** : Permet de définir des dégradés de couleurs pour le lien.
  - **text** : Pas de support pour la couleur du texte (désactivé).
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background` et `link`.

### **Espacement**
- **`spacing`** :
  - **margin** : Permet de définir des marges extérieures pour le lien de réponse.
  - **padding** : Permet de définir des espacements intérieurs pour le lien.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `margin` et `padding`.

### **Typographie**
- **`typography`** :
  - **fontSize** : Permet de définir la taille de la police pour le lien de réponse.
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
  - **radius** : Permet de définir le rayon des coins du lien de réponse.
  - **color** : Permet de définir la couleur de la bordure du lien.
  - **width** : Permet de définir la largeur de la bordure du lien.
  - **style** : Permet de définir le style de la bordure du lien (ex: `solid`, `dashed`).

### **HTML**
- `html` : Ce bloc ne prend pas en charge l'édition HTML.

---

## Styles

- `style` : Définit le style du bloc dans l'éditeur (`wp-block-comment-reply-link`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comment-reply-link`.* 
