# Documentation du bloc `core/button`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/button`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|----------------------|------------|------------------------|-------------------------------------------------------------------------------|
| `tagName`           | `string`   | `a`                    | Définit le tag HTML utilisé pour le bloc (`a` ou `button`).                    |
| `type`              | `string`   | `button`               | Type du bouton, par défaut `button`.                                           |
| `textAlign`         | `string`   | -                      | Alignement du texte à l'intérieur du bouton.                                   |
| `url`               | `string`   | -                      | L'URL associée au bouton (pour les liens).                                     |
| `title`             | `string`   | -                      | Le titre du lien ou du bouton.                                                 |
| `text`              | `rich-text`| -                      | Le texte du bouton.                                                           |
| `linkTarget`        | `string`   | -                      | Définit l'attribut `target` pour le lien (`_blank`, `_self`, etc.).           |
| `rel`               | `string`   | -                      | Définit l'attribut `rel` pour le lien.                                        |
| `placeholder`       | `string`   | -                      | Texte d'espace réservé pour le bouton.                                         |
| `backgroundColor`   | `string`   | -                      | Couleur de fond du bouton.                                                    |
| `textColor`         | `string`   | -                      | Couleur du texte du bouton.                                                   |
| `gradient`          | `string`   | -                      | Gradient appliqué au bouton.                                                  |
| `width`             | `number`   | -                      | Largeur du bouton.                                                            |

---

## Supports (Fonctionnalités prises en charge)

### **Ancrage**
- `anchor` : Permet de définir un identifiant unique pour le bloc.

### **Divisions**
- `splitting` : Permet d'activer le découpage du texte du bloc en plusieurs parties.

### **Alignement et largeurs**
- `align` : Alignement du bloc.
- `alignWide` : Supporte l'alignement large.

### **Couleurs et Styles**

- Supporte les couleurs :
  - `background` : Couleur de fond.
  - `text` : Couleur du texte.
  - `gradients` : Gradient de fond.
  
- Propriétés expérimentales :
  - `shadow` : Ombre (désactivée pour la sérialisation).
  - `border` : Propriétés de bordure (`color`, `radius`, `style`, `width`).
  - `spacing` : Espacement horizontal et vertical.

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
    - `writingMode`

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client.

### **Sélecteur expérimental**
- `__experimentalSelector` : Sélecteur CSS pour cibler le lien dans le bloc.

---

## Styles

- **Styles disponibles** :
  - `fill` : Style par défaut, fond rempli.
  - `outline` : Style avec un contour.

---

## Styles et apparence

- `editorStyle` : Définit le style dans l'éditeur (`wp-block-button-editor`).
- `style` : Définit le style global pour le bouton (`wp-block-button`).
  
---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/button`.*
"""

# Sauvegarde du contenu dans un fichier Markdown
file_path_button = "/mnt/data/core_button_block.md"
with open(file_path_button, "w") as file:
    file.write(button_md)

file_path_button
