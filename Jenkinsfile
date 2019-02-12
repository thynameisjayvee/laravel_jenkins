pipeline {
  agent {
    docker {
      image 'php'
    }

  }
  stages {
    stage('error') {
      steps {
        sh '''apt-get update && apt-get install -y git zip
curl -L https://phar.phpunit.de/phpunit.phar -o /usr/local/bin/phpunit
chmod +x /usr/local/bin/phpunit
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
apt-get install -y libfreetype6-dev
apt-get install -y libjpeg62-turbo-dev
apt-get install -y libpng-dev
docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/
docker-php-ext-install gd
apt-get install -y zip
apt-get install -y unzip
apt-get install -y zlib1g-dev
docker-php-ext-install zip
docker-php-ext-configure pdo_mysql --with-pdo-mysql
docker-php-ext-install pdo_mysql'''
      }
    }
  }
}