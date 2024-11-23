# Documentation du bloc `core/heading`

Ce document décrit les attributs et les fonctionnalités du bloc **`core/heading`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**             | **Type**           | **Valeur par défaut**   | **Description**                                                                                           |
|--------------------------|--------------------|-------------------------|-----------------------------------------------------------------------------------------------------------|
| `textAlign`              | `string`           |                         | Définit l'alignement du texte du titre (par exemple, `left`, `center`, `right`).                           |
| `content`                | `rich-text`        |                         | Le contenu textuel du titre, utilisé pour les balises `h1`, `h2`, `h3`, `h4`, `h5`, ou `h6`.               |
| `level`                  | `number`           | `2`                     | Le niveau du titre (1 pour `h1`, 2 pour `h2`, etc.).                                                      |
| `levelOptions`           | `array`            |                         | Options disponibles pour définir le niveau du titre (par exemple, [1, 2, 3, 4, 5, 6]).                   |
| `placeholder`            | `string`           |                         | Le texte de remplacement à afficher lorsqu'il n'y a pas encore de contenu.                                 |

---

## Fonctionnalités prises en charge (Supports)

### **Alignement et HTML**
- `align` : Permet d'ajuster l'alignement du bloc, avec des options comme `wide` ou `full`.
- `anchor` : Permet d'ajouter un identifiant d'ancrage au bloc.
- `className` : Permet d'ajouter une classe CSS personnalisée.
- `splitting` : Permet de gérer la séparation du texte en plusieurs parties pour une meilleure accessibilité.

### **Bordures**
Le bloc prend en charge la configuration des bordures suivantes :
- `color` : Définir la couleur de la bordure.
- `radius` : Définir le rayon des coins de la bordure.
- `style` : Définir le style de la bordure (par exemple, `solid`, `dashed`).
- `width` : Définir la largeur de la bordure.

### **Couleurs**
- `gradients` : Permet d'ajouter des dégradés comme fond ou couleur.
- `link` : Permet de personnaliser la couleur des liens dans le bloc.
- **Contrôles par défaut pour la couleur de fond et du texte** activés.

### **Espacement**
- `spacing.margin` : Définit la marge autour du bloc.
- `spacing.padding` : Définit le rembourrage du bloc.

### **Typographie**
Le bloc offre une variété de contrôles typographiques, dont :
- `fontSize` : Définir la taille de la police.
- `lineHeight` : Définir la hauteur de ligne du texte.
- `fontFamily` : Choisir la famille de polices utilisée.
- `fontWeight` : Modifier l'épaisseur de la police.
- `fontStyle` : Définir le style de la police (normal, italique).
- `letterSpacing` : Modifier l'espacement entre les lettres.
- `textTransform` : Appliquer des transformations de texte (par exemple, `uppercase`).
- `textDecoration` : Appliquer des décorations de texte (par exemple, `underline`).
- `writingMode` : Modifier le mode d'écriture (par exemple, `vertical-rl`).

### **Interactivité**
- `clientNavigation` : Permet la navigation côté client.

---

## Styles
- **`editorStyle`** : `wp-block-heading-editor` : Style spécifique utilisé dans l'éditeur de blocs.
- **`style`** : `wp-block-heading` : Style appliqué au bloc dans le front-end.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/heading`.*