# Réglages de couleurs dans `theme.json`

## Palette de couleurs

Dans la section `settings.color`, vous pouvez déclarer une palette personnalisée. Chaque couleur de la palette est associée à un *slug* (identifiant), une valeur hexadécimale et un nom. Voici un exemple :

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
        "color": {
            "palette": [
                {
                    "slug": "base",
                    "color": "#f9f9f9",
                    "name": "Base"
                },
                {
                    "slug": "contrast",
                    "color": "#111111",
                    "name": "Contrast"
                },
                {
                    "slug": "accent",
                    "color": "#cfcabe",
                    "name": "Accent"
                }
            ]
        }
    }
}
```

Une fois la palette déclarée, WordPress génère automatiquement des variables CSS pour chaque couleur au format suivant :  
`--wp--preset--color--<slug>`  
Vous pouvez les utiliser dans vos styles avec `var(--wp--preset--color--<slug>)`.

---

## Gradients

Vous pouvez définir des dégradés disponibles dans l'éditeur en les déclarant sous `settings.color.gradients`. Voici comment configurer une liste de dégradés :

```json
{
    "settings": {
        "color": {
            "gradients": [
                {
                    "slug": "gradient-1",
                    "gradient": "linear-gradient(to bottom, #cfcabe 0%, #f9f9f9 100%)",
                    "name": "Vertical soft beige to white"
                },
                {
                    "slug": "gradient-2",
                    "gradient": "linear-gradient(to bottom, #D8613C 0%, #F9F9F9 100%)",
                    "name": "Vertical soft rust to white"
                }
            ]
        }
    }
}
```

Comme pour les couleurs, chaque dégradé a un *slug*, une valeur CSS pour le dégradé, et un nom lisible par l'utilisateur.

---

## Duotones

Les duotones permettent de styliser des images ou des vidéos avec deux couleurs dominantes. Voici un exemple de configuration dans `settings.color.duotone` :

```json
{
    "settings": {
        "color": {
            "duotone": [
                {
                    "slug": "duotone-1",
                    "colors": ["#111111", "#ffffff"],
                    "name": "Black and White"
                },
                {
                    "slug": "duotone-2",
                    "colors": ["#111111", "#D8613C"],
                    "name": "Black and Rust"
                }
            ]
        }
    }
}
```

Chaque duotone se compose :
- D’un *slug*.
- D’une liste de deux couleurs (par exemple, `#111111` et `#ffffff`).
- D’un nom lisible.

---

## Réglages par défaut

Vous pouvez désactiver les palettes, dégradés ou duotones par défaut de WordPress avec ces propriétés dans `settings.color` :

```json
{
    "settings": {
        "color": {
            "defaultPalette": false,
            "defaultGradients": false,
            "defaultDuotone": false
        }
    }
}
```

---

## Exemple complet

Voici un exemple complet avec une palette, des dégradés et des duotones définis :

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
        "color": {
            "defaultPalette": false,
            "defaultGradients": false,
            "defaultDuotone": false,
            "palette": [
                {
                    "slug": "base",
                    "color": "#f9f9f9",
                    "name": "Base"
                },
                {
                    "slug": "contrast",
                    "color": "#111111",
                    "name": "Contrast"
                }
            ],
            "gradients": [
                {
                    "slug": "gradient-1",
                    "gradient": "linear-gradient(to bottom, #cfcabe 0%, #f9f9f9 100%)",
                    "name": "Soft beige to white"
                }
            ],
            "duotone": [
                {
                    "slug": "duotone-1",
                    "colors": ["#111111", "#ffffff"],
                    "name": "Black and White"
                }
            ]
        },
        "styles": {
            "color": {
                "text": "var(--wp--preset--color--contrast)"
            }
        }
    }
}
```

Dans cet exemple, une palette, un dégradé et un duotone sont déclarés, et la couleur de texte globale est définie sur `contrast`.

---

Avec ces réglages, vous pouvez personnaliser entièrement l’expérience visuelle de votre thème WordPress.
