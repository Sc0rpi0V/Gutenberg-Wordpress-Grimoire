# Présentation du theme.json

La création d’un site avec le Full Site Editing commence avec le `theme.json`, du moins pour les développeurs et les low-codeurs. Ce fichier vous permet de déclarer un bon nombre d’informations comme les couleurs, espacements, tailles, typos… à propos de votre thème à l’aide de clés et valeurs. On retrouve en substance tous les réglages que l’on peut faire via l’éditeur de site.

Voici un exemple avec le réglage de largeur des contenus. Depuis l’éditeur, cela ressemble à ceci :

![Exemple largeur contenu](image_exemple.jpg)

---

# Anatomie du theme.json

On va comprendre la structure globale du fichier. Si je me cantonne uniquement aux éléments de premier niveau, on obtient ceci :

- **$schema** : C’est la nomenclature qui contraint les valeurs possibles du fichier ;
- **version** : Le numéro de version du schéma ;
- **settings** : Ici on va définir nos valeurs globales et les fonctionnalités de l’éditeur ;
- **styles** : Pour appliquer nos styles par défaut aux titres, textes, et blocs ;
- **customTemplates** : Pour déclarer des modèles sur-mesure en plus des existants ;
- **templateParts** : Nous permet de déclarer l’en-tête, le pied de page et la sidebar ;
- **patterns** : Ajouter des compositions du répertoire officiel de WordPress.

[Doc officielle theme.json](https://developer.wordpress.org/themes/global-settings-and-styles/)

---

# Les différentes sections du theme.json

## Schéma

On commence avec le schéma. On va systématiquement le mettre dans notre fichier car ça permettra à notre éditeur de code de vérifier que ce que l’on écrira par la suite sera conforme à ce schéma.

**Notice** : L’éditeur de code sera capable de vous suggérer les valeurs possibles lors de l’écriture du fichier. C’est encore plus pratique pour ne pas se tromper.

---

## Settings

Cette partie est probablement la plus importante de ce `theme.json`, car c’est ici qu’on va configurer les 2 choses les plus importantes pour notre site :

1. **Les styles globaux** tout d’abord : couleurs, typographies, espacements…
2. **Les fonctionnalités à activer ou désactiver dans Gutenberg.**

Comme vous pouvez le voir, sous **color** on va avoir des instructions booléennes permettant d’activer ou de désactiver les options de couleur dans l’éditeur Gutenberg. Ensuite, on déclare la liste des couleurs de la palette que l’on va proposer sur le site.

Voici ce que ça donnera dans l’éditeur de WordPress :

![Exemple de couleur](image_couleur.jpg)

À gauche, c’est si je passe toutes les valeurs à `true`, et à droite, si je passe tout à `false`. C’est un bel exemple du contrôle qu’on peut avoir sur Gutenberg, n’est-ce pas ?

---

## Styles

Les éléments de notre charte graphique que nous avons configurés dans **settings** seront disponibles dans l’éditeur. Mais on va également pouvoir appliquer ces styles globalement aux différents éléments du site grâce à la section **styles** du fichier JSON.

Voici à quoi ça ressemble :

Chaque section permet de définir un élément bien précis :

- **color** : Les couleurs des textes, liens, du fond ;
- **spacing** : L’espacement par défaut entre les blocs, et dans les blocs ;
- **typography** : La police des titres et celle des textes ;
- **elements** : Les styles des éléments primitifs : boutons, niveaux de titres, survol ;
- **blocks** : Les styles par défaut à appliquer pour chaque bloc de l’éditeur.

Les valeurs qu’on a définies précédemment sont désormais disponibles au travers de variables CSS, avec des noms parfois un peu longs. Voici un exemple avec les couleurs globales du site :

Dans cet exemple, on applique notre couleur primaire à tous les textes, et la couleur blanche sur le fond du site. Ce ne sera donc pas nécessaire de le faire en CSS. Si on veut maintenant définir une couleur spécifique à la balise `<h2>`, ce sera dans **elements > h2 > color**.

---

## Nommage des valeurs globales CSS dans theme.json

Voici l’anatomie d’une valeur générée par WordPress :

var:preset|color|primary

Décortiquons ce nommage bien singulier :

- La première partie `var:` indique qu’on souhaite utiliser une valeur globale ;
- La seconde partie représente le **type**, il peut être `preset` ou `custom` ;
- La troisième représente la **propriété** : `color`, `font-size`, `spacing…` ;
- Et la dernière partie représente la **valeur configurée en JSON** : `primary`, `s`, `m…`.

---

## Custom Templates

Désormais, les modèles de page sur-mesure devront être déclarés dans le `theme.json`, sous la section **customTemplates**.

Un exemple récurrent est de créer un modèle de page en pleine largeur, sans le titre principal, pour créer toutes vos landing pages du site. Le modèle de page « standard » pourra être réservé aux pages de contenus comme les mentions légales, avec le titre et une zone de contenu étroite.

---

## Template Parts

Les **template parts** sont des morceaux de template, destinés à être réutilisés sur le site. Mais outre l’en-tête, le pied de page et éventuellement une sidebar, on va plutôt désormais utiliser les **compositions**.

---

## Patterns

Et enfin, cette section permet de déclarer les compositions que l’on veut récupérer depuis wp.org. En effet, il existe un répertoire de compositions créées par la communauté, un peu comme le répertoire des extensions. Il suffit de récupérer le **slug** de chaque composition depuis l’URL et de les ajouter à votre fichier JSON.

---

# Configuration via l’éditeur de WordPress et export

L’éditeur de WordPress permet de gérer visuellement la plupart de ces réglages. Vous pourriez donc, au lieu d’écrire le JSON, passer par l’interface du Full Site Editing.

## Limites de l’éditeur visuel

Par contre, en utilisant l’éditeur, vous n’aurez pas autant de possibilités qu’en modifiant le JSON. Il manque notamment :

- L’activation et la désactivation de réglages et de fonctionnalités de l’éditeur.
- La gestion des espacements.
- La gestion de valeurs personnalisées, comme les arrondis.

Il y a quelques temps, il manquait la gestion des ombres, mais elle a été ajoutée avec l’arrivée de WordPress 6.6. Dans un futur proche, il ne manquera probablement plus rien. Mais pour le moment, on est encore obligé de passer par le `theme.json`.
