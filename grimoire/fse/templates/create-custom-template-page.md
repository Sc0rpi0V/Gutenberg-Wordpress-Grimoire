# Créer des modèles de pages personnalisées dans WordPress (FSE)

## Introduction
Lors de la création d'un thème WordPress utilisant le Full Site Editing (FSE) et Gutenberg, on utilise souvent un fichier `page.html` comme modèle de page par défaut. Mais si vous souhaitez créer d'autres modèles de pages personnalisés, voici la marche à suivre. Contrairement aux thèmes classiques, la déclaration des modèles est maintenant réalisée via le fichier `theme.json`. Voici comment procéder.

## Propriétés des modèles personnalisés
Un modèle de page personnalisé doit :

- **Ne pas afficher le titre principal de la page par défaut.**
- **Permettre des sections pleine largeur** pour les contenus dynamiques.

Pour les landing pages, vous pourrez insérer un titre de niveau 1 dans la première section manuellement.

---

## Étapes pour déclarer un modèle de page personnalisé

### 1. Créer le fichier du modèle de page
Dans le dossier `templates` de votre thème, créez un fichier HTML pour le nouveau modèle. Par exemple, créez `page-full-width.html`.

### 2. Ajouter le modèle dans `theme.json`

Dans le fichier `theme.json` de votre thème, ajoutez les informations relatives au nouveau modèle à la fin du fichier. Voici les propriétés à définir :

- **Slug** : Nom du fichier sans l'extension `.html` (par exemple, `page-full-width`).
- **Titre** : Nom du modèle qui apparaîtra dans l'interface d'administration.
- **Types de publication** : Les types de contenus où ce modèle sera applicable (par exemple, `page`, `post`, ou des Custom Post Types).

Cela permet de spécifier des modèles utilisables uniquement pour certains types de contenu personnalisés.

---

## Conception du modèle de page

### 1. Accéder à l'éditeur de blocs

Après avoir déclaré le modèle :

1. Allez dans **Apparence > Éditeur > Modèles**.
2. Votre nouveau modèle devrait apparaître dans la liste avec le titre défini.
3. Cliquez sur le modèle pour ouvrir l'éditeur de blocs.
4. Passez l'étape où l'on vous propose de vous baser sur le modèle standard.

### 2. Ajouter des blocs au modèle

1. **Insérez l'en-tête et le pied de page.**
2. Entre les deux, insérez un bloc **Groupe**.
3. Dans ce groupe, ajoutez un bloc **Contenu**.

#### Configurations des blocs :
- Pour le **Groupe**, dans les options avancées, sélectionnez la balise `<main>`.
- Pour le bloc **Contenu**, activez l'option « Les blocs intérieurs utilisent la largeur du contenu ». Cela permet de centrer les contenus par défaut et d'éviter les marges inutiles.

Votre modèle est maintenant configuré pour offrir une zone pleine largeur pour les contenus, entre l'en-tête et le pied de page.

---

## Appliquer le modèle de page

Pour utiliser ce modèle :

1. Allez dans le menu **Pages** de WordPress.
2. Modifiez une page existante (par exemple, votre page d'accueil).
3. Dans l'inspecteur, cliquez sur « Modèle », puis « Changer de modèle ».
4. Sélectionnez « Page pleine largeur sans titre ».

---

## Gestion des titres des pages

### 1. Titre principal
Insérez manuellement un titre de niveau 1 dans votre page en utilisant :
- Le bloc **Titre de publication**. Par défaut, ce bloc utilise un titre de niveau 2, que vous devrez ajuster en niveau 1.
- Ou le bloc **Titre**, que vous devrez aussi configurer en niveau 1.

### 2. Modifier le titre « officiel »
Pour changer le titre affiché dans l'administration :
1. Cliquez sur les trois points à droite du titre dans l'inspecteur.
2. Sélectionnez « Renommer ».

---

## Problèmes de marges et solutions

### Problème : Espacement entre blocs (gap)

Un **gap par défaut** est souvent défini dans le fichier `theme.json`. Cela provoque un espacement non souhaité entre l'en-tête, le contenu et le pied de page. Voici trois solutions pour y remédier :

### Solution 1 : Remettre le gap à 0
Dans `theme.json`, supprimez l'espacement par défaut entre les blocs. Ensuite, configurez manuellement l'espacement pour chaque groupe ou bloc via l'éditeur.

### Solution 2 : Ajouter un correctif CSS
Ajoutez ce code CSS dans votre fichier `style.css` :

```css
.main-template-part:first-child {
    margin-top: 0;
}
.main-template-part:last-child {
    margin-bottom: 0;
}
```

Vérifiez que le fichier CSS est bien chargé via votre `functions.php`.

### Solution 3 : Modifier `theme.json` (Recommandée)
Ajoutez cette configuration dans `theme.json` :

```json
"styles": {
  "blocks": {
    "core/template-part": {
      "spacing": {
        "margin": "0px"
      }
    }
  }
}
```

Cette solution évite de charger un fichier CSS supplémentaire et applique directement les ajustements via `theme.json`.
