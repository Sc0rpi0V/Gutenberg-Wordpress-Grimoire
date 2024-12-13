# Documentation du bloc `core/comment-template`

Ce document présente les attributs et les fonctionnalités du bloc **`core/comment-template`** dans WordPress Gutenberg. Ce bloc contient les éléments nécessaires pour afficher un commentaire, tels que le titre, la date, l'auteur, l'avatar, etc.

---

## Attributs principaux

Ce bloc ne comporte pas d'attributs personnalisés définis dans le fichier `block.json`. Toutefois, il peut être utilisé pour structurer le contenu de commentaires dans le cadre de discussions.

---

## Contexte utilisé

- **`postId`** : Ce bloc utilise le contexte `postId`, ce qui permet d’afficher les commentaires d’un article spécifique en fonction de son identifiant.

---

## Supports (Fonctionnalités prises en charge)

### **Alignement**
- **`align`** : Ce bloc prend en charge l'alignement. Vous pouvez aligner le contenu du bloc selon les options d'alignement disponibles (gauche, centre, droite).

### **HTML**
- **`html`** : Ce bloc ne permet pas l'édition HTML.

### **Réutilisation**
- **`reusable`** : Ce bloc n'est pas réutilisable.

### **Espacement**
- **`spacing`** :
  - **margin** : Permet de définir les marges extérieures du bloc.
  - **padding** : Permet de définir les espacements internes du bloc.

### **Typographie**
- **`typography`** :
  - **fontSize** : Permet de définir la taille de la police pour le texte du bloc.
  - **lineHeight** : Permet de définir la hauteur de ligne pour le texte du bloc.
  - **__experimentalFontFamily** : Permet de définir la famille de police.
  - **__experimentalFontWeight** : Permet de définir le poids de la police.
  - **__experimentalFontStyle** : Permet de définir le style de la police (ex: italique).
  - **__experimentalTextTransform** : Permet de définir la transformation du texte (ex: `uppercase`).
  - **__experimentalTextDecoration** : Permet de définir la décoration du texte (ex: souligné).
  - **__experimentalLetterSpacing** : Permet de définir l’espacement des lettres.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `fontSize`.

### **Interactivité**
- **`interactivity`** :
  - **clientNavigation** : Permet de naviguer dans l'interface cliente, avec une prise en charge de la navigation côté client.

### **Bordures**
- **`__experimentalBorder`** :
  - **radius** : Permet de définir le rayon des coins du bloc.
  - **color** : Permet de définir la couleur de la bordure du bloc.
  - **width** : Permet de définir la largeur de la bordure.
  - **style** : Permet de définir le style de la bordure (ex: `solid`, `dashed`).
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `radius`, `color`, `width`, et `style`.

---

## Styles

- `style` : Définit le style du bloc dans l'éditeur (`wp-block-comment-template`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/comment-template`.* 
