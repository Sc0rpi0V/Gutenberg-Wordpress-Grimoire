# Réglages du bloc image dans styles

```json 
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "styles": {
        "blocks": {
            "core/image": {
                "variations": {
                    "rounded": {
                        "border": {
                            "radius": "var(--wp--preset--spacing--20)"
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

### Configuration spécifique : Bloc Image

#### Bloc ciblé : core/image

Le bloc core/image est utilisé pour insérer des images dans une page ou un article. Il permet de personnaliser l'apparence des images avec des options comme l'ajustement de la taille, l'alignement, les bordures, etc.

#### Variation ciblée : rounded

La variation rounded applique un effet d'arrondi aux bords de l'image, ce qui permet de lui donner un aspect plus doux et circulaire, souvent utilisé pour des images de profil ou des icônes.

### Propriété modifiée

##### Propriété border

###### radius :

- Définit l'arrondi des coins de l'image, transformant ainsi une image carrée en une image avec des bords arrondis.

- La valeur de radius ici est définie comme var(--wp--preset--spacing--20), une variable CSS prédéfinie dans WordPress qui correspond à un certain rayon d'arrondi défini dans les réglages du thème.

- Cette variable fait référence à une valeur d'arrondi spécifique, souvent utilisée pour assurer des bords arrondis cohérents dans le design du thème.

#### Effet de la propriété border-radius

- border-radius contrôle l'arrondi des coins de l'image.

- Avec une valeur comme var(--wp--preset--spacing--20), l'image aura des coins arrondis, mais pas complètement circulaires (si l'image est carrée). Si l'image est rectangulaire, l'arrondi donnera un effet plus doux aux coins sans rendre l'image circulaire.

### Exemple visuel : Résultat attendu

| **Configuration**                                    | **Résultat**                                                 |
|------------------------------------------------------|--------------------------------------------------------------|
| Sans border-radius		    	    	           | Image avec coins carrés                                      | 
| Avec `border-radius: var(--wp--preset--spacing--20)` | Image avec coins arrondis                                    |

### Personnalisation supplémentaire

Il est possible de personnaliser davantage l'apparence de l'image en ajustant d'autres propriétés de bordure ou en modifiant l'espacement autour de l'image.

#### Exemple avec d'autres ajustements de bordure et d'espacement :

```json 
{
    "styles": {
        "blocks": {
            "core/image": {
                "variations": {
                    "rounded": {
                        "border": {
                            "radius": "var(--wp--preset--spacing--30)",
                            "width": "2px",
                            "color": "#333",
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

##### border-radius: var(--wp--preset--spacing--30)
- Augmente l'arrondi des coins, créant des bords encore plus arrondis.

##### border-width: 2px 
- Applique une bordure de 2 pixels autour de l'image.

##### border-color: #333
- Définit la couleur de la bordure en gris foncé (#333).

##### border-style: solid
- Applique une bordure pleine autour de l'image.