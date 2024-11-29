# Ajouter des valeurs personnalisées

## Pourquoi ajouter des valeurs personnalisées ?
Il existe deux cas pour lesquels ces valeurs sur-mesure sont utiles :

1. **Pallier une limitation technique** : l’option n’est pas proposée dans l’éditeur.
2. **Éviter de proposer certaines valeurs dans l’éditeur** : par exemple, une couleur de survol d’un bouton.

Même si Gutenberg est très complet, certaines valeurs ne peuvent pas encore être définies dans le `theme.json` pour être proposées dans l’interface de l’éditeur. C’est le cas pour :

- La hauteur des lignes de texte ;
- La graisse des textes ;
- Les bordures arrondies.

### Cas d’usage des valeurs personnalisées
Dans Gutenberg, bien que l’on puisse définir n’importe quelle hauteur de ligne, graisse ou arrondi, il est parfois pertinent d’ajouter des valeurs prédéfinies dans le `theme.json` :

- **Sous forme de variables CSS** générées par WordPress.
- **Pour définir des styles par défaut** pour les blocs dans le fichier JSON.

Dans les prochains cours, nous verrons comment configurer les styles par défaut pour chaque bloc (ex. couleur, typographie, espacement), directement dans le `theme.json`, sans avoir besoin d’écrire de CSS.

---

## Exemple : couleurs non proposées dans la palette
Dans une charte graphique, des couleurs intermédiaires peuvent être utiles pour les états (par exemple, un survol de bouton). Par exemple :

- Une couleur de survol (rose légèrement plus foncé) peut être définie dans le `theme.json`, sans apparaître dans la palette visible à l’utilisateur.

---

## Déclarer des valeurs personnalisées

### Structure de déclaration
Les valeurs personnalisées sont définies dans la section `settings > custom` du `theme.json`. Vous êtes libre de nommer les propriétés, mais elles doivent respecter cette structure de base : 

- Une propriété sous forme d’objet.
- À l’intérieur, les différentes valeurs.

### Typographie
Pour ajouter des graisses et des hauteurs de ligne personnalisées :

```json
{
  "settings": {
    "custom": {
      "typography": {
        "fontWeight": {
          "light": "300",
          "regular": "400",
          "semibold": "600"
        },
        "lineHeight": {
          "tight": "1.2",
          "normal": "1.5",
          "relaxed": "1.75"
        }
      }
    }
  }
}
```

### Arrondis
Pour déclarer des valeurs d’arrondis :

```json
{
  "settings": {
    "custom": {
      "borderRadius": {
        "s": "4px",
        "m": "8px",
        "full": "50%"
      }
    }
  }
}
```

Ces valeurs peuvent être utilisées pour les groupes, boutons, ou autres éléments. Par exemple, full permet d’obtenir des cercles pour des photos carrées.

### Couleurs supplémentaires
Pour ajouter des couleurs non proposées dans la palette visible à l’utilisateur :

```json
{
  "settings": {
    "custom": {
      "colors": {
        "hoverPink": "#e63946",
        "backgroundGray": "#f1f1f1",
        "borderBlue": "#3b82f6"
      }
    }
  }
}
```

### Utiliser des valeurs personnalisées
En JSON
Les propriétés créées dans custom sont accessibles sous forme de variables CSS. Voici un exemple d’utilisation pour appliquer un arrondi par défaut aux boutons :

```json
{
  "styles": {
    "blocks": {
      "core/button": {
        "border": {
          "radius": "var(--wp--custom--border-radius--s)"
        }
      }
    }
  }
}
```

Avec ce réglage, tous les boutons auront un arrondi de 4px, que l’on peut surcharger via l’éditeur.

### En CSS
Ces valeurs sont également utilisables dans les fichiers CSS du thème. Exemple d’application d’un arrondi :

```css
.wp-block-group.rounded {
  border-radius: var(--wp--custom--border-radius--s);
}
```

### Subtilités des noms en CSS
Les noms des valeurs définis dans theme.json sont automatiquement convertis en variables CSS. Par exemple :

En JSON : `fontWeight: { "semibold": "600" }`
En CSS : `var(--wp--custom--font-weight--semibold)`
