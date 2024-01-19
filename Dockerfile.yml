# Use the official PHP image with Alpine Linux as the base image
FROM php:8.0-fpm-alpine

# Set working directory
WORKDIR /var/www/html

# Install dependencies
RUN docker-php-ext-install pdo pdo_mysql

# Copy Laravel project files to the container
COPY . .

# Install Composer and run it
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer install

# Expose port 9000 for PHP-FPM
EXPOSE 9000

# Start PHP-FPM
CMD ["php-fpm"]