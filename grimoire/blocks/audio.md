# Documentation du bloc `core/audio`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/audio`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|----------------------|------------|------------------------|-------------------------------------------------------------------------------|
| `blob`              | `string`   | -                      | Définir un fichier audio local à utiliser dans le bloc.                        |
| `src`               | `string`   | -                      | Source de l'audio (URL du fichier audio).                                      |
| `caption`           | `rich-text`| -                      | Légende associée au fichier audio.                                             |
| `id`                | `number`   | -                      | Identifiant unique de l'audio dans la médiathèque.                            |
| `autoplay`          | `boolean`  | `false`                | Si activé, l'audio commence à jouer dès le chargement de la page.             |
| `loop`              | `boolean`  | `false`                | Si activé, l'audio se répète en boucle.                                       |
| `preload`           | `string`   | `auto`                 | Définit le comportement de préchargement de l'audio (`auto`, `metadata`, `none`).|

---

## Supports (Fonctionnalités prises en charge)

### **Ancrage et alignement**
- `anchor` : Permet de définir un identifiant unique pour le bloc.
- `align` : Prend en charge les options d'alignement (`wide`, `full`, `center`, etc.).

### **Espacement**
- Supporte les propriétés d'espacement :
  - `margin` : Marges extérieures.
  - `padding` : Espacement intérieur.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client.

---

## Styles

- `editorStyle` : Définit le style dans l'éditeur (`wp-block-audio-editor`).
- `style` : Définit le style global (`wp-block-audio`).

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/audio`.* 
