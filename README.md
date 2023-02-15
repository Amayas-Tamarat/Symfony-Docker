# Les containers

- ## Lancer les containers.

```Shell
docker-compose up -d
```

Le pr�fix -d` emp�che d'avoir les logs dans le terminal apr�s le lan�ement.

S'ils sont lanc�s pour la premi�re fois, les containers vont metre du temps � s'installer

- ## Acc�der au terminal du container PHP pour les commandes

```Shell
docker exec -it symfony_php bash
```

# Symfony

- ## Recr�er le projet symfony (bien vider le dossier symfony avant)

> symfony new symfony --dir=/var/www/symfony --no-git && chmod -R 777 /var/www/symfony

Pour sp�cifier la version de symfony if faut ajouter `--version="(version)"` derriere `--no-git`

- ## Les Packages

    - ### Annotation Routes
    > composer require annotations

    - ### Twig
    > composer require twig

    - ### Doctrine
      - dire non 'x' quand on demande de modifier/cr�er la config docker
    > composer require symfony/orm-pack
 
    - ### Maker Bundle
    > composer require --dev symfony/maker-bundle

    - ### Security Bundle
    > composer require symfony/security-bundle