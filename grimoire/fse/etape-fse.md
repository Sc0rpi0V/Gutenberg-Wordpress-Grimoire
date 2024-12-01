# 🛠️ Construire son site en 5 étapes avec le Full Site Editing (FSE)

Voici les principales étapes pour réaliser un site WordPress avec le **Full Site Editing** :

1. **Configurer le design system** du site via le fichier `theme.json` (couleurs globales, espacements, typographies, fonctionnalités de l’éditeur).
2. **Déclarer des variations de styles** pour les blocs existants afin de personnaliser leur CSS plus facilement.
3. **Créer des compositions de blocs réutilisables**, utilisables dans le site ou dans de futurs projets.
4. **Réaliser les modèles de pages** du site, conformément au template hierarchy de WordPress.
5. **Installer, modifier ou développer des blocs sur-mesure** pour étendre les possibilités de l’éditeur.

Avec ces étapes, vous serez capable de répondre à n’importe quel cahier des charges !

---

## 🎯 Complexité et temps requis pour chaque étape

- **Variations de styles des blocs** : Les plus simples et rapides à ajouter.
- **Configuration du `theme.json`** : Facile mais demande un peu de temps.
- **Conception des compositions** : Nécessite un peu plus de complexité et de temps.
- **Modèles de pages** : Idem que les compositions.
- **Blocs sur-mesure** : Plus complexe et peut être long à réaliser.

---

## 🚀 Étape 1 : Configurer le thème via `theme.json`

### Intégrer le Design System

Commencez par configurer le **Design System** de votre site, notamment :

- **Palette de couleurs**.
- **Polices et typographies** pour titres et textes.
- **Espacements** (marges et paddings).
- **Ombres, arrondis**.

### Définir les fonctionnalités de l’éditeur

Ajoutez ou limitez les réglages suivants dans l’éditeur :

- Couleurs des titres, textes, liens.
- Espacements (internes et externes).
- Typographies (graisse, hauteur de ligne, espacement).
- Images (choix de fond, dimensions, ratio, hauteur minimale).
- Bordures (style, taille, arrondi).
- Position d’éléments (ex. sticky).

#### Limiter les possibilités de la palette de couleurs

Cela garantit la cohérence du design et limite les choix à des valeurs prédéfinies.

### Appliquer des valeurs globales aux blocs

Utilisez le JSON pour appliquer les valeurs globales aux blocs : titres, textes, boutons, liens, etc. Ces changements peuvent être visualisés dans le **style guide** (icône en forme d’œil).

---

## 🎨 Étape 2 : Créer des variations de styles pour les blocs

Ajoutez des **variations graphiques** activables via l’interface. Cela ajoute une classe CSS spécifique au bloc, permettant de personnaliser son apparence.

### Exemples d’utilisation :

- Déclinaisons infinies de boutons.
- Différents styles de séparateurs de sections.
- Textes mis en avant (conseils, alertes).
- Listes transformées en check-lists.
- Masques pour images (formes spécifiques).

**Exemple avec le bloc "Bouton" :** créez des variations avec des couleurs, tailles ou formes différentes.

---

## 📦 Étape 3 : Créer des compositions de blocs réutilisables

Cette étape consiste à créer des **compositions réutilisables**, selon le principe de l’atomic design :

- **Atomes** : Blocs unitaires (boutons, titres, images).
- **Organismes** : Compositions de plusieurs atomes (sections complètes).

### Avantages :

- Organisation en catégories pour un accès rapide.
- Réutilisation facile dans Gutenberg via l’onglet **Compositions**.

---

## 🖼️ Étape 4 : Créer les modèles de pages

Dans l’éditeur, vous aurez accès à tous les modèles :

- Pages standards.
- Page d’accueil.
- Archives (blog, articles).
- Pages pour custom post types.
- Page 404.

### Utilisation du bloc « Boucle de requête »

Ce bloc permet d’afficher la liste des publications dans une archive. Vous pouvez personnaliser tous ses éléments, car **tout est un bloc** dans WordPress.

---

## 🔧 Étape 5 : Créer ou personnaliser des blocs sur-mesure

Lorsque les solutions précédentes ne suffisent pas, créez des **blocs sur-mesure** pour répondre à des besoins spécifiques.

### Cas d’usage :

- Mise en page précise.
- Affichage de données dynamiques.
- Exemple : au lieu de créer un modèle de page spécifique avec ACF, vous pouvez concevoir un bloc dédié.

---

