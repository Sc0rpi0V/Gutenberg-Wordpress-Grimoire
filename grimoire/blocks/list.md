# Documentation du bloc `core/list`

Ce document décrit les attributs et les fonctionnalités du bloc **`core/list`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**   | **Type**       | **Valeur par défaut** | **Description**                                                                                   |
|----------------|----------------|-----------------------|---------------------------------------------------------------------------------------------------|
| `ordered`      | `boolean`      | `false`               | Détermine si la liste est ordonnée (`true` pour `<ol>`, `false` pour `<ul>`).                     |
| `values`       | `string`       | `""`                  | Contenu HTML des éléments de liste (`<ol>` ou `<ul>` avec des `<li>`).                            |
| `type`         | `string`       |                       | Type d'éléments de liste (par exemple, `disc`, `circle`, `square` pour `<ul>`).                   |
| `start`        | `number`       |                       | Point de départ pour une liste ordonnée (`<ol>`).                                                 |
| `reversed`     | `boolean`      |                       | Indique si une liste ordonnée est affichée dans l'ordre inverse.                                  |
| `placeholder`  | `string`       |                       | Texte d'espace réservé affiché lorsqu'il n'y a pas encore de contenu.                            |

---

## Fonctionnalités prises en charge (Supports)

### **HTML et Classes**
- `anchor` : Permet d'ajouter un identifiant d'ancrage au bloc.
- `html` : Désactivé pour ce bloc.

### **Bordures**
Le bloc prend en charge les propriétés de bordures suivantes :
- `color` : Couleur de la bordure.
- `radius` : Rayon des coins de la bordure.
- `style` : Style de la bordure (par exemple, `solid`, `dashed`).
- `width` : Largeur de la bordure.

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

### **Couleurs**
- `gradients` : Permet d'appliquer des dégradés.
- `link` : Permet de personnaliser la couleur des liens.
- **Contrôles par défaut activés** pour la couleur du texte et l'arrière-plan.

### **Espacement**
- `spacing.margin` : Permet de définir les marges autour du bloc.
- `spacing.padding` : Permet de définir les rembourrages internes du bloc.
- **Contrôles par défaut désactivés** pour la marge et le rembourrage.

### **Interactivité**
- `clientNavigation` : Permet une navigation côté client.

### **Autres fonctionnalités expérimentales**
- `__unstablePasteTextInline` : Permet de coller du texte en ligne.
- `__experimentalOnMerge` : Gère la fusion avec d'autres blocs.
- `__experimentalSlashInserter` : Permet d'insérer ce bloc via la commande `/`.

---

## Sélecteurs CSS

| **Type**   | **Sélecteurs**                                                        |
|------------|-----------------------------------------------------------------------|
| `border`   | `.wp-block-list:not(.wp-block-list .wp-block-list)`                   |

---

## Styles
- **`editorStyle`** : `wp-block-list-editor` : Style spécifique utilisé dans l'éditeur.
- **`style`** : `wp-block-list` : Style appliqué au bloc dans le front-end.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/list`.*
