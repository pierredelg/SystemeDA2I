DELGRANGE Pierre

Ce qui fonctionne

	- /contenu/〈 chemin 〉 	=> Le serveur permet de récupérer un fichier et retourne 406 si c'est un dossier

	- /html/ 〈 chemin 〉 	=> Le serveur renvoie :
									- si c'est un ".csv" 	: une table html avec le contenu du fichier
									- si c'est un ".txt" 	: une version html de son contenu
									- si c'est un dossier 	: une version HTML de son contenu sous forme de liste de 
															  liens permettant de naviguer dans les dossiers fils et  
															  de récupérer le contenu si on clique sur un fichier.


– de type /html/ pour les fichiers CSV, les fichiers texte et les répertoires
– de type /contenu/ pour les autres fichiers
– si 〈chemin〉 correspond à un autre type de fichier de 〈racine〉 le serveur considère la cible comme non acceptable ( 406 )
– sinon le serveur avertit que la cible n’est pas présente ( 404 )
/html/ 〈 chemin 〉 /triepar/ 〈 nombre 〉
/html/ 〈 chemin 〉 /triepar/ 〈 nom 〉
– si 〈chemin〉 correspond à un fichier CSV une version HTML de son contenu est renvoyée par le serveur en triant sur
la colonne numéro 〈nombre〉 ou la colonne portant le label 〈nom〉. Si la colonne demandée est inexistante le serveur
avertit que la cible n’est pas acceptable ( 406 )
– si 〈chemin〉 correspond à un autre type de fichier de 〈racine〉 le serveur avertit que la cible n’est pas acceptable ( 406 )
– sinon le serveur avertit que la cible n’est pas présente ( 404 )
Toutes les autres cibles sont considérées par le serveur comme non acceptables ( 406 ).

Ce qui ne fonctionne pas
Ce qui n'a pas été fait
tout ce que vous jugez utile de me préciser