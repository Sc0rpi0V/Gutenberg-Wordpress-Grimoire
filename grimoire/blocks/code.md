# Documentation du bloc `core/code`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/code`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `content`           | `rich-text`| N/A                   | Permet de saisir du texte enrichi, avec conservation de l'espacement et des tabulations dans le bloc `code`. Le contenu est récupéré à l'aide du sélecteur `code`. |

---

## Supports (Fonctionnalités prises en charge)

### **Alignement**
- `align` : Prend en charge l'option `wide` pour l'alignement.

### **Ancre**
- `anchor` : Permet de définir une ancre personnalisée pour le bloc afin de faciliter la navigation.

### **Typographie**
- `typography` :
  - **fontSize** : Permet de modifier la taille de la police.
  - **lineHeight** : Permet de modifier la hauteur de ligne.
  - Propriétés expérimentales :
    - `__experimentalFontFamily` : Permet de définir la famille de police.
    - `__experimentalFontWeight` : Permet de définir le poids de la police.
    - `__experimentalFontStyle` : Permet de définir le style de la police (ex : italique).
    - `__experimentalTextTransform` : Permet de modifier la transformation du texte (majuscule, minuscule, etc.).
    - `__experimentalTextDecoration` : Permet d'ajouter des décorations au texte (ex : souligné).
    - `__experimentalLetterSpacing` : Permet de définir l'espacement entre les lettres.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `fontSize`.

### **Espacement**
- `spacing` :
  - **margin** : Prend en charge l'option de marge pour les côtés `top` et `bottom`.
  - **padding** : Permet de définir un espacement intérieur.
  - **__experimentalDefaultControls** : Les contrôles par défaut pour la marge et le padding sont désactivés (`false`).

### **Bordures**
- **`__experimentalBorder`** :
  - **radius** : Permet de définir le rayon des coins.
  - **color** : Permet de définir la couleur de la bordure.
  - **width** : Permet de définir la largeur de la bordure.
  - **style** : Permet de définir le style de la bordure (ex : `solid`, `dashed`).
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `width` et `color`.

### **Couleurs**
- `color` :
  - **text** : Permet de définir la couleur du texte.
  - **background** : Permet de définir la couleur de fond.
  - **gradients** : Permet de définir des dégradés de couleurs.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background` et `text`.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client pour un contrôle dynamique des interactions.

---

## Styles

- **`style`** : Définit le style pour ce bloc, ici spécifié par la classe CSS `wp-block-code`.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/code`.* 
