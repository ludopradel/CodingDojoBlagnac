## Coding Dojo

J'ai eu l'occasion d'animer un bon nombre de coding dojo, dans les différentes entreprises avec lesquelles j'ai travaillé ainsi que dans les équipes dans lesquelles j'étais en prestation.

Je vais profiter de la série de Coding dojo actuelle pour écrire sur les katas que l'on pratique.

__Contexte :__
coding dojo toutes les 2 semaines entre midi et deux (~1h30) avec un noyau fixe d'une petite dizaine de personnes.

 * [Roman Numerals]
 * [String calculator]
 * [Mars Rover]
 * [OCR Bank]
 * [Refactoring : Guilded Rose]
 * [Refactoring : Katastrophic]

## #1 Roman Numerals 

__Objectif :__  Écrire une méthode de conversion d'un nombre arabe en nombre romain
```
1 : I                    1 : I
2 : II                   5 : V
3 : III                  10 : X
4 : IV                   50 : L
5 : V                    100 : C
9 : IX                   500 : D
10 : X                   1000 : M
```

Cette première session est une session de découverte. mon but, en tant que facilitateur est de présenter le format du coding dojo et d'intriguer les développeurs avec ces nouvelles pratiques de développements.

J'ai donc pris l'habitude de commencer cette première session par une [présentation rapide du Coding Dojo](https://github.com/ludopradel/pres-codingdojo).
A la fin de la présentation j'enchaine tout de suite par un Kata simple mais qui permet de se mettre rapidement dans le bain et d'appréhender les premières notions :
 
 * Format d'un coding dojo
 * Format d'un test unitaire (Arrange / Act / Assert)
 * TDD
 * Pair programming
 * Ne pas avoir peur de montrer comment on code
 * Copier / Coller c'est mal !

Pour ce premier Kata, je préfère proposer un langage de programmation maitrisé par le plus grand nombre.
Je laisse habituellement chaque participant derrière le clavier 5 à 10 minutes, pour que chacun passe au moins 1 fois (l'utilisation d'un timer est souhaitable).
Il est intéressant de se garder un temps en fin de session pour la rétrospective. Pour le coup, je n'hésite pas à stopper les développeurs qui voudraient à tout prix finir l'application ! Le temps de la rétrospective est important pour reparler des notions amener durant la séance.

__Attention__, En tant que facilitateur, il faut avoir préparer le kata au préalable et il est préférable de l'avoir joué de plusieurs façon différentes.
Vous serez plus à même de répondre aux questions des participants.

__Attention__ à ne pas vouloir diriger les gens vers votre solution, il existe plusieurs solutions à ce kata.

__Attention__ à faire en sorte que le refactoring ermerge du code, n'hésitez pas à faire revenir en arrière une personne qui avait une idée en tête et qui casse tout pour proposer/ imposer sa solution.

## #2 String Calculator

__Objectif :__  Écrire une méthode qui prend en paramètre une chaine de caractère contenant des entiers, et qui retourne la somme de ces entiers.

```
1. Create a simple String calculator with a method int Add(string numbers)

    * The method can take 0, 1 or 2 numbers, and will return their sum (for an empty string it will return 0) for example “” or “1” or “1,2”
    * Start with the simplest test case of an empty string and move to 1 and two numbers
    * Remember to solve things as simply as possible so that you force yourself to write tests you did not think about
    * Remember to refactor after each passing test

2. Allow the Add method to handle an unknown amount of numbers
   
3. Allow the Add method to handle new lines between numbers (instead of commas).
    * the following input is ok:  “1\n2,3”  (will equal 6)
    * the following input is NOT ok:  “1,\n” (not need to prove it - just clarifying)
   
4. Support different delimiters
    * to change a delimiter, the beginning of the string will contain a separate line that looks like this:   “//[delimiter]\n[numbers…]” for example “//;\n1;2” should return three where the default delimiter is ‘;’ .
    * the first line is optional. all existing scenarios should still be supported
   
5. Calling Add with a negative number will throw an exception “negatives not allowed” - and the negative that was passed.if there are multiple negatives, show all of them in the exception message stop here if you are a beginner.

6. Numbers bigger than 1000 should be ignored, so adding 2 + 1001  = 2
7. Delimiters can be of any length with the following format:  “//[delimiter]\n” for example: “//[--]\n1--2--3” should return 6
8. Allow multiple delimiters like this:  “//[delim1][delim2]\n” for example “//[*][%]\n1*2%3” should return 6.
9. Make sure you can also handle multiple delimiters with length longer than one char
```


Aucune difficulté technique pour ce kata, choisir un langage de programmation maitriser par un plus grand nombre.

Le String Calculator est très intéressant car on découvre les les fonctionnalités au fur et à mesure, il n'est donc pas possible d'anticiper sur ce qu'il va être demandé. Je vais jusqu'à fournir la fonctionnalité n°2 seulement dès que les personnes sont satifaits de la solution donnée pour la fonctionnalité n°1.
Voici le lien vers un fichier pdf que j'ai imprimé sur papier cartonné, chaque carte contient une fonctionnalité à développer, il ne faut pas passer à la carte suivante avant d'avoir développé la fonctionnalité actuelle.

=> Cela oblige les développeurs à se focaliser sur le besoin actuel uniquement, sans chercher à deviner ce qui va arriver (une version un peu extreme de ce que l'on a dans la vrai vie avec un client dont le besoin va évolué).
=> Cela oblige aussi les développeurs à refactorer le code au fur et à mesure pour accepter au mieux les futures évolutions.

Pour pimenter un peu la chose, [on](https://twitter.com/avernois) m'a conseillé d'introduire la contrainte des Objects Calisthenics à ce kata.
```
    Only One Level Of Indentation Per Method
    Don't Use The ELSE Keyword
    Wrap All Primitives And Strings
    First Class Collections
    One Dot Per Line
    Don't Abbreviate
    Keep All Entities Small
    No Classes With More Than Two Instance Variables
    No Getters/Setters/Properties
```

Cela permet de secouer un peu la façon de coder, de sortir les personnes de leur zone de confort.

__Durant cette session, on a parlé de : __
 
 * Sortir de la zone de confort
 * Primitives obsessions
 * Tell don't ask
 * Guard Close (no else)
 
 
 ## #3 Mars Rover

__Objectif :__  Écrire une méthode qui prend en paramètre une chaine de caractère contenant une liste de commande, et qui déplace notre robot Mars Rover en fonction sur une grille.

```
- Develop an api that moves a rover around a grid.
- You are given the initial starting point (x,y) of a rover and the direction (N,S,E,W) it is facing.
- The rover receives a character array of commands.
- Implement commands that move the rover forward/backward (f,b).
- Implement commands that turn the rover left/right (l,r).
- The only commands you can give the rover are f,b,l, and r.
- Implement wrapping from one edge of the grid to another. (planets are spheres after all)
- Implement obstacle detection before each move to a new square. If a given sequence of commands encounters an obstacle, the rover moves up to the last possible point and reports the obstacle.

Here is an example:
- Let's say that the rover is located at 0,0 facing North on a 100x100 grid.
- Given the command "ffrff" would put the rover at 2,2 facing East.
```

Pour ce kata, on retourne à un besoin pour l'ensemble de l'atelier.
J'ai choisi de le placer en troisième position parce qu'on n'est plus dans le schéma de l'exercice avec seulement une classe de test et une méthode à coder. Les mécanismes de code propre commence à être compris par la plupart. Il est temps de les appliquer sur un projet un peu plus complexe.
Pour moi, si l'on souhaiter avoir un code propre pour ce Mars Rover, il est nécessaire de créer plusieurs classes.

Je trouve cette application plus concrête que les précédentes et donne souvent lieu a des idées d'évolutions pour aller plus loin (j'ai déjà eu droit à des idées telles que : l'ajout d'obstacles, l'insertion de 2 robots, d'une intélligence artificielle pour le robot, des combats entre robots...)

Pour notre sessions, nous étions un gros groupe d'une 20ène de personne, du coup il y a eu 2 kata en parallèle dans 2 salles différentes et des langages de programmation différents !

__Durant cette session, on a parlé de : __
 
 * Domaine métier
 * Faire émerger les concepts
 * YAGNI
 * KISS
 * un développeur est un fainéant
 * Enum
 * Primitives obsessions
