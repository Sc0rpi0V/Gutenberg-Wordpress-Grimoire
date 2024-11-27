# Documentation du bloc `core/block`

Ce document détaille les attributs et les fonctionnalités du bloc **`core/block`** dans WordPress Gutenberg.

---

## Attributs principaux

| **Attribut**        | **Type**   | **Valeur par défaut** | **Description**                                                               |
|----------------------|------------|------------------------|-------------------------------------------------------------------------------|
| `ref`               | `number`   | -                      | Référence à un autre bloc (identifiant du bloc référencé).                   |
| `content`           | `object`   | `{}`                   | Contenu à insérer dans le bloc sous forme d'objet.                            |

---

## Contexte utilisé

- `pattern/overrides` : Contenu du modèle (fournit le contexte pour personnaliser le bloc).

---

## Supports (Fonctionnalités prises en charge)

### **Personnalisation du bloc**
- `customClassName` : Le bloc ne supporte pas l'ajout de classes CSS personnalisées.
- `html` : Le bloc ne permet pas l'édition HTML.
- `inserter` : Le bloc ne prend pas en charge l'insertion via l'inserteur.

### **Renommage et interactivité**
- `renaming` : Le bloc ne permet pas le renommage.
- `clientNavigation` : Capture les événements de navigation au sein du client.

---

*Cette documentation est basée sur les informations disponibles dans le fichier `block.json` du bloc `core/block`.* 
