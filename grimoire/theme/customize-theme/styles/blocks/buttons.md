# Réglages du bloc buttons dans styles

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "styles": {
        "blocks": {
            "core/buttons": {
                "spacing": {
                    "blockGap": "0.7rem"
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

### Configuration spécifique : Bloc Boutons

#### Bloc ciblé : core/buttons

Le bloc core/buttons est utilisé pour regrouper plusieurs boutons dans une disposition alignée horizontalement ou verticalement. Cela permet de créer des ensembles de boutons avec des espacements et des alignements personnalisés.

### Propriétés modifiées

##### Propriété spacing

###### blockGap :

- Définit l'espacement entre les éléments (ou les boutons) à l'intérieur du bloc core/buttons.

- La valeur 0.7rem spécifie un espace de 0.7rem (environ 11px) entre chaque bouton contenu dans le bloc.

- Cela est utile pour espacer les boutons dans une rangée ou une colonne, de manière uniforme, tout en gardant un alignement cohérent entre les éléments.

#### Effet de la propriété blockGap

- La propriété blockGap permet de définir un espacement entre les éléments enfants d'un bloc. Dans ce cas, elle s'applique entre les boutons contenus dans le bloc core/buttons.

- Si plusieurs boutons sont utilisés, cette valeur permettra de créer une séparation visuelle, donnant ainsi un effet d'aération entre les boutons.

### Exemple visuel : Résultat attendu

| **Configuration**       | **Résultat**                                 |
|-------------------------|----------------------------------------------|
| Sans `blockGap`         | Les boutons sont collés les uns aux autres   | 
| Avec `blockGap: 0.7rem` | Les boutons sont espacés de 0.7rem (11px)    |

### Personnalisation supplémentaire

Il est possible d’ajouter d'autres propriétés pour personnaliser l’apparence des boutons dans le bloc core/buttons, telles que l’alignement, l'espacement interne, ou encore les bordures des boutons eux-mêmes.

#### Exemple avec un autre espacement et alignement :

```json
{
    "styles": {
        "blocks": {
            "core/buttons": {
                "spacing": {
                    "blockGap": "1rem"
                }
            }
        }
    }
}
```

#### Explications :

##### blockGap: 1rem 
- Espacement légèrement plus grand entre les boutons.
