# Activer/Désactiver fonctionnalités éditeur

## Fonctionnalités globales de l’éditeur

On va commencer par regarder du côté des fonctionnalités globales de l’éditeur dans la rubrique **settings** de notre fichier `theme.json`. Les réglages que l’on va activer s’appliqueront ainsi à la majorité des blocs.

![Theme Json]()

### Activer tous les réglages d’un coup

Cette propriété nous permet d’activer les réglages suivants :

- **Bordure** : couleur, arrondi, style, largeur ;
- **Couleur des liens, titres, légendes et boutons** ;
- **Espacements** : espacement entre les blocs, marges internes et externes ;
- **Typographie** : hauteur de ligne ;
- **Dimensions du bloc** : hauteur et ratio ;
- **Position fixe de l’élément** (sticky) ;

Voici ce que ça donne avec le bloc groupe, avant et après l’activation de ce réglage :

![Exemple activation réglages](image_activation.jpg)

Le souci avec cette approche, c’est que ça active également la personnalisation des valeurs.

---

## Les bordures

Commençons avec les bordures. Vous allez pouvoir activer plusieurs réglages les concernant :

- **color** : La couleur de la bordure ;
- **radius** : Son arrondi ;
- **style** : Le style de bordure (trait, tirets, pointillés) ;
- **width** : Et l’épaisseur du trait.

Voici ces réglages dans le `theme.json` :

Ajoutez un bloc « Groupe » par exemple et allez dans l’onglet des styles du bloc. En bas, vous devriez désormais voir les réglages de bordure :

On peut choisir la couleur, le style et l’épaisseur de bordure, ainsi que le rayon. Les icônes représentant des chaînons permettent de désolidariser les réglages pour chaque côté de votre groupe.

---

## Les couleurs

Passons maintenant aux couleurs. Dans **Apparence > Éditeur > Styles** (le FSE), chaque ligne permet d’activer une option bien particulière :

- **link** : la couleur des liens sur tout le site ;
- **text** : la couleur globale des textes ;
- **background** : la couleur de fond du site ;
- **caption** : la couleur des légendes sous les images et vidéos ;
- **button** : la couleur des boutons principaux ;
- **heading** : la couleur des titres, tous niveaux confondus.

Et voici à quoi ça ressemble dans l’interface lorsque vous activez toutes les options :

Ces couleurs seront appliquées globalement à tous les titres, textes, légendes, boutons… indépendamment qu’ils soient dans des blocs ou non. Bien entendu, on pourra surcharger ces réglages au cœur de nos blocs. Si vous souhaitez appliquer une autre couleur à votre liste par exemple, vous pourrez le faire dans l’éditeur de styles des blocs du FSE.

---

## Les espacements

Les espacements ont toute leur importance avec Gutenberg, et on va pouvoir les régler dans les moindres détails grâce aux options disponibles. Ce sont en général les blocs structurels comme le groupe, la rangée et les colonnes qui vont tirer parti de ces réglages.

Voici à quoi sert chaque propriété :

- **blockGap** : L’espacement entre les blocs enfants ;
- **customSpacingSize** : Donner la possibilité d’indiquer une valeur personnalisée ;
- **defaultSpacingSize** : Utiliser les espacements natifs de WordPress ;
- **margin** : Activer le réglage des marges externes ;
- **padding** : Activer le réglage des marges internes ;
- **units** : Indiquer les unités disponibles dans les options de l’éditeur.

Avec les réglages ci-dessus sur un bloc groupe, voilà ce qu’on obtient :

![Espacement bloc groupe](image_espacement.jpg)

On voit qu’on peut modifier les marges internes horizontalement et verticalement. Le petit carré en haut à droite permet de changer les réglages et modifier par exemple uniquement la marge supérieure.

On peut également modifier l’espacement entre les blocs grâce à `blockGap`. Ce dernier utilise la propriété CSS `margin-block-start`, qui prend en compte la direction d’écriture selon la langue. Ce qui veut dire que ce réglage fonctionnera aussi bien à l’horizontale dans les rangées qu’à la verticale dans les colonnes. De ce fait, on n’a pas besoin de définir des marges extérieures ! C’est pour ça que j’ai passé `margin` à `false`.

---

## La typographie

Les textes ont un rôle très important à jouer dans le web design moderne. C’est pour cela que Gutenberg nous propose beaucoup d’options autour de la typographie. Mais comme d’habitude, on va jouer la retenue pour proposer uniquement les réglages intéressants :

Voici le rôle de chaque propriété :

- **customFontSize** : Définir une taille de texte personnalisée ;
- **defaultFontSizes** : Utiliser les tailles fournies par WordPress ;
- **dropCap** : Activer la lettrine en début de paragraphe ;
- **fontStyle** : Pour passer tout le paragraphe en italique ;
- **fontWeight** : Activer le choix de la graisse, au lieu de simplement gras ;
- **letterSpacing** : Choisir l’espacement entre les lettres ;
- **lineHeight** : Choisir la hauteur de ligne (interlignage) ;
- **textAlign** : Aucun effet ;
- **textColumns** : Aucun effet ;
- **textDecoration** : Mettre le texte en souligné ou barré ;
- **textTransform** : Modifier la casse du texte pour forcer la majuscule ;
- **writingMode** : Passer en écriture verticale ;

