# Documentation du bloc `core/post-title`

Le bloc **Post Title** permet d'afficher le titre d'un article, d'une page ou de tout autre type de contenu.

---

## Description

Le bloc **Post Title** affiche le titre d'une publication, qu'il s'agisse d'un article, d'une page ou d'un autre type de contenu. Ce bloc est flexible et permet de personnaliser l'apparence du titre avec diverses options, comme le niveau de titre (H1, H2, etc.), l'alignement, et l'option de transformer le titre en un lien.

---

## Contexte utilisé

Le bloc `core/post-title` utilise les contextes suivants :
- **`postId`** : L'identifiant de la publication ou de la page.
- **`postType`** : Le type de la publication (par exemple, article, page).
- **`queryId`** : Identifiant de la requête utilisée dans le contexte (si applicable).

---

## Propriétés (Attributs)

Le bloc **Post Title** possède plusieurs attributs configurables :

- **`textAlign`** : Définit l'alignement du texte du titre. Les options incluent des valeurs CSS valides telles que `left`, `center`, ou `right`.
- **`level`** : Permet de spécifier le niveau du titre. Par défaut, il est défini sur `2` (correspond à `<h2>`). Il peut être modifié pour `h1`, `h3`, etc.
- **`levelOptions`** : Liste des niveaux disponibles pour le titre (par exemple, `[1, 2, 3, 4, 5, 6]`).
- **`isLink`** : Permet de transformer le titre en un lien. Par défaut, il est défini sur `false`.
- **`rel`** : Permet d'ajouter un attribut `rel` au lien du titre (par exemple, `noopener`, `noreferrer`).
- **`linkTarget`** : Détermine où s'ouvrira le lien du titre. Par défaut, il est défini sur `_self` (ouvrir dans le même onglet).

---

## Exemple

| **Propriétés**         | **Exemple**       |
|------------------------|-------------------|
| **viewportWidth**       | 350px             |

Cet exemple définit la largeur de la vue de l'exemple à 350 pixels.

---

## Fonctionnalités prises en charge (Supports)

### **Alignement**
- **`align`** : Permet d'aligner le titre. Les options incluent `wide` et `full` pour un alignement large ou complet.

### **Couleur**
- **`color`** : Permet de personnaliser la couleur du texte, du fond et des liens.
  - **`gradients`** : Permet d'appliquer des dégradés.
  - **`link`** : Permet de personnaliser la couleur des liens.
  - **Contrôles par défaut expérimentaux** : Ces paramètres permettent de personnaliser les couleurs de fond et de texte.

### **Espacement**
- **`spacing`** : Permet de définir l'espacement autour du bloc.
  - **`margin`** : Espacement extérieur du bloc.
  - **`padding`** : Espacement intérieur du bloc.

### **Typographie**
- **`typography`** : Permet de personnaliser la typographie du titre, y compris :
  - **`fontSize`** : Taille de la police.
  - **`lineHeight`** : Hauteur de ligne.
  - **Propriétés expérimentales** : Permet de personnaliser la famille de polices, le poids, le style, la transformation du texte, la décoration du texte et l'espacement des lettres.

### **Bordure**
- **`__experimentalBorder`** : Permet de définir les bordures du titre.
  - **`radius`** : Rayon de la bordure (arrondi).
  - **`color`** : Couleur de la bordure.
  - **`width`** : Largeur de la bordure.
  - **`style`** : Style de la bordure (par exemple, solide, pointillée).

### **Interactivité**
- **`interactivity`** : Le bloc prend en charge l'interactivité pour la navigation client, permettant une navigation fluide.

---

## Style

Le bloc **Post Title** utilise un style prédéfini :

- **`style`** : Le style du bloc est défini par **`wp-block-post-title`**.

---

## Conclusion

Le bloc **Post Title** permet d'afficher le titre d'une publication, d'une page ou d'un autre type de contenu, avec de nombreuses options de personnalisation. Il permet de contrôler le niveau du titre (H1, H2, etc.), l'alignement du texte, et de le transformer en lien. Il prend également en charge des options de personnalisation avancées, telles que la couleur, la typographie, les bordures et l'espacement.
