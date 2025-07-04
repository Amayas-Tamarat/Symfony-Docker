# Symfony + Docker Setup Guide

This guide will help you set up a Symfony project using Docker. Follow the steps below to get started.

---

## 1. Prérequis (Prerequisites)

### Modifier le fichier `.env`
Avant de lancer les conteneurs, assurez-vous de modifier le fichier `.env` :
- **Changer le préfixe des conteneurs** (si nécessaire).
- **Optionnel** : Modifier le nom de la base de données et le mot de passe root.

---

## 2. Démarrer les Conteneurs

### Lancer les conteneurs
Utilisez la commande suivante pour démarrer les conteneurs Docker :

```sh
docker-compose up -d 
```

- L'option `-d` exécute les conteneurs en arrière-plan sans afficher les logs dans le terminal.
- Lors du premier lancement, l'installation des conteneurs peut prendre un certain temps.

Une fois démarré :
- **Projet Symfony** : [http://localhost](http://localhost) (You need to create a new project with the command below. )
- **PHPMyAdmin** : [http://localhost:8080](http://localhost:8080) (You may have a error, just refresh your page.)

### Accéder au terminal du conteneur PHP
Si vous avez besoin d'exécuter des commandes dans le conteneur PHP, utilisez :

```sh
docker exec -it symfony_php bash
```

Cela ouvrira un terminal dans le conteneur PHP.

---

## 3. Installer et Configurer Symfony

### Recréer un projet Symfony
Si vous souhaitez créer un nouveau projet Symfony (après avoir vidé le dossier existant) :

```sh
symfony new symfony --dir=/var/www/symfony --no-git && chmod -R 777 /var/www/symfony
```

- Pour spécifier une version particulière de Symfony, ajoutez l'option suivante :

  ```sh
  --version="(version)"
  ```

  - Pour crée un projet avec les plugins nécessaire pour une aplication web déja installés, ajoutez l'option suivante :

  ```sh
  --webapp
  ```

---

## 4. Installation des Packages Symfony (pas nécessaire si vous avez fait une webapp.)

Voici une liste de packages utiles pour Symfony et comment les installer.

### Doctrine (ORM pour la base de données) 
(You need this one for the maker bundle)

Lorsque l'installation demande de modifier/créer la configuration Docker, répondez **non** (`x`).

```sh
composer require symfony/orm-pack
```

### Maker Bundle (Génération de Code)

```sh
composer require --dev symfony/maker-bundle
```

### Routes avec Annotations

```sh
composer require annotations
```

### Twig (Moteur de Templates)

```sh
composer require twig
```

### Security Bundle (Gestion des utilisateurs et de l'authentification)

```sh
composer require symfony/security-bundle
```

### Assets (Gestion des fichiers statiques)

```sh
composer require symfony/asset
```

---

## 5. Prochaines Étapes
- Configurer votre `.env` en fonction de vos besoins.
- Tester l'accès à votre base de données avec PHPMyAdmin.
- Commencer à développer ! 

---
