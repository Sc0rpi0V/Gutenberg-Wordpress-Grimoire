
# Utiliser `register_block_style` pour ajouter un style personnalisé sur un bloc Gutenberg FSE

## Introduction

Dans WordPress, vous pouvez personnaliser les blocs Gutenberg, y compris ceux utilisés dans le Full Site Editing (FSE), en utilisant la fonction `register_block_style`. Cette fonction permet d'ajouter des styles personnalisés à des blocs spécifiques, de manière à ce qu'ils soient visibles dans l'éditeur Gutenberg.

### Qu'est-ce que `register_block_style` ?

`register_block_style` permet d'ajouter un ou plusieurs styles supplémentaires à un bloc de contenu. Cela peut inclure des variations de style que vous souhaitez appliquer à un bloc dans l'éditeur. Ces styles seront ensuite disponibles dans le panneau des options du bloc (dans le backoffice de l'éditeur Gutenberg).

### Syntaxe

Voici la syntaxe de base pour utiliser `register_block_style` :

```php
register_block_style(
    'nom_du_bloc', // Le nom du bloc à modifier (ex : 'core/quote')
    array(
        'name'         => 'nom_du_style',      // Le nom du style
        'label'        => 'Label du style',     // Le label affiché dans l'éditeur
        'is_default'   => true|false,           // Définir si c'est le style par défaut
        'inline_style' => 'CSS pour le style',  // Le style CSS à appliquer
    )
);
```

### Exemple d'application

```php
register_block_style(
    'core/quote',
    array(
        'name'         => 'blue-quote',  // Nom du style
        'label'        => __( 'Blue Quote', 'textdomain' ),  // Label à afficher
        'is_default'   => true,  // Définir comme style par défaut
        'inline_style' => '.wp-block-quote.is-style-blue-quote { color: blue; font-style: italic; border-left: 4px solid blue; padding-left: 10px; font-size: 1.2em; }',  // Le style CSS
    )
);
```

### Explication détaillé du code

`core/quote` : Le premier paramètre est le nom du bloc auquel vous ajoutez le style. Ici, core/quote correspond au bloc de citation par défaut de WordPress.
`name` => 'blue-quote' : Le nom du style. Ce nom doit être unique et identifier ce style particulier.
`label` => __( 'Blue Quote', 'textdomain' ) : Le label est ce qui sera affiché dans l'interface de l'éditeur pour que l'utilisateur puisse sélectionner ce style. Vous devez également utiliser la fonction __() pour permettre la traduction du texte si nécessaire.
`is_default` => true : Cette option permet de définir si ce style est le style par défaut pour ce bloc. Si vous définissez true, ce style sera appliqué par défaut lorsqu'un utilisateur insère une citation.
`inline_style` => '...' : Cette option permet de spécifier le CSS qui sera appliqué au bloc. Ici, nous avons ajouté un style qui :
Change la couleur du texte en bleu.
Applique une bordure gauche bleue de 4 pixels.
Met le texte en italique.
Ajoute un peu de padding à gauche pour espacer le texte de la bordure. Augmente la taille de la police.

### Exemple de CSS plus détaillé

```php
register_block_style(
    'core/quote',
    array(
        'name'         => 'fancy-quote',  // Nom du style
        'label'        => __( 'Fancy Quote', 'textdomain' ),  // Label du style
        'is_default'   => false,  // Pas le style par défaut
        'inline_style' => '
            .wp-block-quote.is-style-fancy-quote {
                color: #333;
                background-color: #f0f0f0;
                border-left: 6px solid #ff6347;
                padding: 20px;
                font-size: 1.25em;
                font-style: italic;
                position: relative;
                transition: all 0.3s ease;
            }
            .wp-block-quote.is-style-fancy-quote:hover {
                background-color: #ff6347;
                color: white;
                transform: scale(1.05);
            }
            .wp-block-quote.is-style-fancy-quote::before {
                content: "“";
                font-size: 3em;
                color: #ff6347;
                position: absolute;
                left: 10px;
                top: 50%;
                transform: translateY(-50%);
            }
        ',
    )
);
```

### Explications des ajouts 

background-color: #f0f0f0; : Un fond gris clair.
border-left: 6px solid #ff6347; : Une bordure gauche plus épaisse avec une couleur tomate.
transition: all 0.3s ease; : Une transition fluide lorsque le style change, par exemple au survol.
transform: scale(1.05); : L'effet d'agrandissement au survol.
Pseudo-élément ::before : Ajout d’un guillemet stylisé avant le texte de la citation.
Conclusion

L'utilisation de register_block_style dans Gutenberg permet de personnaliser l'apparence de vos blocs en backoffice. L'exemple détaillé ici montre comment ajouter un style spécifique à un bloc core/quote, y compris la définition de styles CSS dans inline_style pour personnaliser l'apparence.