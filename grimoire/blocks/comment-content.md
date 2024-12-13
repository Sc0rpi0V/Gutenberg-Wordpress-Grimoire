# Création du fichier markdown avec la documentation demandée pour le bloc core/comment-content

markdown_content_6 = """
# Documentation du bloc `core/comment-content`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/comment-content`** dans WordPress Gutenberg. Ce bloc permet d'afficher le contenu d'un commentaire.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `textAlign`         | `string`   |                       | Permet de définir l'alignement du texte du contenu du commentaire.            |

---

## Contexte utilisé

- **`commentId`** : Ce bloc utilise le contexte `commentId`, ce qui permet d'afficher le contenu d'un commentaire spécifique.

---

## Supports (Fonctionnalités prises en charge)

### **Couleurs**
- **`color`** :
  - **gradients** : Permet de définir des dégradés de couleurs pour le texte.
  - **link** : Permet de définir la couleur des liens dans le contenu du commentaire.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background` et `text`.

### **Typographie**
- **`typography`** :
  - **fontSize** : Permet de définir la taille de la police du contenu.
  - **lineHeight** : Permet de définir la hauteur de ligne.
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
  - **padding** : Permet de définir un espacement intérieur, aussi bien horizontal que vertical.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `padding`.

### **HTML**
- `html` : Ce bloc ne prend pas en charge l'édition HTML.

---

## Styles

- `style` : Définit le style dans l'éditeur (`wp-block-comment-content`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comment-content`.* 
