# URL dynamiques des liens et images, traduire les compositions

## Problématique des URL en dur

Un détail important peut poser problème dans les compositions : les **URL des liens et des images** sont écrites en dur. Cela peut poser des soucis lorsque le site est mis en ligne, car les URL ne seront plus valides, ce qui entraînera des liens morts et des images vides.

Par exemple, voici le code HTML généré par une composition pour une image :

```html
<img src="full-site-editing.local/chemin/vers/image.jpg" alt="Exemple Image">
```

L'URL "full-site-editing.local" est écrite en dur, ce qui n'est pas pratique. Heureusement, étant donné que nous utilisons PHP et non du simple HTML, nous pouvons utiliser les fonctions dynamiques de WordPress pour gérer ces URL.

### Objectifs :

Rendre dynamiques les URL des images et des liens/boutons.
Rendre traduisibles les chaînes de textes des contenus par défaut.

## Rendre les URL des liens et des images dynamiques

Solution 1 : Utiliser la fonction WordPress d'URL dynamique
La première solution consiste à remplacer toutes les URL en dur par la fonction dynamique home_url() de WordPress. Vous la connaissez déjà si vous avez développé des thèmes classiques dans le passé. Cela permettra de rendre dynamiques non seulement les URL des images, mais aussi celles des liens et des boutons.

En utilisant la fonction esc_url(), vous pouvez aussi assurer la sécurité des URL en les nettoyant de tout caractère indésirable. Cela reste une bonne pratique de sécurité, même si ici le risque est faible.

```php
$img_url = esc_url( home_url( '/chemin/vers/image.jpg' ) );
```
#### Note : 
Si vous utilisez un bloc "Navigation", il n'y aura pas de problème car les éléments du menu seront enregistrés en base de données. Il suffira simplement d'assigner un menu à votre emplacement lorsque vous insérerez la composition.

## Solution 2 : Rapatrier les images de démonstration dans le thème

Si les images ne sont pas disponibles dans la médiathèque de WordPress, une autre solution consiste à rapatrier les images de démonstration dans votre thème. Cela peut être particulièrement utile si vous souhaitez exporter des compositions entre plusieurs sites.

Voici les étapes pour gérer ce scénario :

Déplacez les images dans le dossier de votre thème. Par exemple, placez-les dans le dossier assets/img de votre thème.
Remplacez les URL statiques des images par des fonctions dynamiques de WordPress comme get_template_directory_uri() qui pointe vers le dossier de votre thème.
Exemple de code pour une image dans votre thème :

```html
<img src="<?php echo get_template_directory_uri(); ?>/assets/img/image.jpg" alt="Exemple Image">
```

### Exemple après modification

Si vous avez correctement configuré cela, l'URL de l'image devrait maintenant pointer vers un dossier dans votre thème :

```html
<img src="wp-content/themes/mon-theme/assets/img/image.jpg" alt="Exemple Image">
```
#### Important : 
Les compositions importées avant cette modification ne changeront pas. Vous devrez réimporter la composition pour voir les changements.

## Traduire vos compositions

Tout comme pour les URL dynamiques, vous pouvez rendre les textes des compositions traduisibles en utilisant les fonctions d'internationalisation de WordPress.

### Fonction esc_html_x() pour la traduction
Nous allons utiliser la fonction esc_html_x(), qui accepte trois paramètres :

1. La chaîne originale à afficher, qui sera traduite.
2. Le contexte pour expliquer au traducteur l'utilisation de cette chaîne.
3. Le textdomain pour isoler les chaînes de votre thème des autres traductions (plugins, cœur de WordPress…).

Exemple de code pour rendre une chaîne traduisible :

```php
echo esc_html_x( 'Texte à traduire', 'Contexte de la chaîne', 'mon-theme' );
```
#### Différence entre _e et _x : 
La fonction _x permet d'ajouter un contexte pour faciliter la traduction, contrairement à _e qui ne permet pas de spécifier un contexte.

## Le code PHP est dynamique à l’import seulement

Lorsque vous utilisez des fonctions PHP dans vos compositions, il est important de comprendre que le code PHP est exécuté uniquement lors de l'importation de la composition.

Par exemple, si vous incluez un bloc dynamique dans une composition, le contenu dynamique sera généré au moment de l'insertion dans l'éditeur. Cependant, ce contenu ne sera pas mis à jour automatiquement lorsque la page est affichée en frontend.

### Exemple avec une requête WP (WP Query)

Si vous voulez récupérer les 3 derniers articles, cela fonctionnera comme prévu au moment de l’insertion de la composition. Toutefois, le contenu ne sera pas mis à jour lorsque la page sera affichée sur le site. Cela peut poser problème si vous souhaitez que le contenu dynamique soit toujours actualisé.

### Solutions :

- Utiliser des blocs dynamiques comme la boucle de requête ou des blocs de navigation.
- Créer des blocs sur mesure qui seront exécutés au moment du rendu de la page en frontend.

Voici un exemple de bloc dynamique avec la boucle de requête :

```html
<!-- Exemple de bloc dynamique avec paramètres JSON dans des commentaires -->
<!-- wp:query {"queryId":"1","query":{"perPage":3,"postType":"post"}} /-->
```

Les blocs dynamiques fonctionnent toujours, même s’ils sont importés avec une composition, car ils sont traités au moment du rendu sur le frontend.

### Exemple de problème de dynamisme

Pour illustrer ce problème, imaginons que vous souhaitez insérer la date de l'année dans le footer, pour un copyright :

### Code avec PHP dans la composition (insertion statique)

```php
<p>&copy; 2025 Mon Site</p>
```

Si vous insérez cette composition en 2025, le pied de page affichera "2025" en permanence, même après le changement d'année.

### Solution : Bloc dynamique ou binding de données

Une meilleure solution serait de créer un bloc dynamique ou d'utiliser un mécanisme de binding de données pour que l'année soit toujours à jour :

```php
<p>&copy; <?php echo date("Y"); ?> Mon Site</p>
```

Cela permettra d'afficher automatiquement l'année actuelle sur le site.
