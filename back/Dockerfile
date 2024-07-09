# Utilisation de l'image PHP avec Apache
FROM php:7.4-apache

# Copier les fichiers du projet dans le répertoire par défaut de l'Apache
COPY . /var/www/html/

# Installer les extensions PHP si nécessaire (exemple pour mysqli)
RUN docker-php-ext-install mysqli

# Exposer le port 80
EXPOSE 80
