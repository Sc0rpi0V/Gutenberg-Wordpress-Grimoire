# Processus de gestion des images

## Objectifs

- **Améliorer la vitesse de chargement** : les images optimisées réduisent le temps de chargement des pages, essentiel pour offrir une navigation fluide et pour favoriser le référencement naturel (SEO).
- **Assurer une cohérence visuelle** : utiliser des formats et dimensions standardisés permet de maintenir une esthétique uniforme sur l’ensemble du site, renforçant ainsi l’identité visuelle de la marque.
- **Optimiser le référencement** : les images bien référencées avec des attributs alt et des noms de fichiers descriptifs améliorent le classement dans les moteurs de recherche, rendant le contenu plus visible.
- **Garantir l’accessibilité** : en ajoutant des textes alternatifs et en structurant les images de manière accessible, le site devient plus inclusif pour les utilisateurs avec des besoins spécifiques.

## 1. Préparation des images

### Format et résolution

- Utiliser des formats adaptés pour le web :
  - SVG pour les icônes vectorielles et illustrations simples
  - JPEG pour les photos (beaucoup de couleurs)
  - PNG pour les images avec transparence
- Les images doivent être optimisées pour le web avec une résolution adéquate (généralement entre 72 et 150 DPI) et une taille de fichier inférieure à 1 Mo pour un chargement rapide.

### Dimensions standardisées

- Privilégier des dimensions fixes (par ex. 1200x800 pixels pour les images en largeur complète) pour garantir une mise en page cohérente.
- Pas de coins arrondis : n’intégrez pas de coins arrondis directement dans les fichiers d’image. La gestion de cet effet doit être réalisée via CSS pour assurer une adaptation fluide en fonction de la taille de l’écran et garder une cohérence dans les tailles d’arrondis pour le responsive.

### Bonnes pratiques d’export depuis Figma

- Nomenclature des fichiers : utiliser un nom de fichier clair et descriptif directement dans Figma avant l’export, ce qui facilitera l’organisation et le référencement des images (ex. header-image-landing-page.jpg).
- Compression automatique : activer une option de compression (ou utilisez un outil comme TinyPNG après l’export) pour réduire la taille des images sans perte de qualité visible.
- Options d’exportation (x1, x2) : exporter les images à différentes échelles si vous anticipez un affichage rétina, en optant pour 1x (standard) et 2x (haute résolution) pour garantir une qualité optimale sur différents appareils.
- Formats Web optimisés : sélectionner le bon format directement dans Figma (JPG ou PNG), et ajustez la qualité de compression pour les JPEG (ex. entre 60 % et 80 %) pour un bon compromis entre taille et qualité.
- Dimensions exactes : vérifier que les dimensions d’exportation correspondent à celles nécessaires sur le site pour éviter le redimensionnement et préserver la netteté.

## 2. Téléchargement des images

Pour ajouter une image dans Gutenberg, utilisez le bloc “Image” ou, pour des galeries, le bloc “Galerie”.

- Utiliser la fonctionnalité d’ajout d’images en sélectionnant des fichiers directement depuis la médiathèque de WordPress ou en téléchargeant des fichiers depuis votre ordinateur.

### Nommage des fichiers

- Renommer chaque fichier avant l’import pour que le nom soit représentatif (par exemple, photo-portrait-client.jpg). Cela facilite la gestion et l’optimisation SEO.
- Ajouter un Texte Alternatif (Alt) : indiquer un texte descriptif pour chaque image, qui décrit l’image pour les moteurs de recherche et les lecteurs d’écran (utile pour l’accessibilité).

### 3. Vérifier de la performance et de l'accessibilité

- Vérifier le Poids Total des Pages : utiliser un outil de vérification de performance (PageSpeed Insights, par exemple) pour s’assurer que la taille des images ne ralentit pas le chargement de la page.
- Valider l’accessibilité en vérifiant que chaque image est correctement décrite via son attribut alt.

## Notes pour les développeurs

- Mettre en place une compression automatique via des plugins comme Smush ou Imagify pour garantir des images légères sans perte notable de qualité.
- Ajouter des règles CSS pour gérer les tailles d’image et éviter les distorsions dans les mises en page.
- Activer des formats d’image adaptatifs (avec l'attribut `srcset`) pour servir des tailles d’image optimisées en fonction de la résolution de l’écran de l’utilisateur.
