# Documentation du bloc `core/avatar`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/avatar`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|----------------------|------------|------------------------|-------------------------------------------------------------------------------|
| `userId`            | `number`   | -                      | ID de l'utilisateur dont l'avatar est affiché.                                |
| `size`              | `number`   | `96`                   | Taille de l'avatar en pixels.                                                 |
| `isLink`            | `boolean`  | `false`                | Si activé, l'avatar devient un lien cliquable.                               |
| `linkTarget`        | `string`   | `_self`                | Définit où s'ouvre le lien (`_self`, `_blank`, etc.).                         |

---

## Contexte utilisé

- `postType` : Type de contenu du post.
- `postId` : ID du post.
- `commentId` : ID du commentaire.

---

## Supports (Fonctionnalités prises en charge)

### **HTML et alignement**
- `html` : Le bloc ne permet pas l'édition HTML.
- `align` : Prend en charge les options d'alignement (`wide`, `full`, `center`, etc.).
- `alignWide` : Ne supporte pas l'alignement large.

### **Espacement**
- Supporte les propriétés d'espacement :
  - `margin` : Marges extérieures.
  - `padding` : Espacement intérieur.

### **Bordures**
- Supporte les propriétés suivantes :
  - `radius` : Rayon des coins arrondis.
  - `width` : Largeur de la bordure.
  - `color` : Couleur de la bordure.
  - `style` : Style de la bordure (`solid`, `dashed`, etc.).

### **Couleur**
- Le bloc ne prend pas en charge la couleur du texte et du fond.
- `__experimentalDuotone` : Applique un effet duotone sur l'image de l'avatar.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client.

---

## Sélecteurs CSS

- `border` : Sélecteur pour cibler l'image de l'avatar `.wp-block-avatar img`.

---

## Styles

- `editorStyle` : Définit le style dans l'éditeur (`wp-block-avatar-editor`).
- `style` : Définit le style global (`wp-block-avatar`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/avatar`.* 
"""

# Sauvegarde du contenu dans un fichier Markdown
file_path_avatar = "/mnt/data/core_avatar_block.md"
with open(file_path_avatar, "w") as file:
    file.write(avatar_md)

file_path_avatar
