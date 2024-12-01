# 📄 Configuration des Custom Templates dans `theme.json`

Depuis les récentes versions de Gutenberg, les modèles de pages personnalisés (Custom Templates) doivent être déclarés dans le fichier `theme.json` du thème. Cela permet de définir des modèles spécifiques adaptés aux besoins variés de vos pages, comme des **landing pages** ou des pages de contenu formel (mentions légales, politique de confidentialité, etc.).

## 📌 Structure des Custom Templates dans `theme.json`

La section des modèles personnalisés est incluse sous la clé `customTemplates` dans le fichier `theme.json`. Voici la structure de base :

```json
{
  "version": 2,
  "settings": {
    "customTemplates": [
      {
        "name": "nom-du-template",
        "title": "Titre du Template",
        "description": "Courte description du template.",
        "postTypes": ["page"]
      }
    ]
  }
}
```

### 📝 Détails des propriétés :

- **`name`** :  
  Le nom unique de l’identifiant du template (slug). Il doit être en minuscules, sans espaces, et peut inclure des tirets.
  
- **`title`** :  
  Le titre affiché pour l’utilisateur dans l’interface d’administration de WordPress.
  
- **`description`** :  
  Une brève description du rôle ou de l’objectif de ce template, utile pour aider les utilisateurs à choisir le bon modèle.
  
- **`postTypes`** :  
  Un tableau qui indique les types de contenus (post types) auxquels ce template est applicable, par exemple `page`, `post`, ou des custom post types (CPT).

---

## 🌟 Exemple : Modèles pour Landing Page et Page Standard

Imaginons que vous souhaitez créer deux templates spécifiques :
1. **Landing Page** : Une page en pleine largeur, sans titre principal.
2. **Page Standard** : Une page classique avec un titre et une zone de contenu plus étroite.

### Déclaration dans `theme.json` :

```json
{
  "version": 2,
  "settings": {
    "customTemplates": [
      {
        "name": "landing-page",
        "title": "Landing Page",
        "description": "Un modèle pour des pages en pleine largeur sans titre.",
        "postTypes": ["page"]
      },
      {
        "name": "page-standard",
        "title": "Page Standard",
        "description": "Un modèle pour des pages de contenu formelles avec titre.",
        "postTypes": ["page"]
      }
    ]
  }
}
```

### Création des Fichiers de Template

Les fichiers correspondants aux templates doivent être placés dans le dossier `templates` de votre thème.

- **Landing Page**  
  Créez un fichier nommé `landing-page.html` :

  ```html
  <!-- wp:group {"layout":{"type":"constrained"}} -->
  <div class="wp-block-group">
      <!-- wp:paragraph -->
      <p>Contenu de la landing page ici.</p>
      <!-- /wp:paragraph -->
  </div>
  <!-- /wp:group -->
  ```

- **Page Standard**  
  Créez un fichier nommé `page-standard.html` :

  ```html
  <!-- wp:group {"layout":{"type":"default"}} -->
  <div class="wp-block-group">
      <!-- wp:post-title /-->
      <!-- wp:post-content /-->
  </div>
  <!-- /wp:group -->
  ```

---

## 💡 Bonnes Pratiques

1. **Clarté des noms et descriptions** : Utilisez des noms et descriptions explicites pour que les administrateurs identifient rapidement le template approprié.
2. **Réutilisabilité** : Créez des templates génériques mais personnalisables pour divers types de contenus.
3. **Tests** : Vérifiez que les templates apparaissent bien dans l’éditeur de blocs et sont correctement appliqués aux pages.

---

## 🛠️ Résultat dans WordPress

Une fois configurés, vos templates seront disponibles dans l’éditeur WordPress lors de la création ou modification d’une page :

1. Accédez à une page existante ou créez-en une nouvelle.
2. Sous **Modèle**, sélectionnez le template souhaité depuis le menu déroulant.

---