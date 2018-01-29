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

## Les Bases de Données
Une base de données (database en anglais), permet de stocker et de retrouver l'intégralité de données brutes ou d'informations en rapport avec un thème ou une activité ; celles-ci peuvent être de natures différentes et plus ou moins reliées entre elles. Dans la très grande majorité des cas, ces informations sont très structurées, et la base est localisée dans un même lieu et sur un même support. 

Ruby On Rails utilise un ORM, un système qui transforme les tables de ta base de donnée en version orienté objet... pour faire simple, tu apprends une nouvelle façon de manipuler ta base de donnée.

Pour Rails, c'est Active Record L'intérêt, ce n'est pas de te compliquer la vie à apprendre un nouveau langage, que du contraire. En utilisant Active Record, Rails va traduire ton code pour que les requêtes se fassent sur ta base de donnée. Peu importe la syntaxe de ta base de donnée, le code sera le même, du code Ruby. C'est très pratique si tu veux changer de système de DB pendant ton projet.

Dans Rails, on peut trouver un dossier DB, dans lequel on trouve : 
- un fichier schema.rb : une vue synthètiques sur les bases de données
- un dossier migrate où on trouve les diffentes ases de données

Il faut savoir que Rails utilise par default sqlite3 comme base de données, on peut voir ceci dans le fichier config/database.yml.

## GET / POST
Deux méthodes couramment utilisées pour une requête-réponse entre un client et un serveur sont: GET et POST.

- GET - Demande des données d'une ressource spécifiée
- POST - Soumet les données à traiter à une ressource spécifiée

La méthode GET

Notez que la chaîne de requête (paires nom / valeur) est envoyée dans l'URL d'une requête GET: /test/demo_form.php?name1=value1&name2=value2

Quelques autres notes sur les requêtes GET:

- Les requêtes GET peuvent être mises en cache
- Les requêtes GET restent dans l'historique du navigateur
- Les requêtes GET peuvent être mises en signet
- Les requêtes GET ne doivent jamais être utilisées avec des données sensibles
- Les requêtes GET ont des restrictions de longueur
- Les requêtes GET ne doivent être utilisées que pour extraire des données

La méthode POST

Notez que la chaîne de requête (paires nom / valeur) est envoyée dans le corps du message HTTP d'une requête POST: POST /test/demo_form.php HTTP / 1.1 Hôte: w3schools.com nom1 = valeur1 & nom2 = valeur2

Quelques autres notes sur les requêtes POST:

- Les requêtes POST ne sont jamais mises en cache
- Les requêtes POST ne restent pas dans l'historique du navigateur
- Les requêtes POST ne peuvent pas être mises en signet
- Les requêtes POST n'ont aucune restriction sur la longueur des données

## Les concepts de migration
Les migrations dans Rails nous permettent de faire évoluer le schema de notre base de donnée facilement, sans faire de SQL. On écrit une migration et celle-ci update notre bdd.

Une migration est donc une sous-classe de la classe ActiveRecord::Migration. A ce titre, elle définit deux méthodes : une méthode « up », qui permet d'ajouter une modification à la base de données, et une méthode« down », qui permet de retirer cette modification de la base de données.

+ **Exemple :** Dans le cas de la création d'un site type blog considérons le code dessous :

		class CreateArticles < ActiveRecord::Migration[5.0]
		  def change
		    create_table :articles do |t|
		      t.string :title
		      t.text :text

		      t.timestamps
		    end
		  end
		end
	
Ce code va créer : 
- Crée une table d'articles à é colonnes
- Créer au format string, un titre
- Créer au format texte, le body de l'article
- timestamp : pour dire la date de création et de maj de l'a BD 

## Les relations entre les models des BDD

## Les fonctions du CRUD
Ce terme permet de désigner les actions de bases pour une ressource prédéfinie :
- **Create**, permet de créer un nouvel enregistrement : 

		POST: /{resources}
- **Read**, permet d'afficher un ou plusieurs enregistrements :

		GET: /{resources} et GET: /{resources}/:id
- **Update**, permet de mettre à jour un enregistrement

		PUT: /{resources}/:id

- **Destroy**, permet de supprimer un enregistrement : 

		DELETE: /{resources}/:id


[logo]: https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/200px-Ruby_On_Rails_Logo.svg.png
