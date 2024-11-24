# Documentation du bloc `core/post-terms`

Le bloc **Post Terms** permet d'afficher les termes associés à un article ou une page, comme les catégories, les étiquettes, ou d'autres taxonomies.

---

## Description

Le bloc **Post Terms** est utilisé pour afficher les termes d'un article ou d'une page, comme les catégories et les étiquettes. Ce bloc peut être personnalisé pour ajuster le séparateur entre les termes, ainsi que les préfixes et suffixes qui les entourent.

---

## Contexte utilisé

Le bloc `core/post-terms` utilise les contextes suivants :
- **`postId`** : L'identifiant de la publication ou de la page.
- **`postType`** : Le type de la publication (par exemple, article, page).

---

## Propriétés (Attributs)

Le bloc **Post Terms** possède plusieurs attributs configurables :

- **`term`** : Permet de spécifier la taxonomie à afficher (par exemple, `category`, `post_tag`).
- **`textAlign`** : Définit l'alignement du texte des termes. Les options sont des valeurs CSS valides telles que `left`, `center`, ou `right`.
- **`separator`** : Détermine le séparateur utilisé entre les termes. Par défaut, il est défini à `", "` (virgule et espace).
- **`prefix`** : Permet d'ajouter un préfixe devant les termes affichés (par exemple, `Catégories : `).
- **`suffix`** : Permet d'ajouter un suffixe après les termes affichés (par exemple, `.`).

---

## Exemple

| **Propriétés**         | **Exemple**       |
|------------------------|-------------------|
| **viewportWidth**       | 350px             |

Cet exemple définit la largeur de la vue de l'exemple à 350 pixels.

---

## Fonctionnalités prises en charge (Supports)

### **Alignement**
- **`align`** : Permet d'aligner le texte des termes. Les options incluent `left`, `center`, et `right`.

### **Couleur**
- **`color`** : Permet de personnaliser la couleur du texte, de l'arrière-plan, et des liens. 
  - **`gradients`** : Permet l'application de dégradés.
  - **`link`** : Permet de personnaliser la couleur des liens.
  - **Contrôles par défaut expérimentaux** : Ces paramètres permettent de personnaliser les couleurs de fond et de texte.

### **Espacement**
- **`spacing`** : Permet de définir l'espacement autour du bloc.
  - **`margin`** : Espacement extérieur du bloc.
  - **`padding`** : Espacement intérieur du bloc.

### **Typographie**
- **`typography`** : Permet de définir la typographie du texte, y compris :
  - **`fontSize`** : Taille de la police.
  - **`lineHeight`** : Hauteur de ligne.
  - **Propriétés expérimentales** : Permet de personnaliser la famille de polices, le poids, le style, la transformation du texte, la décoration du texte et l'espacement des lettres.

### **Bordure**
- **`__experimentalBorder`** : Permet de définir les bordures du bloc.
  - **`radius`** : Rayon de la bordure (arrondi).
  - **`color`** : Couleur de la bordure.
  - **`width`** : Largeur de la bordure.
  - **`style`** : Style de la bordure (par exemple, solide, pointillée).

### **Interactivité**
- **`interactivity`** : Le bloc prend en charge l'interactivité pour la navigation client, permettant une navigation fluide.

---

## Style

Le bloc **Post Terms** utilise un style prédéfini :

- **`style`** : Le style du bloc est défini par **`wp-block-post-terms`**.

---

## Conclusion

Le bloc **Post Terms** permet d'afficher les termes associés à un post ou une page (comme les catégories ou les étiquettes). Il offre une personnalisation étendue des termes affichés, y compris des options pour le séparateur, le préfixe, le suffixe et l'alignement. Le bloc prend également en charge la personnalisation de la couleur, de la typographie, des bordures et de l'espacement, permettant ainsi de l'adapter à l'apparence du site.
