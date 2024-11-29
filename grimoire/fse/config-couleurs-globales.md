# Configurer les couleurs globales de la charte graphique

Nous allons maintenant commencer à intégrer la charte graphique dans notre site WordPress. Pour cela, nous allons définir nos couleurs à l’aide du fichier `theme.json` dans la section **settings > color**. Voici un aperçu des propriétés disponibles :

## La palette de couleurs

Commençons par la palette, qui est la plus importante. Il existe 3 types de couleurs que nous pouvons définir :
1. **Les couleurs classiques**, les plus importantes ;
2. **Les dégradés**, si besoin ;
3. **Les duotones**, qui permettent d’appliquer un filtre bicolore sur les images.

### Déclaration des couleurs dans le JSON

Voici comment déclarer chaque couleur de notre palette dans le fichier JSON. Vous devez indiquer 3 informations pour chaque couleur :
- **name** : Le nom qui sera affiché dans l’interface ;
- **slug** : Le slug unique qui représente la couleur ;
- **color** : La valeur de la couleur, généralement en hexadécimal.

Vous pouvez également déclarer une couche d’opacité hexadécimale en ajoutant la valeur d’opacité à la fin de la couleur. Par exemple, `#2f1847` deviendrait `#2f1847cc`.

### Exemple de palette de couleurs

Voici à quoi ressemblera votre palette de couleurs. Vous pourrez voir vos couleurs dans la rubrique « Thème » de l’interface WordPress.

Il est essentiel de définir une charte de nommage et de s’y tenir. Par exemple :
- Le thème **2024** de WordPress utilise : `base / base-2 / contrast / accent` ;
- Le thème **Ollie** utilise : `primary / primary-accent / secondary / tertiary`.

Cela vous assurera que vos compositions adopteront automatiquement les couleurs de la charte graphique sur tous vos sites.

---

## Les dégradés

Comme pour les couleurs, vous pouvez également déclarer des dégradés dans votre thème. Ces dégradés peuvent contenir 2 couleurs ou plus. Pour cela, vous utiliserez la propriété **gradients** dans la rubrique **settings**.

### Déclaration des dégradés dans le JSON

Pour chaque dégradé, vous devrez définir un **nom** et un **slug** qui sera l’identifiant unique du dégradé. Ensuite, dans la propriété **gradient**, vous indiquerez le CSS du dégradé souhaité. Vous pouvez utiliser un générateur de dégradés CSS pour vous simplifier la tâche, car la syntaxe n’est pas toujours évidente.

Vous pourrez appliquer des dégradés linéaires, circulaires ou coniques, compatibles avec la syntaxe CSS.

---

## Les filtres d’images duotone

Le **duotone** est un filtre CSS appliqué sur une image qui lui donne un rendu en deux tons. Vous pouvez déclarer vos propres duotones bicolores à l’aide de la propriété **duotone**.

---

## Activer / désactiver les couleurs globales

Comme vu dans le cours sur les fonctionnalités de Gutenberg, l’éditeur de thème permet de configurer les couleurs globales de divers éléments primitifs du site dans **Apparence > Éditeur > Styles**. Les couleurs des textes, des liens, des légendes, des boutons, du fond du site et des titres peuvent être configurées globalement, avant même les blocs.

Si vous souhaitez désactiver la possibilité de modifier certains de ces éléments, vous pouvez les désactiver à partir du fichier `theme.json`.

---

## Personnaliser les options de la palette de couleurs

Vous pouvez affiner l'expérience utilisateur en personnalisant les options de la palette. Voici le rôle de chaque propriété :

- **custom** : Désactive le choix d’une couleur personnalisée ;
- **customDuotone** : Désactive le choix d’un duotone personnalisé ;
- **customGradient** : Désactive le choix d’un dégradé personnalisé ;
- **defaultDuotone** : Désactive les duotones par défaut ;
- **defaultGradients** : Désactive les dégradés par défaut ;
- **defaultPalette** : Désactive les couleurs par défaut.

Si vous définissez **custom** et **defaultPalette** à `false`, vous obtiendrez une version minimaliste de la palette. Cela permet à votre utilisateur d'appliquer uniquement les couleurs de la charte graphique.

De la même manière, vous pouvez désactiver les dégradés et duotones par défaut :
- **customGradient** et **defaultGradients** à `false` pour ne garder que les dégradés définis dans votre charte graphique ;
- **customDuotone** et **defaultDuotone** à `false` pour conserver uniquement les duotones définis par votre charte.

---

## Désactiver les dégradés et duotones

Si vous souhaitez désactiver complètement les dégradés et duotones de votre site, vous pouvez :
- Retirer la personnalisation des duotones et dégradés ;
- Retirer les dégradés et duotones par défaut ;
- Ne pas déclarer de dégradé ou duotone, ou omettre la ligne correspondante.

---

## Modifier les couleurs dans l’éditeur de styles

Une fois que vous avez défini vos couleurs, dégradés et duotones dans le fichier `theme.json`, vous pourrez les retrouver dans l’éditeur de styles du **Full Site Editing** (FSE).

Pour cela, rendez-vous dans **Apparence > Éditeur > Styles**. Vous pourrez voir les couleurs de votre palette sur la droite de l’interface. En cliquant sur l’icône en forme d'œil en haut à droite, vous pourrez afficher le guide de style et observer le rendu de chacun des blocs de l’éditeur.

Attention : dans cette interface, vous pourrez ajouter de nouvelles couleurs. Cependant, cela n’ajoutera pas ces couleurs au fichier `theme.json`, mais dans la base de données WordPress. Cela peut poser un problème si vous souhaitez garder un contrôle strict sur les couleurs disponibles. Vous devrez décider si vous souhaitez donner l'accès au Full Site Editing à vos clients ou leur permettre uniquement d'éditer les contenus (pages, articles).

Si vous souhaitez limiter l’accès de votre client, vous pouvez lui attribuer le rôle « éditeur » plutôt que « administrateur », ou créer un rôle sur mesure avec les permissions appropriées (par exemple, en définissant la capacité **edit_theme_options** à `false`).
