# Documentation du bloc `core/archives`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/archives`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|----------------------|------------|------------------------|-------------------------------------------------------------------------------|
| `displayAsDropdown` | `boolean`  | `false`               | Affiche les archives sous forme de menu déroulant si activé.                 |
| `showLabel`         | `boolean`  | `true`                | Affiche une étiquette descriptive pour le bloc si activé.                    |
| `showPostCounts`    | `boolean`  | `false`               | Affiche le nombre de posts pour chaque archive si activé.                    |
| `type`              | `string`   | `"monthly"`           | Type d'archive à afficher (`monthly`, `yearly`, etc.).                       |

---

## Supports (Fonctionnalités prises en charge)

### **Alignement**
- `align` : Prend en charge les options d'alignement (`wide`, `full`, `center`, etc.).

### **Bordures**
- Supporte les propriétés suivantes :
  - `radius` : Rayon des coins.
  - `color` : Couleur de la bordure.
  - `width` : Largeur de la bordure.
  - `style` : Style de bordure (`solid`, `dashed`, etc.).

### **Espacement**
- Supporte les propriétés d'espacement :
  - `margin` : Marges extérieures.
  - `padding` : Espacement intérieur.

### **Typographie**
- Supporte les propriétés typographiques suivantes :
  - `fontSize` : Taille de police.
  - `lineHeight` : Hauteur de ligne.
  - Propriétés expérimentales :
    - `fontFamily`
    - `fontWeight`
    - `fontStyle`
    - `textTransform`
    - `textDecoration`
    - `letterSpacing`

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client.

---

## Styles

- `editorStyle` : Définit le style dans l'éditeur (`wp-block-archives-editor`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/archives`.*
