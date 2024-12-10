## Pourquoi la méthode PHP ne fonctionne pas ?

D’après la documentation de WordPress, il existe une fonction pour retirer des variations de styles de blocs : `unregister_block_style()`.

On pourrait penser que ce bout de code fonctionne :


Mais non ! Comme un commentaire le stipule, **cette méthode fonctionne uniquement pour les styles de blocs déclarés précédemment en PHP**, ce qui n’est pas le cas des blocs natifs.

D’après la documentation, la fonction `unregister_block_style()` fait appel à la classe `WP_Block_Styles_Registry`, je vais donc tenter de voir ce qu’il y a dedans :


Et le résultat est un tableau vide :


Il n’y a même pas les variations que l’on a déclarées, **puisqu’on les déclare désormais en JSON directement** et non plus en PHP. Pas très utile dans notre cas.

## La Méthode JavaScript

Du coup, on va devoir **passer par JavaScript** pour retirer ces variations par défaut. Pas super pratique mais bon, au moins on a une solution. Il suffira de la mettre en place pour chaque projet et le tour sera joué.

Il va tout d’abord falloir **déclarer un script qui se lance avec l’éditeur** :



Ce qui est important ici, c’est **le tableau des dépendances**, car il faut que notre script se charge ni trop tôt, ni trop tard dans l’éditeur, d’où les mentions à `wp-blocks`, `wp-dom-ready` et `wp-edit-post`.

Le hook utilisé pour lancer cette fonction est `enqueue_block_editor_assets`, c’est un hook qui se lance **lorsque l’éditeur Gutenberg s’apprête à charger ses scripts** dans l’administration.

Je crée maintenant un fichier `unregister_block_styles.js` dans le dossier `/assets/js` de mon thème.

À l’intérieur de ce fichier, on va utiliser la fonction `wp.blocks.unregisterBlockStyle()` pour retirer les variations :


Un peu comme avec jQuery à l’époque, il faut bien **attendre que le DOM soit prêt** afin de lancer nos instructions.

Ensuite, la fonction `unregisterBlockStyle` attend 2 arguments :

1. Le slug du **bloc**, par exemple `core/button` ;
2. Et le slug de la **variation**, qui est aussi le nom de la classe CSS.

Vous trouverez la liste complète des variations présentes par défaut sur la documentation des thèmes de WordPress. Voici **la liste des variations par défaut qui existent** à ce jour :

- `core/button` : **outline**, **fill** ;
- `core/image` : **rounded** ;
- `core/quote` : **plain** ;
- `core/site-logo` : **rounded** ;
- `core/separator` : **wide**, **dots** ;
- `core/social-links` : **logos-only**, **pill-shape** ;
- `core/table` : **stripes** ;
- `core/tag-cloud` : **outline** ;

Et voilà, faute de mieux pour le moment, vous pouvez retirer les variations par défaut des blocs natifs de Gutenberg grâce à cette approche.