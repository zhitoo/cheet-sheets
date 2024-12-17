FROM dunglas/frankenphp
 
RUN install-php-extensions \
    pcntl
    RUN apt-get update && apt-get install -y build-essential libonig-dev libpng-dev libzip-dev libjpeg62-turbo-dev \
    libfreetype6-dev locales zip jpegoptim optipng pngquant gifsicle nano unzip git curl

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install extensions
RUN docker-php-ext-install mysqli pdo_mysql mbstring zip exif pcntl \
    && docker-php-ext-configure gd --with-jpeg=/usr/include/ --with-freetype=/usr/include/ \
    && docker-php-ext-install gd

# RUN pecl install -o -f redis \
#     &&  rm -rf /tmp/pear \
#     &&  docker-php-ext-enable redis

RUN apt-get update && \
    apt-get install -y libxml2-dev
RUN docker-php-ext-install soap
RUN docker-php-ext-install intl

RUN apt install -y default-mysql-client

# RUN apt-get install -y ffmpeg

RUN apt-get update && apt-get install -y libssl-dev
RUN docker-php-ext-configure ftp --with-openssl-dir=/usr
RUN docker-php-ext-install ftp

RUN docker-php-ext-install bcmath
RUN apt-get install libpq-dev -y
RUN docker-php-ext-install pdo pdo_pgsql
 
# COPY . /app
 
# ENTRYPOINT ["php", "artisan", "octane:frankenphp", "--workers=30", "--max-requests=200"]