# Projet-Avalam

Projet de developpement informatique, réalisation d'une intelligence artificielle pour le jeu de société Avalam. <br/>
Nathan Buchin, 18092.
## Fonctionnement
Serveur web avec cherrypy qui contient la route move.
Move renvoie le prochain coup à jouer déterminer par l'IA et ce coup est renvoyé au format json comprenant la position actuelle du pion et celle vers laquelle il souhaite aller se positionner. <br/>
Au niveau de l'IA en elle-même, elle fonctionne sur base de 3 fonctions principales: next_move, possible_moves (avec apply_dircetion) et random_move.

## Stratégie de l'IA et But des fonctions 
__**possible_moves**__: cette fonction parcourt toutes les cases de la grille pour créer un dictionnaire ayant en clé la position x et y de la case considérée et en valeur une liste de tous les déplacements possibles en filtrant les cas non autorisés par les règles du jeu. Le bon fonctionnement de cette fonction dépend de la fonction apply_direction qui permet d'obtenir le nouvel emplacement du pion déplacé (coordonnées x et y) mais surtout de supprimer les cas qui mènerait à une position en dehors de la grille de jeu. <br/>
__**next_move**__: cette fonction renvoie le prochain coup à jouer en fonction de l'état de la grille de jeu. Elle essaie toujours de mettre le 5e pion permettant de marquer des points lorsque c'est possible et sinon elle délègue le travail a random. <br/>
__**random_move**__: cette fonction choisit aléatoirement une position x et y et fait un choix aléatoire dans la liste des directions possibles à cet emplacement x et y. <br/>
<br/>
<br/>
Le fichier __AI_Bot.py__ contient le code du serveur avec l'IA et __subscribed.py__ contient le code pour l'inscription d'un joueur sur la plateforme.
