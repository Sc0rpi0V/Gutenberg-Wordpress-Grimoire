# Créer des compositions de blocs réutilisables avec le FSE

## Étape des organismes sur Atomic Design

## Rôle des compositions dans WordPress

Dans WordPress, le but n’est pas de concevoir le design lorsque vous créez vos pages de contenu. L’objectif est de planifier et préparer tout cela en amont. Créer des compositions à l’avance va vous permettre de gagner énormément de temps par la suite lors de la création des contenus.

Si votre designer a bien travaillé dans Figma, il devrait être en mesure de vous proposer des designs de sections et de composants. Notre rôle va donc être de créer une bibliothèque de compositions réutilisables dans tout le site. Ces compositions peuvent ensuite être affichées dans **Apparence > Éditeur > Compositions** et même organisées par catégories.

On peut aller encore plus loin en exportant ces compositions et en les réutilisant dans de futurs sites. Vous commencez à voir le gain de temps, non ?

Lors de la création des contenus, il suffira de faire appel à nos compositions en 3 clics :

1. Dans une page (ou un article), cliquez sur le bouton `+` pour ajouter un bloc.
2. Accédez à l’onglet **Compositions**.
3. Sélectionnez la composition à insérer.

## Créer une composition

Nous allons maintenant créer notre première composition avec l’éditeur de sites de WordPress. Suivez ces étapes :

1. Allez dans **Apparence > Éditeur > Compositions**.
2. Cliquez sur le bouton **Ajouter une composition** et choisissez la première option.

Une fenêtre modale apparaîtra et vous demandera le nom de la composition, une ou plusieurs catégories dans lesquelles la ranger, et si cette composition doit être synchronisée ou non.

Vous pouvez indiquer n’importe quelle catégorie existante ou en ajouter une. Pour cette première composition, désactivez la synchronisation.

### L’interface de création des compositions

Une fois dans l’interface de création de la composition, vous remarquerez un fond gris (même si votre site ne l’est pas) et des barres verticales sur les côtés. Elles vous permettent d’adapter la largeur de l’éditeur en les faisant glisser latéralement, afin de tester le comportement de vos compositions sur plusieurs tailles d’écran.

Avant de continuer, ouvrez la **Vue en liste** à gauche via le dernier bouton du menu supérieur. Elle sera très utile pour comprendre la structure en blocs et sélectionner facilement un bloc à modifier.

#### Astuce

Pour toujours afficher la vue en liste, cliquez sur le menu à 3 points en haut à droite de l’interface, sélectionnez **Préférences** dans le bas du menu, et dans l’onglet **Général**, activez l’option **Toujours ouvrir la vue en liste**.

## Réaliser notre première composition

Voici la composition que je vais créer à l’aide de Gutenberg, uniquement avec des blocs natifs :

1. **Préparation** : Assurez-vous que votre fichier `theme.json` est bien configuré, notamment les couleurs, espacements et quelques variations de styles de blocs (par exemple, pour les boutons).
2. **Commencer la composition** :
    - Créez un groupe et appliquez une couleur de fond et des arrondis.
    - Faites un clic droit > **Renommer** sur le groupe dans la vue en liste et renommez-le en « Hero ».
    - Appliquez des marges internes sur les côtés et en hauteur.

3. **Ajouter des blocs** :
    - Dans le groupe, insérez un bloc de colonnes composé de 2 colonnes.
    - Ajustez l’espacement entre les blocs pour définir le gap entre les colonnes.
    - Définissez une taille de **55%** pour la première colonne et **45%** pour la seconde.

### Colonne 1 :
1. **Ajouter un paragraphe** que vous passez en rose.
2. Ajoutez un titre de niveau 2, auquel vous ajoutez :
    - Une image en ligne.
    - Une couleur de mise en évidence.
3. Ajoutez un autre paragraphe suivi d’un **bloc boutons** :
    - Insérez deux boutons en utilisant le style principal et une variation.
4. Ajoutez un **séparateur** et modifiez sa couleur et sa marge supérieure.
5. Insérez une **rangée** pour aligner un paragraphe et les icônes de réseaux sociaux :
    - Utilisez la variation arrondie pour les icônes et appliquez un fond blanc avec du texte violet.

### Colonne 2 :
1. Insérez une première image avec des arrondis via la variation **Arrondi**.
2. Insérez une galerie avec 2 images supplémentaires et appliquez la même variation **Arrondi**.

## Enregistrer la composition dans le thème

Lorsque vous enregistrez votre composition, elle sera sauvegardée dans la base de données de WordPress sous forme d’une publication, avec le type de publication privé `wp_block`. Cependant, vous souhaitez enregistrer le HTML généré dans les fichiers de votre thème pour pouvoir versionner le code avec Git.

## Exporter le HTML de la composition depuis Gutenberg

Pour exporter la composition, procédez comme suit :

1. Cliquez sur le menu à 3 points tout en haut de l’éditeur.
2. Sélectionnez **Éditeur de code**.

Votre composition sera maintenant remplacée par le code source HTML généré par Gutenberg. Vous pouvez copier ce code pour l'intégrer à votre thème.

## Créer la composition dans le thème en PHP

Dans votre thème, créez un fichier `presentation.php` dans le dossier `/patterns`. Déclarez des informations sur la composition à l’aide de commentaires PHP :

```php
/**
 * Title: Nom de la composition
 * Slug: slug-de-la-composition
 * Description: Description de la composition
 * Category: slug-de-la-catégorie
 * Keywords: mots-clés
 * Viewport Width: largeur indicative de l’aperçu
 * Block Types: types de blocs spécifiques
 * Post Type: type de publication
 * Inserter: afficher ou non dans l’éditeur
 */
``` 
Ajoutez ensuite le HTML copié depuis Gutenberg à la suite, dans ce fichier PHP.

## Dédoublonner la composition
Si vous retournez en arrière en cliquant sur le logo WordPress en haut à gauche, vous reviendrez dans la rubrique Compositions. Rechargez la page pour voir la composition provenant du fichier de votre thème.

Vous verrez qu’il y a deux versions de la composition : une dans la base de données et une dans le thème. La version du thème ne pourra pas être modifiée, elle sera donc protégée par un cadenas à côté de son nom. Supprimez ensuite la composition enregistrée dans la base de données.

## Utiliser la composition dans l’éditeur
Vous pouvez maintenant utiliser cette composition dans n’importe quelle page, article, type de publication personnalisé, ou modèle de page. Pour l’insérer :

1. Cliquez sur le bouton + pour ajouter un bloc.
2. Allez dans l’onglet Compositions.
3. Sélectionnez la composition et cliquez sur Toutes pour afficher la liste.
4. Cliquez sur votre composition pour l’insérer.

## Modifier une composition
Si vous souhaitez modifier une composition après l’avoir ajoutée, voici la procédure :

1. Dupliquer la composition : Dans Apparence > Éditeur > Compositions, dupliquez la composition en cliquant sur le menu à 3 points et sélectionnez Dupliquer.
2. Réexporter la composition vers PHP : Allez dans l’éditeur de code, copiez le HTML généré et remplacez le code dans votre fichier presentation.php dans le thème. N'oubliez pas de conserver les commentaires PHP.
3. Supprimez ensuite la composition dupliquée depuis l’interface de WordPress.