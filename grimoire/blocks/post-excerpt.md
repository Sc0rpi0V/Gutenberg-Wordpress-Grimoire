# Documentation du bloc `core/post-excerpt`

Le bloc **Excerpt** permet d'afficher l'extrait d'une publication, comme un article ou une page.

---

## Description

Le bloc **Excerpt** affiche l'extrait d'une publication, offrant ainsi une manière concise de présenter une partie du contenu. Il permet de personnaliser l'apparence de l'extrait, la longueur, et même d'ajouter un lien vers la publication complète.

---

## Contexte utilisé

Le bloc `core/post-excerpt` utilise les contextes suivants :
- **`postId`** : L’identifiant de la publication ou de la page.
- **`postType`** : Le type de publication (article, page, etc.).
- **`queryId`** : L’identifiant de la requête (utile dans les boucles ou requêtes personnalisées).

---

## Propriétés (Attributs)

Le bloc **Excerpt** possède plusieurs attributs configurables :

- **`textAlign`** : Aligne le texte de l'extrait (par exemple, `left`, `center`, `right`).
- **`moreText`** : Texte à afficher pour le lien "Lire la suite" ou similaire (par exemple, "Lire la suite").
- **`showMoreOnNewLine`** : Un attribut booléen qui détermine si le lien vers la publication complète doit être affiché sur une nouvelle ligne. Par défaut, il est activé (**`true`**).
- **`excerptLength`** : La longueur de l'extrait en nombre de mots. Par défaut, elle est définie à 55 mots.

---

## Exemple

| **Propriétés**         | **Exemple**       |
|------------------------|-------------------|
| **viewportWidth**       | 350px             |

Cet exemple définit la largeur de la vue de l'exemple à 350 pixels.

---

## Fonctionnalités prises en charge (Supports)

### **HTML**
- **`html`** : Le bloc ne permet pas de modification directe du HTML (`html: false`).

### **Couleur**
- **`color`** : Permet de personnaliser les couleurs.
  - **`gradients`** : Applique des dégradés de couleur.
  - **`link`** : Contrôle la couleur des liens.
  - **Contrôles par défaut expérimentaux** :
    - **`background`**, **`text`**, **`link`** : Activés.

### **Espacement**
- **`spacing`** : Permet de gérer l'espacement autour du bloc.
  - **`margin`** : Espacement extérieur du bloc.
  - **`padding`** : Espacement intérieur du bloc.

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

### **Interactivité**
- **`interactivity`** : Le bloc prend en charge l’interactivité pour la navigation client, permettant une navigation fluide.

---

## Styles

Le bloc **Excerpt** possède plusieurs styles associés :

- **`style`** : Le style par défaut du bloc est défini par **`wp-block-post-excerpt`**.
- **`editorStyle`** : Le style d'éditeur pour ce bloc est défini par **`wp-block-post-excerpt-editor`**.

---

## Conclusion

Le bloc **Excerpt** permet d'afficher un extrait d'article ou de page, avec de nombreuses options de personnalisation concernant la longueur de l'extrait, l'alignement du texte, la gestion des couleurs et typographies, ainsi que l'affichage d'un lien vers l'article complet. Ce bloc est utile pour afficher une présentation condensée d'un contenu plus long sur des pages de liste ou d'archive.
