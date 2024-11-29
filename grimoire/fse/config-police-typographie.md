# Configurer les polices et typographies

Dans WordPress, il est possible de déclarer ses polices et de les utiliser dans l’éditeur. L’objectif est de définir globalement quelle police utiliser pour quelle occasion.

Comme d’habitude, tout se configure dans le fichier `theme.json`. Voyons comment :
- Ajouter une police dans le thème ;
- Déclarer les tailles disponibles ;
- Assigner ces polices à nos titres et textes dans les styles globaux de l’éditeur.

---

## Ajouter des polices d’écriture depuis l’éditeur

Depuis WordPress **6.5**, un gestionnaire de polices d’écriture est intégré dans Gutenberg, permettant d’installer des polices personnalisées ou d’en télécharger depuis **Google Fonts**.

### Accéder au gestionnaire de polices
1. Allez dans **Apparence > Éditeur > Styles > Typographie**.
2. Le panneau affichera deux parties :
   - Une liste des **polices d’écriture installées** ;
   - Les options pour définir la typographie pour chaque élément primitif.

3. Cliquez sur une police pour ouvrir le gestionnaire de polices (modale).

### Gestionnaire de polices
Le gestionnaire propose trois onglets :
1. **Bibliothèque** : liste des polices installées avec leurs graisses.
2. **Téléverser** : pour importer une police au format `.woff2`.
3. **Installer** : pour télécharger des polices depuis **Google Fonts**.

#### Installer une police depuis Google Fonts
- Acceptez l’autorisation d’accéder à Google pour télécharger les polices sur votre site (meilleures performances).
- Utilisez le moteur de recherche pour trouver des polices populaires comme **Open Sans, Noto, Roboto, Montserrat**, etc.
- Sélectionnez la police et les graisses nécessaires. **Attention : limitez les graisses au strict minimum pour préserver les performances.**

Une fois la police installée, vous pourrez l’appliquer aux titres, textes, ou blocs spécifiques.

### Où sont stockés les fichiers des polices ?
Les fichiers sont enregistrés dans `wp-content/uploads/fonts`.

---

## Installer des polices manuellement

L’installation manuelle permet de versionner les configurations typographiques dans Git et d’inclure les fichiers de police dans le thème.

### Étapes pour installer une police
1. Obtenez le fichier de police au format `.woff2`.
   - Si nécessaire, utilisez un convertisseur comme **Font Squirrel**.
2. Téléchargez la police depuis **Google Fonts** :
   - Copiez l’URL du fichier dans le CSS généré par Google (`@font-face`).
   - Téléchargez le fichier via le navigateur.
3. Placez le fichier dans le dossier `assets/fonts` de votre thème.

---

## Configurer les polices dans `theme.json`

Avec les fichiers de police en place, vous pouvez les déclarer dans `theme.json` dans la section `settings > typography`.

### Ajouter une police
Utilisez la propriété **fontFamilies** pour déclarer vos polices. Exemple pour Open Sans (regular 400, normal) :

```json
"settings": {
  "typography": {
    "fontFamilies": [
      {
        "fontFamily": "Open Sans",
        "name": "Open Sans",
        "slug": "open-sans",
        "fontFace": [
          {
            "src": "assets/fonts/open-sans-regular.woff2",
            "fontWeight": "400",
            "fontStyle": "normal"
          }
        ]
      }
    ]
  }
}
```

### Ajouter des graisses de police
Ajoutez des entrées dans `fontFace` pour déclarer d’autres graisses. Exemple avec `bold 700` :

```json
{
  "src": "assets/fonts/open-sans-bold.woff2",
  "fontWeight": "700",
  "fontStyle": "normal"
}
```

### Déclarer une police à graisse variable
Les polices variables nécessitent un seul fichier. Déclarez-les en spécifiant l’intervalle des graisses dans `fontWeight`. Exemple :

```json
{
  "fontFamily": "Work Sans",
  "name": "Work Sans",
  "slug": "work-sans",
  "fontFace": [
    {
      "src": "assets/fonts/work-sans-variable.woff2",
      "fontWeight": "300 900",
      "fontStyle": "normal"
    }
  ]
}
```

### Définir des tailles de polices
Les tailles de polices se déclarent dans la propriété `fontSizes`. Exemple :

``` json 
{
    "fontSizes": [
    {
        "name": "Small",
        "size": "12px",
        "slug": "small"
    },
    {
        "name": "Medium",
        "size": "16px",
        "slug": "medium"
    },
    {
        "name": "Large",
        "size": "20px",
        "slug": "large"
    }
    ]
}
```

### Typographies fluides
Pour des tailles fluides, utilisez la fonction clamp() avec la propriété `fluid` :

```json
{
  "name": "Medium",
  "slug": "medium",
  "size": "16px",
  "fluid": {
    "min": "14px",
    "max": "20px"
  }
}
```

### Appliquer des polices aux textes
Les polices et tailles définies peuvent être appliquées dans la section `styles` de theme.json. Exemple :

Appliquer une police par défaut
``` json
"styles": {
  "typography": {
    "fontSize": "var(--wp--preset--font-size--medium)",
    "fontFamily": "var(--wp--preset--font-family--primary)"
  },
  "elements": {
    "heading": {
      "typography": {
        "fontFamily": "var(--wp--preset--font-family--secondary)"
      }
    }
  }
}
```

### Réinitialiser les styles de l’éditeur
Si vos modifications dans theme.json ne sont pas prises en compte :

Cliquez sur les 3 points en haut à droite du panneau des styles.
Sélectionnez Réinitialiser les styles.
Activer ou désactiver des réglages typographiques
Dans theme.json, vous pouvez limiter les réglages disponibles pour les utilisateurs. Voici les options possibles :

- customFontSize : Définir une taille personnalisée.
- defaultFontSizes : Utiliser les tailles fournies par WordPress.
- dropCap : Activer la lettrine en début de paragraphe.
- fontStyle : Passer un texte en italique.
- fontWeight : Choisir la graisse (gras ou autre).
- letterSpacing : Espacement entre les lettres.
- lineHeight : Interlignage.
- textAlign : Aligner le texte.
- textDecoration : Souligner ou barrer.
- textTransform : Modifier la casse.
- writingMode : Passer en écriture verticale.