# Dockerfile

# Base image
FROM php:8.1-fpm
ARG user
ARG uid

# Install dependencies
RUN apt-get update && apt-get install -y \
   git \
   curl \
   zip \
   unzip \
   libonig-dev \
   libxml2-dev \
   libzip-dev \
   libpq-dev

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath xml zip

# Copy the Laravel project to the working directory
# COPY . /var/www/html

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Create system user to run Composer and Artisan Commands
RUN useradd -G www-data,root -u $uid -d /home/$user $user
RUN mkdir -p /home/$user/.composer && \
    chown -R $user:$user /home/$user

# Set working directory
WORKDIR /usr/share/nginx/html

USER $user

# Expose port 9000 for PHP-FPM
EXPOSE 9000

# Start PHP-FPM
CMD ["php-fpm"]
