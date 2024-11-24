# Documentation du bloc `core/media-text`

Ce document détaille les attributs et fonctionnalités du bloc **`core/media-text`** dans WordPress Gutenberg.

---

## Description

Le bloc **Media & Text** permet d’afficher des médias (images, vidéos) à côté d’un contenu textuel, offrant ainsi une mise en page riche et personnalisable.

---

## Attributs principaux

| **Attribut**         | **Type**       | **Valeur par défaut** | **Description**                                                                                      |
|-----------------------|----------------|-----------------------|------------------------------------------------------------------------------------------------------|
| `align`              | `string`       | `none`               | Alignement horizontal du bloc (`wide`, `full`, ou `none`).                                           |
| `mediaAlt`           | `string`       | `""`                 | Texte alternatif pour l’image ou la vidéo.                                                          |
| `mediaPosition`      | `string`       | `left`               | Position du média par rapport au texte (`left` ou `right`).                                          |
| `mediaId`            | `number`       |                       | ID de la pièce jointe du média dans la bibliothèque WordPress.                                       |
| `mediaUrl`           | `string`       |                       | URL de l’image ou de la vidéo à afficher.                                                           |
| `mediaLink`          | `string`       |                       | Lien hypertexte du média.                                                                            |
| `linkDestination`    | `string`       |                       | Destination du lien (`none`, `media`, ou `attachment`).                                              |
| `linkTarget`         | `string`       |                       | Définit si le lien s’ouvre dans un nouvel onglet (`_blank`).                                         |
| `href`               | `string`       |                       | URL du lien hypertexte.                                                                              |
| `rel`                | `string`       |                       | Attribut `rel` pour le lien (par exemple, `nofollow`).                                              |
| `linkClass`          | `string`       |                       | Classes CSS appliquées au lien du média.                                                            |
| `mediaType`          | `string`       |                       | Type de média (`image`, `video`).                                                                    |
| `mediaWidth`         | `number`       | `50`                 | Largeur du média en pourcentage de l’espace disponible.                                              |
| `mediaSizeSlug`      | `string`       |                       | Taille de l’image (par exemple, `thumbnail`, `medium`, `large`).                                     |
| `isStackedOnMobile`  | `boolean`      | `true`               | Définit si le média et le texte sont empilés sur mobile.                                             |
| `verticalAlignment`  | `string`       |                       | Alignement vertical du contenu (`top`, `center`, `bottom`).                                          |
| `imageFill`          | `boolean`      |                       | Définit si l’image occupe entièrement l’espace disponible.                                           |
| `focalPoint`         | `object`       |                       | Coordonnées pour définir le point focal de l’image (x, y).                                           |
| `allowedBlocks`      | `array`        |                       | Liste des blocs autorisés à l’intérieur du bloc.                                                    |
| `useFeaturedImage`   | `boolean`      | `false`              | Permet d’utiliser l’image mise en avant comme média.                                                 |

---

## Fonctionnalités prises en charge (Supports)

### **Alignement et HTML**
- `anchor` : Permet d’ajouter un identifiant d’ancrage au bloc.
- `align` : Prend en charge les alignements `wide` et `full`.
- `html` : Désactivé pour ce bloc.

### **Bordures**
Le bloc prend en charge toutes les propriétés de bordures :
- `color` : Couleur de la bordure.
- `radius` : Rayon des coins de la bordure.
- `style` : Style de la bordure (`solid`, `dashed`...).
- `width` : Largeur de la bordure.

### **Couleurs**
- `gradients` : Permet d’ajouter des dégradés.
- `heading` : Personnalisation de la couleur des titres.
- `link` : Couleur des liens dans le bloc.
- **Contrôles par défaut activés** pour l’arrière-plan et le texte.

### **Espacement**
- Prise en charge des marges et des rembourrages (`margin`, `padding`).

### **Typographie**
- Propriétés prises en charge :
  - `fontSize`
  - `lineHeight`
  - `__experimentalFontFamily`
  - `__experimentalFontWeight`
  - `__experimentalFontStyle`
  - `__experimentalTextTransform`
  - `__experimentalTextDecoration`
  - `__experimentalLetterSpacing`
- **Contrôles par défaut activés** pour la taille de police.

### **Interactivité**
- `clientNavigation` : Prend en charge la navigation côté client.

---

## Contexte utilisé

Le bloc utilise les contextes suivants :
- `postId`
- `postType`

---

## Styles

- **`editorStyle`** : `wp-block-media-text-editor` : Style spécifique à l’éditeur.
- **`style`** : `wp-block-media-text` : Style appliqué dans le front-end.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/media-text`.*
