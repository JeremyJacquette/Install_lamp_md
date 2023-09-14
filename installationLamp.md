###  Liste des commandes linux pour mêttre en place un serveur local LAMP : 

# Mettre à jour la bibliothèque en ligne
`sudo apt update`


# Installer le serveur web
`sudo apt install apache2`


# Démarrer le serveur web
 `sudo service apache2 start`


# Connaitre l'adresse IP de la VM
`ip address`


# Installer un serveur MySQL
`sudo apt install mysql-server`

# Démarrer le serveur MySQL
`sudo service mysql start`


# Se connecter à MySQL
`sudo mysql -u root` 


# Créer un utilisateur admin
`CREATE USER 'admin'@'%' IDENTIFIED BY 'pass';`


# Donner toutes les permissions
`GRANT ALL PRIVILEGES ON *.* TO 'admin'@'%';`
`FLUSH PRIVILEGES;`
`Installer le repo pour PHP`
`sudo add-apt-repository ppa:ondrej/php`
`sudo apt update` 


# Installer PHP
`sudo apt install -y php8.2 libapache2-mod-php8.2`
`sudo apt install -y php8.2-{mbstring,curl,zip,mysql,mysqli,gd,xml,redis}` 


# Installer composer
`sudo apt install composer -y`


# Autoriser la réécriture d'URL
`sudo a2enmod rewrite`


`sudo nano /etc/apache2/sites-available/000-default.conf`


```
<Directory /var/www/html>
Options Indexes FollowSymLinks
AllowOverride All
Require all granted
</Directory>
```

# Installer Adminer

`sudo apt install adminer`
`sudo a2enconf adminer`
`sudo systemctl reload apache2`


# Mettre un raccourci de "html" sur le bureau

`sudo ln -s /var/www/html /home/nom/Bureau/`

# en cas de problème de droit d'écriture dans le dossier HTML :
`sudo chmod -R 777 /var/www/html` 

# Ne pas oublier de scanner les SSH keys si il y as conflit pour cloner des repo avec : 
`ssh-keyscan github.com >> ~/.ssh/known_hosts `