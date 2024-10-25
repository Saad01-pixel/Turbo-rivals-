# Turbo-rivals-

Description:

Le jeu "Turbo Rivals" est un jeu en 2D qui est développé sur Unity et C#. Il est un type ``Arcade`` et un caméra ``top down``, avec le joueur qui conduit une voiture de course contre 9 autres Intelligence artificielle. Le but final est de se rendre au point finale avant les autres véhicules. 
Il va se dérouler dans plusieurs pistes de courses avec des objets spéciaux qui peuvent impacter le joueur ou le (IA) dans la course. 


---------------------
Hiérarchy de classe  ( miro utilisé et gemini pour architecture)

![6d048b10ccfe74860b43397873938212](https://github.com/user-attachments/assets/1f60f07a-3860-4e10-83d5-6c8ebc9e7dc6)


----------------------------------------

Architecture:

Hiérarchie de classes et composants

| Class | Attributes |
|---|---|
| Véhicule |	Position, Vitesse, Direction, Santé, Bouclier, BoostCount	Mouvement(), Accélérer(), Freiner(), TournerGauche(), TournerDroite(), UtiliserBoost(), UtiliserBouclier(), SubirDommages() |
| VéhiculeIA |	NiveauDifficulté	TrouverCheminLePlusCourt(), UtiliserObjetStratégiquement() |
| VéhiculeJoueur |	EntréeJoueur	GérerEntrée() |
| Objet |	Type, Durée, RayonEffet	AppliquerEffet(Véhicule) |
| Circuit |	Disposition, Obstacles	PositionValide(Position), ObtenirWaypointProche(Position) |
| Course |	Participants, TourActuel, LigneArrivée	Démarrer(), MettreÀJour(), EstCourseFinie() |

| Fonctions |
|---|
Explication des fonctions:

- Véhicule:

 Mouvement() : Déplace le véhicule.
Accélérer(): Augmente la vitesse du véhicule.
Freiner(): Réduit la vitesse du véhicule.
TournerGauche(): Tourne le véhicule vers la gauche.
TournerDroite(): Tourne le véhicule vers la droite.
UtiliserBoost(): Active le boost du véhicule.
UtiliserBouclier(): Active le bouclier du véhicule.
SubirDommages(): Applique des dégâts au véhicule.

- VéhiculeIA:

TrouverCheminOptimal(): Calcule le meilleur chemin pour atteindre la ligne d'arrivée.
UtiliserObjetStratégiquement(): Décide quand et comment utiliser les objets spéciaux.

- VéhiculeJoueur:

GérerEntrée(): Gère les entrées du joueur (clavier, manette) pour contrôler le véhicule.

- Objet:

AppliquerEffet(Véhicule): Applique l'effet de l'objet sur un véhicule (par exemple, accélérer, ralentir, créer un obstacle).

- Circuit:

PositionValide(Position): Vérifie si une position donnée est valide sur le circuit.
ObtenirWaypointProche(Position): Trouve le waypoint le plus proche d'une position donnée.

- Course:

Démarrer(): Initialise la course et lance les véhicules.
MettreÀJour(): Met à jour l'état de la course à chaque frame (position des véhicules, temps écoulé, etc.).
EstCourseFinie(): Vérifie si la course est terminée (un véhicule a franchi la ligne d'arrivée).

------------------------------

Les patrons de conceptions utilisés:

- 1. héritage ou héritage :

AIVehicle et PlayerVehicle héritent de la classe de base Vehicle, favorisant la réutilisabilité du code et une structure hiérarchique.
- 2. Strategy Pattern/ ou conception comportementale :

La classe AIVehicle peut employer différentes stratégies d'IA (par exemple, agressive, défensive, équilibrée) en utilisant différents algorithmes pour trouver le chemin le plus court et utiliser les objets de manière stratégique. Cela permet un comportement d’IA flexible et adaptable.
- 3. Modèle d'observateur :

La classe Race peut agir comme un sujet, notifiant d'autres objets (par exemple, des éléments de l'interface utilisateur, des effets sonores) lorsque l'état de la course change (par exemple, la position des véhicules, la récupération d'objets, l'achèvement de la course). Cela garantit que les différentes parties du jeu sont mises à jour de manière cohérente.
- 4. Modèle Singleton :

Des classes telles que GameManager et InputHandler peuvent être implémentées en tant que singletons pour garantir qu'il n'y a qu'une seule instance de chacune tout au long du jeu, offrant ainsi un accès et une coordination globaux.
Ces modèles de conception contribuent à une architecture de jeu bien structurée, flexible et maintenable.

----------------------------------
Algorithm utilisé:
Pour un jeu de course comme Turbo Rivals, Alpha-Beta Pruning est généralement un meilleur choix. Il offre un bon équilibre entre précision et efficacité. En supprimant les branches inutiles, il peut réduire considérablement le coût de calcul tout en trouvant des mouvements forts.