Même si on active tout, on va se retrouver avec une interface épurée. Les options seront disponibles dans le menu 3 points en haut à droite de la section de réglages :

Cela permet de se concentrer sur les options dont on a réellement besoin. Si on active tout, on obtiendra ceci :

![Options typographie](image_typographie.jpg)

---

## Les ombres

Vous allez également pouvoir définir des ombres sur vos blocs. Cette fonctionnalité est déjà activée par défaut.

Pour l’instant, il n’y a pas de valeur pour désactiver les ombres. Du coup, il faudra désactiver les réglages par défaut et déclarer une liste vide.

---

## Les images de fond

Le bloc « Groupe » permet de définir une image de fond et de la positionner avec précision grâce à des réglages de taille, si vous activez les options suivantes dans la rubrique **settings > background**.

Des options supplémentaires apparaîtront alors dans l’onglet « Styles » de l’inspecteur du bloc.

---

## La lightbox pour les images

WordPress intègre désormais une lightbox nativement, pour afficher vos images en plus grand lors du clic, sans changer de page. Pour activer la lightbox lors du clic sur une image, il vous suffit de créer un lien et sélectionner **« Agrandir au clic »**.

Si cela ne convient pas, il faudra impérativement appliquer ces réglages dans le bloc image, et pas globalement, c’est pour cela qu’on doit les placer dans **settings > blocks > core/image > lightbox**.

Le premier réglage `enabled`, s’il est passé à `true`, permet d’activer automatiquement l’agrandissement de l’image lorsque vous l’insérez. Le second réglage, `allowEditing`, permet de définir si vous souhaitez afficher le bouton « Agrandir au clic » ou non dans l’interface de Gutenberg.

Dans l’exemple plus haut, j’ai forcé l’agrandissement de toutes les images du site, et j’ai retiré le réglage de l’éditeur de blocs : l’utilisateur ne pourra donc pas désactiver l’agrandissement des images qu’il insère. En général, je préfère ne pas activer l’agrandissement par défaut, et laisser le rédacteur choisir lesquelles agrandir, ce qui donne plutôt :

---

## La position Sticky

Une propriété qui est très cool en CSS, c’est `position: sticky`, qui permet de dire à un bloc de se fixer lors du défilement une fois qu’il atteint le haut de la page. On s’en sert principalement pour coller un menu en haut de notre écran ou encore faire en sorte qu’un sommaire nous suive lors du scroll.

Dans l’interface, l’option est disponible dans « Emplacement » et ressemble à ceci :

![Position Sticky](image_sticky.jpg)

---

## Les dimensions

Il existe également des options de dimensionnement qui seront disponibles sur plusieurs blocs. Aujourd’hui, 3 valeurs sont disponibles :

- **aspectRatio** : Contraindre les images à un certain ratio ;
- **defaultAspectRatios** : activer ou non les ratios de WordPress par défaut ;
- **minHeight** : Activer ou non l’option de hauteur minimale d’un bloc.

### Hauteur minimale pour les groupes

La hauteur minimale de bloc peut être utile si vous souhaitez faire une section (via un bloc groupe) qui prend par exemple 70% de la hauteur du navigateur. C’est souvent utilisé dans le cas du « Hero », cette première zone de la page qui présente le concept.

### Les proportions d’images

Dans le web moderne, on ne s’embête plus à recadrer les images sur Photoshop avant de les envoyer sur notre site : on va pouvoir définir un ratio d’image directement en CSS grâce aux propriétés `aspect-ratio` et `object-fit`. Avec WordPress, on peut activer ou désactiver les options de ratio avec la propriété `aspectRatio` du `theme.json`.

Le ratio est essentiel lorsque vous voulez que les images aient toutes les mêmes proportions, dans une liste d’articles par exemple. Lorsque vous récupérez des photos sur un site comme Unsplash, elles n’auront pas toutes la même taille et le même format. Sans ratio, on voit que les images du blog n’ont pas toutes la même hauteur, et les titres ne sont pas alignés verticalement.

Si vous désirez plus de contrôle sur les options, vous allez pouvoir retirer les ratios proposés nativement par WordPress au profit des vôtres.

---

## Surcharger appearanceTools

Une autre solution serait de passer `appearanceTools` à `true` pour activer toutes les fonctionnalités, et ensuite de surcharger les réglages afin de désactiver ceux que vous ne voulez pas, si ça vous paraît plus simple.

---

## Activer une fonctionnalité uniquement sur certains blocs

### Appliquer couleurs de fond seulement aux groupes

Pour cela, vous pouvez désactiver **background** à partir de **settings > color**, et l’activer dans **settings > blocks > core/group > color**. Cette fois, seul le groupe aura la possibilité de changer de couleur de fond. Les blocs paragraphe et titre, par exemple, ne proposeront plus cette option.

---

## Liste de toutes les propriétés disponibles

Pour plus de détails sur les réglages, consultez la documentation officielle :  
[Propriétés disponibles dans theme.json](https://developer.wordpress.org/themes/global-settings-and-styles/settings/settings-reference/)
