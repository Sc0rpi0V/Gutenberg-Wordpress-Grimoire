# Documentation du bloc `core/details`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/details`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**           | **Type**           | **Valeur par défaut** | **Description**                                                                                       |
|-------------------------|--------------------|------------------------|-------------------------------------------------------------------------------------------------------|
| `showContent`           | `boolean`          | `false`                | Indique si le contenu supplémentaire doit être affiché par défaut.                                      |
| `summary`               | `rich-text`        | N/A                    | Le texte du résumé affiché par défaut, utilisé pour la bascule de contenu (c'est le texte dans `summary`). |

---

## Supports (Fonctionnalités prises en charge)

### **Alignement et HTML**
- `align` : Prend en charge les alignements `wide` et `full`.
- `anchor` : Permet d'ajouter une ancre au bloc.
- `html` : Ne supporte pas l'édition directe du HTML (`false`).

### **Couleurs**
- `gradients` : Prend en charge les dégradés pour le bloc.
- `link` : Permet de définir la couleur des liens.
- Contrôle de la couleur d'arrière-plan et du texte activé par défaut.

### **Espacement**
- `spacing.margin` : Permet de définir les marges du bloc.
- `spacing.padding` : Permet de définir le rembourrage intérieur du bloc.
- `spacing.blockGap` : Permet de définir l'espacement entre les blocs.

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

### **Bordures**
- Supporte les propriétés suivantes :
  - `color` : Couleur de la bordure.
  - `width` : Largeur de la bordure.
  - `style` : Style de bordure (`solid`, `dashed`, etc.).

---

## Contexte utilisé

Aucun contexte spécifique n'est utilisé dans ce bloc.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/details`.*