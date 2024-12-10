# Organiser les compositions par catégories

Si vous suivez la méthodologie pour créer des sites avec le **Full Site Editing**, vous finirez par avoir de nombreuses compositions sur votre site, en fonction de leur taille. Toutefois, il peut devenir difficile de s'y retrouver sans une organisation adéquate. C'est pourquoi dans ce guide, je vous propose :

1. Déclarer des catégories de compositions en PHP.
2. Assigner une ou plusieurs catégories à chaque composition.
3. Renommer les fichiers du thème en ajoutant le nom de la catégorie.

Avec cette organisation, vous gagnerez en lisibilité dans l'éditeur, et vous faciliterez la maintenabilité de votre thème.

## Déclarer des catégories de compositions

Commençons par déclarer nos catégories de compositions. Dans les cours précédents, nous avons vu que nous pouvions assigner une catégorie via l'interface lorsqu'on ajoute une composition. Cependant, il est préférable de le faire via PHP pour avoir un meilleur contrôle sur les catégories proposées.

Le résultat sera similaire : dans l'interface de l'éditeur, la colonne de gauche listera chaque catégorie disponible, avec le nombre de compositions dans chacune.

### Catégories communes dans les thèmes

Voici quelques catégories fréquemment utilisées dans les thèmes WordPress :

- **Appel à l'action** : pour tous les **call to action** visant à vendre un produit ou service.
- **Cartes** : pour des éléments d'interface récurrents (comme des cartes d'information).
- **Bannières** : des sections pour introduire une page ou une idée principale.
- **Marketing** : pour des listes de fonctionnalités, arguments, témoignages clients, grilles de tarifs...
- **Publications** : pour tout ce qui concerne le blog, telles que les fiches d'article, listes d'articles, informations sur l'auteur...

Les catégories peuvent bien sûr varier d'un site à l'autre. Maintenant, voyons comment déclarer ces catégories dans le fichier `functions.php` de votre thème, en utilisant le hook `init`.

### Code pour déclarer une catégorie

Pour déclarer une catégorie, utilisez la fonction `register_block_pattern_category()` de WordPress. Cette fonction accepte deux arguments :

1. **Le nom unique de la catégorie** : C'est ce nom que vous utiliserez dans vos compositions.
2. **Les propriétés de la catégorie** : Sous forme de tableau PHP, vous aurez généralement besoin de spécifier uniquement le libellé qui apparaît dans l'interface.

Voici un exemple de code pour déclarer des catégories dans votre fichier `functions.php` :

```php
function declare_compositions_categories() {
    register_block_pattern_category( 'appel-action', array( 'label' => __( 'Appel à l’action', 'mon-theme' ) ) );
    register_block_pattern_category( 'cartes', array( 'label' => __( 'Cartes', 'mon-theme' ) ) );
    register_block_pattern_category( 'bannières', array( 'label' => __( 'Bannières', 'mon-theme' ) ) );
    register_block_pattern_category( 'marketing', array( 'label' => __( 'Marketing', 'mon-theme' ) ) );
    register_block_pattern_category( 'publications', array( 'label' => __( 'Publications', 'mon-theme' ) ) );
}
add_action( 'init', 'declare_compositions_categories' );
```

#### Note : 
Vous pouvez ajouter autant de catégories que nécessaire, mais il est préférable de rester simple pour une meilleure organisation.

## Assigner des catégories dans nos compositions

Une fois que vos catégories sont déclarées, vous pouvez les assigner à vos compositions. Pour cela, vous devez spécifier le slug de la catégorie que vous avez définie plus tôt en PHP.
Par exemple, pour assigner une composition aux catégories card, marketing et hero, vous pouvez le faire dans le fichier PHP de votre composition comme suit :

```php
/**
 * Nom de la composition
 *
 * @category card, marketing, hero
 */
```

#### Conseil : 
Bien que vous puissiez assigner plusieurs catégories à une composition, il est recommandé de n'en assigner qu'une seule pour garder les choses simples et éviter une trop grande complexité.

## Renommer les compositions dans le thème

Lorsque vous accumulez plusieurs compositions, vous finirez avec une longue liste de fichiers dans votre dossier patterns. Cependant, WordPress ne permet pas d'organiser ces fichiers par sous-dossiers dans le répertoire patterns.

Pour rester organisé, il est utile de suivre une convention de nommage. Le thème par défaut de WordPress propose une méthode de nommage efficace, que je vous recommande de suivre.

### Méthode de nommage recommandée

La convention consiste à indiquer le nom de la catégorie principale en début de fichier, sur ce modèle :

```html
<category>-<pattern>.php
```

Par exemple, si votre composition appartient à la catégorie marketing et qu'elle s'appelle "box promotion", le fichier pourrait être nommé ainsi :

```html
marketing-box-promotion.php
```

### Exemple de nommage et de slug dans les commentaires

Dans le fichier PHP de votre composition, vous devrez également modifier le slug dans les commentaires pour éviter tout risque de conflit avec un fichier portant un nom similaire d'une autre catégorie. Voici un exemple de commentaire de fichier :

```php
/**
 * Template: Box Promotion
 * Category: marketing
 * Slug: marketing-box-promotion
 */
```

En appliquant cette méthode d'organisation, vous améliorez non seulement la lisibilité de vos compositions dans l'éditeur WordPress, mais aussi la maintenabilité de votre thème sur le long terme.