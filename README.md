# Prérequis

- Changer les identifiants git à la fin de [docker/php/Dockerfile](docker/php/Dockerfile)

# Les containers

- ## Lancer les containers.

>docker-compose up -d

Le préfix -d` empêche d'avoir les logs dans le terminal après le lançement.

S'ils sont lancés pour la première fois, les containers vont metre du temps à s'installer

- ## Accéder au terminal du container PHP pour les commandes

>docker exec -it symfony_php bash

# Symfony

- ## Recréer le projet symfony

>symfony new symfony --dir=/var/www/symfony

Pour spécifier la version de symfony if faut ajouter `--version="(version)"`

- ## Les Packages

    - ### Annotation Routes
    > composer require annotations

    - ### Twig
    > composer require twig

    - ### Doctrine
    > composer require symfony/orm-pack
 
    - ### Maker Bundle
    > composer require --dev symfony/maker-bundle

    - ### Security Bundle
    > composer require symfony/security-bundle