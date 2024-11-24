# Documentation du bloc `core/post-date`

Le bloc **Date** permet d'afficher la date de publication d'une entrée, comme un article ou une page.

---

## Description

Le bloc **Date** affiche la date de publication d’un article ou d’une page WordPress. Il peut être configuré pour afficher la date dans différents formats et aligner le texte selon les besoins.

---

## Contexte utilisé

Le bloc `core/post-date` utilise les contextes suivants :
- **`postId`** : L’identifiant de la publication ou de la page.
- **`postType`** : Le type de publication (par exemple, article, page).
- **`queryId`** : L’identifiant de la requête (utile dans les boucles ou les requêtes personnalisées).

---

## Propriétés (Attributs)

Le bloc **Date** possède plusieurs attributs configurables :

- **`textAlign`** : Aligne le texte de la date (ex. : `left`, `right`, `center`).
- **`format`** : Le format de la date à afficher (par exemple : `Y-m-d` pour l'année, mois et jour).
- **`isLink`** : Un attribut booléen qui définit si la date est un lien. Par défaut, il est défini sur **`false`**.
- **`displayType`** : Définit le type d'affichage de la date, comme **`date`** (date classique) ou d'autres formats.

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

Le bloc **Date** possède plusieurs styles associés :

- **`style`** : Le style par défaut du bloc est défini par **`wp-block-post-date`**.
- **`editorStyle`** : Le style d'éditeur pour ce bloc est défini par **`wp-block-post-date-editor`**.

---

## Conclusion

Le bloc **Date** permet une personnalisation poussée de l'affichage de la date de publication, y compris la gestion des couleurs, de la typographie, et de l'espacement. Il prend en charge plusieurs options d'alignement et de format de la date pour une présentation flexible et attrayante.
