# L’Auto Layout dans Figma

## Introduction

Dans le web design, **l’organisation des éléments** (empilement vertical ou horizontal) est essentielle. Cependant, avec les outils de design classiques, il fallait positionner manuellement chaque élément. Cela rendait les modifications complexes et fastidieuses.

Figma révolutionne cette pratique grâce à son outil **Auto Layout**, qui permet de structurer automatiquement des éléments dans un conteneur parent. Ce système est extrêmement puissant et pratique.

---

## Fonctionnement de l’Auto Layout

### Principe de Base

1. **Activation** : L’Auto Layout est activé sur une couche parent.
2. **Alignement** : Les éléments enfants sont automatiquement alignés selon les paramètres définis (vertical ou horizontal).
3. **Espacement automatique** : Un espacement homogène peut être configuré entre les éléments.

#### Illustration : Alignement Vertical

Voici un exemple où des blocs sont alignés verticalement grâce à l’Auto Layout :

![L’auto layout de Figma qui permet aux éléments de s’empiler](/grimoire/img/auto-layout-figma.jpg.avif)

---

## Avantages de l’Auto Layout

### Espacement Dynamique

L’Auto Layout permet de configurer automatiquement des **espacements constants** entre les éléments enfants. Cela garantit une structure uniforme et une mise à jour rapide en cas de changement.

### Gestion Dynamique des Modifications

Imaginez que, après avoir terminé une page, votre client demande d’ajouter une section tout en haut :
- Avec un positionnement manuel, vous devez **tout décaler manuellement**, ce qui est chronophage.
- Avec **l’Auto Layout**, il suffit d’ajouter la nouvelle section : tous les éléments se décaleront automatiquement.

---

## Configuration de l’Auto Layout

### Exemple de Réglages

Dans l’exemple ci-dessous, voici les paramètres définis :
- **Alignement Vertical** : Les éléments s’empilent de haut en bas.
- **Espacement entre éléments** : 20 pixels.
- **Marges internes** : 30 pixels entre les bords du conteneur parent et les éléments enfants.

#### Illustration : Réglages Auto Layout

![Les réglages de l'Auto layout de Figma qui montre un alignement vertical et des espacements](/grimoire/img/figma-auto-layout-settings.jpg.avif)

---

## Réglages Spécifiques

### Largeur des Éléments

Pour que les sections grises occupent toute la largeur disponible dans le conteneur :
- Réglez la **largeur** des éléments sur **Fill** (remplir l’espace horizontal).
- Ce paramètre s’adapte automatiquement à la taille du conteneur, au lieu d’utiliser une valeur fixe en pixels.

#### Illustration : Réglage de Largeur

![Le réglage Fill est appliqué à la largeur de l’élément](/grimoire/img/figma-auto-layout-vertical.jpg.avif)

### Marges Internes et Alignement

En combinant les paramètres suivants :
- **Espacement uniforme** : Espaces réguliers entre chaque élément.
- **Marges internes** : Distance entre les bords du conteneur parent et les enfants.
- **Alignement** : Les éléments peuvent être alignés à gauche, à droite, ou centrés.

Ces paramètres offrent une flexibilité optimale.

---

## L’Auto Layout et le Développement Web

Figma s’adapte de près aux contraintes du HTML, ce qui facilite le dialogue entre designers et développeurs :
- **Structure proche du DOM** : Les conteneurs avec Auto Layout fonctionnent comme des **divs** avec des propriétés CSS (flexbox ou grid).
- **Gain de temps** : Les développeurs peuvent traduire les designs en code plus rapidement, avec moins d’ajustements.

---

## Conclusion

### À Retenir

1. **L’Auto Layout** permet de structurer efficacement vos designs en automatisant l’alignement et l’espacement des éléments.
2. **Dynamique et flexible**, il facilite les modifications en cascade, même après la conception initiale.
3. **Optimisation pour le web** : Son fonctionnement proche du HTML en fait un excellent outil pour une collaboration fluide entre designers et développeurs.

Grâce à l’Auto Layout, vous gagnez du temps, améliorez la qualité de vos designs, et facilitez le passage du design au développement.
