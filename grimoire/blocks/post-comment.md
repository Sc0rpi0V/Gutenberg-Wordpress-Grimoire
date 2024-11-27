# Documentation du bloc `core/post-comment`

Ce document détaille les attributs et fonctionnalités du bloc **`core/post-comment`**, qui est **déprécié**.

---

## Description

Le bloc **Comment** est utilisé pour afficher les commentaires d'une publication. **Ce bloc est obsolète** et il est recommandé d'utiliser le bloc **Comments** à la place.

---

## Attributs principaux

| **Attribut** | **Type** | **Description**                            |
|--------------|----------|--------------------------------------------|
| `commentId`  | `number` | Identifiant unique d’un commentaire.       |

---

## Contexte fourni

Le bloc transmet le contexte suivant aux blocs enfants :
- **`commentId`** : L’identifiant du commentaire actuel.

---

## Blocs autorisés

Le bloc `core/post-comment` peut inclure les blocs suivants :
- **`core/avatar`** : Affichage de l’avatar de l’auteur du commentaire.
- **`core/comment-author-name`** : Nom de l’auteur du commentaire.
- **`core/comment-content`** : Contenu du commentaire.
- **`core/comment-date`** : Date du commentaire.
- **`core/comment-edit-link`** : Lien pour modifier le commentaire (si applicable).
- **`core/comment-reply-link`** : Lien pour répondre au commentaire.

---

## Fonctionnalités prises en charge (Supports)

### **HTML**
- Le bloc ne permet pas de modifier directement le code HTML (`html: false`).

### **Inserteur**
- Ce bloc n’apparaît pas dans l’inserteur de blocs (`inserter: false`).

### **Interactivité**
- Prend en charge la navigation côté client pour les interactions (`clientNavigation: true`).

---

## Statut de dépréciation

Le bloc est marqué comme **déprécié**. Il n’est plus activement maintenu et pourrait être supprimé dans de futures versions de WordPress. Il est fortement recommandé d'utiliser le bloc **Comments** à la place pour une meilleure compatibilité et des fonctionnalités améliorées.

---

*Cette documentation est basée sur les informations contenues dans le fichier `block.json` du bloc `core/post-comment`.*
