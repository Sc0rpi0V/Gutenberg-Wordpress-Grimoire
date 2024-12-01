
# Utiliser valeurs globales en CSS et en JSON

## Les variables CSS

### Introduction
On a vu que WordPress génère automatiquement des variables CSS à partir des valeurs que l’on a définies dans le `theme.json`.

Les variables ont été une grosse révolution dans le langage CSS il y a quelques années. C’est l’arrivée du nouvel éditeur Gutenberg qui a permis de les adopter au sein de WordPress. Les variables sont compatibles avec tous les navigateurs et font partie de la **Web Platform Baseline**. Une technologie dans la « Baseline » indique qu’elle est largement adoptée par tous les navigateurs.

### Exemple en CSS
Si vous ne les avez jamais utilisées, voici un petit résumé en pur CSS. Vous déclarez d’abord une variable dans le sélecteur `:root` de votre feuille de style :

```css
:root {
  --main-color: #3498db;
}
```

Une fois déclarées à la racine, vous pouvez les utiliser partout dans vos feuilles de styles CSS :

```css
h1 {
  color: var(--main-color);
}
```

Vous pourrez même changer la valeur d’une variable de manière contextuelle, par exemple à l’intérieur d’une media query :

```css
@media (max-width: 768px) {
  :root {
    --main-color: #2ecc71;
  }
}
```

### Avantages des variables CSS
- Déclarez une valeur une seule fois, elle est appliquée dynamiquement partout.
- Modifiez-la selon le contexte (ex. media query).
- Disponibles globalement dans la page, réutilisables dans d’autres fichiers.
- Compatibles avec tous les navigateurs modernes.

Ainsi, vous n’avez plus besoin de préprocesseurs comme Sass.

---

## Les variables CSS selon WordPress

### Observation des variables générées
Depuis le front-end, ouvrez l’inspecteur du navigateur dans l’onglet **Elements > Styles**. Sélectionnez la balise `<html>` : vous verrez le sélecteur `:root` avec toutes les variables à l’intérieur.

Ces valeurs sont générées automatiquement lorsque WordPress interprète votre fichier `theme.json`. Les noms sont un peu longs, mais voici pourquoi.

---

## Le nommage des variables CSS dans WordPress

### Structure des noms
Les noms de variables CSS dans WordPress sont divisés en **quatre parties** :

1. **Le préfixe**
   - Toutes les variables générées par WordPress commencent par `--wp`.
   - Cela permet de les distinguer des autres variables (ex. créées par des plugins).

2. **Le type**
   - Deux types existent : `--preset` ou `--custom`.
   - Si la variable est déclarée dans `settings > custom` dans le `theme.json`, elle sera `--custom`.
   - Sinon, c’est un preset WordPress, donc `--preset`.

3. **La propriété**
   - Exemple de propriétés : `--color`, `--spacing`, `--font-size`, etc.
   - Exemple dans le `theme.json` :
     ```json
     "settings": {
       "color": {
         "palette": [
           { "slug": "primary", "color": "#2f1847" }
         ]
       }
     }
     ```
   - En CSS :
     ```css
     --wp--preset--color--primary: #2f1847;
     ```

4. **La valeur**
   - La dernière partie représente la valeur appliquée.
   - Exemple avec des espacements déclarés dans le JSON :
     ```json
     "settings": {
       "spacing": {
         "sizes": [
           { "slug": "s", "size": "1.6rem" }
         ]
       }
     }
     ```
   - Côté CSS :
     ```css
     --wp--preset--spacing--s: 1.6rem;
     ```

---

## Tableau des types de variables

| Type de style   | Variables générées                       |
|------------------|------------------------------------------|
| Couleurs        | `--wp--preset--color--<valeur>`          |
| Dégradés        | `--wp--preset--gradient--<valeur>`       |
| Espacements     | `--wp--preset--spacing--<valeur>`        |
| Police          | `--wp--preset--font-family--<valeur>`    |
| Taille de police| `--wp--preset--font-size--<valeur>`      |
| Ombres          | `--wp--preset--shadow--<valeur>`         |
| Personnalisée   | `--wp--custom--<propriété>--<valeur>`    |

---

## Les variables CSS disponibles
Exemple de palette de couleurs dans le `theme.json` :

```json
"settings": {
  "color": {
    "palette": [
      { "slug": "primary", "color": "#2f1847" },
      { "slug": "secondary", "color": "#fe2c70" }
    ]
  }
}
```

Variables CSS générées :
| Variable                        | Valeur appliquée |
|---------------------------------|------------------|
| `--wp--preset--color--primary`  | `#2f1847`        |
| `--wp--preset--color--secondary`| `#fe2c70`        |

---

## Utilisation des variables en CSS
Les variables sont accessibles partout dans vos feuilles de styles grâce à leur déclaration dans le sélecteur `:root`.

Exemple :
```css
.button {
  background-color: var(--wp--preset--color--primary);
}
```

---

## Les variables dans le `theme.json`

### Syntaxe
Dans le `theme.json`, il y a une section dédiée aux valeurs globales. Exemple :
```json
"settings": {
  "color": {
    "text": "var(--wp--preset--color--primary)",
    "background": "var(--wp--preset--color--secondary)"
  }
}
```

### Syntaxe simplifiée avec des pipes
WordPress propose une syntaxe simplifiée avec des **pipes** (`|`) :
```json
"settings": {
  "color": {
    "text": "var|preset|color|primary",
    "background": "var|preset|color|secondary"
  }
}
```

### Structure des pipes
1. **`var`** : indique l’utilisation d’une variable CSS.
2. **`type`** : `preset` ou `custom`.
3. **`key`** : propriété (ex. `color`, `spacing`).
4. **`value`** : valeur définie (ex. `primary`, `small`).

---

## Besoins spécifiques
Si vous avez un besoin CSS particulier (ex. un calcul), vous devrez utiliser la syntaxe classique en pur CSS.

Exemple :
```css
font-size: calc(var(--wp--preset--font-size--small) * 1.2);
```
