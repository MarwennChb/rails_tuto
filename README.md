# Découverte de Ruby on Rails

1. La différence entre un site statique et un site dynamique
2. Le MVC
3. Les routes
4. Les Bases de Données
5. GET / POST
6. Le concept de migration
7. Les relations entre les models des BDD
8. Les fonctions du CRUD

## La différence entre un site statique et un site dynamique
Une page web statique est une page web dont le contenu ne varie pas en fonction de la requête (de qui demande la page), en gros tout le monde recoit le même contenu.

Une page web dynamique est générée à la demande et son contenu varie en fonction de qui effectue la demande (heure, adresse IP de l'ordinateur du demandeur, formulaires remplis...).

## Le MVC
Le modèle MVC est un principe de code qui consiste à séparer l’affichage des informations (la vue), les actions de l’utilisateur (le contrôleur) et l’accès aux bases de données (le modèle).

+ Le **modèle** est ce que l’on appelle un objet, c’est le cœur de l’application. Il traite principalement les données et les interactions avec la base de données.

+ La **vue** traite ce que nous voyons dans notre navigateur web, elle restitue le modèle au sein de notre interface web et permet à l’utilisateur d’interagir avec le modèle.

+ Le **contrôleur** fait le lien entre le modèle et la vue, il gère les requêtes des utilisateurs et détermine les traitements qui doivent être effectués pour chaque action. Il va utiliser les données du modèle, les traiter et les envoyer à la vue pour que celle-ci les affiche.

<p align="center">

    <img src="http://french.railstutorial.org/images/figures/mvc_detailed-full.png" alt="Modèle MVC" target="_blank">

</p>
