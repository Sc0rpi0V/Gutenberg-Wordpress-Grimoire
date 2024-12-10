
# Les compositions des boucles de requête

La **boucle de requête** est un bloc permettant d’afficher une liste d’articles, similaire à la WP Query de WordPress, mais sans code. Ce bloc est extrêmement personnalisable grâce aux nombreux sous-blocs qui y sont intégrés. Il permet de créer des compositions avec une mise en page variée, très utile pour les **Custom Post Types** ou des modèles d'articles spécifiques.

## Créer des compositions de boucles de requête

### 1. Créer une première composition (vue en grille)

Pour commencer, créons une composition en utilisant la boucle de requête. Voici les étapes pour réaliser une vue en grille des articles :
1. Insérer un **bloc "Groupe"** en pleine largeur.
2. Définir une couleur de fond blanche et appliquer des marges internes.
3. Ajouter un **bloc "Titre"** de niveau 2 : **Mes dernières actualités**.
4. Insérer un **bloc "Boucle de requête"** et sélectionner l'option **"partir de zéro"**.
5. Sélectionner le modèle de base : **image**, **date** et **titre**.
6. Appliquer la largeur "large" (wide) au bloc **Boucle de requête**.
7. Dans le bloc "Modèle de publication", choisir l'option **vue grille** et sélectionner **2 colonnes**.
8. Regrouper les éléments (titre, date, extrait) dans un **groupe** pour appliquer un fond blanc.
9. Appliquer des arrondis autour des éléments, mais sans marge interne.
10. Appliquer des marges au groupe contenant les éléments (titre, date, extrait) pour éloigner le contenu des bords.
11. Appliquer des arrondis à l’image uniquement en haut.

> **Note** : Un petit souci : les groupes à fond blanc n’auront pas tous la même hauteur. Une solution temporaire serait d’ajouter une variation de styles en CSS pur pour uniformiser la hauteur des blocs.

Une fois cette composition créée, elle peut être exportée dans le fichier `/patterns/post-grid.php`. La seule différence avec ce que l’on a déjà vu est l’ajout de la propriété `Block Types` qui permet d'indiquer que cette composition est disponible uniquement pour le bloc **core/query**.

### 2. Créer une seconde composition (vue verticale)

Maintenant, créons une seconde composition avec un affichage **vertical**. Voici les étapes :
1. Laisser la vue en **liste** dans le bloc **"Modèle de publication"**.
2. Utiliser le **bloc "Média & texte"** pour afficher l'image et le texte côte à côte.
   - L'avantage de ce bloc est que l'image peut occuper toute la hauteur, contrairement à une construction avec des colonnes classiques.
   - Il permet aussi d’afficher l’image mise en avant plutôt qu’une image statique depuis la médiathèque.

Cette composition sera enregistrée dans le fichier `/patterns/posts-list.php`.

### 3. Ajouter une composition à la boucle de requête

Une fois vos compositions créées, vous pouvez les insérer dans vos pages via le bloc **boucle de requête**. Voici comment procéder :
1. Lorsque vous insérez un bloc **boucle de requête** sur votre site, vous avez deux options :
   - **Partir de zéro** (création manuelle).
   - **Choisir une composition**.
2. Si vous cliquez sur **"Choisir"**, une liste des compositions compatibles apparaît.
3. Vous pouvez alors choisir entre les deux compositions que vous avez créées : une **vue en grille** et une **vue en liste**.
4. Après avoir sélectionné une composition, celle-ci est importée d’un seul clic, et votre boucle de requête affichera automatiquement les publications.

### 4. Inverser l'approche

Il est aussi possible de procéder dans l'autre sens : vous pouvez insérer directement une composition dans votre page, sans passer d'abord par le bloc **boucle de requête**. Cette méthode fonctionne également parfaitement et vous permet d'ajouter vos modèles de contenu avec facilité.

> **Astuce** : En utilisant la fonctionnalité de composition, vous pouvez personnaliser l’affichage de vos publications de manière flexible et rapide, sans avoir besoin de recourir au code.

---
## Conclusion

Les boucles de requête permettent une grande flexibilité dans l'affichage des articles. Que vous choisissiez un affichage en grille ou en liste, vous pouvez facilement adapter la présentation de vos publications. En combinant différents sous-blocs et personnalisations, vous pourrez créer des compositions uniques et professionnelles pour votre site.