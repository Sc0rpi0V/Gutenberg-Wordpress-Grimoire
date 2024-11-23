# Documentation du bloc `core/group`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/group`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**         | **Type**           | **Valeur par défaut** | **Description**                                                                                        |
|----------------------|--------------------|-----------------------|--------------------------------------------------------------------------------------------------------|
| `tagName`            | `string`           | `div`                 | Le nom de la balise HTML utilisée pour afficher le bloc.                                               |
| `templateLock`       | `string`, `boolean`| `false`               | Définit les verrouillages de modèle, contrôlant les modifications du contenu ou de la structure.         |
| `allowedBlocks`      | `array`            |                       | Liste des blocs autorisés à être ajoutés dans ce groupe.                                               |

---

## Supports (Fonctionnalités prises en charge)

### **Alignement et HTML**
- `align` : Prend en charge les alignements `wide` et `full`.
- `anchor` : Permet d'ajouter un identifiant d'ancrage pour ce bloc.
- `ariaLabel` : Permet de définir un label accessible (pour l'ARIA).
- `html` : Ne supporte pas l'édition directe du HTML (`false`).

### **Arrière-plan**
- `backgroundImage` : Prend en charge l'ajout d'une image d'arrière-plan.
- `backgroundSize` : Permet de contrôler la taille de l'image d'arrière-plan.
- Contrôle d'arrière-plan activé par défaut.

### **Couleurs**
- `gradients` : Prend en charge les dégradés de couleur.
- `heading` : Permet de définir la couleur des titres.
- `button` : Permet de définir la couleur des boutons.
- `link` : Permet de définir la couleur des liens.
- Contrôle d'arrière-plan et de texte activé par défaut.

### **Ombres**
- `shadow` : Permet de définir des ombres sur le bloc.

### **Espacement**
- `spacing.margin` : Permet de définir les marges du bloc (top, bottom).
- `spacing.padding` : Permet de définir le rembourrage intérieur du bloc.
- `spacing.blockGap` : Permet de définir l'écart entre les blocs enfants.
- Contrôle des espacements activé par défaut.

### **Dimensions**
- `dimensions.minHeight` : Permet de définir une hauteur minimale pour le bloc.

### **Bordures**
- Supporte les propriétés suivantes :
  - `color` : Couleur de la bordure.
  - `radius` : Rayon des coins.
  - `style` : Style de la bordure (par exemple, `solid` ou `dashed`).
  - `width` : Largeur de la bordure.
- Contrôle des bordures activé par défaut.

### **Position**
- `position.sticky` : Permet de rendre le bloc "collant" lors du défilement.

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
- Contrôle de la taille de la police activé par défaut.

### **Disposition**
- `layout.allowSizingOnChildren` : Permet de redimensionner les blocs enfants au sein du groupe.

---

## Contexte utilisé

Le bloc utilise le contexte suivant :
- `clientNavigation` : Permet la navigation côté client.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/group`.*