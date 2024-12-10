# Retirer les suggestions de blocs/compositions et les compositions par défaut

## Problématique des compositions par défaut

Le premier problème est que WordPress propose des compositions par défaut depuis le **Pattern Directory**, mais elles ne sont pas adaptées à notre site, car elles utilisent leur propre charte graphique. De plus, elles ajoutent de nombreuses catégories qui risquent de noyer nos compositions légitimes.

La meilleure solution ici est de désactiver ces compositions par défaut.

## Problématique des suggestions de blocs

Le second problème survient lors de la recherche de blocs via le champ de recherche du menu d'insertion. Gutenberg va parfois nous proposer d'autres blocs disponibles via des extensions installées sur le site, ainsi que des compositions créées par la communauté.

Ces blocs supplémentaires proviennent des **Block-enabled Plugins** que WordPress utilise pour étendre ses fonctionnalités.

Heureusement, il existe une solution simple pour nettoyer cela avec **deux lignes de code**.

## Retirer les compositions par défaut

Pour supprimer les compositions par défaut, ainsi que les suggestions de compositions dans la recherche, ajoutez la ligne suivante dans le fichier `functions.php` de votre thème :

```php
remove_theme_support( 'core-block-patterns' );
```
Cela désactivera les compositions par défaut de WordPress.

## Retirer les suggestions de blocs
Pour supprimer les suggestions de blocs provenant du Block Directory de WordPress.org, ajoutez cette ligne dans le fichier functions.php de votre thème :

```php
remove_action( 'wp_ajax_block_directory_search', 'block_directory_search' );
```
Cela supprimera les blocs provenant du répertoire de blocs de WordPress.org.

