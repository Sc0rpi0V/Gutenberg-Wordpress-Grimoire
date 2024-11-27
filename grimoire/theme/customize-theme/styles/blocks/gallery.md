# Réglages du bloc gallery dans styles

```json 
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "styles": {
        "blocks": {
            "core/gallery": {
                "spacing": {
                    "margin": {
                        "bottom": "var(--wp--preset--spacing--50)"
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

### Configuration spécifique : Bloc Gallery

#### Bloc ciblé : core/gallery

Le bloc core/gallery est utilisé pour afficher des galeries d'images, souvent sous forme de grille. Ce bloc permet aux utilisateurs de disposer plusieurs images dans un format organisé, avec la possibilité de définir des espacements, des marges et des alignements.

### Propriété modifiée

##### Propriété spacing

###### margin :

- Définit les marges extérieures du bloc, c’est-à-dire l'espace autour de l'ensemble de la galerie.

- La propriété bottom permet de contrôler l'espacement sous le bloc de la galerie.

###### bottom : 

- La valeur de bottom est définie comme var(--wp--preset--spacing--50), une variable CSS prédéfinie dans WordPress qui correspond à un certain espacement, généralement défini dans les réglages de thème ou les styles par défaut.

- Cette variable fait référence à une valeur de marge, spécifiquement la valeur définie sous spacing--50, qui est une unité de mesure disponible dans les réglages de thème pour offrir des espacements cohérents avec les autres éléments de la page.

#### Effet de la propriété margin-bottom

- La propriété margin-bottom définit l'espacement entre la galerie et l'élément suivant sur la page. Cela permet de créer une séparation claire entre la galerie et les autres blocs ou éléments situés en dessous.

- L'utilisation de la variable CSS --wp--preset--spacing--50 permet de garder la cohérence avec les autres marges définies dans le thème, garantissant ainsi que l'espacement reste harmonieux avec l'ensemble du design du site.

### Exemple visuel : Résultat attendu

| **Configuration**                                    | **Résultat**                                                 |
|------------------------------------------------------|--------------------------------------------------------------|
| Sans marge bottom ou marge par défaut	               | La galerie se retrouve directement contre l'élément suivant  | 
| Avec margin-bottom: `var(--wp--preset--spacing--50)` | Un espacement de taille prédéfinie sous la galerie           |

### Personnalisation supplémentaire

Il est possible de personnaliser davantage l'espacement de la galerie en ajustant les valeurs de marge et en modifiant d'autres propriétés, telles que la marge en haut, à gauche ou à droite, ou encore en ajoutant des bordures et des espacements internes dans la galerie elle-même.

#### Exemple avec une marge supplémentaire et un ajustement des autres côtés :

```json 
{
    "styles": {
        "blocks": {
            "core/gallery": {
                "spacing": {
                    "margin": {
                        "bottom": "var(--wp--preset--spacing--60)",
                        "top": "var(--wp--preset--spacing--30)"
                    }
                }
            }
        }
    }
}
```

#### Explications :

##### margin-bottom: var(--wp--preset--spacing--60)
- Augmente l'espacement sous la galerie en utilisant une variable différente (un peu plus grande que la valeur précédente).
##### margin-top: var(--wp--preset--spacing--30)
- Ajoute de l'espace au-dessus de la galerie.