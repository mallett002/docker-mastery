FROM drupal:8.8.2

# install git && remove cache after install (unnecessary bloat)
RUN apt-get update && apt-get install -y git \
 && rm -rf /var/lib/apt/lists/*

# Set dir to /themes for cloning image into (next step)
WORKDIR /var/www/html/themes

# clone repo && change ownership to www-data:www-data (This build runs as root)
RUN git clone --branch 8.x-3.x --single-branch --depth 1 https://git.drupalcode.org/project/bootstrap.git \
 && chown -R www-data:www-data bootstrap

# set working dir back to what drupal expects
WORKDIR /var/www/html

# Don't need anything else. Rest comes from "FROM drupal:8.8.2"
