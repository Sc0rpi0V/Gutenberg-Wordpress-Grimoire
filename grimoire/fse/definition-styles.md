# Définir les styles du site

L'une des parties les plus importantes de la conception d'un site dans WordPress est la rubrique **Styles**. C'est ici que vous pouvez définir les valeurs globales pour les styles de votre site : couleurs, typographies, tailles, et bien plus encore. Cela permet d'appliquer la charte graphique à l'ensemble du design system du site.

## Choisir une variation de style

Lorsque vous cliquez sur la section **Styles**, vous arrivez sur l'écran de sélection des variations de styles proposées par votre thème. Si votre thème inclut des déclinaisons préconçues, elles apparaîtront ici.

### Exemple : Thème Ollie

Le thème Ollie propose 4 variations de styles prédéfinies. D’un simple clic, vous pouvez appliquer une nouvelle charte graphique à votre site. Par exemple, en sélectionnant la variation « Studio », tout le site adopte une palette de couleurs rose et des polices spécifiques.

- **Utilité des variations de styles** :  
  Ces variations sont particulièrement pratiques si vous souhaitez offrir plusieurs options aux utilisateurs de votre thème, ou pour des ajustements saisonniers (comme pour Noël).

## Modifier les styles du thème

Pour personnaliser les styles, cliquez sur l’icône **stylo** en haut à droite du panneau **Styles**. Cela ouvre un éditeur détaillé, où vous pouvez ajuster plusieurs aspects :

1. **Typographie**  
2. **Couleurs**  
3. **Ombres**  
4. **Mise en page**  
5. **Styles des blocs**  

### Typographie

La section **Typographie** permet de gérer les polices d’écriture, leurs variantes de graisse et leurs tailles. Vous pouvez importer des polices ou utiliser directement les **Google Fonts**.

#### Points importants :
- **Optimisation des performances** :  
  Limitez-vous à 2 polices principales et réduisez les variantes de graisse pour améliorer le chargement des pages.
- **Application globale** :  
  Les styles typographiques peuvent être appliqués globalement aux textes, liens, titres, boutons, etc.

Exemple : Appliquer la police Nunito en « extra-gras » à tous les boutons. Ce réglage sera automatiquement appliqué à tous les blocs contenant des boutons.

> *Aparté technique* : WordPress utilise des **variables CSS** pour gérer ces styles globalement, ce qui permet des modifications simples et rapides.

---

### Couleurs

Dans le panneau **Couleurs**, vous pouvez :
- Modifier la palette principale.
- Personnaliser les couleurs par défaut des éléments (titres, textes, boutons, arrière-plan).
- Ajouter des couleurs personnalisées.

#### Palette et personnalisation
Cliquez sur une couleur pour la modifier et voir les changements en temps réel. Vous pouvez également ajouter de nouvelles couleurs ou des dégradés.

#### Application globale
Les couleurs de la palette peuvent être assignées aux éléments primitifs du site, comme :
- Les titres
- Les textes
- Les liens (et leur survol)
- Les boutons

---

### Ombres

La gestion des ombres est également intégrée dans l'éditeur de styles. Vous pouvez :
- Ajouter des ombres prédéfinies à des blocs comme les images ou les groupes.
- Créer des ombres personnalisées en combinant plusieurs effets pour des rendus complexes.

---

### Mise en page

Les réglages de mise en page vous permettent de :
- Définir la largeur du contenu des pages.
- Ajuster les marges internes (padding) par défaut des blocs.
- Gérer l’espacement entre les blocs.

#### Largeurs
- **Standard** : Pour des pages simples (mentions légales, articles de blog).
- **Large** : Pour mettre en avant des éléments importants (images, sections principales).
- **Pleine largeur** : Pour des sections à fond coloré qui couvrent toute la largeur de l'écran.

#### Marges internes
Les marges internes latérales sont essentielles sur mobile pour éviter que les textes soient collés aux bords de l'écran. Par contre, les marges verticales doivent rester à 0 pour maintenir le header et le footer en place.

---

### Conseil pour la mise en page

Ces réglages sont cruciaux pour réussir vos mises en page dans l'éditeur visuel. Ils doivent être bien compris pour éviter des complications à l'avenir.

> Pour les développeurs, il est souvent préférable d'utiliser le fichier `theme.json` pour une personnalisation avancée.
