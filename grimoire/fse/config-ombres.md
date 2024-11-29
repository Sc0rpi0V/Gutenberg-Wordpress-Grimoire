# Configurer les ombres

C’est un élément supplémentaire de notre **design system** que l’on va désormais pouvoir gérer depuis notre site. On pourra ensuite les appliquer aux images, galeries, bannières, boutons…

Comme pour les autres éléments, on va pouvoir manipuler les ombres directement à partir du fichier `theme.json` :

---

## Les ombres natives de WordPress

Par défaut, les ombres sont **désactivées** dans WordPress. Par exemple, dans Gutenberg, ajoutez un bouton ou une image et regardez dans l’onglet des styles du bloc. Dans la section **« Bordure & ombre »**, vous ne trouverez que les réglages de bordure et de rayon.

Pour activer le réglage d’ombre :
1. Cliquez sur le menu **3 points** en haut à droite.
2. Activez le réglage d’ombre.

### Résultat
Le réglage d’ombre apparaît juste après les réglages de rayon. Vous pouvez alors sélectionner l’ombre à afficher.

Les ombres apparaissent dans une petite pop-up. Il ne vous reste qu’à choisir celle que vous souhaitez appliquer à votre bloc. Voici un exemple avec quelques **ombres prédéfinies appliquées aux images d’une galerie** :

---

## CSS généré côté front

Dans le CSS généré par WordPress :
- Chaque ombre est déclarée sous forme de **variable CSS** dans le `body`.
- Les valeurs de ces ombres utilisent des réglages classiques de la propriété CSS `box-shadow()`.

---

## Déclarer des ombres sur mesure

### Objectif
Déclarer vos propres ombres en CSS pour rester cohérent avec votre **design system**.

### Étapes
1. **Désactiver les ombres par défaut** : passez `defaultPresets` à `false`.
2. **Déclarer vos ombres personnalisées** via la propriété `presets`.

### Déclaration d'une ombre
Comme pour les couleurs ou les tailles de texte, chaque ombre doit être déclarée avec **3 paramètres** :
- **`name`** : le nom de l’ombre qui apparaîtra dans l’interface.
- **`slug`** : l’identifiant unique de l’ombre, utilisé en CSS.
- **`shadow`** : le CSS de la propriété `box-shadow()`.

### Exemple
Dans l’éditeur, vos **ombres portées personnalisées** seront désormais proposées. Côté front, les variables CSS ressembleront à ceci :

- Les ombres natives de WordPress sont toujours déclarées, même si elles ne sont pas utilisées.
- Les nouvelles ombres ajoutées incluent bien leur **slug** dans la variable CSS, par exemple : `light`, `neat`, `huge`.

---

## Appliquer une ombre par défaut à un bloc

### Objectif
Appliquer automatiquement une ombre à un bloc (par exemple, une image), pour éviter que l’utilisateur ait à la sélectionner à chaque insertion dans l’éditeur.

### Étapes
1. Allez dans la section `styles` du fichier `theme.json`.
2. Appliquez la **variable CSS générée par WordPress** correspondant à l’ombre souhaitée.

### Exemple
Pour appliquer une ombre avec le slug `neat`, voici ce qui se passera :
- Lorsqu’une image sera ajoutée dans Gutenberg, elle aura directement l’ombre appliquée.

```json
"styles": {
  "blocks": {
    "core/image": {
      "shadow": "var(--wp--preset--shadow--neat)"
    }
  }
}
```