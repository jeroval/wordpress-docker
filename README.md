# wordpress-docker
wordpress with docker compose


1.	Cloner le repository GIT (Vous trouverez les détails de ce dépôt en annexe D)
git clone https://github.com/jeroval/wordpress-docker

2.	Se déplacer dans le répertoire importé

root@debian10-wordpress:cd /wordpress-docker/wordpress-docker
root@debian10-wordpress:/wordpress-docker/wordpress-docker# ls -la
total 48
drwxr-xr-x 7 root             root             4096 23 mars  21:54 .
drwxr-xr-x 3 root             root             4096 23 mars  21:52 ..
drwxr-xr-x 2 root             root             4096 23 mars  21:52 config
-rw-r--r-- 1 root             root             2154 23 mars  21:52 docker-compose.yml
-rw-r--r-- 1 root             root             1587 23 mars  21:54 .env
drwxr-xr-x 8 root             root             4096 23 mars  21:52 .git
-rw-r--r-- 1 root             root              445 23 mars  21:52 Makefile
drwxr-xr-x 6 systemd-coredump systemd-coredump 4096 23 mars  21:54 mysql
-rw-r--r-- 1 root             root               49 23 mars  21:52 README.md
drwxr-xr-x 5 www-data         www-data         4096 23 mars  22:06 wordpress
-rw-r--r-- 1 root             root             1672 23 mars  21:52 wp-auto-config.yml
drwxr-xr-x 2 root             root             4096 23 mars  21:52 wpcli

3.	Changer les variables du .env (les mots de passes sont à titre indicatifs, et seront bien évidemment remplacés)
vi .env

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

