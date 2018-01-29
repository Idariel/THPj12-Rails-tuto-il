# THPj12-Rails-tuto-il


## La différence entre un site statique et un site dynamique
> ### Site *statique*
> > Le site est généré une fois pour toutes à partir du HTML et de la CSS. Il est le même pour tout les utilisateurs qui ne peuvent que lire le contenu ou se promener entre les pages. On appelle aussi ça un site vitrine.

> ### Site *dynamique*
> > Les pages du site sont générées à la demande, souvent liées à une base de données. Les pages peuvent être différentes en fonction de l'utilisateur et des données de l'utilisateurs stockées dans la base de données. 

> > *__Exemple__* : le "Bonjour Truc", qui apparaît dès que vous avez rentré vos identifiants, ou encore les pages Facebook (ou celles de votre fournisseur d'email) qui présentent des publicités adaptées à vos goûts (en fonction des pages précédemment visitées), elles seront différentes pour une autre personne.

## Le MVC
> > Le **MVC**, en anglais **Model - View -Controller** ou en français **Modèle - Vue - Controller**. Est utilisé uniquement dans le cas d'un site dynamique où il faut aller chercher un peu plus d'infos que simplement un fichier HTML et ses CSS associées.

> > Sépare l'application en 3 "modules" indépendants qui permettent d'ordonner le code et de voir plus facilement qui fait quoi. De façon pratique, tous les fichiers correspondant au model sont regroupés dans le dossier Models, ceux correspondants au controller sont dans le dossier Controller et ceux relatifs à la View sont dans Views. 3 bonnes raisons d'utiliser le MVC :

> > > - permet de faire évoluer le code plus facilement

> > > - la mise à jour du code est plus facile. Les parties sont indépensante

> > > - le même modèle peut être utilisé pour générer plusieurs View.

> > Le modèle MVC, c'est comme si 2 personnes (Model - View) avec des fonctions bien précises travaillaient ensemble sous la houlette d'un contrôleur (Controller) pour rendre un travail adapté à chaque utilisateur.

> Le **model**
> > _**Logique Métier**_ : Manipule les données (en lien avec la base de données).

> La **view**
> > _**Logique Graphique**_ : Contient toutes les éléments de l'interface graphique qui doivent être affichés. C'est elle qui "créée" la page à afficher avec les données qu'elle possède déjà (HTML/CSS) et les données qui lui sont transmises par le Model. On parle aussi d'_**Interface Homme Machine**_.

> Le **controller**
> > _**Logique Applicative**_ : C'est un peu celui qui distribue les actions à faire. Il reçoit la demande (requête) de page de l'utilisateur, la redirige vers le Model (qui discute avec la base de données pour récupérer les données pertinentes). 

> > Une fois que le Model a fini son traitement, la requête et les données sont renvoyées vers le Controller qui redirige le tout vers la View. La View va chercher la page HTML et la CSS qui vont bien, intègre les données fournies par le Model (et la base de données), et renvoie la nouvelle page ainsi fabriquée vers le Controller qui lui affiche alors la page sur l'écran de l'utilisateur.


## Les routes
> > Un site est une collection de pages qui peuvent être cartographiées comme un atlas routier. Chaque page a une adresse par rapport à la page d'accueil. On appelle cette adresse une route, qui est stockée dans le fichier routes.rb.
> > L'utilisateur demande d'afficher une page. Le navigateur transmet la demande au router qui fournit la route à suivre (/monSite/maPageQuiVaBien) si elle se trouve dans routes.rb. Si le routeur n'a pas la route correspondante dans le fichier routes.rb, il renvoie un message d'erreur à l'utilisateur (j'avais envie de dire qu'il fait Seppuku, mais je n'aurais pas été compréhensible), sinon, il transmet l'info au Controller. Si la page n'existe pas => message d'erreur.

> > En gros, si je veux aller à Chartres, Mappy (le router) va envoyer ma voiture (la requête) sur la route de Chartres et pas sur celle de Colmar !

## Les Bases de Données
> > On parle en général de bases de données relationnelles.

Une base de données relationnelle est un répertoire d'éléments de données dotés d'une relation prédéfinie entre eux. Ces éléments sont organisés en des tableaux définis, composés de colonnes et de rangées. Les tableaux permettent de répertorier les informations sur les objets qui doivent être représentés dans la base de données. Chaque colonne d'un tableau répertorie un certain type de données et chaque champ indique la valeur réelle d'un attribut. Les rangées d'un tableau représentent un ensemble de valeurs liées à un objet ou à une entité. Chaque rangée d'un tableau peut être marquée avec un identifiant unique, qu'on appelle une clé principale, et les rangées reprises dans plusieurs tableaux peuvent être associées en utilisant des clés étrangères. Ces données sont accessibles de plusieurs manières sans qu'il ne soit nécessaire de réorganiser les tableaux de base de données eux-mêmes.
## GET / POST

## Le concept de migration
Migrations are a convenient way for you to alter your database in a structured and organized manner. You could edit fragments of SQL by hand but you would then be responsible for telling other developers that they need to go and run them. You’d also have to keep track of which changes need to be run against the production machines next time you deploy.

Active Record tracks which migrations have already been run so all you have to do is update your source and run rake db:migrate. Active Record will work out which migrations should be run. It will also update your db/schema.rb file to match the structure of your database.

Migrations also allow you to describe these transformations using Ruby. The great thing about this is that (like most of Active Record’s functionality) it is database independent: you don’t need to worry about the precise syntax of CREATE TABLE any more than you worry about variations on SELECT * (you can drop down to raw SQL for database specific features). For example you could use SQLite3 in development, but MySQL in production.

## Les relations entre les models des BDD

## Les fonctions du CRUD
> > **Create**, permet de créer un nouvel enregistrement. (Il s'agit d'une action POST, d'écriture)

> > **Read**, permet d'afficher un ou plusieurs enregistrements. (Il s'agit d'une action GET, de lecture)

> > **Update**, permet de mettre à jour un enregistrement. (Il s'agit d'une action PUT, de mise à jour)

> *> *Destroy** ou **Delete**, permet de supprimer un enregistrement.

> >

> > Que dire de plus, ce sont les 4 actions de base que l'ont peut pratiquer sur une base de données et dont on attend qu'elles puissent être faites par l'intermédiaire du code d'une application (créer un utilisateur, accéder à ses données, modifier ses données, supprimer l'utilisateur).
