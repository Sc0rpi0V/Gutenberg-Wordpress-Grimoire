# Étapes pour déclarer un Custom Post Type

## 1. Choisir l’emplacement du code

Il est recommandé de placer le code de déclaration du Custom Post Type (CPT) dans une extension plutôt que dans le fichier `functions.php` du thème. Cela garantit que le CPT restera actif même si le thème est changé ou évolue.

Créer un plugin personnalisé :

1. Dans le dossier `public/plugins/`, créez un nouveau dossier, par exemple `mon-custom-post-type`.
2. À l’intérieur de ce dossier, créez un fichier PHP, par exemple `mon-custom-post-type.php`.
3. Ajoutez l’en-tête du plugin au début du fichier :

```php

<?php
/*
Plugin Name: Mon Custom Post Type
Description: Plugin pour créer un Custom Post Type personnalisé.
Version: 1.0
Author: Votre Nom
*/
```

## 2. Utiliser la fonction register_post_type()

La fonction `register_post_type()` est utilisée pour enregistrer un nouveau CPT. Elle doit être appelée lors de l’initialisation de WordPress, généralement en utilisant le hook init.

## 3. Exemple

Voici un exemple pour créer un CPT nommé “Produit” :

```php
add_action('init', 'custom_post_type_produit', 0);

function custom_post_type_produit()
{
	$labels = [
		'name' => _x('Produits', 'Post Type General Name', 'text_domain'),
		'singular_name' => _x('Produit', 'Post Type Singular Name', 'text_domain'),
		'menu_name' => __('Produits', 'text_domain'),
		'name_admin_bar' => __('Produit', 'text_domain'),
		'archives' => __('Archives des produits', 'text_domain'),
		'attributes' => __('Attributs du produit', 'text_domain'),
		'parent_item_colon' => __('Produit parent:', 'text_domain'),
		'all_items' => __('Tous les produits', 'text_domain'),
		'add_new_item' => __('Ajouter un nouveau produit', 'text_domain'),
		'add_new' => __('Ajouter nouveau', 'text_domain'),
		'new_item' => __('Nouveau produit', 'text_domain'),
		'edit_item' => __('Éditer le produit', 'text_domain'),
		'update_item' => __('Mettre à jour le produit', 'text_domain'),
		'view_item' => __('Voir le produit', 'text_domain'),
		'view_items' => __('Voir les produits', 'text_domain'),
		'search_items' => __('Rechercher un produit', 'text_domain'),
		'not_found' => __('Aucun produit trouvé', 'text_domain'),
		'not_found_in_trash' => __(
			'Aucun produit trouvé dans la corbeille',
			'text_domain'
		),
		'featured_image' => __('Image du produit', 'text_domain'),
		'set_featured_image' => __('Définir l’image du produit', 'text_domain'),
		'remove_featured_image' => __(
			'Supprimer l’image du produit',
			'text_domain'
		),
		'use_featured_image' => __(
			'Utiliser comme image du produit',
			'text_domain'
		),
		'insert_into_item' => __('Insérer dans le produit', 'text_domain'),
		'uploaded_to_this_item' => __('Téléversé dans ce produit', 'text_domain'),
		'items_list' => __('Liste des produits', 'text_domain'),
		'items_list_navigation' => __(
			'Navigation de la liste des produits',
			'text_domain'
		),
		'filter_items_list' => __('Filtrer la liste des produits', 'text_domain'),
	];
	$args = [
		'label' => __('Produit', 'text_domain'),
		'description' => __('Type de contenu pour les produits', 'text_domain'),
		'labels' => $labels,
		'supports' => ['title', 'editor', 'thumbnail', 'excerpt', 'custom-fields'],
		'taxonomies' => ['category', 'post_tag'],
		'hierarchical' => false,
		'public' => true,
		'show_in_menu' => true,
		'menu_position' => 5,
		'menu_icon' => 'dashicons-cart',
		'show_in_admin_bar' => true,
		'show_in_nav_menus' => true,
		'can_export' => true,
		'has_archive' => true,
		'exclude_from_search' => false,
		'publicly_queryable' => true,
		'rewrite' => ['slug' => 'produits'],
		'capability_type' => 'post',
		'show_in_rest' => true,
	];
	register_post_type('produit', $args);
}
```

### 4. Explication du code

- `$labels` : définit les étiquettes utilisées dans l’interface d’administration pour le CPT.
- `$args` : paramètres du CPT, incluant les fonctionnalités supportées, la visibilité et les options de réécriture d’URL.
- `supports` : indique les fonctionnalités supportées par le CPT (titre, éditeur, image à la une, etc.).
- `taxonomies` : associe des taxonomies existantes (catégories, étiquettes) au CPT.
- `rewrite` : personnalise la structure des permaliens pour le CPT.
- `show_in_rest` : active la prise en charge de l’API REST, nécessaire pour l’éditeur Gutenberg.

## Enregistrer le type de contenu personnalisé

- Activation du plugin : rendez-vous dans le tableau de bord WordPress, sous Extensions, et activez votre nouveau plugin.
- Vérification : un nouveau menu “Produits” devrait apparaître dans la barre latérale.

## Mise à jour des permaliens

Après l’ajout d’un nouveau CPT, il est conseillé de rafraîchir les permaliens :

1. Allez dans "Réglages > Permaliens".
2. Cliquez sur "Enregistrer" les modifications sans apporter de changements. Cela régénère les règles de réécriture d’URL.

## Bonnes pratiques

- Utiliser un préfixe unique : pour éviter les conflits, préfixez vos fonctions et variables (par exemple, `creer_custom_post_type_produit`).
- Internationalisation : utiliser les fonctions `__()` et `_x()` pour préparer votre CPT à la traduction.
- Gestion des capacités : si nécessaire, définir des capacités personnalisées pour contrôler l’accès au CPT.
- Sécurité : valider et assainir toutes les données entrantes si vous ajoutez des métaboxes ou des champs personnalisés.
- Documentation : commenter votre code pour faciliter la maintenance future.
