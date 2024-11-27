# Processus pour créer un composant

## Définition

- Le composant doit être réutilisable et flexible.
- Un composant est une représentation fonctionnelle d'un élément graphique.
- Ce fcontionnel peut être réutilisé dans plusieurs contextes.
- Les représentations graphiques d'un composant sont définies par des décorateurs.

## Objectifs

- Modularité : faciliter la maintenance et l’évolution du code en segmentant les fonctionnalités en composants indépendants.
- Réutilisabilité : utiliser les composants à travers différents projets ou plateformes sans modifications majeures.
- Flexibilité : permettre une intégration aisée avec diverses technologies ou frameworks au-delà de WordPress.
- Isolation : développer des composants UI/UX indépendants, sans dépendances spécifiques à WordPress ou Gutenberg.

### Avantages des composants agnostiques

#### Indépendance technologique

- Interopérabilité : les composants peuvent être utilisés avec différents langages de programmation (PHP, JavaScript, etc.).
- Évolutivité : facilité d’adaptation aux évolutions technologiques sans refonte complète du code.

#### Amélioration du workflow de développement

- Collaboration : les équipes peuvent travailler simultanément sur différents composants sans conflits.
- Maintenance : identification et correction plus rapides des bugs grâce à l’isolement des composants.

## 1. Identification des composants

- Analysez les maquettes et les spécifications du projet.
- Identifiez les éléments réutilisables et les patterns récurrents.
- Déterminez si un nouveau composant est nécessaire ou si un composant existant peut être adapté.
- Nommez le composant de manière claire et descriptive (ex: HeadingComponent, ButtonComponent, etc.).
- Créez [une documentation pour le composant](./document-component.md).

## 2. Création du Data Mapper

- Créez un nouveau fichier PHP dans le dossier public/themes/wordplate/block-data-mapper/.
- Nommez le fichier en fonction du composant (ex: heading.php, button.php).
- Structurez le Data Mapper comme suit :

```php
<?php

use PQP\Components\YourComponent;
// Importez les décorateurs nécessaires

add_action('render_block_core/block_name', 'block_name_render', 10, 3);

function your_component_render(string $blockContent, array $block): string
{
	$component = new YourComponent();

	// Logique de mapping des attributs du bloc vers le composant
	// Utilisez les décorateurs pour ajouter des fonctionnalités

	return $component->getMarkup();
}
```

- Identifiez les attributs du bloc Gutenberg et mappez-les aux propriétés du composant.
- Utilisez les décorateurs appropriés pour modifier l'apparence du composant en fonction du contexte (couleur, alignement, etc.).

## 3. Création du Composant

- Créez un nouveau fichier PHP dans le dossier public/themes/wordplate/components/.
- Nommez le fichier en fonction du composant (ex: HeadingComponent.php, ButtonComponent.php).
- S'assurer que le composant est compatible avec les dernières normes HTML5.
- Une attention particulière doit être portée sur la sémantique.
- Structurez le composant comme suit :

```php
<?php

namespace BlockDataMapper;

use Components\Component;

class YourComponent extends Component
{
}
```

## 4. Implémentez la logique spécifique au composant dans la méthode getMarkup().

- Assurez-vous que le composant est flexible et réutilisable.
