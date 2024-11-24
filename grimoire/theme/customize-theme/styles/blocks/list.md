# Réglages du bloc list dans styles

```json 
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "styles": {
        "blocks": {
            "core/list": {
                "spacing": {
                    "padding": {
                        "left": "var(--wp--preset--spacing--10)"
                    }
                }
            }
        }
    }
}
```

## Détails de la configuration

### Structure principale

#### styles :

- Permet de définir les styles globaux pour tous les blocs ou pour des blocs spécifiques.

#### blocks :

- Regroupe les styles applicables aux blocs individuels.

### Configuration spécifique : Bloc List

#### Bloc ciblé : core/list

Le bloc core/list est utilisé pour afficher des listes ordonnées ou non ordonnées (à puces). Ces listes permettent de structurer des informations de manière claire et organisée, et elles sont souvent personnalisées pour s'intégrer harmonieusement dans un thème.

### Propriété modifiée

##### Propriété spacing

###### padding :

- Définit les espacements internes d'un élément, en l'occurrence les marges intérieures de la liste par rapport à son contenu.

###### left :

- La valeur de padding-left est définie comme var(--wp--preset--spacing--10), une variable CSS prédéfinie dans WordPress.

- Cette variable correspond à un espacement standardisé, souvent utilisé pour garder une uniformité dans le design global du thème.

- Ici, elle ajuste l'espacement entre le bord gauche du conteneur de liste et le texte ou les puces à l'intérieur de la liste.

#### Effet de la propriété padding-left

- La propriété padding-left déplace le contenu de la liste (puces et texte) vers la droite, créant un espacement interne sur le côté gauche.

- Cela est utile pour améliorer la lisibilité ou aligner les listes avec d'autres contenus de la page, tout en évitant qu'elles paraissent trop proches du bord du conteneur ou des éléments adjacents.

### Exemple visuel : Résultat attendu

| **Configuration**                                    | **Résultat**                                                 |
|------------------------------------------------------|--------------------------------------------------------------|
| Sans padding-left	    	    	                   | Liste collée au bord gauche du conteneur                     | 
| Avec padding-left: `var(--wp--preset--spacing--10)`  | Liste avec un léger retrait sur la gauche                    |

### Personnalisation supplémentaire
Il est possible de personnaliser davantage les listes en ajoutant des propriétés supplémentaires pour modifier l'espacement, les marges, ou encore le style des puces.

#### Exemple avec des ajustements de padding et de marges :

```json 
{
    "styles": {
        "blocks": {
            "core/list": {
                "spacing": {
                    "padding": {
                        "left": "var(--wp--preset--spacing--20)",
                        "top": "var(--wp--preset--spacing--5)"
                    },
                    "margin": {
                        "bottom": "var(--wp--preset--spacing--10)"
                    }
                }
            }
        }
    }
}
```

#### Explications :

##### padding-left: var(--wp--preset--spacing--20)
- Augmente le retrait à gauche pour un effet visuel plus marqué.

##### padding-top: var(--wp--preset--spacing--5) 
- Ajoute un léger espacement en haut de la liste pour la séparer du contenu précédent.

###### margin-bottom: var(--wp--preset--spacing--10)
- Ajoute un espace sous la liste pour la distinguer de l'élément suivant.