# Réglages de Typographie

## Introduction

Les réglages de typographie permettent de définir les polices disponibles, les tailles de texte, ainsi que des options supplémentaires pour personnaliser l’apparence textuelle des blocs pris en charge.

---

## Exemple de configuration basique

Voici un exemple de déclaration JSON pour configurer des tailles de texte et des familles de polices.

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
        "color": { ... },
        "typography": {
            "fontSizes": [
                {
                    "slug": "small",
                    "size": "1rem",
                    "name": "Small"
                },
                {
                    "slug": "medium",
                    "size": "1.5rem",
                    "name": "Medium"
                }
                // ...
            ],
            "fontFamilies": [
                {
                    "fontFamily": "-apple-system,BlinkMacSystemFont,\"Segoe UI\",Roboto,Oxygen-Sans,Ubuntu,Cantarell,\"Helvetica Neue\",sans-serif",
                    "name": "System Font",
                    "slug": "system-font"
                },
                {
                    "fontFamily": "Muli, sans-serif",
                    "name": "Muli",
                    "slug": "muli",
                    "fontFace": [
                        {
                            "fontFamily": "Muli",
                            "fontStyle": "normal",
                            "fontWeight": "400",
                            "src": [
                                "file:./assets/fonts/muli/muli-Regular.woff2"
                            ]
                        },
                        {
                            "fontFamily": "Muli",
                            "fontStyle": "italic",
                            "fontWeight": "400",
                            "src": [
                                "file:./assets/fonts/muli/muli-Regular-Italic.woff2"
                            ]
                        },
                        {
                            "fontFamily": "Muli",
                            "fontStyle": "normal",
                            "fontWeight": "700",
                            "src": [
                                "file:./assets/fonts/muli/muli-Bold.woff2"
                            ]
                        },
                        {
                            "fontFamily": "Muli",
                            "fontStyle": "italic",
                            "fontWeight": "700",
                            "src": [
                                "file:./assets/fonts/muli/muli-Bold-Italic.woff2"
                            ]
                        }
                    ]
                }
            ]
        }
    },
    "styles": { ... }
}
```

### Explications
- **`fontSizes`** : Définit les différentes tailles disponibles pour les blocs. Chaque taille est associée à un `slug`, une `size` et un `name` pour identification.
- **`fontFamilies`** : Permet de déclarer les polices disponibles. Inclut des informations comme le nom (`name`), l’identifiant (`slug`), ainsi que les variantes à travers une déclaration `fontFace` (nécessaire pour des polices hébergées localement).

---

## Configuration avancée avec des polices fluides et plusieurs familles

Exemple d’une configuration plus élaborée, avec des polices "fluides" et des familles de polices supplémentaires :

```json
{
    "typography": {
        "fluid": true,
        "fontFamilies": [
            {
                "fontFace": [
                    {
                        "fontFamily": "Inter",
                        "fontStretch": "normal",
                        "fontStyle": "normal",
                        "fontWeight": "300 900",
                        "src": [
                            "file:./assets/fonts/inter/Inter-VariableFont_slnt,wght.woff2"
                        ]
                    }
                ],
                "fontFamily": "\"Inter\", sans-serif",
                "name": "Inter",
                "slug": "body"
            },
            {
                "fontFace": [
                    {
                        "fontFamily": "Cardo",
                        "fontStyle": "normal",
                        "fontWeight": "400",
                        "src": ["file:./assets/fonts/cardo/cardo_normal_400.woff2"]
                    },
                    {
                        "fontFamily": "Cardo",
                        "fontStyle": "italic",
                        "fontWeight": "400",
                        "src": ["file:./assets/fonts/cardo/cardo_italic_400.woff2"]
                    },
                    {
                        "fontFamily": "Cardo",
                        "fontStyle": "normal",
                        "fontWeight": "700",
                        "src": ["file:./assets/fonts/cardo/cardo_normal_700.woff2"]
                    }
                ],
                "fontFamily": "Cardo",
                "name": "Cardo",
                "slug": "heading"
            },
            {
                "fontFamily": "-apple-system, BlinkMacSystemFont, avenir next, avenir, segoe ui, helvetica neue, helvetica, Cantarell, Ubuntu, roboto, noto, arial, sans-serif",
                "name": "System Sans-serif",
                "slug": "system-sans-serif"
            },
            {
                "fontFamily": "Iowan Old Style, Apple Garamond, Baskerville, Times New Roman, Droid Serif, Times, Source Serif Pro, serif, Apple Color Emoji, Segoe UI Emoji, Segoe UI Symbol",
                "name": "System Serif",
                "slug": "system-Serif"
            }
        ],
        "fontSizes": [
            {
                "fluid": false,
                "name": "Small",
                "size": "0.9rem",
                "slug": "small"
            },
            {
                "fluid": false,
                "name": "Medium",
                "size": "1.05rem",
                "slug": "medium"
            },
            {
                "fluid": {
                    "min": "1.39rem",
                    "max": "1.85rem"
                },
                "name": "Large",
                "size": "1.85rem",
                "slug": "large"
            },
            {
                "fluid": {
                    "min": "1.85rem",
                    "max": "2.5rem"
                },
                "name": "Extra Large",
                "size": "2.5rem",
                "slug": "x-large"
            },
            {
                "fluid": {
                    "min": "2.5rem",
                    "max": "3.27rem"
                },
                "name": "Extra Extra Large",
                "size": "3.27rem",
                "slug": "xx-large"
            }
        ],
        "writingMode": true
    }
}
```

### Points clés :
- **Polices fluides** : Les tailles ajustables automatiquement en fonction de l’écran (utilisation de `fluid` avec les paramètres `min` et `max`).
- **Families supplémentaires** : Ajout de `Cardo` et de polices système.

---

## Génération automatique

Une fois configurées, WordPress génère automatiquement les variables CSS correspondantes. Par exemple :
- `--wp--preset--font-size--small`
- `--wp--preset--font-family--inter`

Utilisez ces variables dans vos styles ou au sein des blocs pris en charge.
