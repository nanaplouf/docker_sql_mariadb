<p class="text-center text-primary"># docker_sql_mariadb<p>
<p class="text-center">## Explication du code Docker Compose</p>
<p class="text-center">Voici une explication détaillée de ton fichier docker-compose.yml :</p>

```version: '3.8'```
<p style="color: #DD51E6">**version: '3.8' :**</p> Spécifie la version du schéma de configuration Docker Compose. La version 3.8 est une version relativement récente et stable qui supporte de nombreuses fonctionnalités.

```services:```
<p style="color: #DD51E6">**services :**</p> Définit les différents services (conteneurs) qui composent ton application.

```mariadb:```
<p style="color: #DD51E6">**mariadb :**</p> Nom du service pour la base de données MariaDB.

```image: mariadb:latest```
<p style="color: #DD51E6">**image:**</p> mariadb:latest : Spécifie l'image Docker à utiliser pour ce service. Ici, c'est l'image officielle de MariaDB avec le tag latest.

```container_name: mariadb_alone```
<p style="color: #DD51E6">**container_name:**</p> mariadb_alone : Définit un nom personnalisé pour le conteneur. Cela peut être utile pour identifier facilement le conteneur.

```environment:```
```      MYSQL_ROOT_PASSWORD: rootpassword```
```      MYSQL_DATABASE: mydb```
```      MYSQL_USER: user```
```      MYSQL_PASSWORD: userpassword```
<p style="color: #DD51E6">**environment :**</p> Définit les variables d'environnement pour configurer la base de données MariaDB.
<p style="color: #DD51E6">**MYSQL_ROOT_PASSWORD :**</p> Mot de passe pour l'utilisateur root de la base de données.
<p style="color: #DD51E6">**MYSQL_DATABASE :**</p> Nom de la base de données à créer.
<p style="color: #DD51E6">**MYSQL_USER :**</p> Nom d'un utilisateur supplémentaire à créer.
<p style="color: #DD51E6">**MYSQL_PASSWORD :**</p> Mot de passe pour cet utilisateur supplémentaire.

```ports:```
```      - "3306:3306"```
<p style="color: #DD51E6">**ports :**</p> Mappe le port 3306 du conteneur au port 3306 de l'hôte, permettant d'accéder à la base de données depuis l'extérieur du conteneur.

```volumes:```
```      - mariadb_data:/var/lib/mysql```
<p style="color: #DD51E6">**volumes :**</p> Définit un volume pour stocker les données de la base de données. Cela permet de persister les données même si le conteneur est supprimé ou recréé.
<p style="color: #DD51E6">**mariadb_data:/var/lib/mysql :**</p> Monte le volume mariadb_data sur le chemin /var/lib/mysql dans le conteneur, où MariaDB stocke ses données.

```volumes:```
```  mariadb_data:```
<p style="color: #DD51E6">**volumes :**</p> Définit les volumes utilisés par les services.
<p style="color: #DD51E6">**mariadb_data :**</p> Nom du volume qui sera créé et géré par Docker pour stocker les données de MariaDB.