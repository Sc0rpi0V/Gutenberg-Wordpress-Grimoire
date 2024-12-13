# Documentation du bloc `core/comment-author-avatar` (déprécié)

Ce document détaille les attributs et les fonctionnalités du bloc **`core/comment-author-avatar`** dans WordPress Gutenberg. Ce bloc est désormais déprécié et il est recommandé d'utiliser le bloc **`Avatar`** à la place.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|---------------------|------------|-----------------------|-------------------------------------------------------------------------------|
| `width`             | `number`   | `96`                  | Largeur de l'avatar en pixels.                                                |
| `height`            | `number`   | `96`                  | Hauteur de l'avatar en pixels.                                                |

---

## Contexte utilisé

- **`commentId`** : Ce bloc utilise le contexte `commentId`, ce qui permet de lier l'avatar à un commentaire spécifique.

---

## Supports (Fonctionnalités prises en charge)

### **HTML**
- `html` : Ce bloc ne prend pas en charge l'édition HTML.

### **Inserter**
- `inserter` : Le bloc est désactivé dans l'inserteur, ce qui signifie qu'il ne peut pas être ajouté directement à l'éditeur de blocs via l'interface.

### **Bordures**
- **`__experimentalBorder`** :
  - **radius** : Permet de définir le rayon des coins de l'avatar.
  - **width** : Permet de définir la largeur de la bordure de l'avatar.
  - **color** : Permet de définir la couleur de la bordure de l'avatar.
  - **style** : Permet de définir le style de la bordure (ex : `solid`, `dashed`).

### **Couleurs**
- **`color`** :
  - **background** : Permet de définir la couleur de fond de l'avatar.
  - **text** : Pas de support pour la couleur du texte.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background`.

### **Espacement**
- **`spacing`** :
  - **margin** : Permet de définir des marges autour de l'avatar.
  - **padding** : Permet de définir un espacement intérieur pour l'avatar.
  - **__experimentalSkipSerialization** : Indique que les propriétés d'espacement ne sont pas sérialisées dans le bloc de manière classique.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client.

---

## Notes supplémentaires
- Ce bloc est **déprécié** et il est recommandé de remplacer ce bloc par le bloc **`Avatar`** pour une meilleure compatibilité et flexibilité dans les versions futures de WordPress.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comment-author-avatar`.* 
