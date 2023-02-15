# Les containers

- ## Lancer les containers.

```Shell
docker-compose up -d
```

Le préfix -d` empêche d'avoir les logs dans le terminal après le lançement.

S'ils sont lancés pour la première fois, les containers vont metre du temps à s'installer

- ## Accéder au terminal du container PHP pour les commandes

```Shell
docker exec -it symfony_php bash
```

# Symfony

- ## Recréer le projet symfony (bien vider le dossier symfony avant)

> symfony new symfony --dir=/var/www/symfony --no-git && chmod -R 777 /var/www/symfony

Pour spécifier la version de symfony if faut ajouter `--version="(version)"` derriere `--no-git`

- ## Les Packages

    - ### Annotation Routes
    > composer require annotations

    - ### Twig
    > composer require twig

    - ### Doctrine
      - dire non 'x' quand on demande de modifier/créer la config docker
    > composer require symfony/orm-pack
 
    - ### Maker Bundle
    > composer require --dev symfony/maker-bundle

    - ### Security Bundle
    > composer require symfony/security-bundle