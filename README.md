# LU2IN013 - Projet de Développement Sorbonne Université

*Ce projet a été réalisé dans le cadre du cours de Projet de Développement à Sorbonne Université de janvier 2024 à mai 2024.*


# Notice d'utilisation de l'application

Methodes de votes et leurs consequences.

On crée un Political Compass avec des électeurs et des candidats. Chaque votant a une liste ordonnée des candidats (préférés au moins préférés), et on teste les différentes méthodes de vote pour voir leurs influences sur le résultat final. On implémente une méthode de Monte-Carlo en fonction des différents types de vote, et des cartes prédéfinies (par exemple une carte représentant la France en fonction des statistiques des différentes élections, etc).

Mini-sprint : Démocratie Liquide

On a créé une fonction délégation qui choisit à qui déléguer en utilisant l'algorithme fournit, dans cette fonction on a calculer les probabilités normalisées (on divise le niveau de compétence de l'electeur par la somme du niveau de compétence de tous les électeurs éligibles à recevoir le vote) et on a utilisé les probabilités cumulatives pour faire le choix.
On a créé une fonction Zone qui calcule la liste des electeurs qui n'ont pas délégué dans la zone d'un individu et on a créé une fonction qui met à jours les poids des electeurs.
Enfin on a mis à jour les fonctions de votes pour prendre en compte les poids d'importance.
Notre fonction STV ne fonctionne pas sur l'interface graphique mais elle fonctionne sur les tests (on est toujours entrain de résoudre ce problème)


----------------------------------------------------------------------------------------------------

## Projet de Simulation de Vote

Ce projet est dédié à la simulation de différents types de votes, y compris mais non limité aux méthodes coplanaires Borda, STV, etc. Le système intègre également l'intelligence artificielle pour la reconnaissance visuelle utilisée dans la création de populations, ainsi que pour la reconnaissance vocale permettant d'exécuter des commandes simples.
Le logiciel intègre également un système de journalisation permettant de mieux tracer les actions effectuées(app.log).

## Problèmes connus

Actuellement, un conflit de dépendances entre MediaPipe et OpenCV (cv2) empêche le fonctionnement correct des méthodes de Monte Carlo.

## Performances

La génération de populations dépassant 1 million d'individus peut devenir lente.
La complexité du calcul des fonctions de vote est constante en fonction du nombre d'individus et linéaire en fonction du nombre de candidats.

## Limitations

Il est possible de simuler des tournois sans limite de tours. Cependant, la simulation est limitée à 8 candidats pour inclure des manipulations dans l'arbre des décisions, et à 10 candidats maximum pour maintenir un temps de calcul raisonnable sur un ordinateur personnel.

## Instructions pour utilisateurs de processeurs Apple ARM (M1, M2, M3)

Les utilisateurs disposant de processeurs ARM développés par Apple doivent installer un environnement spécifique :

Exécutez le fichier install_env.sh.
En cas de bugs liés à la bibliothèque MediaPipe, désinstallez mediapipe-silicon et installez la version standard de mediapipe pour Windows ou Linux.
## Lancement :

Dans le terminal, entrer la commande : 

```bash
./run_app.sh
```


## Fonctionnalités :

Dans la fenêtre principale, plusieurs options afin de paramétrer la map :

    - Soumission : Ajout d'un rayon de population en entrant le rayon et la position du centre du cercle (x, y)
      ou cliquer directement sur la grille et entrer le nombre d'individus composant la population avec un rayon prédéfini
    - ajouter 0.1 : Augmenter le rayon du cercle de 0.1
    - ajouter -0.1 : Diminuer le rayon du cercle de 0.1
    - Supprimer : Supprimer la population
    - Activer CV : Activer le système de vision par ordinateur
    - Choix du type de génération :
        - Uniforme
        - Beta
        - Exponentiel
        - Triangulaire

    Une fois fini et que tous les paramètres ont été choisis :

    - Lancer l'application : Créer la map 3D ou 2D (au choix)


Une fois que la map a été créée :

    - Menu :
        - Soumission : Ajout manuel d'un candidat sur la map en entrant son nom, prénom, charisme et sa position (x, y)
        - Générer un Candidat : Génération d'un candidat avec un nom, prénom, charisme et une position (x, y) aléatoire
        - Sauvegarder : Sauvegarde du modèle actuel dans un fichier dont il faut entrer le nom (si non existant, il est automatiquement créé)
        - Recharger : Chargement d'un modèle dans un fichier dont il faut entrer le nom
        - Règles de vote (Liste des différentes règles de vote) :
            - Copeland
            - Borda
            - Pluralite
            - STV
            - Approbation
    
    - Statistiques :
        - Arbre tournoi : Affiche le résultat du tournoi sous forme d'arbre
        - Bilan Carbone : Affiche l'emission carbone depuis le lancement du logiciel
        - Visualisation 3D : Représentation des individus sur une surface 3D

    - Commande vocale


## Données émission carbone :

!! ATTENTION !!

Les mesures faites pour l'émission carbone ont été sur un ordinateur comportant un système AMD et NVIDIA.  
Les mesures ont été faites en France de code iso FRA.  
Les mesures sont susceptibles de changer d'un ordinateur à un autre.  
Les mesures sont susceptibles de changer dans le temps.  


## Credits :

Zhou Jeremy

Khamis Yara

Nistor Iarina

Kinane-Daouadji Isaac (scrum master)

Benhaddou Chady
