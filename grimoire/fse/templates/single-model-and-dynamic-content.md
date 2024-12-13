# Les modèles de publications "single" et le contenu dynamique dans WordPress

## Introduction

Le modèle `single.html` est utilisé pour afficher le contenu d'un article de blog individuel. Pour ce faire, nous allons ajouter plusieurs éléments à ce modèle pour structurer la page d'affichage de chaque publication.

### Étapes initiales

1. **Rendez-vous dans** : **Apparence > Éditeur > Modèles**.
2. **Sélectionnez** : « **Publications seules** » pour éditer le modèle.
3. **Ajoutez les éléments suivants** :
   - Le bloc de template part **"Header"**.
   - Un **Groupe** pour la section contenu.
   - Un **second Groupe** pour la section commentaires.
   - Enfin, le **Footer**.

---

## Les blocs dynamiques de contenu

Comme pour les pages standard, nous allons insérer les trois blocs principaux nécessaires pour afficher un article de blog :

1. **Le titre de la publication** : C'est un bloc de niveau 1, il est déjà configuré comme tel, donc pas besoin de modification.
2. **Le contenu** : Le corps de l'article.
3. **L'image mise en avant** : Vous pouvez laisser l'image au format standard ou la fixer dans un ratio de **16:9** via les options de mise en page du bloc.

---

## Les méta d'article

Ensuite, nous allons ajouter des blocs dynamiques pour les informations supplémentaires relatives à l'article :

1. **Le bloc « Catégories »** : Affiche les catégories assignées à cet article.
2. **Le bloc « Nom de l’auteur »** : Affiche le nom de l’auteur de l’article.
3. **Le bloc « Date de publication »** : Affiche la date de publication de l’article.

---

## L’auteur et la navigation vers les autres articles

Après avoir affiché le contenu de l'article, nous allons ajouter des éléments relatifs à l’auteur et à la navigation entre les articles.

1. **Bloc « Auteur »** : Ce bloc affiche, en plus du nom de l’auteur, son **avatar** et sa **biographie**. Cette biographie peut être remplie dans l’administration de WordPress sous **Comptes > Votre profil**.
2. **Rangée de navigation** : Ajoutez une rangée avec la justification « **Répartir les blocs** » et insérez les blocs « **Article précédent** » et « **Article suivant** » pour permettre aux visiteurs de naviguer entre les articles.

---

## Les blocs de commentaires

Dans le second groupe, nous allons ajouter le bloc **« Commentaires »**. Ce bloc est une composition de plusieurs blocs dédiés à la gestion des commentaires d’une publication.

### Titre des commentaires

Par défaut, le bloc « Commentaires » inclut un titre. Cependant, ce titre peut prêter à confusion, car mettre un titre de niveau `<H2>` ou `<H3>` pourrait nuire à la hiérarchie sémantique de la page. Une alternative pourrait être d’utiliser un **texte personnalisé** sans titre.

- **Problème** : Un titre de niveau `<H2>` pour les commentaires mettrait les commentaires au même niveau que le contenu principal de l’article.
- **Solution** : Utiliser un bloc custom pour afficher le nombre de commentaires dans un **paragraphe** avec la fonction PHP `comments_number()`.

### Le modèle des commentaires

À l’intérieur du bloc **"Commentaires"**, vous pouvez définir plusieurs éléments pour personnaliser l’apparence des commentaires dans la liste des commentaires :

1. **Avatar** : Affiche l'avatar de la personne commentant, via Gravatar.
2. **Nom de la personne** : Affiche le nom de l'auteur du commentaire.
3. **Date de publication** : Affiche la date à laquelle le commentaire a été publié.
4. **Texte du commentaire** : Affiche le contenu du commentaire.
5. **Bouton de réponse** : Permet de répondre au commentaire.
6. **Bouton de modification** : Permet à l’auteur du commentaire ou aux administrateurs de le modifier.

### La pagination des commentaires

La pagination des commentaires est nécessaire uniquement si vous avez activé le réglage **"Diviser les commentaires en pages"** dans **Réglages > Commentaires**. Cela vous permet de limiter le nombre de commentaires affichés par page, généralement 50 par défaut.

### Formulaire de commentaire

Le bloc **"Formulaire de commentaire"** permet à vos visiteurs de laisser des commentaires. Ce bloc est indépendant et peut être placé où vous le souhaitez, y compris dans des **colonnes** ou à côté du contenu principal.

---

## Aller plus loin : afficher des articles liés

Bien que WordPress ne propose pas nativement de bloc pour afficher des articles liés, il existe plusieurs solutions pour le faire :

1. **Extensions** : Utilisez des extensions comme **Related Posts** pour afficher des articles similaires en fonction de la thématique.
2. **Bloc personnalisé** : Vous pouvez également développer un bloc sur-mesure pour afficher des articles liés.

### Solution maison avec la boucle de requête

Une approche simple consiste à insérer une **boucle de requête** pour afficher des articles similaires. Voici les paramètres pour cette boucle :

1. **Afficher 3 articles** liés à l'article en cours.
2. **Supprimer la navigation** entre les articles.
3. **Présentation en grille** de 3 colonnes avec une taille d’image en **16:9**.

#### Structure HTML et CSS

- Le titre avant la boucle sera en `<H2>`.
- Les titres des articles seront en `<H3>`, avec une taille de police réduite.
- Seulement les titres et la date de publication seront affichés sous les images.

---

## Modifier la boucle en PHP

Pour que la boucle de requête affiche uniquement les articles de la même catégorie, vous devez modifier la requête dans le fichier `functions.php`. Voici les étapes pour personnaliser la boucle :

### Conditions à respecter

1. **Exclure l'article actuel** de la liste des articles liés.
2. **Limiter les articles** aux articles de la même catégorie que l'article affiché.

Utilisez le **tag conditionnel `is_singular()`** pour vérifier que nous sommes sur un article spécifique (et non sur la page d'accueil ou un autre type de page).

Voici un exemple de code PHP à ajouter dans `functions.php` pour personnaliser la requête :

```php
function my_related_posts_query( $query ) {
    if ( is_singular('post') && !is_admin() && $query->is_main_query() ) {
        $query->set( 'posts_per_page', 3 );
        $query->set( 'post__not_in', array( get_the_ID() ) );
        $query->set( 'category__in', wp_get_post_categories( get_the_ID() ) );
    }
}
add_action( 'pre_get_posts', 'my_related_posts_query' );
````

Ce code ajustera la boucle de requête pour n'afficher que 3 articles de la même catégorie que l'article actuel, en excluant l'article en cours.