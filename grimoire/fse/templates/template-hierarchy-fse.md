# Le Template Hierarchy à l’heure du Full Site Editing

Nous allons maintenant attaquer la quatrième étape du Full Site Editing, et c’est ici que notre site va enfin commencer à prendre vie ! Après avoir configuré le `theme.json`, déclaré nos variations de styles de blocs, et créé nos compositions, on va désormais passer à la conception des principaux modèles de pages qui composent notre site. À l’issue de ce chapitre, on aura un site digne de ce nom, quasiment prêt à l’emploi !

## Introduction au Template Hierarchy de WordPress

### Qu'est-ce que le Template Hierarchy ?

Le **Template Hierarchy** de WordPress est un système qui détermine quel modèle de page WordPress doit afficher en fonction de l'URL demandée. Voici les étapes basiques :
- **Page d’accueil** ? `front-page.php`
- **Page standard** ? `page.php`
- **Blog** ? `home.php`
- **Archive** ? `archive.php`
- **Article unique** ? `single.php`

Bien que le système soit simple, des cas plus spécifiques existent, comme les archives d'un **Custom Post Type** ou les pages d'un **Auteur**. Par exemple :
- **Portfolio** : `archive-portfolio.php`
- **Auteur** : `author.php`

Les modèles spécifiques sont recherchés avant les modèles généraux (ex. : `archive.php`).

### Différence fondamentale pour le FSE

Le Full Site Editing (FSE) ne change pas la hiérarchie de base, mais la méthode de création de modèles. Plutôt que d'utiliser des fichiers PHP pour chaque modèle, vous allez utiliser des fichiers **HTML**. Ces fichiers devront être placés dans le dossier `templates` de votre thème, au lieu de la racine.

#### Exemple d'architecture des fichiers avec et sans FSE :

- **Thème classique** :

- front-page.php
- page.php
- single.php
- archive.php

- **Thème avec FSE** :

- templates/
    - front-page.html
    - page.html
    - single.html
    - archive.html


## Les principaux modèles de pages en FSE

### Page d’accueil
La page d’accueil est souvent utilisée pour mettre en avant les avantages du produit ou du service. En FSE, vous n'avez plus besoin de créer un modèle de page spécifique pour la page d’accueil. Le modèle **`front-page.html`** est optionnel et peut être remplacé par le modèle standard du site, conçu via l'éditeur de blocs.

### Pages de contenu
Les pages classiques de contenu utilisent le modèle **`page.html`**. Ce modèle est assez simple, et pour les pages de contenu standard, vous pouvez utiliser ce modèle en personnalisant l’en-tête, le pied de page et la zone centrale pour afficher le contenu.

### Pages du blog

#### Archives
Les pages d'archives affichent une liste de publications. Vous aurez principalement le modèle **`archive.html`**, que ce soit pour des archives générales, par catégorie, par étiquette, ou par auteur.

- Exemple : `archive-author.html` pour afficher les publications d'un auteur avec un design spécifique.
- Par défaut, **`archive.html`** sera suffisant pour de nombreux projets.

#### Page d’accueil du blog
Le modèle **`home.html`** est utilisé pour la page d’accueil du blog, qui est généralement plus détaillée que les autres archives. Cette page peut afficher les derniers articles, un article mis en avant, etc.

#### Publication
Le modèle **`single.html`** est utilisé pour afficher les articles individuels.

### Autres pages importantes

#### Page de recherche
Le modèle **`search.html`** est utilisé pour afficher les résultats de recherche. Ce modèle est également personnalisé via l’éditeur de blocs avec le bloc **`Boucle de requête`**.

#### Page 404
La page d'erreur 404 est définie par le modèle **`404.html`**, qui affiche un message d'erreur personnalisé. Cette page est désormais éditable visuellement grâce au FSE.

#### Page index
Le modèle **`index.html`** sert de modèle de secours si WordPress ne trouve pas un modèle plus spécifique à l'URL demandée. C'est le modèle obligatoire dans votre thème, et il peut être utilisé pour des sites très simples (par exemple, un site one-page).

## Template Hierarchy optimisé pour FSE

Avec le FSE, certains chemins et modèles de page deviennent obsolètes et peuvent être supprimés. Voici un schéma simplifié pour le FSE :

### Schéma simplifié pour FSE



### Retirer les modèles superflus

L'ancien système PHP permettait de créer des modèles de pages personnalisés (par exemple `page-<nom>.php`). Aujourd’hui, vous pouvez nommer vos modèles comme vous le souhaitez, tant qu'ils sont dans le dossier **`templates`**. Vous pouvez aussi les déclarer dans le fichier `theme.json` pour les associer à des types de pages spécifiques.

#### Modèle sur-mesure pour la page d’accueil
Plutôt que de créer un modèle spécifique pour la page d’accueil, vous pouvez réutiliser **`page-full-width.html`** pour obtenir une page pleine largeur.

### Création des modèles dans votre thème

Dans votre thème, créez les fichiers suivants :

- **`index.html`** : Modèle de secours obligatoire.
- **`archive.html`** et **`home.html`** pour le blog.
- **`single.html`** pour les articles.
- **`page.html`** et **`page-full-width.html`** pour les pages standard.
- **`404.html`** pour la page d’erreur.
- **`search.html`** pour la page de recherche.

Ces fichiers doivent être placés dans le dossier **`templates`** de votre thème. Voici un exemple d’arborescence de votre thème :

- templates/
    - index.html
    - archive.html
    - home.html
    - single.html
    - page.html
    - page-full-width.html
    - 404.html
    - search.html