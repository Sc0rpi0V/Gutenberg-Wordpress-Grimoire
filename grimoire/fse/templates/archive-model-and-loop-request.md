# Les modèles d’archives et le bloc "boucle de requête" dans WordPress

## Introduction

WordPress propose plusieurs façons d’afficher des listes d'articles sur votre site, en fonction de critères spécifiques :

- **Par ordre chronologique** : Exemple typique de la page d’accueil du blog.
- **Par catégorie** : Afficher uniquement les articles d’une certaine catégorie.
- **Par étiquette** : Afficher les articles avec une étiquette particulière.
- **Par auteur** : Afficher uniquement les articles d’un auteur donné.
- **Autres types de publications et taxonomies** : Vous pouvez créer des modèles spécifiques pour ces cas. Nous aborderons ces points dans un prochain cours.

### Configuration du nombre d'articles par page

Par défaut, WordPress affiche 10 articles par page. Pour modifier ce nombre, allez dans **Réglages > Lecture** et ajustez la valeur du champ « Les pages du site doivent afficher au plus ».

---

## Rôle du modèle Archive

Le modèle `archive.html` est un modèle principal du blog dans WordPress. Il permet de traiter les différents cas d’affichage des articles mentionnés plus haut. Ce modèle est observé dans la **template hierarchy** (hiérarchie des modèles).

- **Cas d’usage** : Si vous n’avez pas besoin de designs spécifiques pour chaque type de contenu, ce modèle unique suffira.
- **Compatibilité** : Il est également utilisé pour tous les **Custom Post Types (CPT)** que vous avez déclarés sur votre site. Si vous avez des types de contenu différents comme un blog et un portfolio, il peut être utile de créer des modèles différents pour ces types.
- **Rôle des fichiers home.html et archive.html** : Les fichiers `home.html` et `archive.html` jouent un rôle similaire, mais vous pourriez vouloir des designs différents pour la page d’accueil du blog et les autres pages d'archives. Nous aborderons cela dans un prochain chapitre.

---

## Concevoir le modèle avec la boucle de requête

1. Rendez-vous dans **Apparence > Éditeur > Modèles** et sélectionnez le modèle vide nommé « Toutes les archives ».
2. Cliquez dessus pour le modifier.

### La boucle de requête

Le bloc **"Boucle de requête"** est essentiel dans ce modèle. Il permet de récupérer et afficher les publications sous forme de liste.

#### Sélection du type de requête

- Dans l’inspecteur à droite, vérifiez que l’option « Type de requête » est définie sur « Par défaut ». Cela permet à WordPress de charger les publications en fonction de l’URL de la page.
- Si vous choisissez l’option **"Personnalisée"**, vous pouvez créer une seconde boucle de requête sur la même page.

**Note** : Depuis WordPress 6.7, sur certains modèles de page, le bloc "boucle de requête" passe automatiquement en mode personnalisé. Vous aurez alors plusieurs options et filtres pour personnaliser les résultats.

---

## Gérer les blocs enfants de la boucle de requête

Les blocs enfants sont des éléments placés à l'intérieur de la boucle de requête. Voici trois éléments principaux à gérer :

1. **Le modèle de publication** : Affiche la liste des articles.
2. **La pagination** : Permet de naviguer entre les pages.
3. **Le message Aucun résultat** : Affiche un message lorsque aucun article n’est trouvé.

Bien que seuls les blocs nécessaires à la boucle doivent être utilisés, vous pouvez ajouter d'autres blocs pour améliorer la mise en page.

### Exemple de blocs dynamiques

Dans le **modèle de publication**, vous pouvez insérer des blocs dynamiques comme :

- **Titre de la publication**
- **Catégories**
- **Bouton "Lire la suite"**
- **Image mise en avant**

---

## Exporter le modèle vers le thème

Pour exporter votre modèle, suivez ces étapes :

1. Cliquez sur les 3 points en haut à droite de l’éditeur.
2. Passez en vue « **Éditeur de code** ».
3. Copiez le HTML généré.
4. Collez-le dans les fichiers `/templates/archive.html` et `/templates/home.html`.
5. Réinitialisez le modèle dans Gutenberg depuis l’interface des modèles.

### Pourquoi ces deux fichiers sont importants

Il est essentiel d'avoir à la fois `home.html` et `archive.html` pour un bon fonctionnement de votre blog.

---

## Configurer la page d’accueil du site et du blog

Si votre blog n’est pas destiné à être la page d’accueil de votre site, vous devrez créer deux pages dans WordPress : **"Accueil"** et **"Blog"**.

Allez dans **Réglages > Lecture** et attribuez chacune de ces pages aux rôles appropriés.

---

## Autres modèles d’archives

Dans la **template hierarchy**, plusieurs modèles peuvent être utilisés en fonction du type de page :

- **home.html** : Utilisé uniquement pour la page d’accueil du blog.
- **archive.html** : Affiche les articles chronologiquement, page après page.
- **date.html** : Filtre par date de publication (utilisé par le widget calendrier).
- **category.html** : Affiche les articles d’une catégorie spécifique.
- **tag.html** : Affiche les articles d’une étiquette spécifique.
- **author.html** : Affiche les articles d’un auteur particulier.

### Personnalisation des modèles d’archives

- **Category model** : Il est rare mais possible de créer des modèles de page spécifiques pour des catégories particulières (par exemple, `category-promotions.html`).
- **Modèle auteur** : Ce modèle peut être utile sur un blog avec plusieurs rédacteurs. Vous pourriez ajouter une section pour présenter l’auteur avec des blocs dédiés.

---

## Différence entre `archive.html` et `home.html`

- **home.html** : Utilisé uniquement pour la page d’accueil du blog. Il met généralement en avant un article ainsi qu’un appel à l’action.
- **archive.html** : Utilisé pour les pages d’archives, comme la page 2 et au-delà, des articles du blog. Ce modèle n'affichera pas d’article en avant comme la page d’accueil.

### Epingler un article

Si vous souhaitez afficher un article épinglé sur la page d’accueil, suivez ces étapes :

1. Sélectionnez l’article à épingler dans l’interface d’édition.
2. Dans la boucle personnalisée, sélectionnez **"Publications épinglées"** et définissez la valeur sur **"Uniquement"** pour que cet article soit mis en avant.

### Alternative sans épingler d’articles

Une autre solution consiste à utiliser deux boucles personnalisées :

- La première boucle n’affichera que le premier article.
- La seconde boucle commencera à partir du second article (en ajustant l'offset).

---