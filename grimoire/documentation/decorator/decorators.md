# Les décorateurs pour styliser les composants

## Introduction

Dans le cadre de notre approche de création de composants agnostiques, nous préconisons l’utilisation de “décorateurs” pour styliser ces composants. Les décorateurs sont un concept que nous avons introduit pour ajouter de manière flexible des styles aux composants sans les lier directement à des implémentations spécifiques ou à des dépendances externes.

## Qu’est-ce qu’un décorateur ?

Un décorateur est une classe qui suit un contrat spécifique défini par une interface (dans notre cas, `StyleDecorator`). Il a pour rôle d’ajouter des classes CSS ou des attributs de style à un composant de manière modulaire et réutilisable. Les décorateurs permettent d’enrichir les composants avec des styles sans modifier leur structure interne.

### Avantages de l’Utilisation des Décorateurs

- Modularité : les décorateurs permettent d’ajouter ou de modifier les styles sans toucher au code du composant lui-même.
- Réutilisabilité : les mêmes décorateurs peuvent être appliqués à différents composants.
- Flexibilité : on peut combiner plusieurs décorateurs pour créer des styles complexes.


```php
<?php

namespace PQP\Decorators;

interface StyleDecorator
{
    public function getClassName(): string;
}
```

## Exemple de décorateur

```php
<?php

namespace PQP\Decorators;

class IsStyleCardDecorator implements StyleDecorator
{
    public function getClassName(): string
    {
        return 'rounded px-7 py-5 lg:px-10 lg:py-7 shadow-light';
    }
}
```

## Bonnes pratiques

- Respecter le contrat : tous les décorateurs doivent implémenter l’interface StyleDecorator pour assurer une cohérence.
- Nommer les décorateurs de manière explicite : le nom du décorateur doit refléter clairement le style ou la fonctionnalité qu’il apporte.
- Documenter les décorateurs : chaque décorateur doit être documenté pour faciliter sa compréhension et son utilisation.

## Exemple d'utilisation 

```php
<?php

use PQP\Components\TokenComponent;
use PQP\Decorators\IsStyleCardDecorator;
use PQP\Decorators\CustomBackgroundDecorator;

// Création du composant
$component = new TokenComponent();

// Ajout de décorateurs
$component->addDecorator(new IsStyleCardDecorator());
$component->addDecorator(new CustomBackgroundDecorator('blue-500'));

// Génération du markup
echo $component->getMarkup();
```

Dans cet exemple :

- `IsStyleCardDecorator` : ajoute des styles de carte au composant.
- `CustomBackgroundDecorator` : ajoute une classe pour un arrière-plan personnalisé, le nom de la couleur est passé en paramètre. Ce nom sera utilisé pour récupérer la classe CSS correspondante dans le thème.


## Pour aller plus loin

- [Les types de décorateurs](./decorator-granularity.md)
