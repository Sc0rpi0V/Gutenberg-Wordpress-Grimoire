# Guide pour les Header, Footer et Template Parts dans le FSE de WordPress

## Préparatifs
Avant de commencer à créer l'en-tête et le pied de page, quelques étapes préliminaires sont nécessaires :

1. **Créer les fichiers nécessaires :**
   - Assurez-vous que les fichiers `header.html` et `footer.html` existent dans le dossier `parts` de votre thème.

2. **Modifier le fichier `theme.json` :**
   - Ajoutez les lignes suivantes dans la section `templateParts` de ce fichier :

```json
{
  "templateParts": [
    {
      "area": "header",
      "name": "header",
      "title": "Header"
    },
    {
      "area": "footer",
      "name": "footer",
      "title": "Footer"
    }
  ]
}
```

- Ces paramètres permettent de déclarer les templates parts **Header** et **Footer**.
- Les propriétés :
  - `area` : Définit si le part est un header ou un footer.
  - `name` : Correspond au nom du fichier sans l'extension `.html`.
  - `title` : Le titre visible dans l'interface WordPress.

3. **Vérifier le fichier `index.html` :**
   - Le fichier situé dans le dossier `templates` doit contenir le strict minimum pour permettre un aperçu dans l'éditeur.

---

## Création de l'en-tête

1. **Conception dans Gutenberg :**
   - Insérez une **rangée**.
   - Configurez des **marges internes** et une **couleur de fond**.
   - Choisissez la justification "Répartir les blocs".

2. **Ajout des blocs :**
   - **Logo du site :** Ajoutez le bloc et sélectionnez l'image du logo.
   - **Menu de navigation :** Insérez un menu et ajoutez les liens.
   - **Bouton :** Ajoutez un bouton de devis.

3. **Disposition :**
   - Grâce à la justification "Répartir les blocs", les éléments se répartissent automatiquement :
     - Le logo à gauche.
     - Le menu au centre.
     - Le bouton à droite.

4. **Exporter le HTML :**
   - Dans l'éditeur, cliquez sur le menu à 3 points (en haut à droite) et choisissez **Éditeur de code**.
   - Exportez le code généré vers `parts/header.html`.

5. **Vérification dans WordPress :**
   - Allez dans **Apparence > Éditeur > Compositions** pour voir l'aperçu.
   - Dans **Apparence > Éditeur**, l'en-tête devrait apparaître en haut de la page.

6. **Réinitialiser un modèle si besoin :**
   - Si une version a été sauvegardée en base de données, retournez dans l'éditeur et choisissez **Réinitialiser** dans le menu sous l'onglet "Élément de modèle".

---

## Création du pied de page

La procédure est similaire à celle de l'en-tête, mais pour le modèle **Footer**. Voici les étapes :

1. **Structure :**
   - Ajoutez un **groupe** avec des marges internes et une couleur de fond.
   - Ce groupe contiendra :
     - **Deux parties :**
       - Une avec 3 colonnes (50/25/25).
       - Une rangée justifiée "Répartir les blocs".
     - Un séparateur avec des marges externes entre les deux parties.

2. **Contenu des colonnes :**
   - Insérez :
     - Le **logo du site**.
     - Des **paragraphes**.
     - Des **menus de navigation**.

3. **Partie basse :**
   - Ajoutez un **paragraphe** avec les réseaux sociaux.

4. **Exporter le code :**
   - Exportez le HTML et enregistrez-le dans `parts/footer.html`.
   - Vérifiez l'affichage dans **Apparence > Éditeur**.

---

## Insérer des Template Parts dans un modèle

- Les template parts apparaissent dans le menu des blocs de Gutenberg.
- Dans l'éditeur de code, cela se manifeste par :

```html
<!-- wp:template-part {"slug":"header"} /-->
```

- Ce système synchronisé garantit que toute modification appliquée à un template part sera reflétée partout où il est utilisé.

---

## Déclarer des en-têtes et pieds de page secondaires

Pour des besoins spécifiques (landing pages, tunnels de conversion, etc.), vous pouvez créer des variantes d'en-têtes ou de pieds de page :

1. **Ajout dans `theme.json` :**

```json
{
  "templateParts": [
    {
      "area": "header",
      "name": "header-marketing",
      "title": "Header minimaliste"
    }
  ]
}
```

2. **Créer le fichier correspondant :**
   - Exemple : `parts/header-marketing.html`.

3. **Réalisation :**
   - Par exemple, un logo dans une rangée simple.

4. **Exporter le HTML :**
   - Sauvegardez le code dans le fichier de votre thème.

---

## Utilisation de la sidebar

Bien que la sidebar soit moins utilisée aujourd'hui, vous pouvez toujours la déclarer :

```json
{
  "templateParts": [
    {
      "area": "sidebar",
      "name": "sidebar",
      "title": "Sidebar"
    }
  ]
}
```

---

## Créer ses propres Template Parts

- Les template parts peuvent être utilisés pour centraliser du code réutilisable, comme :
  - Une zone d'appel à l'action.
  - Un layout commun pour `blog.html` et `archive.html`.

---

## Gestion des balises HTML de base

WordPress gère automatiquement les balises HTML de base (comme `<head>`), vous libérant de cette responsabilité. Cependant, pour insérer des balises personnalisées :

- Utilisez les hooks suivants dans `functions.php` :

```php
// Ajouter des balises dans <head>
add_action('wp_head', function() {
    echo '<meta name="custom-meta" content="value">';
});

// Ajouter des classes CSS dans <body>
add_filter('body_class', function($classes) {
    $classes[] = 'custom-class';
    return $classes;
});

// Ajouter du contenu au début du document
add_action('wp_body_open', function() {
    echo '<div class="custom-content">Hello World</div>';
});
```
