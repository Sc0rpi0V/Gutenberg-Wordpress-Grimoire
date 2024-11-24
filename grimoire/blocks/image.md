# Documentation du bloc `core/image`

Ce document décrit les attributs et les fonctionnalités du bloc **`core/image`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**          | **Type**      | **Valeur par défaut** | **Description**                                                                 |
|-----------------------|---------------|-----------------------|---------------------------------------------------------------------------------|
| `blob`               | `string`      |                       | Représente une chaîne pour l'accès local.                                      |
| `url`                | `string`      |                       | URL de l'image, extraite de l'attribut `src` de l'élément `<img>`.             |
| `alt`                | `string`      | `""`                  | Texte alternatif de l'image, utilisé pour l'attribut `alt` de l'élément `<img>`. |
| `caption`            | `rich-text`   |                       | Texte riche utilisé pour afficher une légende sous l'image.                    |
| `lightbox.enabled`   | `boolean`     |                       | Indique si le mode lightbox est activé ou non.                                 |
| `title`              | `string`      |                       | Titre de l'image, extrait de l'attribut `title` de l'élément `<img>`.          |
| `href`               | `string`      |                       | Lien associé à l'image, extrait de l'attribut `href` de l'élément `<a>`.       |
| `rel`                | `string`      |                       | Relation du lien, extrait de l'attribut `rel` de l'élément `<a>`.              |
| `linkClass`          | `string`      |                       | Classes CSS associées au lien `<a>`.                                           |
| `id`                 | `number`      |                       | Identifiant unique associé à l'image.                                          |
| `width`              | `string`      |                       | Largeur de l'image.                                                            |
| `height`             | `string`      |                       | Hauteur de l'image.                                                            |
| `aspectRatio`        | `string`      |                       | Ratio d'aspect de l'image (par exemple, `16:9`).                               |
| `scale`              | `string`      |                       | Échelle appliquée à l'image.                                                   |
| `sizeSlug`           | `string`      |                       | Taille de l'image, par exemple `thumbnail`, `medium`, `large`.                 |
| `linkDestination`    | `string`      |                       | Destination du lien (par exemple, image ou fichier).                           |
| `linkTarget`         | `string`      |                       | Cible du lien (par exemple, `_blank`).                                         |

---

## Fonctionnalités prises en charge (Supports)

### **Alignement et HTML**
- `align` : Permet d'ajuster l'alignement de l'image, avec des options comme `left`, `center`, `right`, `wide`, et `full`.
- `anchor` : Permet d'ajouter un identifiant d'ancrage au bloc.

### **Couleurs**
- Les contrôles de couleur de fond et du texte sont désactivés pour ce bloc.

### **Filtres**
- `duotone` : Permet d'appliquer un filtre de type "duotone" à l'image.

### **Espacement**
- `spacing.margin` : Permet de définir les marges autour de l'image.

### **Bordures**
Le bloc prend en charge les configurations de bordures suivantes :
- `color` : Couleur de la bordure.
- `radius` : Rayon des coins de la bordure.
- `width` : Largeur de la bordure.
- **Contrôles par défaut** :
  - Couleur, rayon et largeur des bordures activés.

### **Ombres**
- Le bloc permet de définir des ombres, mais elles ne sont pas sérialisées dans le DOM.

### **Interactivité**
- `interactivity` : Activée pour permettre des interactions personnalisées.

---

## Sélecteurs CSS

| **Type**       | **Sélecteurs**                                                                                               |
|----------------|-------------------------------------------------------------------------------------------------------------|
| `border`       | `.wp-block-image img`, `.wp-block-image .wp-block-image__crop-area`, `.wp-block-image .components-placeholder` |
| `shadow`       | `.wp-block-image img`, `.wp-block-image .wp-block-image__crop-area`, `.wp-block-image .components-placeholder` |
| `filter.duotone` | `.wp-block-image img`, `.wp-block-image .components-placeholder`                                           |

---

## Styles
- **Styles par défaut** :
  - **`default`** : Style par défaut.
  - **`rounded`** : Style arrondi pour les coins de l'image.
- **`editorStyle`** : `wp-block-image-editor` : Style spécifique utilisé dans l'éditeur.
- **`style`** : `wp-block-image` : Style appliqué au bloc dans le front-end.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/image`.*
