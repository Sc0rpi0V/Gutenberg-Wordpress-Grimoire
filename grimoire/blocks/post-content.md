# Documentation du bloc `core/post-content`

Le bloc **Content** permet d'afficher le contenu d'un article ou d'une page.

---

## Description

Le bloc **Content** est utilisé pour afficher le contenu principal d’un article ou d’une page. Il est automatiquement rempli avec le contenu d’une publication lorsque utilisé dans une page ou un article WordPress.

---

## Contexte utilisé

Le bloc `core/post-content` utilise les contextes suivants :
- **`postId`** : L’identifiant de la publication ou de la page.
- **`postType`** : Le type de publication (par exemple, article, page).
- **`queryId`** : L’identifiant de la requête (utile dans les boucles ou les requêtes personnalisées).

---

## Exemple

| **Propriétés**         | **Exemple**       |
|------------------------|-------------------|
| **viewportWidth**       | 350px             |

Cet exemple définit la largeur de la vue de l'exemple à 350 pixels.

---

## Fonctionnalités prises en charge (Supports)

### **Alignement**
- **`align`** : Le bloc prend en charge les alignements **wide** et **full**.

### **HTML**
- **`html`** : Le bloc ne permet pas de modification directe du HTML (`html: false`).

### **Disposition**
- **`layout`** : Le bloc prend en charge la mise en page.

### **Fond**
- **`background`** : Permet de personnaliser l'image d'arrière-plan et sa taille.
  - **`backgroundImage`** : Définit une image d'arrière-plan.
  - **`backgroundSize`** : Définit la taille de l'image d'arrière-plan.
  - **Contrôles par défaut expérimentaux** :
    - **`backgroundImage`** : Activé.

### **Dimensions**
- **`dimensions`** : Prend en charge la configuration de la hauteur minimale.
  - **`minHeight`** : Hauteur minimale pour le bloc.

### **Espacement**
- **`spacing`** : Permet de gérer l'espacement autour du bloc.
  - **`blockGap`** : Espacement entre les blocs.
  - **`padding`** : Espacement intérieur du bloc.
  - **`margin`** : Espacement extérieur du bloc.
  - **Contrôles par défaut expérimentaux** :
    - **`margin`** et **`padding`** : Désactivé.

### **Couleur**
- **`color`** : Permet la gestion des couleurs.
  - **`gradients`** : Applique des dégradés de couleur.
  - **`link`** : Contrôle la couleur des liens.
  - **Contrôles par défaut expérimentaux** :
    - **`background`** et **`text`** : Désactivés.

### **Typographie**
- **`typography`** : Permet de personnaliser les propriétés typographiques.
  - **`fontSize`** : Taille de la police.
  - **`lineHeight`** : Hauteur de ligne.
  - **`fontFamily`** : Famille de police.
  - **`fontWeight`** : Poids de la police.
  - **`fontStyle`** : Style de la police (italique, normal).
  - **`textTransform`** : Transformation du texte (majuscules, minuscules).
  - **`textDecoration`** : Décoration du texte (souligné, barré, etc.).
  - **`letterSpacing`** : Espacement des lettres.
  - **Contrôles par défaut expérimentaux** :
    - **`fontSize`** : Activé.

### **Bordure**
- **`__experimentalBorder`** : Prend en charge les propriétés de bordure.
  - **`radius`** : Rayon des bords.
  - **`color`** : Couleur de la bordure.
  - **`width`** : Largeur de la bordure.
  - **`style`** : Style de la bordure (solide, pointillé, etc.).
  - **Contrôles par défaut expérimentaux** :
    - **`radius`**, **`color`**, **`width`**, **`style`** : Activés.

---

## Styles

- **`style`** : Le style par défaut du bloc est défini par **`wp-block-post-content`**.
- **`editorStyle`** : Le style d'éditeur pour ce bloc est défini par **`wp-block-post-content-editor`**.

---

*Cette documentation est basée sur les informations contenues dans le fichier `block.json` du bloc `core/post-content`.* 
