# Documentation du bloc `core/column`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/column`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**           | **Type**           | **Valeur par défaut** | **Description**                                                                                       |
|-------------------------|--------------------|------------------------|-------------------------------------------------------------------------------------------------------|
| `verticalAlignment`     | `string`          | -                      | Alignement vertical du contenu de la colonne.                                                        |
| `width`                 | `string`          | -                      | Largeur de la colonne.                                                                                |
| `allowedBlocks`         | `array`           | -                      | Liste des blocs autorisés à l'intérieur de cette colonne.                                            |
| `templateLock`          | `string | boolean`| -                      | Contrôle le verrouillage de l'édition (`all`, `insert`, `contentOnly`, ou `false`).                 |

---

## Supports (Fonctionnalités prises en charge)

### **Ancrage et alignement**
- `anchor` : Permet de définir un identifiant unique pour le bloc.
- `reusable` : Le bloc n'est pas réutilisable (`false`).
- `html` : Ne supporte pas l'édition directe du HTML (`false`).

### **Couleurs**
- `gradients` : Prend en charge les dégradés pour le bloc.
- `heading` : Permet de définir la couleur des titres.
- `button` : Permet de définir la couleur des boutons.
- `link` : Permet de définir la couleur des liens.
- Contrôle de la couleur d'arrière-plan et du texte activé par défaut.

### **Espacement**
- `spacing.blockGap` : Gère l'écart entre les blocs enfants.
- `spacing.padding` : Contrôle le rembourrage intérieur.

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

### **Dispositions (Layout)**
- Supporte la gestion de la disposition des éléments enfants.

### **Interactivité**
- `clientNavigation` : Permet de capturer des événements de navigation.

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

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/column`.*