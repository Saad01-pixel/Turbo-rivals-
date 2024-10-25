# Turbo-rivals-

Description:

Le jeu "Turbo Rivals" est un jeu en 2D qui est développé sur Unity et C#. Il est un type ``Arcade`` et un caméra ``top down``, avec le joueur qui conduit une voiture de course contre 9 autres Intelligence artificielle. Le but final est de se rendre au point finale avant les autres véhicules. 
Il va se dérouler dans plusieurs pistes de courses avec des objets spéciaux qui peuvent impacter le joueur ou le (IA) dans la course. 


---------------------
Hiérarchy de classe 

![6d048b10ccfe74860b43397873938212](https://github.com/user-attachments/assets/1f60f07a-3860-4e10-83d5-6c8ebc9e7dc6)


----------------------------------------

Architecture:

Fonctions des attributs de classe
Position du véhicule, vitesse, direction, santé, bouclier, BoostCount Move(), Accelerate(), Brake(), SteerLeft(), SteerRight(), UseBoost(), UseShield(), TakeDamage()
AIVehicle DifficultyLevel FindShortestPath(), UseItemStrategically()
PlayerVehicle PlayerInput HandleInput()
Type d'élément, durée, EffectRadius ApplyEffect (Véhicule)
Disposition du circuit, obstacles IsValidPosition (Position), GetNearestWaypoint (Position)
Participants à la course, CurrentLap, FinishLine Start(), Update(), IsRaceFinished()
