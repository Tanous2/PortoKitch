# PortoKitch · KOSH

Site public : https://tanous2.github.io/PortoKitch/

Design KOSH : identité visuelle, photos originales des restaurants, accueil, cartes, recherche, catégories, favoris, options des produits et navigation horizontale supérieure. Minha est affichée à 18h45, horaire à confirmer auprès de la communauté.

Les interfaces de démonstration et les parcours de commande non opérationnels ne sont pas proposés sur cette publication publique. Aucun compte partagé ni aucune collecte de coordonnées de commande.

## Modifier le site
La branche `main` est la source de GitHub Pages : les changements y sont publiés automatiquement.

- `index.html` : interface KOSH, styles, scripts et catalogue intégrés dans un seul fichier.
- `img/` : photographies originales des restaurants, conservées.
- `data/catalogue.csv` : catalogue d’origine.

## Service de commande
La version KOSH complète dispose séparément d’un serveur Python et d’une base SQLite pour les commandes, comptes et suivi professionnel. Leur hébergement doit être configuré avant de réintroduire ces fonctions ici. GitHub Pages sert des fichiers statiques ; il ne lance pas ce serveur.

Ne pas ajouter de base privée, clés ou données de compte réel au dépôt public.

## Publication depuis GitHub
Le fichier `index.html` livré dans cette archive intègre les styles, scripts, logo et photographie d’accueil. Remplacer uniquement le `index.html` à la racine du dépôt PortoKitch en conservant le dossier `img/` existant. GitHub Pages publie ensuite la branche `main`.
