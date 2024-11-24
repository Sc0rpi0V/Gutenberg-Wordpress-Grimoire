# Réglages d’espacement dans `theme.json`

## Activation des réglages d’espacement

Pour activer les options d’espacement (comme les marges et les paddings) pour les blocs qui les supportent, ajoutez une entrée `spacing` dans `settings` :

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
        "spacing": {
            "padding": true,
            "margin": true,
            "units": ["px", "em", "rem", "vh", "vw", "%"]
        }
    }
}
```

Ce réglage permet d’utiliser différentes unités d’espacement, comme `px`, `rem`, ou `%`.

---

## Échelle d’espacement personnalisée

### Définir des valeurs spécifiques

Vous pouvez définir une échelle d’espacement personnalisée en utilisant `spacingSizes`. Voici un exemple :

```json
{
    "settings": {
        "spacing": {
            "spacingSizes": [
                {
                    "name": "Extra-small",
                    "size": "0.25rem",
                    "slug": "xs"
                },
                {
                    "name": "Small",
                    "size": "0.5rem",
                    "slug": "s"
                },
                {
                    "name": "Medium",
                    "size": "1rem",
                    "slug": "m"
                },
                {
                    "name": "Large",
                    "size": "2rem",
                    "slug": "l"
                }
            ]
        }
    }
}
```

Chaque espacement est défini par :
- Un nom lisible (par exemple, `"Small"`).
- Une valeur (par exemple, `"0.5rem"`).
- Un *slug* utilisé pour générer une variable CSS.

Cela génère des variables CSS au format :  
`--wp--preset--spacing--<slug>`.

### Calcul automatique de l’échelle

Au lieu de spécifier chaque valeur, vous pouvez laisser WordPress générer une échelle avec `spacingScale`. Voici un exemple :

```json
{
    "settings": {
        "spacing": {
            "spacingScale": {
                "operator": "+",
                "increment": 0.25,
                "steps": 10,
                "mediumStep": 1,
                "unit": "rem"
            }
        }
    }
}
```

#### Paramètres de `spacingScale` :
- `operator`: Détermine si les valeurs sont additionnées (`+`) ou multipliées (`*`).
- `increment`: La valeur ajoutée (ou multipliée) à chaque étape.
- `steps`: Le nombre de pas dans l’échelle.
- `mediumStep`: La valeur intermédiaire par défaut.
- `unit`: L’unité utilisée (par exemple, `"rem"`).

Dans cet exemple :
- L’échelle commence à `1rem` (valeur de `mediumStep`).
- Des pas de `0.25rem` sont ajoutés jusqu’à atteindre `10 étapes`.
- La variable `--wp--preset--spacing--50` correspond à `1rem`, tandis que les autres valeurs (comme `--wp--preset--spacing--10` à `--wp--preset--spacing--100`) sont calculées automatiquement.

---

## Exemple avancé

Vous pouvez combiner `spacingSizes` avec d'autres options comme ceci :

```json
{
    "settings": {
        "spacing": {
            "spacingScale": {
                "steps": 0
            },
            "spacingSizes": [
                {
                    "name": "1",
                    "size": "1rem",
                    "slug": "10"
                },
                {
                    "name": "2",
                    "size": "min(1.5rem, 2vw)",
                    "slug": "20"
                },
                {
                    "name": "3",
                    "size": "min(2.5rem, 3vw)",
                    "slug": "30"
                },
                {
                    "name": "4",
                    "size": "min(4rem, 5vw)",
                    "slug": "40"
                },
                {
                    "name": "5",
                    "size": "min(6.5rem, 8vw)",
                    "slug": "50"
                },
                {
                    "name": "6",
                    "size": "min(10.5rem, 13vw)",
                    "slug": "60"
                }
            ],
            "units": ["%", "px", "em", "rem", "vh", "vw"]
        }
    }
}
```

Dans cet exemple, les tailles sont définies en utilisant des calculs CSS dynamiques avec `min()`.

---

## Exemple complet

Voici un exemple avec des réglages complets pour l’espacement :

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
        "spacing": {
            "padding": true,
            "margin": true,
            "units": ["px", "em", "rem", "vh", "vw", "%"],
            "spacingSizes": [
                {
                    "name": "Extra-small",
                    "size": "0.25rem",
                    "slug": "xs"
                },
                {
                    "name": "Medium",
                    "size": "1rem",
                    "slug": "m"
                }
            ],
            "spacingScale": {
                "operator": "*",
                "increment": 2,
                "steps": 5,
                "mediumStep": 1,
                "unit": "em"
            }
        }
    }
}
```

Ce fichier configure à la fois des tailles spécifiques et une échelle automatique.

---

Avec ces réglages, vous pouvez gérer finement les espacements dans votre thème WordPress tout en permettant une flexibilité maximale.
