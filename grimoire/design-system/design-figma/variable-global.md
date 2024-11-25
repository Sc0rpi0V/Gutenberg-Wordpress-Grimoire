# Les Variables Globales

## Introduction

Dans Figma, les **variables globales** permettent de standardiser et d’uniformiser les valeurs clés de votre design, comme :
- Les **couleurs**.
- Les **espacements**.
- Les **arrondis**.

### Pourquoi utiliser des variables globales ?

1. **Gain de temps** : Plus besoin de répéter les mêmes valeurs dans chaque élément.
2. **Cohérence** : Les éléments de votre design suivent les mêmes standards.
3. **Facilité de mise à jour** : En cas de changement, il suffit de modifier la valeur de la variable globale. Elle sera appliquée automatiquement à tous les éléments qui l’utilisent.

---

## Accéder aux Variables Globales

Pour configurer vos variables globales dans Figma :
1. Assurez-vous qu’**aucun élément n’est sélectionné** dans votre design.
2. Dans la colonne de droite, cliquez sur **« Local Variables »**.

### Exemple d’Interface

#### Illustration : Configuration des Variables

- [Style Interface Figma](/grimoire/img/styles-globaux-figma.jpg.avif)

Dans cette interface, vous pouvez voir un exemple de variables globales configurées, incluant :
- Plusieurs couleurs (exemple : `#FF5733` pour un rouge).
- Des valeurs d’arrondis.
- Une largeur.

Ces variables constituent les bases de votre **charte graphique**, un élément clé pour maintenir une identité visuelle cohérente.

---

## Bonnes Pratiques pour Nommer les Variables

### Organisation par Nom

Pour regrouper plusieurs valeurs dans un tableau commun, utilisez une **nomination structurée**. Exemple :
- **Base commune** + **Slash** : `Main/500`, `Main/300`.

### Gestion des Couleurs

Pour une **palette de couleurs avec différentes variations** :
- Adoptez un système de notation par **tonalité** :
  - `100` pour un ton clair.
  - `900` pour un ton sombre.

Cette approche est similaire à ce que propose des outils comme **TailwindCSS**.

#### Génération Automatique de Couleurs

Des outils comme **UIColors** peuvent générer automatiquement des tons à partir d’un code hexadécimal. Par exemple, à partir d’un rose, vous obtiendrez plusieurs déclinaisons allant de très clair à très foncé.

---

## Utiliser les Variables dans Figma

### Application de Couleurs Globales

Lorsque vous sélectionnez un élément, vous pouvez appliquer une couleur globale :
1. Cliquez sur l’élément.
2. Accédez aux variables globales depuis le **sélecteur de couleurs**.

#### Illustration : Appliquer une Couleur

Dans l’interface de sélection, vous avez accès aux couleurs globales enregistrées, organisées selon leur nomenclature.

---

### Application de Tailles et Espacements

Pour appliquer une taille ou un espacement défini par une variable :
1. Sélectionnez le champ correspondant (ex. : arrondi ou espacement).
2. Cliquez sur le **petit hexagone** à droite du champ pour accéder aux variables disponibles.

#### Illustration : Appliquer une Taille ou un Espacement

- [Définition style](/grimoire/img/styles-globaux-figma-ombres.jpg.avif)

L'interface vous permet de sélectionner une valeur parmi les variables préenregistrées, assurant cohérence et rapidité.

---

## Comparaison avec WordPress

### Variables dans le Full Site Editing

Le système de variables globales de Figma trouve son équivalent dans WordPress grâce au **Full Site Editing (FSE)**. Ces variables peuvent être définies dans le fichier `theme.json` d’un thème. Cela permet de :
- Centraliser la gestion des couleurs et des styles.
- Garantir une personnalisation facile et une cohérence dans tout le site.

Le prochain chapitre détaillera cette fonctionnalité.

---

## À Retenir

1. Les **variables globales** dans Figma permettent de gérer :
   - **Couleurs** : Palette organisée avec des tons variés.
   - **Espacements** et **arrondis** : Standardisation des tailles.
2. **Avantages** :
   - Modification centralisée.
   - Cohérence dans le design.
   - Gain de temps et simplicité.
3. Adoptez de **bonnes pratiques de nomenclature** (par ex. `Main/500`).
4. Des outils comme **UIColors** peuvent simplifier la génération de palettes.

Ces principes s’appliquent également à WordPress dans le cadre du **Full Site Editing**, rendant la gestion des styles encore plus accessible.