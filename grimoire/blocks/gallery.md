# Documentation du bloc `core/gallery`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/gallery`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**             | **Type**           | **Valeur par défaut**   | **Description**                                                                                        |
|--------------------------|--------------------|-------------------------|--------------------------------------------------------------------------------------------------------|
| `images`                 | `array`            | `[]`                    | Liste des images à afficher dans la galerie, chaque image ayant plusieurs propriétés (`src`, `alt`, `caption`, etc.). |
| `ids`                    | `array`            | `[]`                    | Liste des IDs des images associées à la galerie.                                                        |
| `shortCodeTransforms`    | `array`            | `[]`                    | Transformation des shortcodes de la galerie.                                                             |
| `columns`                | `number`           |                         | Nombre de colonnes dans la galerie, compris entre 1 et 8.                                               |
| `caption`                | `rich-text`        |                         | Légende de la galerie ou d'une image spécifique.                                                        |
| `imageCrop`              | `boolean`          | `true`                  | Si l'image doit être rognée pour s'ajuster à la grille de la galerie.                                  |
| `randomOrder`            | `boolean`          | `false`                 | Si les images doivent être affichées dans un ordre aléatoire.                                           |
| `fixedHeight`            | `boolean`          | `true`                  | Si la galerie doit avoir une hauteur fixe.                                                              |
| `linkTarget`             | `string`           |                         | L'URL cible pour les liens d'images.                                                                    |
| `linkTo`                 | `string`           |                         | Définit si les images doivent être liées à l'URL complète ou à une autre destination.                   |
| `sizeSlug`               | `string`           | `large`                 | Taille des images à afficher dans la galerie.                                                          |
| `allowResize`            | `boolean`          | `false`                 | Permet de redimensionner les images dans la galerie.                                                    |

---

## Contexte utilisé

Le bloc utilise le contexte suivant :
- `allowResize` : Permet de redimensionner les images.
- `imageCrop` : Contrôle le rognage des images dans la galerie.
- `fixedHeight` : Définit si la galerie a une hauteur fixe.

---

## Fonctionnalités prises en charge (Supports)

### **Alignement et HTML**
- `anchor` : Permet d'ajouter un identifiant d'ancrage pour ce bloc.
- `align` : Permet d'ajuster l'alignement du bloc.
- `html` : Ne prend pas en charge l'édition directe du HTML (`false`).

### **Bordures**
- Supporte les propriétés suivantes :
  - `color` : Couleur de la bordure.
  - `radius` : Rayon des coins.
  - `style` : Style de la bordure (par exemple, `solid` ou `dashed`).
  - `width` : Largeur de la bordure.
- Contrôle des bordures activé par défaut.

### **Espacement**
- `spacing.margin` : Permet de définir les marges du bloc.
- `spacing.padding` : Permet de définir le rembourrage intérieur du bloc.
- `spacing.blockGap` : Permet de définir l'écart entre les éléments de la galerie (horizontal et vertical).
- Contrôle des espacements activé par défaut.

### **Couleurs**
- `background` : Permet de définir la couleur d'arrière-plan du bloc.
- `gradients` : Permet d'appliquer des dégradés à la galerie.

### **Disposition**
- `layout` : Définit la disposition du bloc. Par défaut, il utilise un type `flex` pour les éléments enfants.
- Les options de modification de la disposition sont désactivées (`allowSwitching`, `allowInheriting`, `allowEditing`).

### **Interactivité**
- `clientNavigation` : Permet la navigation côté client.

---

## Styles
- **`editorStyle`** : `wp-block-gallery-editor` : Le style spécifique pour l'éditeur de blocs.
- **`style`** : `wp-block-gallery` : Le style appliqué au bloc dans le front-end.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/gallery`.*