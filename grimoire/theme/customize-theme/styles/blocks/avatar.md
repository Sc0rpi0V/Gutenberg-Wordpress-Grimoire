# Réglages du bloc avatar dans styles

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "styles": {
        "blocks": {
            "core/avatar": {
                "border": {
                    "radius": "90px"
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

### Configuration spécifique : Bloc Avatar

#### Bloc ciblé : core/avatar
Ce bloc correspond à l’élément Avatar, utilisé pour afficher des images d’utilisateur (souvent circulaires ou carrées).

#### Propriété modifiée : border

##### radius :

- Définit l’arrondi des coins de l’avatar.
- La valeur 90px crée une forme très arrondie, généralement circulaire si l’image est carrée.

### Explication technique

#### Le bloc Avatar (core/avatar)

##### Usage :

- Utilisé pour afficher des avatars utilisateur ou des images de profil.
- Fréquent dans des blocs comme les commentaires ou les auteurs.

##### Styles par défaut :

- Par défaut, les avatars peuvent être carrés ou légèrement arrondis.
- En modifiant le rayon de bordure (radius), on personnalise la forme.

#### Effet de la propriété radius

- La propriété CSS border-radius contrôle l'arrondi des coins d'un élément.
- Avec une valeur élevée comme 90px, les coins deviennent presque complètement arrondis.
- Si l'image de l'avatar est carrée, elle apparaîtra circulaire. Si elle est rectangulaire, elle sera ovalisée.

### Exemple visuel : Résultat attendu

| **Configuration**          | **Résultat**   |
|----------------------------|----------------|
| Sans `border-radius`	     | Pas d'arrondis | 
| Avec `border-radius: 90px` | Bord arrondis  |

### Personnalisation supplémentaire

Vous pouvez ajouter d'autres propriétés pour affiner encore plus le style du bloc Avatar :

#### Exemple avec d'autres options de bordure :

```json
{
    "styles": {
        "blocks": {
            "core/avatar": {
                "border": {
                    "radius": "50%",
                    "width": "3px",
                    "color": "rgba(0, 0, 0, 0.5)",
                    "style": "solid"
                }
            }
        }
    }
}
```

#### Explications :

##### radius: 50% :
- Rend l’avatar parfaitement circulaire, quel que soit le rapport largeur/hauteur de l’image.

##### width: 3px :
- Définit une bordure de 3 pixels d’épaisseur.

##### color: rgba(0, 0, 0, 0.5) :
- Ajoute une bordure semi-transparente noire.

##### style: solid :
- Définit le type de bordure (ici pleine, mais cela peut être dashed, dotted, etc.).