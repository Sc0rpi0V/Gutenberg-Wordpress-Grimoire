# Documentation du bloc `core/post-author-biography`

Ce document détaille les attributs et fonctionnalités du bloc **`core/post-author-biography`** dans WordPress Gutenberg.

---

## Description

Le bloc **Author Biography** affiche la biographie de l’auteur du contenu. Il est utilisé pour donner un aperçu de l’identité de l’auteur, accompagné éventuellement de détails sur son profil.

---

## Attributs principaux

| **Attribut** | **Type** | **Valeur par défaut** | **Description**                                                 |
|--------------|----------|-----------------------|-----------------------------------------------------------------|
| `textAlign`  | `string` |                       | Alignement du texte : peut être `left`, `center`, ou `right`.   |

---

## Contexte utilisé

Le bloc exploite les contextes suivants :
- **`postType`** : Le type de publication auquel appartient le contenu.
- **`postId`** : L’identifiant de la publication en cours.

---

## Exemple

- **Largeur suggérée pour la vue d’aperçu** : `350px`.

---

## Fonctionnalités prises en charge (Supports)

### **Espacement**
- Gestion des marges (`margin`) et des paddings (`padding`).

### **Couleurs**
- Prend en charge les dégradés (`gradients`) et la personnalisation des liens.
- **Contrôles activés par défaut** pour :
  - La couleur d’arrière-plan.
  - La couleur du texte.

### **Typographie**
Le bloc propose des options complètes pour la personnalisation typographique :
- `fontSize` : Taille de la police.
- `lineHeight` : Hauteur de ligne.
- `__experimentalFontFamily` : Famille de police personnalisée.
- `__experimentalFontWeight` : Épaisseur de la police.
- `__experimentalFontStyle` : Style de la police (italique, normal, etc.).
- `__experimentalTextTransform` : Transformation du texte (majuscule, minuscule, capitalisé).
- `__experimentalTextDecoration` : Décoration du texte (souligné, barré, etc.).
- `__experimentalLetterSpacing` : Espacement entre les lettres.
- **Contrôle activé par défaut** pour la taille de la police.

### **Interactivité**
- `clientNavigation` : Permet la navigation côté client si le contenu contient des liens.

### **Bordures**
Les bordures sont entièrement personnalisables :
- `radius` : Rayon des coins.
- `color` : Couleur de la bordure.
- `width` : Largeur de la bordure.
- `style` : Style de la bordure (`solid`, `dotted`, `dashed`, etc.).
- **Contrôles activés par défaut** pour toutes ces options.

---

## Styles

- **`style`** : `wp-block-post-author-biography` : Applique des styles front-end spécifiques au bloc.

---

*Cette documentation est basée sur les informations contenues dans le fichier `block.json` du bloc `core/post-author-biography`.*
