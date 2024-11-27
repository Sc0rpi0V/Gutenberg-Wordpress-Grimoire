# Documentation du bloc `core/post-author`

Ce document détaille les attributs et fonctionnalités du bloc **`core/post-author`** dans WordPress Gutenberg.

---

## Description

Le bloc **Author** permet d’afficher les détails de l’auteur d’un contenu, notamment :
- Nom
- Avatar
- Biographie (facultative)

---

## Attributs principaux

| **Attribut**   | **Type**   | **Valeur par défaut** | **Description**                                                                 |
|-----------------|------------|-----------------------|---------------------------------------------------------------------------------|
| `textAlign`     | `string`   |                       | Alignement du texte : peut être `left`, `center`, ou `right`.                   |
| `avatarSize`    | `number`   | `48`                 | Taille de l’avatar en pixels.                                                  |
| `showAvatar`    | `boolean`  | `true`               | Indique si l’avatar de l’auteur doit être affiché.                             |
| `showBio`       | `boolean`  |                       | Indique si la biographie de l’auteur doit être affichée.                       |
| `byline`        | `string`   |                       | Texte d’introduction (ex. : "Écrit par").                                       |
| `isLink`        | `boolean`  | `false`              | Indique si le nom de l’auteur doit être un lien cliquable.                      |
| `linkTarget`    | `string`   | `_self`              | Cible du lien : `_self` pour ouvrir dans la même fenêtre, `_blank` pour ouvrir dans une nouvelle fenêtre. |

---

## Contexte utilisé

Le bloc exploite les contextes suivants :
- **`postType`** : Le type de publication auquel appartient le contenu.
- **`postId`** : L’identifiant de la publication en cours.
- **`queryId`** : L’identifiant de la requête (si applicable).

---

## Fonctionnalités prises en charge (Supports)

### **HTML**
- Le code HTML ne peut pas être modifié directement (`html: false`).

### **Espacement**
- Gestion des marges (`margin`) et des paddings (`padding`).

### **Couleurs**
- Personnalisation des couleurs, avec prise en charge des dégradés (`gradients`) et de l’effet de duotone sur l’avatar.
- **Contrôles activés par défaut** pour :
  - La couleur d’arrière-plan.
  - La couleur du texte.
  - Les couleurs des liens.

### **Typographie**
Le bloc propose des options complètes pour la personnalisation typographique :
- `fontSize` : Taille de la police.
- `lineHeight` : Hauteur de ligne.
- `__experimentalFontFamily` : Famille de police personnalisée.
- `__experimentalFontWeight` : Épaisseur de la police.
- `__experimentalFontStyle` : Style de la police (italique, normal, etc.).
- `__experimentalTextTransform` : Transformation du texte (majuscule, minuscule, capitalisé).
- `__experimentalTextDecoration` : Décoration du texte (souligné, barré, etc.).
- `__experimentalLetterSpacing` : Espacement entre les lettres.
- **Contrôle activé par défaut** pour la taille de la police.

### **Interactivité**
- `clientNavigation` : Permet la navigation côté client si le contenu contient des liens.

### **Bordures**
Les bordures sont entièrement personnalisables :
- `radius` : Rayon des coins.
- `color` : Couleur de la bordure.
- `width` : Largeur de la bordure.
- `style` : Style de la bordure (`solid`, `dotted`, `dashed`, etc.).
- **Contrôles activés par défaut** pour toutes ces options.

---

## Styles et éditeur

- **Style éditeur** : `wp-block-post-author-editor`.
- **Style front-end** : `wp-block-post-author`.

---

*Cette documentation est basée sur les informations contenues dans le fichier `block.json` du bloc `core/post-author`.*
