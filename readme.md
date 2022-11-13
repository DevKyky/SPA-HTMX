# Single-Page Application with HTMX

Découverte d'HTMX ([documentation](https://htmx.org/examples/)).

Ce projet utilise Symfony 6.1 avec PHP 8.1.


## I. Prérequis

- [Composer](https://getcomposer.org/)
- [NodeJS](https://nodejs.org/en/)
- [WampServer](https://www.wampserver.com/) (ou équivalent)
- [Symfony CLI](https://symfony.com/download)

Il faudra également penser à indiquer les informations pour la base de données
dans le fichier .env.local et à créer la base puis la structure pour utiliser la page de Contact du projet.

```
symfony console d:d:c
symfony console d:s:u --force

# OU (sans Symfony CLI)

php bin/console d:d:c
php bin/console d:s:u --force
```

## II. Installation

- ### Symfony CLI

  Installer [Scoop](https://scoop.sh/) depuis un terminal PowerShell avec ces commandes :
  ```
  Set-ExecutionPolicy RemoteSigned -Scope CurrentUser # Optional: Needed to run a remote script the first time
  irm get.scoop.sh | iex
  ```
  
  puis, depuis une invite de commandes :
  ```
  scoop install symfony-cli
  ```

- ### Depuis ce projet
  - Télécharger le [zip](https://github.com/DevKyky/SPA-HTMX/archive/refs/heads/main.zip) puis, dézippez-le.
  - Ouvrez votre terminal sur le dossier venant d'être dézippé.
  - Utilisez les commandes :
    - `composer install`
    - `npm install --force`
  - (optionnel) un framework CSS ou votre propre CSS. Ce projet utilise [Skeleton](http://getskeleton.com/).

- ### De zéro

  (avec Symfony CLI)
  
  ```
  # Projet
  symfony new your_project --version="6.1.*" --webapp
  
  # Debug Toolbar
  cd your_project
  composer req symfony/apache-pack
  
  # Webpack Encore
  composer req symfony/webpack-encore-bundle
  npm i --force
  ```
  
  #### Mise en place de HTMX :
  
  Utiliser la commande `npm i htmx.og`.
  Dans `assets\app.js`, ajoutez à la fin du fichier :
  
  ```
  import 'htmx.org';
  window.htmx = require('htmx.org');
  ```