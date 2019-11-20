#	DELGRANGE Pierre

##	Ce qui fonctionne :

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


##	Ce qui ne fonctionne pas :

	- J'ai une erreur que je n'ai pas réussi à corriger:
	mkfifo: impossible de créer la FIFO '/tmp/requete': Le fichier existe

	(J'ai essayé de faire un rm /tmp/requete mais lorsque le fichier n'existe pas j'ai l'erreur inverse)


## Remarque :

	Je ne suis pas sur d'avoir bien utilisé l'imbrication les scripts, particulièrement get-request.
	En fait, j'ai modifié le fichier get-request afin de pouvoir changer le chemin de la racine, le chemin du modele et le port.
	De ce fait, je ne suis pas sur que cela respecte votre script de test.


## Déroulement du script :

	Le script pour lancer le serveur est http-server dans lequel il est possible d'ajouter les parametres (le chemin de la racine, le chemin du modele et le port).

	Le script http-server appelle le script get-request en lui passant en parametre le chemin de la racine, le chemin du modele et le port.
	
	Ensuite le script get-request appelle le script http-request en lui passant en parametre le chemin de la racine et le chemin du modele.