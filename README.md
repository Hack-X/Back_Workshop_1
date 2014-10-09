Workshop X - Cours #1
=======

Objectifs de l'atelier :

* Installer un environnement de développement pour la partie serveur (API)
* Découvrir des tutoriaux
* Réaliser un `Hello World !`

Pour la partie serveur, nous utiliserons ces technologies :

* Ruby
* Rails
* Git
* SQLite3 / MySQL / PostgreSQL



# Ressources

#### Tutoriaux

Le tutoriel le plus simple est complet est la documentation officielle de Rails : [http://guides.rubyonrails.org/getting_started.html
](http://guides.rubyonrails.org/getting_started.html)


# Prérequis & Installation


### Installation de Rails & Ruby

* Windows : [http://railsinstaller.org/](http://railsinstaller.org/)
* Mac : [https://github.com/tokaido/tokaidoapp](https://github.com/tokaido/tokaidoapp)

** Attention : ** il y a différentes versions de Ruby (1.9.3, 2.0.0 etc...) et de Rails. Nous utiliserons ici Ruby 2.0.0 et Rails 4.1. Votre version de rails et ruby n'est pas très grave, mais il est important d' **avoir la même version de Rails chez tous les étudiants d'un même groupe **


### Git & Github

Comme vu lors du cours d'introduction, Git sera utilisé en permanence pour **versionner** le code et **collaborer**. Cela servira aussi à vos coachs pour vous aider et vous débloquer par moment. Il est donc indispensable de commencer par ça.

Nous utiliserons **GitHub** comme serveur de Git en profitant de l'offre gratuite pour les comptes open sources.

Avant de commencer, il faudra donc :

* Vous créer un compte sur Github
* Vous pourrez ensuite créer une __organization__ sur Github qui correspondra à votre groupe (__Workshop-Polytechnique__ dans cet exemple).

N'hésitez pas à aller sur cette petite application interactive pour vous former à Git & Github : [http://try.github.io](http://try.github.io)

### Editeur de code

Il vous faudra un IDE ou éditeur de code tout au long de ce cours. Le plus simple sera le mieux, vous pouvez par exemple utiliser [**Sublime Text 3**](http://www.sublimetext.com/3).

### Avant de commencer

Vous devez donc avoir accès à un Terminal / une console, et pour tester que tout est installé vous pouvez réaliser ces petits tests.

    $ git --version
    git version 1.9.3 (Apple Git-50)
    $ ruby --version
    ruby 2.0.0p481 (2014-05-08 revision 45883) [universal.x86_64-darwin14]
    $ rails --version
    Rails 4.1.6

Le test est validé si à chaque fois un numéro de version s'affiche (même si il n'est pas identique à celui présenté ici) et échoue si vous une réponse du type `command not found`


# Workshop

#### Etape 1 : Création d'un projet sur Github

* Création d'un **repository** sur Github avec un fichier Readme (comme celui là)
* Cloner le projet sur sa machine avec la commande `git clone`

Vous devez donc avoir à la fin de cette étape le projet quasiment vide sur votre machine.

#### Etape 2 : Génération d'une première application rails

* A l'intérieur du projet, vous allez générer l'application avec la commande `rails new .` : cela va créaer une application qui aura le même nom que votre dossier courant (ici Cours_1). Cette commande va générer un certain nombre de fichiers et dossier.


        $ ls
        Gemfile      README.rdoc  bin          db           public       vendor
        Gemfile.lock Rakefile     config       lib          test
        README.md    app          config.ru    log          tmp


* Vous pouvez ensuite ouvrir le dossier en entier avec Sublime Text par exemple pour voir ces mêmes dossiers.
* Enfin, vous allez lancer votre serveur rails en local avec la commande `rails server` ou `rails s` dans sa version courte. Allez ensuite sur `http://localhost:3000` avec votre navigateur. Vous devez obtenir ça :

![Welcome Aboard Rails](https://photos-5.dropbox.com/t/1/AAADFZoKCDHyU7NpLqUGAJdd3SuU5Ag0DaBVi2_a3clmlA/12/13814809/png/1024x768/3/1412287200/0/2/Screenshot%202014-10-02%2022.29.48.png/OhlolFndE-Ta-JLubg6oalSmprCoJukhXSDEe9rgoV4 =600x "Welcome Aboard Rails")


#### Etape 3 : Création d'un Hello World

Comme le message de Rails nous y invite, nous allons créer 3 éléments pour réaliser notre Hello World

* Création d'un controller : je demande à rails de générer un controller qui s'appelle "Home" avec une méthode "Index".

        $ rails g controller home index
        create  app/controllers/home_controller.rb
        route  get 'home/index'
        invoke  erb
        create    app/views/home
        create    app/views/home/index.html.erb
        invoke  test_unit
        create    test/controllers/home_controller_test.rb
        invoke  helper
        create    app/helpers/home_helper.rb
        invoke    test_unit
        create      test/helpers/home_helper_test.rb
        invoke  assets
        invoke    coffee
        create      app/assets/javascripts/home.js.coffee
        invoke    scss
        create      app/assets/stylesheets/home.css.scss

Comme on peu le voir en dessous, cette commande va générer un certain nombre de dossiers et fichiers dont 2 nous intéressent particulièrement : le controller `app/controllers/home_controller.rb` et la vue correspondante `app/views/home/index.html.erb`.

* Il faut ensuite créer une **route** comme nous invite rails, qui va diriger l'adresse http://localhost:3000/ (notre route root sans mauvais jeux de mots) en allant ajouter la ligne `root 'home#index'` au fichier `config/routes.rb`

On peut ensuite voir ceci en allant sur notre adresse [http://localhost:3000](http://localhost:3000)

![Home index](https://photos-2.dropbox.com/t/1/AAAwAbPLF06OTVMurNLFKUXNu-u8Xs6DoqqaQ1CzR3ZuwQ/12/13814809/png/1024x768/3/1412287200/0/2/Screenshot%202014-10-02%2022.55.15.png/Zwsodnf235wKlJUnwF2u1GjdavT9-y0NfNBCig1v4m4 =300x "Home index")

* Vous allez maintenant allez modifier la vue correspondante pour obtenir un (joli) `Hello World` à la place de ce `Home#index`


#### Etape 4 : Push du projet sur Github

* Vous allez maintenant **commiter** votre code et le **pusher** sur Github

        $ git add -A
        $ git commit -m 'mon tout premier commit'
        $ git push



Bravo, vous avez réussi !








