# wordpress-docker
wordpress with docker compose


1.	Cloner le repository GIT (Vous trouverez les détails de ce dépôt en annexe D)

git clone https://github.com/jeroval/wordpress-docker

2.	Se déplacer dans le répertoire importé


3.	Changer les variables du .env (les mots de passes sont à titre indicatifs, et seront bien évidemment remplacés)


4.	Lancer la création du conteneur (2 méthodes possibles), Avec ou sans fichier Makefile

Avec le fichier Makefile (recommandé) ?

Se déplacer dans le dossier contenant le fichier makefile et taper la commande suivante.

make install

Puis attendre la fin de l’installation avec le lancement du healthcheck qui vérifiera l’état des services

Si je n’ai pas le fichier Makefile ? (Dépannage)
Trois lignes de commandes docker-compose :

-	Construire des images d’applications docker

-	Démarrer l’installation de Wordpress en mode détaché

-	Vérifier la disponibilité des services de docker WordPress

docker-compose build

docker-compose up -d 

docker-compose run --rm healthcheck

	-d      (Démarre les conteneurs en option détachée)
	
	--rm (Retirer les conteneurs lorsqu’ils sont arrêtés)

Accéder à la console Wordpress via l’IP ou le nom de domaine sélectionné précédemment.
Dans notre cas, c’est http://localhost/wp-admin/

Une fois l’installation terminé, nous arrivons sur la page web WordPress d’accueil, celui-ci nous propose de configurer la langue ainsi qu’un compte admin pour le site web. Il sera possible de personnaliser le site et notamment par la suite ajouter des plugins pour la double authentification.

