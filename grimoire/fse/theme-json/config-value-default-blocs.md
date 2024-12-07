# Configurer les valeurs par défaut des blocs et des primitives

## Configurations via le fichier theme.json

Jusqu’à maintenant, on a passé du temps dans la section `settings` du `theme.json`. Cette section nous a permis de configurer les fonctionnalités de l’éditeur, ainsi que les valeurs d’espacement, couleurs, ombres…

Maintenant, c’est dans la section `styles` que nous allons nous attarder. Dans cette section, nous allons pouvoir indiquer le style par défaut de chaque bloc, mais aussi les styles globaux comme la couleur des textes, du fond, l’espacement par défaut entre les blocs, les polices du site…

Les réglages que l’on va faire ici sont l’équivalent de ceux que l’on ferait dans **Apparence > Éditeur > Styles**.

### Couleurs et blocs

Dans **Couleurs > Éléments**, on peut définir les couleurs globales des éléments comme le texte, l’arrière-plan, les liens, les titres, les boutons :

Dans **Blocs**, on peut définir des styles particuliers très précis pour chaque bloc de l’éditeur.

### Structure de la section styles

Dans la documentation, WordPress nous indique qu’il y a 3 niveaux de styles globaux :

1. **Les styles à la racine du site** ;
2. **Les éléments primitifs** ;
3. **Les blocs**.

En clair, on va aller des réglages les plus généraux au niveau du site, à ceux les plus précis au niveau des blocs.

---

## Les Styles racines

Cette partie configure les styles à la racine du site, soit les éléments les plus généralistes possibles :

- **Couleurs** : les couleurs des textes et du fond du site ;
- **Espacements** : l’espacement par défaut entre tous les blocs et les marges ;
- **Typographie** : la police et la taille des textes.

Lorsqu’on descend dans les niveaux, on pourra être plus précis et appliquer des styles différents par élément.

### Exemple de section styles

#### Couleurs

Dans la sous-section `color`, on peut définir :

- La couleur des textes (tous les textes) ;
- La couleur du fond du site.

#### Espacements

L’espacement est crucial pour définir :

1. **Propriété `blockGap`** :  
   Définit l’espacement entre les blocs. Ce sera la valeur par défaut, mais elle pourra être personnalisée pour chaque bloc.

2. **Marges latérales** :  
   Une marge interne est essentielle pour éviter que le contenu ne soit collé aux bords de l’écran, surtout sur mobile.

#### Typographie

La sous-section `typography` permet de définir :

- La police par défaut du site ;
- La taille de texte ;
- La graisse et la hauteur de ligne.

---

## Les éléments primitifs

Les éléments primitifs sont des éléments généraux comme :

- Les textes,
- Les titres,
- Les légendes,
- Les boutons,
- Les liens…

Ces éléments sont présents dans plusieurs blocs, par exemple :

- Les boutons dans des blocs comme recherche ou fichier PDF ;
- Les légendes sous les images, galeries ou tableaux.

### Section `elements`

Dans le fichier `theme.json`, vous pouvez configurer bien plus que la couleur, comme par exemple :

#### Boutons

Propriétés configurables pour les boutons :

- **Border** : style, largeur et rayon de bordure ;
- **Color** : couleur du texte et du fond ;
- **Spacing** : marges internes ;
- **Typography** : taille, graisse et police du texte ;
- **Shadow** : ombre éventuelle ;
- **Pseudo-classes** : `:hover`, `:active`, `:visited`, `:focus`.

#### Titres

Propriétés configurables pour les titres (`heading`, `h1`, `h2`…).

Exemple :

- Tous les titres utilisent la police secondaire avec une graisse normale ;
- Les titres H1 et H2 ont une graisse semibold ;
- Le titre H1 a une taille XXL, et le H2 une taille XL.

#### Liens et légendes

De la même manière, vous pouvez configurer :

- Les liens ;
- Les légendes (images, galeries, tableaux…).

---

## Ajout CSS sur-mesure

Pour ajouter une propriété CSS non prise en charge par le `theme.json`, utilisez la propriété `css`.  
Exemple : Ajouter une transition CSS sur les boutons.

---

## Les blocs

Le troisième niveau de personnalisation concerne les **blocs spécifiques**. Ici, vous pouvez surcharger les styles définis au niveau des racines ou des éléments primitifs.

### Exemple

#### Images

Appliquer un arrondi et une ombre à toutes les images :

```json
"core/image": {
    "styles": {
        "borderRadius": "8px",
        "boxShadow": "0px 4px 10px rgba(0,0,0,0.1)"
    }
}
```

#### Groupes

Supprimer les marges entre des sections dans un bloc groupe :

```json
"core/group": {
    "styles": {
        "spacing": {
            "margin": {
                "top": "0px"
            }
        }
    }
}
```

---

## Hooker le theme.json en PHP

### Hook `wp_theme_json_data_theme`

Ce hook permet de surcharger dynamiquement un réglage de votre `theme.json`. Exemple :

```php
add_filter('wp_theme_json_data_theme', function($theme_json) {
    // Modifier les couleurs
    $theme_json['settings']['color']['palette'] = [
        [
            'name' => 'Primary',
            'slug' => 'primary',
            'color' => '#3498db',
        ],
        [
            'name' => 'Secondary',
            'slug' => 'secondary',
            'color' => '#2ecc71',
        ]
    ];

    // Modifier les titres H1
    $theme_json['styles']['elements']['h1']['typography']['fontSize'] = '3rem';

    return $theme_json;
});
```

### Autres hooks disponibles

1. **wp_theme_json_data_default** : Réglages par défaut de WordPress.
2. **wp_theme_json_data_blocks** : Réglages des blocs.
3. **wp_theme_json_data_theme** : Réglages du thème.
4. **wp_theme_json_data_user** : Réglages faits par l’utilisateur via l’éditeur.

**Astuce** : Pour une priorité maximale, branchez-vous sur `wp_theme_json_data_user`.
