# Configurer les espacements

Dans notre quête d’interpréter notre design system, nous allons continuer à renseigner les informations dans notre fichier `theme.json`, cette fois-ci pour définir les espacements. Ces espacements seront utiles pour créer de l’espace entre les blocs, mais aussi pour ajouter des marges internes à nos sections. Nous allons nous concentrer sur la section **settings > spacing** de notre fichier JSON.

## Définir les espacements

Pour définir les espacements dans l'éditeur, nous allons utiliser la propriété `spacingSizes` dans notre fichier JSON.

### Désactivation des espacements par défaut

Tout d’abord, assurez-vous de définir **defaultSpacingSizes** à `false` afin de retirer les espacements par défaut de WordPress. Sinon, ils vont se cumuler avec les vôtres.

### Définition des valeurs d’espacement

Dans `spacingSizes`, vous devez définir pour chaque valeur :
- **name** : Le nom affiché dans l’interface ;
- **slug** : Un identifiant unique pour chaque espacement ;
- **size** : La taille sous forme de valeur en CSS.

Gardez une nomenclature cohérente entre tous vos projets, par exemple : `xs`, `s`, `m`, `l`, `xl`, `xxl`, qui est un nommage court, simple et facile à retenir.

### Résultat dans l’éditeur

Dans l’éditeur, lorsque vous insérez un bloc "Groupe" et que vous ajustez les marges ou l’espacement des blocs :
- Si vous avez défini 7 valeurs ou moins, vous aurez une interface avec une glissière crantée de type `range`.
- Si vous avez défini plus de 7 valeurs, vous aurez un menu déroulant de type `select`.

---

## Désynchroniser les réglages de marge

Par défaut, WordPress propose des réglages de marges groupés : haut/bas et gauche/droite, qui sont le cas d’usage le plus courant. Si vous avez besoin de modifier un côté spécifique, vous pouvez cliquer sur l’icône carrée à droite de l’interface pour désynchroniser les marges et choisir les côtés indépendamment.

---

## Espacements dynamiques avec CSS `clamp()`, `min()` et `max()`

Comme il est possible d’utiliser n’importe quelle valeur CSS valide dans la propriété `spacingSizes` de notre JSON, rien ne nous empêche d'utiliser des fonctions CSS modernes comme `clamp()`, `min()` ou `max()`.

### La fonction CSS `clamp()`

La fonction `clamp()` permet d’adapter l’espacement en fonction de la taille de l’écran, évitant ainsi l’utilisation excessive de media queries CSS.

Elle fonctionne avec 3 paramètres :
1. La taille minimale (par exemple `1rem`) ;
2. La taille dynamique (par exemple `4vw` pour 4% de la largeur de l'écran) ;
3. La taille maximale (par exemple `2rem`).

Cela signifie que l’espacement sera compris entre 1rem et 2rem, mais pourra s’ajuster en fonction de la largeur du viewport.

### Les fonctions CSS `min()` et `max()`

- La fonction `min()` permet de prendre la plus petite valeur parmi plusieurs paramètres.
- La fonction `max()` permet de prendre la valeur la plus élevée parmi les paramètres.

Ces fonctions permettent de garantir des espacements flexibles qui s’adaptent à la taille de l’écran.

---

## Définir une échelle d’espacements

Au lieu de définir chaque valeur d’espacement manuellement avec `spacingSizes`, vous pouvez créer une échelle automatique avec la propriété `spacingScale`. Voici les paramètres que vous devrez définir :
- **steps** : Nombre de tailles différentes (par exemple 5 tailles) ;
- **increment** : Espacement entre chaque taille (par exemple `1rem`) ;
- **mediumStep** : La taille de base (par exemple `2rem`) ;
- **operator** : L’opération à utiliser entre les étapes (par exemple, addition ou multiplication) ;
- **unit** : L’unité CSS utilisée (par exemple `rem`).

En utilisant l’opérateur `*` pour `operator`, les espacements vont grandir proportionnellement.

---

## Réglages d’espacement dans l’éditeur de blocs

Nous avons déjà abordé ces réglages dans le cours sur les fonctionnalités de l’éditeur. L'objectif est de définir les options d'espacement dans l’éditeur de blocs :

### Recommandations :
- **Activez l’espacement entre les blocs**, car c'est essentiel pour la création de vos designs.
- **Activez les marges internes**, nécessaires pour l’intérieur de vos sections, notamment avec le bloc "Groupe".
- **Désactivez les marges externes** : avec l’espacement des blocs, ces marges externes ne sont normalement pas nécessaires, sauf dans des cas exceptionnels.

### Propriétés à configurer :
- **blockGap** : Activez l’espacement entre les blocs enfants ;
- **customSpacingSize** : Permet d’indiquer une valeur personnalisée ;
- **defaultSpacingSizes** : Utiliser les espacements natifs de WordPress ;
- **margin** : Activez les marges externes ;
- **padding** : Activez les marges internes ;
- **units** : Spécifiez les unités disponibles dans l’éditeur.

Je recommande également de désactiver les valeurs d’espacement personnalisées. De cette manière, les utilisateurs devront choisir parmi les valeurs définies et ne pourront plus activer la personnalisation des valeurs.

Enfin, ne gardez que les unités dont vous aurez besoin (par exemple `px`, `%` et `rem`).

---

## Supprimer les marges entre les sections

Lorsqu’on ajoute deux sections à la suite dans WordPress, un espace blanc apparaît entre elles, car WordPress applique par défaut un espacement entre tous les blocs. 

Nous avons vu que cet espacement peut être modifié dans **Apparence > Éditeur > Styles > Mise en page**. Mais l’objectif ici est de le supprimer directement via `theme.json`.

### Suppression des espaces dans `theme.json`

Allez dans la sous-rubrique **styles** du fichier `theme.json`. Cette sous-rubrique permet de configurer les valeurs par défaut pour les éléments et blocs dans l'éditeur.

- Pour le bloc "Groupe", vous pouvez spécifier que vous ne voulez pas d’espace entre les blocs. Utilisez la propriété `margin` et définissez la valeur de `top` à `0` :

```json
{
  "styles": {
    "core/group": {
      "margin": {
        "top": "0 !important"
      }
    }
  }
}
```

Désormais, lorsque vous ajouterez deux blocs "Groupe", ils seront collés l’un à l’autre. Les autres blocs continueront d’avoir leurs espacements par défaut.