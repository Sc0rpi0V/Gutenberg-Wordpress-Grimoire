# Documentation du bloc `core/list-item`

Ce document décrit les attributs et les fonctionnalités du bloc **`core/list-item`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**  | **Type**       | **Valeur par défaut** | **Description**                                                                  |
|---------------|----------------|-----------------------|----------------------------------------------------------------------------------|
| `placeholder` | `string`       |                       | Texte d'espace réservé affiché lorsqu'il n'y a pas encore de contenu.           |
| `content`     | `rich-text`    |                       | Contenu textuel riche pour l'élément de liste, extrait de l'élément `<li>`.      |

---

## Fonctionnalités prises en charge (Supports)

### **HTML et Classes**
- `anchor` : Permet d'ajouter un identifiant d'ancrage au bloc.
- `className` : Non pris en charge pour ce bloc.

### **Bordures**
Le bloc prend en charge les propriétés de bordures suivantes :
- `color` : Couleur de la bordure.
- `radius` : Rayon des coins de la bordure.
- `style` : Style de la bordure (par exemple, `solid`, `dashed`).
- `width` : Largeur de la bordure.

### **Couleurs**
- `gradients` : Permet d'appliquer des dégradés en arrière-plan.
- `link` : Permet de personnaliser la couleur des liens.
- `background` : Permet de définir une couleur d'arrière-plan.
- **Contrôles par défaut activés** pour la couleur du texte.

### **Espacement**
- `spacing.margin` : Permet de définir les marges autour du bloc.
- `spacing.padding` : Permet de définir les rembourrages internes du bloc.
- **Contrôles par défaut** pour la marge et le rembourrage désactivés.

### **Typographie**
Le bloc prend en charge une variété de propriétés typographiques :
- `fontSize` : Taille de la police.
- `lineHeight` : Hauteur de ligne.
- `__experimentalFontFamily` : Famille de polices.
- `__experimentalFontWeight` : Épaisseur de la police.
- `__experimentalFontStyle` : Style de la police (par exemple, italique).
- `__experimentalTextTransform` : Transformation de texte (par exemple, `uppercase`).
- `__experimentalTextDecoration` : Décorations de texte (par exemple, `underline`).
- `__experimentalLetterSpacing` : Espacement entre les lettres.
- **Contrôles par défaut activés** pour la taille de police.

### **Interactivité**
- `clientNavigation` : Permet une navigation côté client.

---

## Sélecteurs CSS

| **Type**   | **Sélecteurs**                                          |
|------------|---------------------------------------------------------|
| `root`     | `.wp-block-list > li`                                   |
| `border`   | `.wp-block-list:not(.wp-block-list .wp-block-list) > li` |

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/list-item`.*
