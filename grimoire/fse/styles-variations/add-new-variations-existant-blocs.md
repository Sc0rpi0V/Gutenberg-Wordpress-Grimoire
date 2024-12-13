# Ajouter de nouvelles variations de styles aux blocs existants

Les variations de styles de blocs dans WordPress permettent de personnaliser l’apparence d’un bloc facilement. Ces variations permettent à l’utilisateur de choisir directement depuis Gutenberg la variation à appliquer en un clic.

---

## Objectifs et exemples

Les variations de styles de blocs sont utiles pour :  
- Personnaliser les listes à puces en check-lists.  
- Proposer des séparations originales sur les groupes de section.  
- Transformer un paragraphe en texte d’introduction.  
- Donner des bords arrondis aux images.  

---

## Déclarer des variations en JSON

Pour créer des variations de styles pour les blocs :  
1. Créez un dossier `/styles` dans votre thème.  
2. Ajoutez des fichiers JSON pour chaque variation.

### Exemple : Boutons alternatifs

Créez le fichier `/styles/button/alt.json` avec le contenu suivant :

```json
{
  "title": "Bouton alternatif",
  "slug": "alt",
  "blockTypes": ["core/button"],
  "styles": {
    "color": {
      "background": "#ffcc00",
      "text": "#000000"
    },
    "border": {
      "width": "2px",
      "color": "#000000"
    }
  }
}
```

---

### Surcharger les styles des enfants

Une variation peut également influencer les styles des blocs enfants.

#### Exemple 1 : Groupe sombre et texte clair

Fichier `/styles/group/primary.json` :

```json
{
  "title": "Groupe sombre",
  "slug": "primary",
  "blockTypes": ["core/group"],
  "styles": {
    "color": {
      "background": "#333333",
      "text": "#ffffff"
    },
    "elements": {
      "heading": {
        "color": "#00ff00"
      }
    }
  }
}
```

#### Exemple 2 : Images arrondies dans les galeries

Fichier `/styles/gallery/rounded.json` :

```json
{
  "title": "Galerie arrondie",
  "slug": "rounded",
  "blockTypes": ["core/gallery"],
  "styles": {
    "elements": {
      "image": {
        "borderRadius": "15px"
      }
    }
  }
}
```

---

## Déclarer des variations en PHP et CSS

L’approche JSON est privilégiée depuis WordPress 6.6, mais l’approche PHP reste valide.

### Exemple avec `register_block_style()`

Ajoutez au fichier `functions.php` :

```php
function register_custom_block_styles() {
    register_block_style(
        'core/button',
        [
            'name'  => 'alt',
            'label' => 'Bouton alternatif',
        ]
    );
}
add_action('init', 'register_custom_block_styles');
```

### Ajouter un fichier CSS associé

Créez `/assets/css/button.css` :

```css
.wp-block-button.is-style-alt {
    background-color: #ffcc00;
    color: #000000;
    border: 2px solid #000000;
}
```

Enregistrez ce style dans `functions.php` :

```php
function enqueue_custom_block_styles() {
    wp_enqueue_block_style(
        'core/button',
        [
            'handle' => 'custom-button-styles',
            'src'    => get_template_directory_uri() . '/assets/css/button.css',
        ]
    );
}
add_action('init', 'enqueue_custom_block_styles');
```

---

## Déclarer des styles directement dans PHP

Pour éviter des fichiers CSS multiples, déclarez les styles dans PHP :

```php
register_block_style(
    'core/button',
    [
        'name'       => 'alt',
        'label'      => 'Bouton alternatif',
        'style_data' => '.wp-block-button.is-style-alt { background-color: #ffcc00; color: #000000; border: 2px solid #000000; }'
    ]
);
```

---

## Déclarer plusieurs variations

Vous pouvez déclarer plusieurs variations comme suit :

```php
function register_multiple_block_styles() {
    $variations = [
        [
            'block' => 'core/button',
            'name'  => 'alt',
            'label' => 'Bouton alternatif'
        ],
        [
            'block' => 'core/group',
            'name'  => 'primary',
            'label' => 'Groupe sombre'
        ]
    ];

    foreach ($variations as $variation) {
        register_block_style(
            $variation['block'],
            [
                'name'  => $variation['name'],
                'label' => $variation['label'],
            ]
        );
    }
}
add_action('init', 'register_multiple_block_styles');
```
