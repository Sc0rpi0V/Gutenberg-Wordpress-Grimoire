# Variations de thème (Couleurs et typographies)

## Offrir des choix de variations à l'utilisateur

Il est possible de donner à vos utilisateurs le choix d’une variation de thème en proposant :

- Des palettes de couleurs différentes ;
- Des jeux de polices d’écriture différents ;
- Ou des déclinaisons complètes du thème.

Cette fonctionnalité est essentielle pour les créateurs de thèmes qui souhaitent les vendre en ligne.

---

## Préparer un modèle basique pour l’aperçu

Pour commencer, ouvrez le fichier `/templates/index.html` et ajoutez-y le code suivant :

```html
<!-- Exemple de modèle basique -->
<!-- Insérer votre code HTML ici -->
```

---

## Préparer nos variations

### Structure des fichiers

Pour déclarer une variation de style de thème :

1. Créez un dossier `/styles` à la racine de votre thème ;
2. Ajoutez des fichiers `.json` pour chaque variation.

---

## Créer des déclinaisons de palettes

### Exemple : Palette estivale

1. Créez un fichier `/styles/estival.json`.
2. Ajoutez-y vos réglages de palette.

Une fois enregistré, votre palette sera détectée automatiquement dans **Apparence > Éditeur > Styles**.

> **Note :** Pensez à surcharger avec la même précision (racine / élément / block) que dans votre `theme.json` originel.

---

## Ajouter des déclinaisons de polices

### Exemple : Fichier cartoon.json

Dans cet exemple, le thème principal utilise **Open Sans** comme police générale. La déclinaison utilise **Borel** et **ACME** de Google Fonts.

1. Créez un fichier `/styles/cartoon.json`.
2. Déclarez deux nouvelles polices dans `settings > typography > fontFamilies`.

Assurez-vous de bien déclarer la bonne source dans `src`.

### Astuce

Vous pouvez également :

- Modifier les tailles de texte ;
- Modifier les styles par défaut appliqués aux blocs et éléments.

Exemple : Appliquer la police **ACME** aux titres de niveau 1.

---

## Créer des déclinaisons complètes

### Exemple : Thème Halloween

Vous pouvez combiner typographies et palettes dans une même variation.

1. Créez un fichier `/styles/halloween.json`.
2. Déclarez une typographie et une palette en même temps.

Dans l’éditeur de sites, vous verrez votre nouvelle déclinaison. Cliquez sur le stylo en haut à droite pour modifier la variation et voir les nouveaux styles appliqués.

---

## Résumé

- Utilisez des fichiers dans `/styles` pour ajouter des déclinaisons ;
- Précisez les réglages pour chaque variation (couleurs, polices, styles par bloc) ;
- Testez vos déclinaisons dans **Apparence > Éditeur > Styles**.

Cela permet de créer une expérience personnalisée et flexible pour vos utilisateurs.
