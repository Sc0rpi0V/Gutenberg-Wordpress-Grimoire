# Documentation du bloc `core/columns`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/columns`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**           | **Type**           | **Valeur par défaut** | **Description**                                                                                       |
|-------------------------|--------------------|------------------------|-------------------------------------------------------------------------------------------------------|
| `verticalAlignment`     | `string`          | -                      | Alignement vertical du contenu des colonnes.                                                         |
| `isStackedOnMobile`     | `boolean`         | `true`                 | Détermine si les colonnes doivent être empilées sur les écrans mobiles.                               |
| `templateLock`          | `string | boolean`| -                      | Contrôle le verrouillage de l'édition (`all`, `insert`, `contentOnly`, ou `false`).                 |

---

## Supports (Fonctionnalités prises en charge)

### **Ancrage et alignement**
- `anchor` : Permet de définir un identifiant unique pour le bloc.
- `align` : Prend en charge les alignements `wide` et `full`.
- `html` : Ne supporte pas l'édition directe du HTML (`false`).

### **Couleurs**
- `gradients` : Prend en charge les dégradés pour le bloc.
- `link` : Permet de définir la couleur des liens.
- `heading` : Permet de définir la couleur des titres.
- `button` : Permet de définir la couleur des boutons.
- Contrôle de la couleur d'arrière-plan et du texte activé par défaut.

### **Espacement**
- `spacing.blockGap` : Définit l'écart entre les blocs enfants (par défaut `2em`).
- `spacing.margin` : Permet de définir les marges en haut et en bas des colonnes.
- `spacing.padding` : Permet de définir le rembourrage intérieur des colonnes.

### **Dispositions (Layout)**
- `layout.allowSwitching` : Empêche le changement de type de disposition.
- `layout.allowInheriting` : Empêche l'héritage de la disposition des colonnes.
- `layout.allowEditing` : Empêche la modification de la disposition des colonnes.
- Par défaut, utilise une disposition `flex` avec `flexWrap` défini sur `nowrap`.

### **Bordures**
- Supporte les propriétés suivantes :
  - `color` : Couleur de la bordure.
  - `radius` : Rayon des coins.
  - `style` : Style de bordure (`solid`, `dashed`, etc.).
  - `width` : Largeur de la bordure.

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

### **Ombres (Shadow)**
- Supporte l'ajout d'ombres sur le bloc.

---

## Styles

- **Éditeur** : Gère l'apparence de l'éditeur avec les contrôles définis ci-dessus.
- **Global** : Applique un style global basé sur les contrôles d'interface.

---

## Contexte utilisé

Le bloc utilise les variables de contexte suivantes :
- `postId` : ID du post parent.
- `postType` : Type de contenu (`post`, `page`, etc.).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/columns`.*