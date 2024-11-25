# La responsabilité des décorateurs

[Les décorateurs](./decorator.md) sont un moyen flexible et modulaire d’ajouter des styles et des comportements aux composants. Ils peuvent être classés en plusieurs catégories en fonction de leur rôle et de leur impact sur le composant. Voici les principaux types de décorateurs que nous utilisons :

## 1. Clarté des responsabilités

### Principe de responsabilité unique (Single Responsibility Principle)

- Décorateurs comportementaux (Behavioral Decorator) : gèrent le comportement interne du composant.
- Décorateurs liés au Thème (Theme Decorator) : s’occupent de l’intégration visuelle avec le thème actif.
- Décorateurs de Gutenberg (Gutenberg Decorator) : reflètent les paramètres spécifiques choisis par l’utilisateur.

Cette séparation permet à chaque décorateur de se concentrer sur une seule tâche, rendant le code plus facile à comprendre et à maintenir.

## 2. Cohérence du Code

### Isolation des changements

- Les modifications apportées à un type de décorateur n’affectent pas les autres, minimisant le risque d’introduire des bugs.
- Facilite le débogage en permettant d’identifier rapidement quelle partie du code est responsable d’un comportement donné.

### Standardisation

- Encourage l’utilisation de conventions communes, ce qui améliore la lisibilité et la cohérence du code à travers toute l’application.

## 3. Meilleure Collaboration

### Division du travail

- Les développeurs peuvent travailler sur différents types de décorateurs en parallèle sans entrer en conflit.
- Clarifie les responsabilités de chaque membre de l’équipe, ce qui améliore l’efficacité du développement.

## Exemple

```php
// Création du composant
$component = new TokenComponent();

// Application du décorateur comportemental
$component->addDecorator(new InteractiveDecorator());

// Application du décorateur lié au thème
$component->addDecorator(new ThemeColorDecorator());

// Récupération des paramètres de Gutenberg
$alignment = $blockAttributes['alignment'] ?? 'left';
$component->addDecorator(new AlignmentDecorator($alignment));

// Génération du markup
echo $component->getMarkup();
```

## Gestion des Conflits

### Priorités

- Définir un ordre d’application des décorateurs si nécessaire pour gérer les conflits potentiels.
- Les décorateurs liés à Gutenberg pourraient avoir la priorité sur ceux liés au thème pour refléter les choix de l’utilisateur.

### Vérification des Conditions

- Appliquer certains décorateurs uniquement si certaines conditions sont remplies (par exemple, si un certain thème est actif ou si un paramètre est défini).

## Cas d’utilisation

### 1. Décorateur comportemental (Behavioral Decorator)

Un composant bouton qui doit avoir un comportement différent lorsqu’il est désactivé :

```php
class DisabledStateDecorator implements StyleDecorator
{
    public function getClassName(): string
    {
        return 'cursor-not-allowed opacity-50';
    }
}
```

### 2. Adaptation au Thème Actif (Theme Decorator)

```php
class ThemeTypographyDecorator implements StyleDecorator
{
    public function getClassName(): string
    {
        return 'font-theme-body text-theme-color';
    }
}
````

### 3. Réflexion des Paramètres de Gutenberg (Gutenberg Decorator)

```php
class AlignmentDecorator implements StyleDecorator
{
    private string $alignment;

    public function __construct(string $alignment)
    {
        $this->alignment = $alignment;
    }

    public function getClassName(): string
    {
        $alignmentClasses = [
            'left' => 'text-left',
            'center' => 'text-center',
            'right' => 'text-right',
        ];

        if (!in_array($this->alignment, ['left', 'center', 'right'])) {
            throw new \InvalidArgumentException('Invalid alignment value');
        }

        return $alignmentClasses[$this->alignment];
    }
}
```

## Conclusion

La séparation des décorateurs en fonction de leur rôle est une pratique essentielle pour maintenir un code propre, modulaire et facile à maintenir.

Cette approche permet de gérer efficacement la complexité croissante des applications modernes en isolant les responsabilités, en améliorant la réutilisabilité et en facilitant la collaboration entre les membres de l’équipe.
