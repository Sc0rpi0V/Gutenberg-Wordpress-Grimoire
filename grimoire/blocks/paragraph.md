# Documentation du bloc `core/paragraph`

Ce document détaille les attributs et fonctionnalités du bloc **`core/paragraph`** dans WordPress Gutenberg.

---

## Description

Le bloc **Paragraph** constitue le point de départ pour tout contenu narratif. Il permet d’ajouter et de personnaliser du texte dans une page ou un article.

---

## Attributs principaux

| **Attribut**    | **Type**       | **Valeur par défaut** | **Description**                                                                                  |
|------------------|----------------|-----------------------|--------------------------------------------------------------------------------------------------|
| `align`         | `string`       |                       | Alignement horizontal du paragraphe (`left`, `center`, `right`, ou `justify`).                  |
| `content`       | `rich-text`    |                       | Contenu textuel enrichi du paragraphe.                                                          |
| `dropCap`       | `boolean`      | `false`               | Active ou désactive le **lettrine** (majuscule stylisée au début du paragraphe).                 |
| `placeholder`   | `string`       |                       | Texte indicatif affiché lorsque le paragraphe est vide.                                          |
| `direction`     | `string`       |                       | Direction du texte (`ltr` pour gauche à droite, `rtl` pour droite à gauche).                     |

---

## Fonctionnalités prises en charge (Supports)

### **Scission et ancrage**
- `splitting` : Permet de diviser un paragraphe en plusieurs blocs.
- `anchor` : Ajoute un identifiant d’ancrage unique au bloc.

### **Bordures**
Le bloc prend en charge toutes les propriétés de bordure :
- `color` : Couleur de la bordure.
- `radius` : Rayon des coins.
- `style` : Style de la bordure (`solid`, `dashed`, etc.).
- `width` : Largeur de la bordure.

### **Couleurs**
- `gradients` : Prend en charge les dégradés.
- `link` : Personnalisation de la couleur des liens.
- **Contrôles par défaut activés** pour :
  - La couleur d’arrière-plan.
  - La couleur du texte.

### **Espacement**
- Prend en charge :
  - `margin` : Gestion des marges externes.
  - `padding` : Gestion des marges internes.
- **Contrôles désactivés par défaut** pour ces options.

### **Typographie**
Le bloc propose des options étendues pour personnaliser la typographie :
- `fontSize` : Taille de la police.
- `lineHeight` : Hauteur de ligne.
- `__experimentalFontFamily` : Famille de police personnalisée.
- `__experimentalTextDecoration` : Décoration du texte (souligné, barré, etc.).
- `__experimentalFontStyle` : Style de la police (normal, italique).
- `__experimentalFontWeight` : Épaisseur de la police.
- `__experimentalLetterSpacing` : Espacement des lettres.
- `__experimentalTextTransform` : Transformation du texte (majuscule, minuscule, capitalisé).
- `__experimentalWritingMode` : Orientation du texte (`horizontal`, `vertical`).
- **Contrôle par défaut activé** pour la taille de la police.

### **Sélecteur CSS**
- `__experimentalSelector` : Définit le sélecteur CSS par défaut comme `p`.

### **Interactivité**
- `clientNavigation` : Active la navigation côté client lorsque des liens sont présents.

### **Collage de texte brut**
- `__unstablePasteTextInline` : Permet de coller directement du texte sans mise en forme.

---

## Styles

- **`editorStyle`** : `wp-block-paragraph-editor` : Style spécifique à l’éditeur.
- **`style`** : `wp-block-paragraph` : Style appliqué dans le front-end.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/paragraph`.*
