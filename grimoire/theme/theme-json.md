# Documentation sur la gestion des dimensions des blocs dans WordPress

Lors de la création d'un site WordPress avec un thème FSE (Full Site Editing), l'une des premières étapes cruciales est de définir les dimensions des blocs, notamment les blocs de contenu et les blocs élargis. Ces paramètres sont souvent utilisés pour contrôler l'apparence de ces éléments, en particulier leur largeur dans la page.

## Configuration des dimensions dans `theme.json`

Les dimensions des blocs sont configurées dans le fichier `theme.json` au sein de la section `settings` : `{ "layout" }`. Cette configuration détermine la largeur maximale du contenu et des blocs élargis (wide). Ces paramètres s'appliquent globalement à tous les blocs conteneurs de la page.

### Exemple de configuration dans `theme.json` :

```json
{
    "settings": {
        "layout": {
            "contentSize": "1280px",
            "wideSize": "1440px"
        }
    }
}
```

contentSize : Définit la largeur maximale pour les blocs de contenu classiques. Dans cet exemple, elle est fixée à 1280px.
wideSize : Définit la largeur maximale pour les blocs élargis (wide). Dans cet exemple, elle est fixée à 1440px.

## Application des dimensions aux blocs

Ces dimensions s'appliqueront automatiquement à l'ensemble des blocs conteneurs de la page. Les blocs en mode pleine largeur ou élargie ne pourront pas avoir une taille différente de celle définie par ces paramètres dans theme.json.

### Règles CSS générées

La configuration des dimensions dans le fichier theme.json ne génère pas de règle CSS width dans la feuille de style de WordPress. Cependant, elle attribue une largeur maximale aux blocs du conteneur principal. Voici un exemple de ce que cela pourrait produire dans le CSS de votre thème

```css
.wp-container-my-block-id > * {
    max-width: 1280px;
    margin-left: auto !important;
    margin-right: auto !important;
}

.wp-container-my-block-id > .alignwide {
    max-width: 1440px;
}

.wp-container-my-block-id > .alignfull {
    max-width: none;
}
```

`.wp-container-my-block-id > * :` Cette règle applique une largeur maximale de 1280px pour tous les éléments dans le conteneur, avec une mise en page centrée grâce à margin-left et margin-right définis sur auto.
`.wp-container-my-block-id > .alignwide :` Cette règle applique une largeur maximale de 1440px pour les blocs alignés en mode large (wide).
`.wp-container-my-block-id > .alignfull :` Les blocs en mode pleine largeur (full width) n'ont pas de restriction de largeur maximale, donc la règle max-width: none est utilisée pour les étirer sur toute la largeur disponible.

### Contrôle des dimensions pour les blocs imbriqués (InnerBlocks)

Certains blocs imbriqués, comme les blocs de boucle de requête, les groupes, les contenus de publication, les bannières, les blocs de texte et média, ou encore les colonnes, utilisent ces valeurs de contentSize et wideSize définies dans theme.json. Cependant, ces blocs peuvent également être ajustés via deux champs individuels dans l'éditeur Gutenberg :

`content : ` Permet d'ajuster la largeur du bloc de type contenu.
`wide : ` Permet d'ajuster la largeur du bloc en mode large (wide).
Ces contrôles permettent de personnaliser les dimensions des blocs imbriqués tout en respectant les valeurs définies globalement dans le fichier theme.json.

## Choix des unités de réglages pour les marges et espaces

En fonction des conventions requises pour la livraison de votre thème FSE, vous pourrez proposer aux utilisateurs, tout ou partie des unités valides pour les spécifications CSS pour la définition des espacements sur le site.

Ces unités sont définies à l’aide de la propriété « units » de la même sous-section du fichier theme.json :

```json
{
    "settings" : {
        "spacing" : {
            "units" : [ "px", "rem", "em", "vw", "wh" ]
        }
    }
}
```

L’interface Gutenberg proposera alors une liste déroulante incluant l’ensemble des unités mises à disposition dans le fichier de configuration du thème.

## Gestion des marges internes et externes sur un thème Full Site Editing de WordPress

Les marges externes et internes (margin et padding) sont désactivées par défaut pour les thèmes FSE (basés sur les blocs) de WordPress. Nous aurons donc besoin d’activer leur fonctionnalité dans la section « settings » du fichier `theme.json` pour nous en servir sur le thème, et proposer à l’utilisateur WordPress des contrôles de blocs en relation.

```json
{
    "settings": {
        "useRootPaddingAwareAlignments": true,
        "spacing": {
            "margin": true,
            "padding": true
        }
    }
}

On notera néanmoins que l’activation de la propriété appearanceTools dans la même section permettra de ne pas avoir à activer cette prise en charge des marges.

```json 
{
    "settings": {
        "appearanceTools": true
    }
}
```

Cette même section « settings » va aussi nous permettre d’activer la gestion des marges pour des groupes spécifiques au sein de la sous-section blocks. Cette possibilité sera notamment intéressante sur un site WordPress n’étant pas destiné à être stylisé plus avant par l’utilisateur final :

```json
{
    "settings": {
        "blocks": {
            "core/site-title": {
                "spacing": {
                    "padding": false,
                    "margin": false
                }
            }
        }
    }
}
```