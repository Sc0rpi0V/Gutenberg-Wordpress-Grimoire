# Documentation du bloc `core/calendar`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/calendar`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**  | **Type**  | **Valeur par défaut** | **Description**                                      |
|---------------|-----------|-----------------------|------------------------------------------------------|
| `month`       | `integer` | N/A                   | Le mois à afficher dans le calendrier.               |
| `year`        | `integer` | N/A                   | L'année à afficher dans le calendrier.              |

---

## Supports (Fonctionnalités prises en charge)

### **Alignement**
- `align` : Prend en charge les options d'alignement (`wide`, `full`, `center`, etc.).

### **Couleurs**
- `color` : 
  - **link** : Permet de personnaliser la couleur des liens.
  - **__experimentalSkipSerialization** : Liste les propriétés dont la sérialisation est ignorée, ici pour `text` et `background`.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `background` et `text`.
  - **__experimentalSelector** : Sélecteur CSS pour cibler certains éléments comme `table` et `th` pour les styles de couleur.

### **Typographie**
- `typography` :
  - **fontSize** : Permet de modifier la taille de la police.
  - **lineHeight** : Permet de modifier la hauteur de ligne.
  - Propriétés expérimentales :
    - `__experimentalFontFamily` : Permet de définir la famille de police.
    - `__experimentalFontWeight` : Permet de définir le poids de la police.
    - `__experimentalFontStyle` : Permet de définir le style de la police (ex : italique).
    - `__experimentalTextTransform` : Permet de modifier la transformation du texte (majuscule, minuscule, etc.).
    - `__experimentalLetterSpacing` : Permet de définir l'espacement entre les lettres.
  - **__experimentalDefaultControls** : Active les contrôles par défaut pour `fontSize`.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client, ce qui permet une navigation dynamique dans le calendrier.

---

## Styles

- **`style`** : Définit le style pour ce bloc dans l'éditeur, ici spécifié par la classe CSS `wp-block-calendar`.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/calendar`.* 
