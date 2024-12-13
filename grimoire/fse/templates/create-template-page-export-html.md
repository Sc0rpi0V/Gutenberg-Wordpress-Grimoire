# Créer les templates de vos pages et exporter le HTML généré

## Modèles de pages
Nous aurons besoin de deux modèles de pages différents :

- **Modèle standard** : Adapté aux pages comme les mentions légales.
- **Modèle landing page** : En pleine largeur et sans titre.

---

## Créer le modèle de page

1. **Accédez à l'éditeur de modèles** :
   - Rendez-vous dans `Apparence > Éditeur > Modèles`.
   - Sélectionnez "Page". Ce modèle sera vide si vous ne l'avez pas encore configuré.

2. **Ajoutez les parties de template (header/footer)** :
   - Dans l'éditeur, cliquez sur le bouton `+` pour insérer un bloc.
   - Recherchez le `Header` dans la liste des blocs (rubrique "Thème", affiché en violet).
   - Insérez de la même manière le `Footer`.
   - Répétez cette procédure pour tous vos modèles de pages.

3. **Configurer la zone centrale** :
   - Ouvrez la "Vue en liste" pour plus de facilité.
   - Créez un groupe pour contenir le contenu central.

4. **Sémantique améliorée avec `<main>`** :
   - Sélectionnez le groupe, accédez à `Avancé > Élément HTML`.
   - Changez la balise en `<main>` au lieu de `<div>`.
   - Cela garantit une structure HTML logique et cohérente.

---

## Les blocs dynamiques

### Définir les zones de contenu

Chaque page aura un contenu unique (titre, texte, image mise en avant). Pour cela, utilisez des **blocs dynamiques** disponibles dans la rubrique "Thème" :

- **Titre de la publication** (`post-title`)
- **Contenu de la publication** (`post-content`)
- **Image mise en avant** (`post-featured-image`)
- Autres blocs disponibles :
  - Extrait de la publication
  - Auteur
  - Catégories et étiquettes
  - Dates de publication et modification
  - Commentaires, titres de taxonomie (pour les archives)

Ces blocs sont équivalents aux `template tags` comme `the_title()` ou `the_content()`, mais sous forme de blocs.

> **Remarque** : Pour commencer, utilisez uniquement le titre, le contenu et l'image mise en avant.

---

## Exporter le HTML

1. **Générer le HTML** :
   - Une fois satisfait du modèle, accédez à l'éditeur de code via les trois points en haut à droite.
   - Copiez le code HTML généré. Vous devriez y voir les parties de template `header` et `footer` ainsi qu'un bloc `groupe` contenant les blocs dynamiques (`post-title`, `post-featured-image`, `post-content`).

2. **Enregistrez le fichier** :
   - Collez le HTML dans un fichier `page.html` situé dans le dossier `templates` de votre thème.

3. **Tester le modèle** :
   - Créez une page dans l'interface WordPress (`Pages > Ajouter une page`).
   - Ajoutez une image mise en avant et du contenu.
   - Cliquez sur le bouton "Aperçu" pour vérifier le rendu.

---

## Afficher le modèle complet dans l'éditeur

Vous pouvez activer un **aperçu en temps réel** dans l'éditeur :

1. Dans l'inspecteur à droite, cliquez sur le modèle de page.
2. Sélectionnez "Afficher le modèle" pour voir le rendu complet pendant l'édition.

---

## Les deux types d'éditeurs

WordPress utilise deux éditeurs principaux :

1. **Éditeur d'apparence** :
   - Permet de gérer les templates et compositions (ex : création de modèles).

2. **Éditeur de contenu** :
   - Utilisé pour créer et modifier les publications (pages, articles).

Lors de la génération de la page en front-end :
- Le modèle est chargé en premier (structure globale).
- Le contenu est appliqué aux blocs dynamiques.

---

## Permettre la pleine largeur dans les contenus

1. **Problème de largeur** :
   - Par défaut, les groupes insérés dans une page standard ne peuvent pas être configurés en "pleine largeur".
   - Cela est dû à la contrainte imposée par le groupe parent centrant les contenus.

2. **Solution** :
   - Retournez dans votre template et configurez le bloc `contenu` en **pleine largeur**.
   - Activez l'option "Les blocs intérieurs utilisent la largeur du contenu".

3. **Configuration du `theme.json`** :
   - Ajoutez une valeur `wideSize` dans votre `theme.json`.
   - Passez le réglage `allowEditing` à `true`.

4. **Vérification** :
   - Vous devriez voir un liseré bleu autour du bloc prenant toute la largeur de l'éditeur.
   - Le contenu reste limité mais permet des ajustements de largeur.

5. **Exporter le HTML** :
   - Générez le nouveau code HTML et mettez à jour `page.html`.
   - Réinitialisez le modèle de page depuis l'interface Gutenberg.

6. **Utilisation** :
   - Les sections en "pleine largeur" seront disponibles dans vos contenus.
   - Une option "grande largeur" permettra de limiter certains éléments à une largeur normale ou large (mais pas pleine largeur).

---
