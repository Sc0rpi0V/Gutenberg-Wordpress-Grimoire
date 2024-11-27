# L’Alignement Automatique Horizontal dans Figma

## Introduction

En design, l’alignement horizontal des éléments est crucial, que ce soit pour une **en-tête de site**, un **menu de navigation**, ou même un simple **bouton**. Figma facilite cette tâche grâce à l’**Auto Layout horizontal**, une extension naturelle de l’Auto Layout vertical.

---

## Fonctionnement de l’Alignement Horizontal

### Exemple d’Utilisation : Bouton

Prenons un composant bouton. Dans cet exemple :
- Les **icônes** (flèches, par exemple) et le **libellé** sont alignés **horizontalement**.
- Ils sont **centrés** dans le conteneur du bouton.
- Un **espacement de 20px** est configuré entre les différents éléments.

#### Illustration : Alignement Horizontal pour un Bouton

![L’auto layout à l’horizontal pour un bouton](/grimoire/img/auto-layout-horizontal-figma.jpg.avif)

---

## Réglages de l’Alignement Horizontal

Pour configurer un Auto Layout horizontal, vous devez définir :
- **Orientation** : Aligner les éléments horizontalement.
- **Centrage** : Centrer les éléments par rapport à leur conteneur.
- **Espacement** : Définir une distance fixe entre chaque élément.

### Exemple : Réglages de l’Auto Layout

Dans cet exemple :
- L’alignement est configuré pour être **horizontal**.
- L’espacement entre les éléments est fixé à **20px**.
- Tous les éléments sont **centrés** dans leur conteneur.

#### Illustration : Réglages de l’Auto Layout Horizontal

![Les réglages de l'Auto layout de Figma qui montre un alignement horizontal](/grimoire/img/figma-auto-layout-settings.jpg.avif)

---

## Adaptation Dynamique avec les Paramètres de Taille

Pour que la **taille du bouton** s’ajuste automatiquement à son contenu :
1. **Réglez la largeur et la hauteur** sur la valeur **Hug** (s’adapter au contenu enfant).
2. Si le texte ou les icônes du bouton sont modifiés, la taille s’ajuste automatiquement.

### Exemple : Valeur *Hug* pour la Taille du Conteneur

Dans cet exemple :
- La largeur et la hauteur du bouton sont configurées sur **Hug**.
- Cela garantit une **adaptation automatique** aux contenus.

#### Illustration : Réglages de Taille avec Hug

![La largeur et la hauteur ont la valeur Hug](/grimoire/img/taille-auto-hug-figma.jpg.avif)

---

## Concepts Clés pour l’Alignement

### Quand Utiliser les Paramètres de Taille

- **Hug** : Le conteneur s’ajuste à son contenu.
- **Fill** : L’enfant occupe tout l’espace disponible dans le conteneur parent.

### Résultat Dynamique

Grâce à ces réglages :
- Si le texte ou les icônes sont modifiés, le bouton s’ajuste automatiquement.
- Tous les éléments sont **dynamiques** et conscients de leur environnement, garantissant une mise en page flexible et réactive.

---

## Parallèle avec WordPress

Dans WordPress, le **bloc rangée** (Row) offre des fonctionnalités similaires :
- Permet l’**alignement horizontal** d’éléments.
- Offre la possibilité de définir l’**espacement** entre chaque bloc.

Ce parallèle démontre que les principes de Figma peuvent être appliqués directement dans un contexte de conception et de développement web.

---

## Conclusion

### À Retenir

1. **Alignement Horizontal** : Simplifie l’agencement d’éléments dans un conteneur.
2. **Valeur Hug** : Ajuste automatiquement la taille du parent au contenu enfant.
3. **Flexibilité Dynamique** : Les designs restent modulables et réactifs, même après des modifications.

L’**Auto Layout horizontal** est un outil essentiel pour des designs structurés et dynamiques, tant dans Figma que dans d’autres outils comme WordPress.
