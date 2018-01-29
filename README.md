# THPj12-Rails-tuto-il


## La différence entre un site statique et un site dynamique
### Site *statique*
> > Le site est généré une fois pour toutes à partir du HTML et de la CSS. Il est le même pour tout les utilisateurs qui ne peuvent que lire le contenu.

> ### Site *dynamique*
> > Les pages du site sont générées à la demande, souvent liées à une base de données. Les pages peuvent être différentes en fonction de l'utilisateur et des données de l'utilisateurs stockées dans la base de données. 

> Exemple : le "Bonjour Truc", qui apparaît dès que vous avez rentré vos identifiants, ou encore les pages Facebook (ou celles de votre fournisseur d'email) qui présentent des publicités adaptées à vos goûts (en fonction des pages précédemment visitées), elles seront différentes pour une autre personne.

## Le MVC
> Le **MVC**, en anglais **Model - View -Controller** ou en français **Modèle - Vue - Controller*. Est utilisé uniquement dans le cas d'un site dynamique où il faut aller chercher un peu plus d'infos que simplement un fichier HTML et ses CSS associées.

> Sépare l'application en 3 "modules" qui permettent d'ordonner le code et de voir plus facilement qui fait quoi. 
> Le modèle MVC, c'est comme si 2 personnes (Model - View) avec des fonctions bien précises travaillaient ensemble sous la houlette d'un contrôleur (Controller) pour rendre un travail adapté à chaque utilisateur.

Le **model**
> Manipule les données (en lien avec la base de données).

La **view**
> Contient toutes les éléments de l'interface graphique qui doivent être affichés. C'est elle qui "créée" la page à afficher avec les données qu'elle possède déjà (HTML/CSS) et les données qui lui sont transmises du Model. Dans certains cas, on parle d'IHM (Interface Homme Machine).

Le **controller**
> C'est un peu celui qui distribue les actions à faire. Il reçoit la demande (requête) de page de l'utilisateur, la redirige vers le Model (qui discute avec la base de données pour récupérer les données pertinentes). 

> Une fois que le Model a fini son traitement, il renvoie la page vers le Controller qui la dirige alors vers la View. La View va chercher la page HTML et la CSS qui vont bien, intègre les données fournies par le Model (et la base de données), et renvoie la nouvelle page ainsi fabriquée vers le Controller qui lui affiche alors la page sur l'écran de l'utilisateur.


## Les routes

## Les Bases de Données

## GET / POST

## Le concept de migration

## Les relations entre les models des BDD

## Les fonctions du CRUD
> **Create**, permet de créer un nouvel enregistrement. (Il s'agit d'une action POST, d'écriture)

> **Read**, permet d'afficher un ou plusieurs enregistrements. (Il s'agit d'une action GET, de lecture)

> **Update**, permet de mettre à jour un enregistrement. (Il s'agit d'une action PUT, de mise à jour)

> **Destroy** ou **Delete**, permet de supprimer un enregistrement.

> Que dire de plus, ce sont les 4 actions de base que l'ont peut pratiquer sur une base de données et dont on attend qu'elles puissent être faites par l'intermédiaire du code d'une application (créer un utilisateur, accéder à ses données, modifier ses données, supprimer l'utilisateur).
