# Paramètres supplémentaires dans theme.json

## **useRootPaddingAwareAlignments**

Le paramètre `useRootPaddingAwareAlignments` permet d'activer la prise en compte des alignements basés sur le remplissage (padding) racine pour les blocs alignés (comme les blocs larges ou pleins).  
Cela garantit que les blocs respectent les espaces définis globalement tout en maintenant une cohérence visuelle.

### Exemple de configuration :

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
        "layout": { ... },
        "useRootPaddingAwareAlignments": true
    },
    "styles": { ... }
}
```

Fonctionnement :
Lorsque activé (true), ce paramètre ajuste automatiquement les alignements des blocs pour qu'ils s'adaptent aux marges internes (padding) définies à la racine.
Utile pour des mises en page cohérentes, en particulier lorsqu'on utilise des alignements larges (alignwide) ou pleins (alignfull).

## **appearanceTools**

Le paramètre appearanceTools active des outils d'apparence supplémentaires pour les blocs dans l'éditeur de blocs WordPress.
Cela simplifie la personnalisation visuelle en exposant des réglages avancés directement dans l'interface utilisateur de l'éditeur.

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
        "appearanceTools": true
    },
    "styles": { ... }
}
```

Fonctionnement :
Lorsque activé (true), ce paramètre ajoute des options comme :
- Contrôle des bordures (taille, style, couleur).
- Contrôle des ombres.
- Autres ajustements visuels spécifiques aux blocs.