### Installer

## Etape 1 - Mettre à jour le serveur

````
apt-get update && apt-get upgrade
````

### MySQL sur un serveur distant en ssh


## 1) Pour installer MySQL lancez la commande

````
apt-get install mysql-server mysql-client

Renseignez le mot de passe du superutilisateur pour MySQL. Il est demandé une seconde fois. L’installation continue automatiquement.
````


## 2) Connectez-vous à MySQL lorsque l’installation est terminée.

````
mysql -u root -p

Entrez le password
````


## 3) Créer un nouvel utilisateur MySQL

````
Pour créer un nouvel utilisateur dans mysql, nous devons nous y connecter en tant que root.

mysql –u root –p
````


## 4) Saisissez la commande du dessous en remplaçant New_User et New_User_Password par vos informations.

````
GRANT ALL PRIVILEGES ON *.* TO 'New_User'@'localhost' IDENTIFIED BY 'New_User_Password' WITH GRANT OPTION;
````


## 5) Pour nous connecter avec cette utilisateur utilisez la commande

````
mysql –u New_User –p

Insérez le password
````



### phpMyAdmin sur un serveur distant en SSH

## 1) Pour installer phpMyAdmin lancez la commande

````
apt-get install phpmyadmin

Lorsque le serveur nous le demande, sélectionnez Apache2 à l’aide de la touche espace

Sélectionnez oui
````

````
Lorsque celui-ci vous sera demandé, renseignez le mot de passe Administrateur qui servira pour la connexion à phpMyAdmin.
````


## 2) Verifier son bon fonctionnement

````
Pour vérifier le fonctionnement le cet outil, entrez l’adresse suivante dans un navigateur web

http://ip_de_votre_serveur/phpmyadmin
````

### Apache

## Etape 1 Pour installer Apache utilisez

````
apt-get install apache2
````


## Etape 2 Vérifier le fonctionnement d’Apache

````
Dans le navigateur :

http://ip_de_votre_serveur

ou 

Depuis votre propre serveur à l’aide de la commande lynx :

lynx http://127.0.0.1 (IP du serveur).

Si lynx ne marche pas il faut l'installer avec la commande :

apt-get install lynx

````


#### Php 

## Etape 1 Insérez la commande

````
apt-get install php5 php5-mysql libapache2-mod-php5
````

## Etape 2 Tester son bon fonctionnement 

````
1/ Créez un fichier .php avec la commande nano /var/www/html/info.php
2/ Modifier le contenu en entrant <?php echo “Votre_Texte”;?>
3/ Depuis un navigateur internet, entrez l’adresse http://ip_de_votre_serveur/info.php
4/ Si Votre Texte s'affiche C'est GOOD sinon Cherche la solution.
````