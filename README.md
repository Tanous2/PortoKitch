# Porto Kitch

Plateforme de commande casher à Porto : restaurants, épicerie, agenda communautaire, jeux d'attente, espace restaurateur.

## Contenu
- `index.html` : toute l'application (interface, logique, catalogue) dans un seul fichier, sans dépendance à installer.
- `img/` : logos, affiches des restaurants, photos des événements.
- `data/catalogue.csv` : la carte d'origine de chaque enseigne (source du catalogue intégré dans `index.html`).

## Voir l'application
Ouvrir `index.html` depuis un petit serveur web (par exemple `python3 -m http.server` dans ce dossier, puis http://localhost:8000), ou activer GitHub Pages sur le dépôt.

## État actuel : maquette fonctionnelle, pas encore un service en ligne
Hors de Claude, l'application tourne en **mode démo** : commandes, cartes modifiées, notes, classement et événements restent sur l'appareil et ne sont partagés avec personne.

Dans le code, tout ce qui doit devenir une vraie base de données passe par deux points :
- `put(chemin, données)` pour écrire ;
- les abonnements `db.collection(...).onSnapshot(...)` en fin de fichier pour lire en direct.

Collections attendues : `menus/<restaurant>` (carte modifiée, stock, horaires, lien Revolut, codes promo, code d'accès), `orders/<id>` (commandes, statut, note, réclamations), `events/<id>` (agenda), `scores/<joueur>` (classement des jeux), `conf/main` (code organisateur).

## Reste à faire pour une mise en ligne
1. Un serveur et une vraie base de données derrière `put()` et les abonnements.
2. De vrais comptes restaurateurs (aujourd'hui : un simple code, `0000` par défaut, vérifié dans le navigateur, donc sans valeur de sécurité).
3. Protection des données clients : aujourd'hui toute personne ayant accès à la base lit toutes les commandes.
4. Calcul des prix, du stock et des codes promo côté serveur (aujourd'hui dans le navigateur).
5. Paiement : lien Revolut du restaurateur, validation manuelle. Pas de confirmation automatique.
6. Livraison : la course Glovo est réservée à la main par le restaurateur.
7. Notifications, suivi GPS, impression des tickets.
8. Remplacer les événements d'exemple et faire confirmer les horaires de prière (calculés sur le coucher du soleil à Porto).

## Réglages utiles dans le code
- Commission par commande : `COM` (1,50 €). Frais de livraison : `FEE` (3,50 €).
- Horaires par défaut : 19h-23h, sauf `HRS` (O'Kaffé 10h-22h, Le J 12h30-14h30).
- Langues : objets `T.fr`, `T.en`, `T.he`, `T.pt`.
