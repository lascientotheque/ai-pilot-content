(Machine_Learning)=
# Apprentissage automatique et algorithmes

## Aperçu

|||
:--- | :--- |
|Âge |10 à 14 ans|
|Notions abordées|Intelligence artificielle, algorithme, apprentissage par renforcement, logique, sens des opérateurs ET et OU.|
| Durée| 2h ou 3h avec extension le jeu de Nim en Scratch|
| Dispositif pédagogiques| Par groupe de 2|

**Objectif**

Aborder les mécanismes d’apprentissage automatiques omniprésents en matière d’intelligence artificielle et, plus spécifiquement, l’apprentissage par renforcement en utilisant des « machines » physiques jouant au jeu de Nim.



**Matériel**

Par équipe :

* 8 gobelets numérotés de 1 à 8
* 8 allumettes
* Boules / jetons colorés ou numérotés pour représenter 1, 2 ou 3

<img src="images/Game_Setup.png" width="300"></img>

**Annexes**

* Fiche explicative : le jeu de Nim en Scratch

<h1>Description détaillée</h1>

*Inspirée et adaptée à partir d’une activité proposée par Marie-Duflot-Kremer, maîtresse de conférence en informatique à l'Université de Lorraine.*

## Phase 1 : présentation des règles du jeu de Nim

* L’animatrice.eur explique que le ou plutôt les jeux de Nim sont très anciens et existent dans de nombreuses variantes. Le principe du jeu de cette activité est le suivant :
	* 8 allumettes sont posées sur une table 
	* 2 joueurs prennent chacun leur tour une, deux ou trois allumettes
	* le joueur qui prend le ou les dernières allumettes a gagné

* Il est ensuite demandé aux jeunes de jouer plusieurs parties jusqu’à ce qu’ils trouvent une stratégie gagnante. 

* Les binômes sont ensuite invités à proposer oralement leurs hypothèses.

* La stratégie gagnante se résume en deux conditions :
	* Laisser l’adversaire commencer
	* Faire en sorte de toujours laisser un multiple de 4 allumettes à l’adversaire 

	Exemple : si l’adversaire commence et pioche 1 allumette sur les 8 posées, le joueur en piochera 3 pour en laisser 4 à l’adversaire. Ce dernier ne pourra ainsi jamais piocher la dernière allumette quel que soit le nombre qu’il choisit de piocher pour son deuxième coup.

* Si besoin, il est possible de mettre les jeunes sur la voie en leur demandant si cela change quelque chose de commencer ou non la partie ou découper en quatre groupes de quatre allumettes (4x4)

* Expliquer que la stratégie gagnante est un algorithme, c’est à dire une méthode, une recette, un programme qu’il suffit à ‘ordinateur d’exécuter pour gagner.  

* Cette version est assez simple pour que les règles soient maîtrisées rapidement, et que les participant.e.s puissent trouver la stratégie seul.e.s ou sans trop d'aide. Elle est également assez riche pour pouvoir aborder les notions de répétition et de test. C'est donc un bon moyen pour parler d'algorithmique. Pour complexifier un peu, il est possible de jouer avec un nombre plus élevé d’allumettes.

## Phase 2 : présentation du principe de la machine qui apprend à jouer au jeu de Nim

* L’animatrice.eur fait d’abord une démonstration devant toute la classe en jouant la « machine » contre un « joueur » (un élève ou toute la classe) pour expliquer le principe :

	* la « machine » est représentée par les 8 gobelets numérotés de 1 à 8
	* un jeton de chaque valeur est placé dans chaque gobelet
	* 8 allumettes sont posées sur la table
	* le joueur et la machine jouent plusieurs parties en commençant à tour de rôle
	* au fur et à mesure des parties, la machine apprend en appliquant les principes suivants :

		* Lorsque c’est à son tour de jouer, la machine pioche au hasard un jeton dans le pot correspondant à la dernière allumette restant en jeu. Elle place le jeton devant le pot et retire le nombre d’allumettes correspondant au jeton tiré. Si le nombre d’allumettes qu’il faut retirer est plus grand que le nombre d’allumettes restantes, elle élimine simplement ce jeton et pioche un autre jeton.  

		* Si la machine gagne la manche, elle remet les jetons tirés dans les différents pots.

		* Si la machine perd, elle retire le dernier jeton qu’elle a tiré lors de la manche et remet le ou les autres pions dans les pots correspondants. Si un pot est vidé de ses jetons, on le retourne.

		* Si la machine tombe sur un pot vide (impossibilité de piocher un jeton), elle abandonne.


* Les participant.e.s sont ensuite réparti.e.s en équipes de 2 ou 3 personnes pour faire l’entraînement de la machine (un ou plusieurs élèves doivent « manipuler » la machine, les autres sont le ou les joueurs qui jouent contre la machine)

* Les participant.e.s qui jouent contre la machine sont invité.e.s à essayer de trouver la stratégie permettant de la battre

* Après un certain nombre de manches (idéalement après qu’un des pots ait été retourné), l’animatrice.eur interroge les participant.e.s pour faire émerger la stratégie qui permet de jouer de manière optimale et de gagner si les circonstances s’y prêtent.

