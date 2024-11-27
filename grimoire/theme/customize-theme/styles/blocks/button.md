# Réglages du bloc button dans styles

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "styles": {
        "blocks": {
            "core/button": {
                "variations": {
                    "outline": {
                        "spacing": {
                            "padding": {
                                "bottom": "calc(0.6rem - 1px)",
                                "left": "calc(1rem - 1px)",
                                "right": "calc(1rem - 1px)",
                                "top": "calc(0.6rem - 1px)"
                            }
                        },
                        "border": {
                            "width": "1px"
                        }
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

### Configuration spécifique : Bloc Bouton

#### Bloc ciblé : core/button

Ce bloc correspond au bouton, un élément interactif souvent utilisé pour des actions comme des soumissions de formulaire, des redirections, etc.

#### Variation ciblée : outline

La variation outline représente un bouton avec une bordure et un fond transparent. Cela permet de créer des boutons dont l'apparence est plus légère, souvent utilisée pour des actions secondaires ou dans des designs minimalistes.

#### Propriétés modifiées

##### Propriété spacing

###### padding :

Définit l'espacement interne (marges) autour du texte du bouton.
Ici, les valeurs sont définies avec des calculs calc pour ajuster précisément l'espacement :

- bottom : calc(0.6rem - 1px) — Un léger retrait du bas, ajusté par rapport à un pixel.
- left : calc(1rem - 1px) — Espacement à gauche, également ajusté par un pixel.
- right : calc(1rem - 1px) — Espacement à droite, similaire à celui de gauche.
- top : calc(0.6rem - 1px) — Espacement en haut, ajusté de manière similaire à celui du bas.

Ces ajustements permettent un contrôle précis de l'espacement autour du texte à l'intérieur du bouton.

##### Propriété border

###### width :

Définit la largeur de la bordure du bouton.
Ici, la valeur est fixée à 1px, ce qui donne une bordure fine autour du bouton.

#### Effet de la propriété border et spacing

- padding : L'ajustement des valeurs de padding permet de créer un bouton avec des espacements plus précis et cohérents, en évitant les effets de bordures imprévues dues à des arrondis de pixel.

- border-width : La largeur de la bordure affecte la visibilité du contour du bouton. Un 1px reste très léger mais permet de marquer la forme du bouton sans alourdir visuellement l'élément.

### Exemple visuel : Résultat attendu

| **Configuration**                  | **Résultat**                                                           |
|------------------------------------|------------------------------------------------------------------------|
| Sans bordure et sans padding	     | Bouton sans contour et compact                                         | 
| Avec padding ajusté et bordure 1px | Bouton avec une bordure fine et des espaces réguliers autour du texte  |

### Personnalisation supplémentaire

Il est possible d'ajouter d'autres propriétés pour personnaliser davantage l'apparence du bouton, telles que la couleur de la bordure, le type de bordure (pleine, en pointillés, etc.), ou des changements dans l'espacement.

#### Exemple avec plus de personnalisations :

```json
{
    "styles": {
        "blocks": {
            "core/button": {
                "variations": {
                    "outline": {
                        "spacing": {
                            "padding": {
                                "bottom": "calc(0.8rem - 1px)",
                                "left": "calc(1.2rem - 1px)",
                                "right": "calc(1.2rem - 1px)",
                                "top": "calc(0.8rem - 1px)"
                            }
                        },
                        "border": {
                            "width": "2px",
                            "color": "#0073e6",
                            "style": "solid"
                        }
                    }
                }
            }
        }
    }
}
```

#### Explications :

##### padding ajusté : 
- Augmentation des espacements internes pour donner un bouton plus large et plus aéré.

##### border-width: 2px : 
- Bordure plus épaisse.

##### border-color: #0073e6 : 
- Bordure de couleur bleue (#0073e6).

##### border-style: solid : 
- Bordure pleine, solide.