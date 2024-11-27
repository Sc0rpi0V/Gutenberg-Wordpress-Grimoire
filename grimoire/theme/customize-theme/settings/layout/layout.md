# Réglages du layout

La gestion des alignements wide et full se fait en fournissant une entrée layout.

```json
{
    "version": 2,
    "$schema": "https://schemas.wp.org/trunk/theme.json",
    "settings": {
	"color": { ... },
	"typography": { ... },
	"layout" : {
	    "contentSize": "768px",
	    "wideSize": "1024px"
	}
    },
    "styles": { ... }
}
```

Cela permet définir la largeur du contenu par défaut, et la largeur des blocs ayant l’alignement wide. Des variables CSS `--wp--style--global--content-size` et `--wp--style--global--wide-size` seront imprimées sur le devant du site. Par contre, à vous de les exploiter ! C’est un réglage qui ne fonctionnera pas automagiquement comme un réglage de typographie ou de couleur.