Avec ces 5 étapes, vous disposez d’un workflow clair et efficace pour concevoir un site WordPress moderne et performant avec le Full Site Editing.

# 🛠️ Construire son site en 5 étapes avec le Full Site Editing (FSE)

Voici les principales étapes pour réaliser un site WordPress avec le **Full Site Editing** :

1. **Configurer le design system** du site via le fichier `theme.json` (couleurs globales, espacements, typographies, fonctionnalités de l’éditeur).
2. **Déclarer des variations de styles** pour les blocs existants afin de personnaliser leur CSS plus facilement.
3. **Créer des compositions de blocs réutilisables**, utilisables dans le site ou dans de futurs projets.
4. **Réaliser les modèles de pages** du site, conformément au template hierarchy de WordPress.
5. **Installer, modifier ou développer des blocs sur-mesure** pour étendre les possibilités de l’éditeur.

Avec ces étapes, vous serez capable de répondre à n’importe quel cahier des charges !

---

## 🎯 Complexité et temps requis pour chaque étape

- **Variations de styles des blocs** : Les plus simples et rapides à ajouter.
- **Configuration du `theme.json`** : Facile mais demande un peu de temps.
- **Conception des compositions** : Nécessite un peu plus de complexité et de temps.
- **Modèles de pages** : Idem que les compositions.
- **Blocs sur-mesure** : Plus complexe et peut être long à réaliser.

---

## 🚀 Étape 1 : Configurer le thème via `theme.json`

### Intégrer le Design System

Commencez par configurer le **Design System** de votre site, notamment :

- **Palette de couleurs**.
- **Polices et typographies** pour titres et textes.
- **Espacements** (marges et paddings).
- **Ombres, arrondis**.

### Définir les fonctionnalités de l’éditeur

Ajoutez ou limitez les réglages suivants dans l’éditeur :

- Couleurs des titres, textes, liens.
- Espacements (internes et externes).
- Typographies (graisse, hauteur de ligne, espacement).
- Images (choix de fond, dimensions, ratio, hauteur minimale).
- Bordures (style, taille, arrondi).
- Position d’éléments (ex. sticky).

#### Limiter les possibilités de la palette de couleurs

Cela garantit la cohérence du design et limite les choix à des valeurs prédéfinies.

### Appliquer des valeurs globales aux blocs

Utilisez le JSON pour appliquer les valeurs globales aux blocs : titres, textes, boutons, liens, etc. Ces changements peuvent être visualisés dans le **style guide** (icône en forme d’œil).

---

## 🎨 Étape 2 : Créer des variations de styles pour les blocs

Ajoutez des **variations graphiques** activables via l’interface. Cela ajoute une classe CSS spécifique au bloc, permettant de personnaliser son apparence.

### Exemples d’utilisation :

- Déclinaisons infinies de boutons.
- Différents styles de séparateurs de sections.
- Textes mis en avant (conseils, alertes).
- Listes transformées en check-lists.
- Masques pour images (formes spécifiques).

**Exemple avec le bloc "Bouton" :** créez des variations avec des couleurs, tailles ou formes différentes.

---

## 📦 Étape 3 : Créer des compositions de blocs réutilisables

Cette étape consiste à créer des **compositions réutilisables**, selon le principe de l’atomic design :

- **Atomes** : Blocs unitaires (boutons, titres, images).
- **Organismes** : Compositions de plusieurs atomes (sections complètes).

### Avantages :

- Organisation en catégories pour un accès rapide.
- Réutilisation facile dans Gutenberg via l’onglet **Compositions**.

---

## 🖼️ Étape 4 : Créer les modèles de pages

Dans l’éditeur, vous aurez accès à tous les modèles :

- Pages standards.
- Page d’accueil.
- Archives (blog, articles).
- Pages pour custom post types.
- Page 404.

### Utilisation du bloc « Boucle de requête »

Ce bloc permet d’afficher la liste des publications dans une archive. Vous pouvez personnaliser tous ses éléments, car **tout est un bloc** dans WordPress.

---

## 🔧 Étape 5 : Créer ou personnaliser des blocs sur-mesure

Lorsque les solutions précédentes ne suffisent pas, créez des **blocs sur-mesure** pour répondre à des besoins spécifiques.

### Cas d’usage :

- Mise en page précise.
- Affichage de données dynamiques.
- Exemple : au lieu de créer un modèle de page spécifique avec ACF, vous pouvez concevoir un bloc dédié.

---

Avec ces 5 étapes, vous disposez d’un workflow clair et efficace pour concevoir un site WordPress moderne et performant avec le Full Site Editing.
