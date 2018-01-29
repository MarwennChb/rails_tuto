# Découverte de Ruby on Rails ![alt text][logo]

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

<p align="center">

<img src="https://www.pluralsight.com/content/pluralsight/en/blog/creative-professional/sta/static-dynamic-websites-theres-difference/_jcr_content/main/hero_blog_block/image-res.img.jpg/1446605940972.jpg" alt="Diff Static Dynamic" target="_blank">

</p>

## Le MVC
Le modèle MVC est un principe de code qui consiste à séparer l’affichage des informations (la vue), les actions de l’utilisateur (le contrôleur) et l’accès aux bases de données (le modèle).

+ Le **modèle** traite principalement les données et les interactions avec la base de données. Contient les données à afficher.

+ La **vue** il contient la présentation de l'interface graphique.

+ Le **contrôleur** le gars qui gère tout, il fait le lien entre les view et le model et renvoi l'information vers le navigateur. Il contient la logique qui fait tourner le programme.

<p align="center">

<img src="http://french.railstutorial.org/images/figures/mvc_detailed-full.png" alt="Modèle MVC" target="_blank">

</p>

Cheminement d'une requête :
1. L’utilisateur envoie une requête HTTP (via le navigateur) vers le server Rails
2. Le rooter la transmet au Controller via la méthode indexe
3. Le contrôleur appelle le modèle, celui-ci va récupérer les données concernant cette requete
4. Le modèle consulte la base de données 
5. Le modèe retourne les données au contrôleur
6. Le contrôleur décide de la vue à afficher et va l’appeler au sein du View
7. Le code HTML de la vue est envoyé au controleur 
8. Le controlleur encoie la vue à afficher au navigateur

## Les routes
Les routes permettent d’interpréter les URL et d’orienter vers les bonnes actions des controlleurs. La configuration se trouve dans le fichier config/routes.rb .

On peut utiliser la commande 
  GET /articles(:id) articles#index

On peut également utiliser l'active record et déclarer : 
  resources :articles



[logo]: https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/200px-Ruby_On_Rails_Logo.svg.png
