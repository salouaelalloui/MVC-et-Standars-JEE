Application web basée sur MVC et Standards JEE
l'objectif de cet atelier c'est la mise en place d'une application  web qui va se charger de la gestion des commandes de plusieurs clients , en utilisant les Standars JEE et en se basant sur le patron de conception MVC (Model,Controller,View).
Dans cet atelier en respectant le MVC , on a créé la couche model qui contient les classes entités (les java beans se situent dans le package ma.fstt.etities),les classes DAO (se situent dans le package ma.fstt.dao ) et les interfaces qui seront être implémenter par les classes dao. 
pour la couche view on a créé plusieurs pages jsp qui vont se charger des composants de l'interface en utilisant les expressions JSTL( conçernant les boucles , l'affichage et les conditions) .
pour la couche controller contient la servlet qui joue le role de controlleur qui va lier la couche model et la couche view.
et pour avoir une liaison entre les couches MVC on utilise les annotations @inject et @ApplicationScoped à l'aides dépendences à ajouter au niveau du pom.xml

Pour le diagramme de classe on a travailler sur 4 classes : Client, Commande, Produit , Ligne_commande qui sont liées par des relations , 
entre Client et Commande : relation one to many (un client peut passer plusieurs commandes ) 
entre Commande et Ligne_Commande : relation one to many ( une commande contient plusieurs lignes de commandes )
entre Produit et Ligne_commande : relation one to many ( un produit a plusieurs ligne de commande)
de sorte que la classe Ligne_Commande va contenir les clés étrangèrs des classes Produit et Commande  et la classe Commande va contenir le clé étrangèr de la classe Client. 
pour la partie vue on commence par l'inscription du client ou il s'inscrire  ,puis on passe à une autre page qui demande d'entrer l'identifiant du client afin de l'utliser pour commander , une fois il entre un idantifiant incorrecte , il va être dirigé vers une page qui mentionne que l'identifiant est incorrecte, sinon il passe à la page qui affiche la liste de tous les produits en affichant le nom,le prix unitaire , et la quantité de stock , on lui donne la possibilité de commander de façcon que lorsqu'il va passer une commande il va pourvoir constater que la quantité du stock diminue, on  donne aussi la possibilité de consulter la liste des commandes effectuées en affichant la date de chaque commande , et en cliquant sur une commande on aura la liste de tous les produits choisis par le client dans cette commande (ici réside le rôle de la classe Ligne_commande ), comme on a traiter la modification des produits , et aussi la suppression.




 
