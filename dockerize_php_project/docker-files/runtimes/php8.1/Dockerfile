FROM docker.arvancloud.ir/php:8.1-fpm
# Install dependencies
RUN apt-get update && apt-get install -y build-essential libonig-dev libpng-dev libzip-dev libjpeg62-turbo-dev \
    libfreetype6-dev locales zip jpegoptim optipng pngquant gifsicle nano unzip git curl

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install extensions
RUN docker-php-ext-install mysqli pdo_mysql mbstring zip exif pcntl \
    && docker-php-ext-configure gd --with-jpeg=/usr/include/ --with-freetype=/usr/include/ \
    && docker-php-ext-install gd

RUN pecl install -o -f redis \
    &&  rm -rf /tmp/pear \
    &&  docker-php-ext-enable redis

RUN apt-get update && \
    apt-get install -y libxml2-dev
RUN docker-php-ext-install soap

RUN apt install -y default-mysql-client

#get composer
COPY --from=docker.arvancloud.ir/composer:latest /usr/bin/composer /usr/local/bin/composer
RUN cd /var/www/html

ARG USER_ID
ARG GROUP_ID
RUN addgroup --gid $GROUP_ID user
RUN adduser --disabled-password --gecos '' --uid $USER_ID --gid $GROUP_ID user
USER user

EXPOSE 9000
CMD ["php-fpm"]
