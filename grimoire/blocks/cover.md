# Documentation du bloc `core/cover`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/cover`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**           | **Type**           | **Valeur par défaut** | **Description**                                                                                       |
|-------------------------|--------------------|------------------------|-------------------------------------------------------------------------------------------------------|
| `url`                  | `string`          | -                      | L'URL de l'image ou de la vidéo utilisée comme arrière-plan.                                         |
| `useFeaturedImage`     | `boolean`         | `false`                | Utilise l'image à la une du post si activée.                                                        |
| `id`                   | `number`          | -                      | ID de l'image ou de la vidéo dans la médiathèque.                                                   |
| `alt`                  | `string`          | `""`                   | Texte alternatif de l'image.                                                                        |
| `hasParallax`          | `boolean`         | `false`                | Active l'effet de parallaxe pour l'image de fond.                                                   |
| `isRepeated`           | `boolean`         | `false`                | Indique si l'image de fond doit se répéter (répétition en mosaïque).                                 |
| `dimRatio`             | `number`          | `100`                  | Opacité du calque superposé (valeurs entre 0 et 100).                                               |
| `overlayColor`         | `string`          | -                      | Nom de la couleur du calque superposé (si définie dans le thème).                                   |
| `customOverlayColor`   | `string`          | -                      | Code hexadécimal pour une couleur superposée personnalisée.                                         |
| `isUserOverlayColor`   | `boolean`         | -                      | Indique si une couleur superposée personnalisée a été définie par l'utilisateur.                   |
| `backgroundType`       | `string`          | `"image"`              | Type d'arrière-plan (`image` ou `video`).                                                           |
| `focalPoint`           | `object`          | -                      | Position du point focal de l'image (objet avec `x` et `y`).                                         |
| `minHeight`            | `number`          | -                      | Hauteur minimale du bloc Cover.                                                                     |
| `minHeightUnit`        | `string`          | -                      | Unité de la hauteur minimale (par exemple, `px`, `%`, `vh`).                                        |
| `gradient`             | `string`          | -                      | Nom d'un dégradé défini par le thème.                                                               |
| `customGradient`       | `string`          | -                      | Code CSS pour un dégradé personnalisé.                                                              |
| `contentPosition`      | `string`          | -                      | Position du contenu (`top left`, `center`, `bottom right`, etc.).                                    |
| `isDark`               | `boolean`         | `true`                 | Indique si le calque est sombre (utile pour vérifier le contraste avec le texte).                   |
| `allowedBlocks`        | `array`           | -                      | Liste des blocs autorisés à l'intérieur du bloc Cover.                                              |
| `templateLock`         | `string | boolean`| -                      | Contrôle le verrouillage de l'édition (`all`, `insert`, `contentOnly`, ou `false`).                 |
| `tagName`              | `string`          | `"div"`                | Balise HTML utilisée pour le bloc (`div`, `header`, `section`, etc.).                               |
| `sizeSlug`             | `string`          | -                      | Taille d'image définie (`thumbnail`, `medium`, `large`, etc.).                                       |

---

## Supports (Fonctionnalités prises en charge)

### **Ancrage et alignement**
- `anchor` : Permet de définir un identifiant unique pour le bloc.
- `align` : Prend en charge l'alignement (`wide`, `full`, `center`, etc.).
- `html` : Ne supporte pas l'édition directe du HTML (`false`).

### **Espacement**
- `spacing.padding` : Contrôle le rembourrage intérieur.
- `spacing.margin` : Permet des marges uniquement en haut et en bas.
- `spacing.blockGap` : Gère l'écart entre les blocs enfants.

### **Bordures**
- Supporte les propriétés suivantes :
  - `color` : Couleur de la bordure.
  - `radius` : Rayon des coins.
  - `style` : Style de bordure (`solid`, `dashed`, etc.).
  - `width` : Largeur de la bordure.

### **Couleurs**
- Supporte les paramètres pour le texte (`text`) et les en-têtes (`heading`).
- Prise en charge des couleurs de dégradé et des filtres de type **duotone**.

### **Dimensions**
- Supporte un rapport d'aspect (`aspectRatio`) pour l'arrière-plan.

### **Typographie**
- Gère les propriétés suivantes :
  - `fontSize`
  - `lineHeight`
  - `fontFamily` (expérimental)
  - `fontWeight` (expérimental)
  - `fontStyle` (expérimental)
  - `textTransform` (expérimental)
  - `textDecoration` (expérimental)
  - `letterSpacing` (expérimental)

### **Interactivité**
- `clientNavigation` : Permet de capturer des événements de navigation.

---

## Styles

- `editorStyle` : Définit le style dans l'éditeur (`wp-block-cover-editor`).
- `style` : Définit le style global (`wp-block-cover`).

---

## Contexte utilisé

Le bloc utilise les variables de contexte suivantes :
- `postId` : ID du post parent.
- `postType` : Type de contenu (`post`, `page`, etc.).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/cover`.*
