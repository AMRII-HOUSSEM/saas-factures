# 1. Image PHP avec extensions Laravel
FROM php:8.2-fpm

# 2. Installer les dépendances
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libzip-dev \
    libpng-dev \
    libonig-dev \
    curl \
    npm

# 3. Installer extensions PHP
RUN docker-php-ext-install pdo pdo_mysql mbstring zip gd

# 4. Installer Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

# 5. Définir le dossier de travail
WORKDIR /var/www

# 6. Copier les fichiers Laravel
COPY ./backend /var/www

# 7. Installer les dépendances Laravel
RUN composer install

# 8. Exposer le port 9000 pour PHP-FPM
EXPOSE 9000

CMD ["php-fpm"]
