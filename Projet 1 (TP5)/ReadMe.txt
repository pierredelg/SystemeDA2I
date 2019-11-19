#	DELGRANGE Pierre

##	Ce qui fonctionne

	- /contenu/〈 chemin 〉 	=> Le serveur permet de récupérer un fichier et retourne 406 si c'est un dossier

	- /html/ 〈 chemin 〉 	=> Le serveur renvoie :
									- si c'est un ".csv" 	: une table html avec le contenu du fichier
									- si c'est un ".txt" 	: une version html de son contenu
									- si c'est un dossier 	: une version HTML de son contenu sous forme de liste de 
															  liens permettant de naviguer dans les dossiers fils et  
															  de récupérer la version html(pour les fichiers ".csv",
															  ".txt",dossier) ou le contenu si on clique sur un 
															  fichier.

	- /html/ 〈 chemin 〉 /triepar/ 〈 nombre 〉	=> Si le 〈 chemin 〉est un fichier ".csv", le serveur envoie une version HTML de son contenu en triant sur la colonne numéro 〈 nombre 〉

	- /html/ 〈 chemin 〉 /triepar/ 〈 nom 〉		=> Si le 〈 chemin 〉est un fichier ".csv", le serveur envoie une version HTML de son contenu en triant sur la colonne portant le label 〈nom〉

	- La gestion des erreurs => - 405 lorsque la methode n'est pas GET
								- 505 lorsque la version HTTP n'est pas HTTP/1.1
								- 404 lorsque la cible n’est pas présente
								- 406 lorsque la cible est non acceptable



##	Ce qui ne fonctionne pas

- j'ai une erreur que je ne comprends pas:
	mkfifo: impossible de créer la FIFO '/tmp/requete': Le fichier existe


## Remarque

Je ne suis pas sur d'avoir bien utilisé les scripts, particulièrement get-request.
