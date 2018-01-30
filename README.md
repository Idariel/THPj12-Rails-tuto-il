# THPj12-Rails-tuto-il


## La différence entre un site statique et un site dynamique
> ### Site *statique*
> > Le site est généré une fois pour toutes à partir du HTML et de la CSS. Il est le même pour tout les utilisateurs qui ne peuvent que lire le contenu ou se promener entre les pages. On appelle aussi ça un site vitrine.

> ### Site *dynamique*
> > Les pages du site sont générées à la demande, souvent liées à une base de données. Les pages peuvent être différentes en fonction de l'utilisateur et des données de l'utilisateurs stockées dans la base de données. 

> > *__Exemple__* : le "Bonjour Truc", qui apparaît dès que vous avez rentré vos identifiants, ou encore les pages Facebook (ou celles de votre fournisseur d'email) qui présentent des publicités adaptées à vos goûts (en fonction des pages précédemment visitées), elles seront différentes pour une autre personne.

## Le MVC
![MVC](https://qph.ec.quoracdn.net/main-qimg-5d53e5e0fa03da841194868be4e14a18)
> > Le **MVC**, en anglais **Model - View -Controller** ou en français **Modèle - Vue - Controller**. Est utilisé uniquement dans le cas d'un site dynamique où il faut aller chercher un peu plus d'infos que simplement un fichier HTML et ses CSS associées.

> > Sépare l'application en 3 "modules" indépendants qui permettent d'ordonner le code et de voir plus facilement qui fait quoi. De façon pratique, tous les fichiers correspondant au model sont regroupés dans le dossier Models, ceux correspondants au controller sont dans le dossier Controller et ceux relatifs à la View sont dans Views. 3 bonnes raisons d'utiliser le MVC :

> > - permet de faire évoluer le code plus facilement

> > - la mise à jour du code est plus facile. Les parties sont indépensante

> > - le même modèle peut être utilisé pour générer plusieurs View.

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
> > L'utilisateur demande d'afficher une page. Le navigateur transmet la demande au router qui fournit la route à suivre (/monSite/maPageQuiVaBien) si elle se trouve dans routes.rb. Si le routeur n'a pas la route correspondante dans le fichier routes.rb, il renvoie un message d'erreur à l'utilisateur, sinon, il transmet l'info au Controller. Si la page n'existe pas => message d'erreur.

> > En gros, si je veux aller à Chartres, Mappy (le router) va envoyer ma voiture (la requête) sur la route de Chartres et pas sur celle de Colmar !

## Les Bases de Données
> > On parle en général de bases de données relationnelles.

> > Une base de données relationnelle est un ensemble données qui ont des relations prédéterminées entre elles. Ces éléments sont organisés en tables. 

> > Les tables se présentent sous forme de colonnes et de lignes et regroupent des entités de même type 
Chaque colonne est un attribut auquel correspond un type de donnée particuler (char, varchar, integer, date, ou autre).

> > Les lignes, elles, correspondent à des objets ou des entités appartenant à la table.  

> > Exemple : si on modélisait une bibliothèque, on aurait une table 'users' qui regrouperait tous les abonnées de la bibliothèque et une table 'livres' qui regrouperait tous les livres). Une ligne de chaque table correspondrait à un abonné ou à un livre. Les colonnes, elles, serait le nom de l'abonné, son adresse, ou pour le livre, son titre, le nom de son auteur, etc.

> > Pour chaque table, il y a une ou plusieurs colonnes supplémentaires :
> > - une colonne id qui est un chiffre unique dans la table. Chaque entité a une id différente qui sert à l'identifier (idUser dans la table 'users', ou idLivre dans la table 'livres'). C'est la **clé primaire** ou **clé principale**
> > - la table peut aussi appeler les champs d'autres tables afin de faire la liaison avec elles, il s'agit alors d'une **clé étrangère**
![Exemple de base de données](http://www.ballajack.com/wp-content/uploads/2011/07/base-donnees-mysql.jpg)

## GET / POST
> > Ce sont les deux méthodes les plus utilisées du HTTP (HyperText Transfer Protocol) pour envoyer et recevoir des données. Mais elles ont une première différence majeure :
> > - Les requêtes GET sont systématiquement ajoutée dans l'URL qui apparaît dans la barre d'adresse. Elles sont limitées en taille (impossible d'envoyer des emails) et peuvent être aisément modifiées par un utilisateur malintentionné (injection SQL).

> > - Au contraire, une requête POST est envoyé directement dans le corps de la requête. Elle est donc invisible pour l'utilisateur et de ce fait plus sécurisée et permet d'envoyer des textes de bonne taille.

## Le concept de migration
> > Les migrations permettent de créer et modifier les bases de données de façon structurée et organisée, par l'intermédiare de Ruby on Rails, sans intervention manuelle dans la base et sans avoir à prévenir les autres développers.

> > Rails utilise par défaut Active Record qui permet suivre les migrations qui ont déja été faites et celles qui sont à faire. ActiveRecord indique à Rails que la base de données doit être modifiée.

> > Il suffit d'écrire la modification à faire, puis de faire un $ rails db:migrate pour créer ou mettre à jour la base de données.

> > L'utilisation d'Active Record présente un gros avantage : cette méthode peut être utilisée avec toutes les bases de données. Le développeur peut donc utiliser une base de données pendant le développement et une autre en production sans que cela n'exige de lui de coder différemment.

## Les relations entre les models des BDD
> > La relation entre les models et la base de données, c'est Active Record. 

> > Le model est une class (nom de classe : Toto) avec des attributs. La base de données est un ensemble de tables (nom de table : totos) avec des champs qui correspondent aux attributs du model.

> > Active Record permet de générer la base de données directement à partir des classes des models avec la syntaxe correcte de SQL. 

> > Si on fait un .all sur une class (en mode console irb), on constate qu'Active Record fait une requête SQL en utilisant le nom de la table en minuscule et au pluriel (totos) alors que le .all a été fait en utilisant le nom de classe de type Toto.
![Conventions de nommage Rails / SQL](http://www.isalechat.fr/visuels/namingConvention.png)


> > ActiveRecord est un ORM (Object Relational Mapping). Il représente :

> > - les models et leurs données.
> > - les associations entre les différents models.
> > - les relations hiérarchique entre les models associés par les relations (héritage de classe).
> > - Il valide les models avant qu'ils ne soitent persistés dans la base de données.
> > - Il effectue des opérations dans la base de donnée en utilisant la POO.


## Les fonctions du CRUD
> > Permettent à l'utilisateur d'interagir avec la base de données par l'intermédiaire de l'interface en front-end.

> > - **Create**, permet de créer un nouvel enregistrement. (Il s'agit d'une action POST, d'écriture)

> > - **Read**, permet d'afficher un ou plusieurs enregistrements. (Il s'agit d'une action GET, de lecture)

> > - **Update**, permet de mettre à jour un enregistrement. (Il s'agit d'une action PUT, de mise à jour)

> *> *- Destroy** ou **Delete**, permet de supprimer un enregistrement.

> > 

> > Que dire de plus, ce sont les 4 actions de base que l'ont peut pratiquer sur une base de données et dont on attend qu'elles puissent être faites par l'intermédiaire du code d'une application (créer un utilisateur, accéder à ses données, modifier ses données, supprimer l'utilisateur).
