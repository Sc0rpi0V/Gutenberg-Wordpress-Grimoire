# Documentation du bloc `core/buttons`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/buttons`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**           | **Type**     | **Valeur par défaut** | **Description**                                                                 |
|------------------------|--------------|------------------------|---------------------------------------------------------------------------------|
| `allowedBlocks`        | `array`      | `core/button`          | Définit les blocs autorisés à être inclus dans le bloc `core/buttons`.          |

---

## Supports (Fonctionnalités prises en charge)

### **Ancrage**
- `anchor` : Permet de définir un identifiant unique pour le bloc.

### **Alignement**
- `align` : Permet l'alignement `wide` et `full` du bloc.

### **Couleurs et Styles**
- Supporte les couleurs :
  - `background` : Couleur de fond.
  - `gradients` : Gradient de fond.
  
- Propriétés expérimentales :
  - `border` : Propriétés de bordure (`color`, `radius`, `style`, `width`).

### **Espacement**
- `spacing` : Définit les marges et le remplissage (horizontal, vertical, et top/bottom).
  - `blockGap` : Espace entre les blocs.
  
### **Typographie**
- Supporte les propriétés typographiques suivantes :
  - `fontSize` : Taille de police.
  - `lineHeight` : Hauteur de ligne.
  - Propriétés expérimentales :
    - `fontFamily`
    - `fontWeight`
    - `fontStyle`
    - `textTransform`
    - `textDecoration`
    - `letterSpacing`

### **Dispositif de mise en page**
- `layout` :
  - `default` : Utilisation du type `flex` pour l'agencement.
  - `allowSwitching` : Désactivé pour interdire le changement de mise en page.
  - `allowInheriting` : Désactivé pour interdire l'héritage de la mise en page.

### **Interactivité**
- `clientNavigation` : Capture les événements de navigation au sein du client.

---

## Styles

- **Styles disponibles** :
  - `editorStyle` : Définit le style dans l'éditeur (`wp-block-buttons-editor`).
  - `style` : Définit le style global pour le bloc `buttons` (`wp-block-buttons`).

---

## Conclusion

Ce bloc permet de créer un groupe de boutons dans une mise en page flexible, avec un contrôle précis de l'alignement, des couleurs, de la typographie et des espacements.

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/buttons`.*
