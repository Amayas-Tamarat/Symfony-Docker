# Pr�requis

- Changer les identifiants git � la fin de [docker/php/Dockerfile](docker/php/Dockerfile)

# Les containers

- ## Lancer les containers.

>docker-compose up -d

Le pr�fix -d` emp�che d'avoir les logs dans le terminal apr�s le lan�ement.

S'ils sont lanc�s pour la premi�re fois, les containers vont metre du temps � s'installer

- ## Acc�der au terminal du container PHP pour les commandes

>docker exec -it symfony_php bash

# Symfony

- ## Recr�er le projet symfony

>symfony new symfony --dir=/var/www/symfony

Pour sp�cifier la version de symfony if faut ajouter `--version="(version)"`

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