# Documentation du bloc `core/categories`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/categories`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `taxonomy`          | `string`   | `"category"`          | La taxonomie des termes à afficher (ex : `category`, `post_tag`, etc.).        |
| `displayAsDropdown` | `boolean`  | `false`               | Affiche les termes sous forme de menu déroulant si activé.                     |
| `showHierarchy`     | `boolean`  | `false`               | Affiche la hiérarchie des termes si activé (affiche les sous-catégories).     |
| `showPostCounts`    | `boolean`  | `false`               | Affiche le nombre de posts pour chaque terme si activé.                        |
| `showOnlyTopLevel`  | `boolean`  | `false`               | Affiche uniquement les termes de niveau supérieur.                            |
| `showEmpty`         | `boolean`  | `false`               | Affiche les termes qui n'ont pas de posts associés si activé.                 |
| `label`             | `string`   | N/A                   | Libellé à afficher pour le bloc.                                              |
| `showLabel`         | `boolean`  | `true`                | Affiche une étiquette descriptive pour le bloc si activé.                     |

---

## Contextes utilisés

- **`enhancedPagination`** : Ce bloc utilise le contexte `enhancedPagination` pour offrir une pagination améliorée.

---

## Supports (Fonctionnalités prises en charge)

### **Alignement**
- `align` : Prend en charge les options d'alignement (`wide`, `full`, `center`, etc.).

### **HTML**
- `html` : La gestion du HTML est désactivée pour ce bloc (`false`).

### **Espacement**
- `spacing` : 
  - **margin** : Prend en charge l'option de marge extérieure.
  - **padding** : Prend en charge l'option de padding intérieur.
  - **__experimentalDefaultControls** : Les contrôles par défaut pour la marge et le padding sont désactivés (`false`).

### **Typographie**
- `typography` :
  - **fontSize** : Permet de modifier la taille de la police.
  - **lineHeight** : Permet de modifier la hauteur de ligne.
  - Propriétés expérimentales :
    - `__experimentalFontFamily` : Permet de définir la famille de police.
    - `__experimentalFontWeight` : Permet de définir le poids de la police.
    - `__experimentalFontStyle` : Permet de définir le style de la police (ex : italique).
    - `__experimentalTextTransform` : Permet de modifier la transformation du texte (majuscule, minuscule, etc.).
    - `__experimentalTextDecoration` : Permet d'ajouter des décorations au texte (ex : souligné).
    - `__experimentalLetterSpacing` : Permet de définir l'espacement entre les lettres.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `fontSize`.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client, ce qui permet une navigation dynamique entre les termes.

### **Bordures**
- **`__experimentalBorder`** :
  - **radius** : Permet de définir le rayon des coins.
  - **color** : Permet de définir la couleur de la bordure.
  - **width** : Permet de définir la largeur de la bordure.
  - **style** : Permet de définir le style de la bordure (ex : `solid`, `dashed`).
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `radius`, `color`, `width`, et `style`.

---

## Styles

- **`editorStyle`** : Définit le style dans l'éditeur pour ce bloc, ici spécifié par la classe CSS `wp-block-categories-editor`.
- **`style`** : Définit le style dans le front-end pour ce bloc, ici spécifié par la classe CSS `wp-block-categories`.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/categories`.* 
