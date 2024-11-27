# Documentation du bloc `core/post-featured-image`

Le bloc **Featured Image** permet d'afficher l'image à la une d'un article ou d'une page.

---

## Description

Le bloc **Featured Image** permet d'afficher l'image à la une d'un post, d'une page ou de tout autre type de contenu. Il offre des options pour personnaliser l'affichage de l'image, son aspect, son lien, et des effets visuels tels que des filtres ou des superpositions.

---

## Contexte utilisé

Le bloc `core/post-featured-image` utilise les contextes suivants :
- **`postId`** : L'identifiant de la publication ou de la page.
- **`postType`** : Le type de la publication (par exemple, article, page).
- **`queryId`** : L'identifiant de la requête (utile dans les boucles ou requêtes personnalisées).

---

## Propriétés (Attributs)

Le bloc **Featured Image** possède plusieurs attributs configurables :

- **`isLink`** : Attribut booléen déterminant si l'image est cliquable et redirige vers l'article. Par défaut, il est désactivé (`false`).
- **`aspectRatio`** : Permet de définir un ratio d'aspect spécifique pour l'image (par exemple, "16:9").
- **`width`** : La largeur de l'image.
- **`height`** : La hauteur de l'image.
- **`scale`** : Définit l'échelle de l'image, avec des valeurs comme `cover` ou `contain`. Par défaut, il est défini à `cover`.
- **`sizeSlug`** : Permet de spécifier la taille de l'image à afficher (par exemple, `thumbnail`, `medium`, `large`).
- **`rel`** : Spécifie l'attribut `rel` du lien, utile pour le SEO ou la gestion des liens externes.
- **`linkTarget`** : Détermine si le lien de l'image s'ouvre dans une nouvelle fenêtre (`_self`, `_blank`, etc.).
- **`overlayColor`** : Permet d'ajouter une couleur de superposition sur l'image.
- **`customOverlayColor`** : Permet de définir une couleur de superposition personnalisée.
- **`dimRatio`** : Le taux de fondu de l'image (0 = sans effet, 100 = entièrement foncée).
- **`gradient`** : Permet d'appliquer un gradient sur l'image.
- **`customGradient`** : Permet d'appliquer un gradient personnalisé.
- **`useFirstImageFromPost`** : Attribut booléen permettant d'utiliser la première image de l'article comme image à la une, au lieu de la valeur définie manuellement.

---

## Exemple

| **Propriétés**         | **Exemple**       |
|------------------------|-------------------|
| **viewportWidth**       | 350px             |

Cet exemple définit la largeur de la vue de l'exemple à 350 pixels.

---

## Fonctionnalités prises en charge (Supports)

### **Alignement**
- **`align`** : Permet d'aligner l'image. Les options sont `left`, `right`, `center`, `wide`, et `full`.

### **Couleur**
- **`color`** : L'image ne permet pas de modification des couleurs de texte ou de fond (c'est-à-dire `text: false`, `background: false`).

### **Bordure**
- **`__experimentalBorder`** : Permet de personnaliser les bordures de l'image.
  - **`color`** : Couleur de la bordure.
  - **`radius`** : Rayon de la bordure (arrondie).
  - **`width`** : Largeur de la bordure.
  - **Contrôles par défaut expérimentaux** : Ces paramètres sont activés et permettent la personnalisation.

### **Filtre**
- **`filter`** : Permet d'appliquer un filtre de type **duotone** sur l'image.

### **Ombre**
- **`shadow`** : Il est possible d'ajouter des ombres à l'image. Toutefois, la sérialisation de ces styles est désactivée.

### **Espacement**
- **`spacing`** : Permet de gérer l'espacement autour du bloc.
  - **`margin`** : Espacement extérieur du bloc.
  - **`padding`** : Espacement intérieur du bloc.

### **Interactivité**
- **`interactivity`** : Le bloc prend en charge l’interactivité pour la navigation client, permettant une navigation fluide.

---

## Sélecteurs

Le bloc **Featured Image** utilise plusieurs sélecteurs CSS pour appliquer des styles :

- **`border`** : Cible les éléments de bordure de l'image.
  - Sélecteurs : `.wp-block-post-featured-image img`, `.wp-block-post-featured-image .block-editor-media-placeholder`, `.wp-block-post-featured-image .wp-block-post-featured-image__overlay`.
- **`shadow`** : Cible les éléments d'ombre de l'image.
  - Sélecteurs : `.wp-block-post-featured-image img`, `.wp-block-post-featured-image .components-placeholder`.
- **`filter` (duotone)** : Cible les éléments nécessitant un filtre duotone.
  - Sélecteurs : `.wp-block-post-featured-image img`, `.wp-block-post-featured-image .wp-block-post-featured-image__placeholder`, `.wp-block-post-featured-image .components-placeholder__illustration`, `.wp-block-post-featured-image .components-placeholder::before`.

---

## Styles

Le bloc **Featured Image** possède plusieurs styles associés :

- **`style`** : Le style par défaut du bloc est défini par **`wp-block-post-featured-image`**.
- **`editorStyle`** : Le style d'éditeur pour ce bloc est défini par **`wp-block-post-featured-image-editor`**.

---

## Conclusion

Le bloc **Featured Image** est utile pour afficher l'image à la une d'un article, d'une page, ou de tout autre type de contenu. Il offre de nombreuses options de personnalisation telles que le ratio d'aspect, l'échelle de l'image, les effets de filtre, les superpositions et les bordures. De plus, il permet de lier l'image à l'article ou d'afficher l'image comme un simple élément visuel sans lien.
