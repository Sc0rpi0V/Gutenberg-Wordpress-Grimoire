# Nom du composant

## Description

Brève description du composant et de son utilisation.

## Propriétés

| Nom   | Type    | Description                   | Valeur par défaut |
| ----- | ------- | ----------------------------- | ----------------- |
| prop1 | string  | Description de la propriété 1 | 'default'         |
| prop2 | boolean | Description de la propriété 2 | false             |
| ...   | ...     | ...                           | ...               |

## Utilisation

### Exemple de base

```php
$component = new YourComponent();
$component->setProp1('value');
$component->setProp2(true);

echo $component->getMarkup();
```

## Rendu HTML

```html
<tag class="composant">
	<!-- Structure HTML du composant -->
</tag>
```

## Décorateurs compatibles

- **Decorator1 :** description de l'utilisation avec ce composant
- **Decorator2 :** description de l'utilisation avec ce composant
- …

## Notes supplémentaires

Ajoutez ici toute information supplémentaire pertinente pour l'utilisation ou la personnalisation du composant.
