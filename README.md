[center][color=#2043DF]# docker_sql_mariadb[/color][/center]
[center]## Explication du code Docker Compose[/center]
[center]Voici une explication détaillée de ton fichier docker-compose.yml :[/center]

```version: '3.8'```
[color=#DD51E6]**version: '3.8' :**[/color] Spécifie la version du schéma de configuration Docker Compose. La version 3.8 est une version relativement récente et stable qui supporte de nombreuses fonctionnalités.

```services:```
[color=#DD51E6]**services :**[/color] Définit les différents services (conteneurs) qui composent ton application.

```mariadb:```
[color=#DD51E6]**mariadb :**[/color] Nom du service pour la base de données MariaDB.

```image: mariadb:latest```
[color=#DD51E6]**image:**[/color] mariadb:latest : Spécifie l'image Docker à utiliser pour ce service. Ici, c'est l'image officielle de MariaDB avec le tag latest.

```container_name: mariadb_alone```
[color=#DD51E6]**container_name:**[/color] mariadb_alone : Définit un nom personnalisé pour le conteneur. Cela peut être utile pour identifier facilement le conteneur.

```environment:```
```      MYSQL_ROOT_PASSWORD: rootpassword```
```      MYSQL_DATABASE: mydb```
```      MYSQL_USER: user```
```      MYSQL_PASSWORD: userpassword```
[color=#DD51E6]**environment :**[/color] Définit les variables d'environnement pour configurer la base de données MariaDB.
[color=#DD51E6]**MYSQL_ROOT_PASSWORD :**[/color] Mot de passe pour l'utilisateur root de la base de données.
[color=#DD51E6]**MYSQL_DATABASE :**[/color] Nom de la base de données à créer.
[color=#DD51E6]**MYSQL_USER :**[/color] Nom d'un utilisateur supplémentaire à créer.
[color=#DD51E6]**MYSQL_PASSWORD :**[/color] Mot de passe pour cet utilisateur supplémentaire.

```ports:```
```      - "3306:3306"```
[color=#DD51E6]**ports :**[/color] Mappe le port 3306 du conteneur au port 3306 de l'hôte, permettant d'accéder à la base de données depuis l'extérieur du conteneur.

```volumes:```
```      - mariadb_data:/var/lib/mysql```
[color=#DD51E6]**volumes :**[/color] Définit un volume pour stocker les données de la base de données. Cela permet de persister les données même si le conteneur est supprimé ou recréé.
[color=#DD51E6]**mariadb_data:/var/lib/mysql :**[/color] Monte le volume mariadb_data sur le chemin /var/lib/mysql dans le conteneur, où MariaDB stocke ses données.

```volumes:```
```  mariadb_data:```
[color=#DD51E6]**volumes :**[/color] Définit les volumes utilisés par les services.
[color=#DD51E6]mariadb_data :[/color] Nom du volume qui sera créé et géré par Docker pour stocker les données de MariaDB.