**Apprentissage automatique**

* Lorsque la machine perd, elle en « déduit » que son dernier coup était fautif. Elle apprend de son erreur en retirant la solution fautive soit le dernier pion concerné. Si pour une situation de jeu, le pot ne contient plus de jetons, cela signifie qu’il n’existe pas de possibilité de gagner et elle doit abandonner.

* Après un certain nombre de manches, la machine va de mieux en mieux jouer et commettre de moins en moins d’erreurs.

* Après un certain nombre de manches, la machine présente la configuration finale ci-dessous dans laquelle elle joue de manière optimale. Il en ressort que si elle commence (c’est différent avec un nombre impair d’allumettes), elle doit abandonner car elle ne peut gagner (sauf si son adversaire commet des erreurs).

<img src="images/Nimm_Phase_2.png" width="300"></img>

**La stratégie**

* Pour 8 allumettes en jeu, un joueur est certain de gagner lorsqu’il reste 3 allumettes au maximum en jeu. Donc, si son adversaire se trouve dans la situation où il reste 4 allumettes (maximum d’allumettes qu’il est possible de retirer + 1), il lui sera impossible de gagner. Quel que soit le nombre d’allumettes qu’il retire, le joueur aura la possibilité de retirer la dernière. De fil en aiguille, lorsqu’on recule dans le jeu, la stratégie consiste à amener l’adversaire à tomber sur un multiple de 4 allumettes. 

*Généralisation*

* Si le nombre d’allumettes qui restent en jeu est un multiple du nombre d’allumettes maximum que l’on peut retirer + 1 alors on ne peut pas gagner sauf si l’adversaire joue mal. 
* Dans le cas contraire, pour gagner à coup sûr, il faut s’arranger pour laisser un multiple du nombre d’allumettes maximum que l’on peut retirer + 1 à l’adversaire. Autrement dit, il faut retirer le multiple du nombre d’allumettes maximum que l’on peut retirer + 1 du nombre d’allumettes restantes pour gagner.
* Lorsque les deux joueurs jouent de manière optimale, il ne peut y avoir de réel gagnant.

<img src="images/Nimm_Classroom.jpg" width="600"></img>

Les différentes étapes sont expliquées dans la vidéo ci-dessous :
[https://www.youtube.com/watch?v=eFlRZ7tRFc8&t=6s](https://www.youtube.com/watch?v=eFlRZ7tRFc8&t=6s)

## Phase 3 : Formulation de l’algorithme

* Demander aux jeunes de formuler avec leurs mots, en leur donnant des indices si besoin, l’algorithme permettant à la machine d’apprendre à jouer au jeu de Nim.
Convention
allumettes restantes = nombre d’allumettes restantes en jeu
max = nombre d’allumettes maximum à retirer par coup

	* Tant qu’il y a des allumettes en jeu
	
		* Si allumettes restantes est un multiple de max +1 (allumettes restantes modulo max+1 = 0)
		
			* Je joue un # aléatoire d’allumettes car j’ai perdu si l’adversaire joue bien
			* Alternative : Je retire 1 allumette en espérant que l’adversaire joue mal (pour lui laisser le maximum de choix)
		* Sinon
			* Je retire le nombre d’allumettes nécessaire pour laisser un multiple de max+1 allumettes à l’adversaire
			* Alternative : Je retire du nombre d’allumettes restantes, le multiple de (max+1) 

			
**Pour aller plus loin : montrer le processus d’apprentissage automatique.**

Afin de montrer la totalité du processus d’apprentissage, il est possible d’utiliser le programme scratch dont les fonctionnalités sont détaillées dans la fiche « Jeu de Nim en Scratch » en annexes.

## ANNEXE : Jeu de Nim en Scratch

Voir [fiche complète sur le site de la Scientothèque](https://scratch.mit.edu/projects/561543016).

## Références et liens utiles

* [Activité développée par Marie-Duflot-Kremer](https://members.loria.fr/MDuflot/files/med/IAnim.html), maîtresse de conférence en informatique à l'Université de Lorraine 
* Vidéos explicatives :
	* [Conférence de Marie-Duflot-Kremer lors de la finale du concours de création de jeux numériques Jeux Fabrique (de 1 :00 à 21 :30)](
https://www.dailymotion.com/video/x7magex?start=50)
	* [Comprendre l’informatique en jouant au jeu de Nim](
https://www.youtube.com/watch?list=PLWvGMqXvyJAPSMFgCiy6qVHW9bAPu93X5&v=3WIghG_B4nU )
* [Site « Tangente éducation » et publication « Bibliothèque Tangente »](
http://www.tangente-education.com/article.php?art=4076&dos=158) - 
Bibliothèque Tangente – « Intelligence artificielle – L’alliance des mathématiques et de la technologie »
* [Laboratoire d’InfoRmatique en Image et Systèmes d’Information (LIRIS)
La machine qui apprend à (bien) jouer toute seule (Eric Duchêne et Aline Parreau)](
https://projet.liris.cnrs.fr/lirismed/index.php?id=la-machine-qui-apprend-a-jouer-toute-seule)
