# Documentation du bloc `core/comments`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/comments`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**           | **Type**           | **Valeur par défaut** | **Description**                                                                                       |
|-------------------------|--------------------|------------------------|-------------------------------------------------------------------------------------------------------|
| `tagName`              | `string`          | `div`                 | Le nom de la balise HTML utilisée pour afficher le bloc.                                              |
| `legacy`               | `boolean`         | `false`                | Indique si le bloc utilise une configuration héritée ou non.                                          |

---

## Supports (Fonctionnalités prises en charge)

### **Alignement et HTML**
- `align` : Prend en charge les alignements `wide` et `full`.
- `html` : Ne supporte pas l'édition directe du HTML (`false`).

### **Couleurs**
- `gradients` : Prend en charge les dégradés pour le bloc.
- `heading` : Permet de définir la couleur des titres.
- `link` : Permet de définir la couleur des liens.
- Contrôle de la couleur d'arrière-plan et du texte activé par défaut.

### **Espacement**
- `spacing.margin` : Permet de définir les marges du bloc.
- `spacing.padding` : Permet de définir le rembourrage intérieur du bloc.

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
  - `radius` : Rayon des coins.
  - `color` : Couleur de la bordure.
  - `width` : Largeur de la bordure.
  - `style` : Style de bordure (`solid`, `dashed`, etc.).

---

## Contexte utilisé

Le bloc utilise les variables de contexte suivantes :
- `postId` : ID du post parent.
- `postType` : Type de contenu (`post`, `page`, etc.).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comments`.*