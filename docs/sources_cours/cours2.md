class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 2

#### PHP

#### Créé par Mikaël Ruffieux, 04.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---

## Petit <span class="secondary-color">rappel</span>

- Comment fonctionne **PHP** ?

- Comment l’utiliser dans nos **documents HTML** ?

- Comment **afficher un élément** sur notre page en utilisant PHP ?

- Comment fonctionne une **variable** ?

---

## Petit <span class="secondary-color">rappel</span>

- Comment fonctionne **PHP** ? 

    PHP est un langage qui s’exécute sur le serveur, contrairement à HTML CSS, qui s’exécutent du côté du client (notre navigateur).

- Comment l’utiliser dans nos **documents HTML** ? 

    En utilisant les "balises" : `<?php … ?>`

- Comment **afficher un élément** sur notre page en utilisant PHP ? 

    En utilisant la commande `echo`

- Comment fonctionne une **variable** ?

    Une variable fonctionne comme une boîte : on lui donne un nom, une étiquette, et on peut ranger à l’intérieur de cette boîte ce qu’on veut (textes, nombres, etc.).

    Elle se définit de la manière suivante : `$maVariable = ... ;`

---

## Les <span class="secondary-color">chaînes de caractères</span>

Nous avons vu la dernière fois qu’il existait différents **types de données** :

- Les nombres ;
- Les booléen (vrai ou faux) ;
- Les chaînes de caractères ;
- **NOUVEAUTÉ : Les tableaux (en anglais, *array*)**

Nous verrons dans les prochains cours le type suivant :
- Les *objets* 

*Note : nous n’apprendrons pas à créer des objets, mais uniquement à les utiliser.*

---

## Les <span class="secondary-color">fonctions</span>

*Définition :*

"Une fonction est un **sous-programme** permettant d'effectuer des **opérations répétitives**.

Au lieu d'écrire le code complet autant de fois que nécessaire, on crée une **fonction** que l’on appellera pour l'exécuter, ce qui peut aussi **alléger** le code." 

*(Wikipedia)*

En PHP, pour utiliser une fonction, on utilise la syntaxe suivante : 

`nomDeLaFonction(parametre1, parametre2, ...);`

Il existe en PHP un très grand nombre de **fonctions prédéfinies**, mais nous pouvons aussi créer nos propres fonctions.

Nous étudierons comment créer une fonction dans le **cours 5**.

*Remarque : echo est une des seules fonctions qui n’utilise pas les parenthèses.*

---

## Les fonctions sur des <span class="secondary-color">chaînes de caractères</span>

```php
<?php

strlen("Ma chaîne de caractères") 
// retourne la taille de ma chaîne, avec les espaces

str_word_count("Ma chaîne de caractères") 
// retourne le nombre de mot, ici 4

strpos("Je m’appelle Mikael", "Mikael") 
// retournera 13 (pourquoi ?)

str_replace("caractères", "vélo", "Ma chaîne de caractères"); 
// retournera "Ma chaîne de vélo"

?>
```


---

## Exercice <span class="secondary-color">pratique</span>

Copiez cet extrait de code dans votre programme :

```php
$texte = "PHP est un langage de script utilisé le plus souvent côté 
serveur : dans cette architecture, le serveur interprète le code 
PHP des pages web demandées et génère du code (HTML, XHTML, 
CSS par exemple) et des données (JPEG, GIF, PNG par exemple) 
pouvant être interprétés et rendus par un navigateur web. PHP
peut également générer d'autres formats comme le WML, le SVG
et le PDF. Il a été conçu pour permettre la création 
d'applications dynamiques, le plus souvent développées pour 
le Web. PHP est le plus souvent couplé à un serveur Apache 
bien qu'il puisse être installé sur la plupart des serveurs 
HTTP tels que IIS ou nginx. Ce couplage permet de récupérer 
des informations issues d'une base de données, d'un système 
de fichiers (contenu de fichiers et de l'arborescence) ou 
plus simplement des données envoyées par le navigateur afin 
d'être interprétées ou stockées pour une utilisation ultérieure.";

```

---

## Exercice <span class="secondary-color">pratique</span>

À l’aide des fonctions suivantes, trouvez :

- La **longueur** du texte ;

- Le **nombre de mots** dans le texte ;

- La **position** du mot "nginx" ;

- Et **remplacez** dans le texte le mot "PHP" par votre prénom.

Les fonctions :

- `strlen(...);`

- `str_word_count(...);`

- `strpos("leTexte", "leMotATrouver");`

- `str_replace("leMotARemplacer", "leNouveauMot", "LeTexte");`

---

## Solution

```php
<?php 
$texte = "...";

strlen($texte); // retourne 936
str_word_count($texte); // retourne 172
strpos($texte, "nginx"); // retourne 644
str_replace("PHP", "Mikael", $texte); // retourne ... 

?>
```

---

## Les fonctions <span class="secondary-color">mathématiques</span>
```php
<?php 

min(0, 150, 30, 20, -8, -200);
// retourne la valeur minimale entrée, ici -200

max(0, 150, 30, 20, -8, -200);
// retourne la valeur maximale entrée, ici 150

pi();
// retourne la valeur de pi, utilise pour calculer des cercles

rand(1, 100);
// retourne un nombre aléatoire entre 1 et 100

round(0.68);
// retourne le nombre entier le plus proche, ici 1

?>
```

---

## À votre <span class="secondary-color">tour</span>

À l’aide des fonctions mathématiques de PHP, trouvez : 

- La **surface** et le **périmètre** d’un cercle de **rayon aléatoire** entre 1 et 100.

Pour vous aider, voici les formules mathématiques pour le périmètre et la surface d’un cercle :

- Périmètre : `2 * pi * r`
- Surface : `pi * r * r`

*(à vous de les transformer en PHP)*

---

## À votre <span class="secondary-color">tour</span>

Ainsi que le squelette de code suivant :



```php
<?php

$rayonAleatoire = … ;
$perimetre = ; 2 * pi() * … ;
$surface = … * … * ... ;

echo "Mon rayon est de ". $rayonAleatoire . "cm. <br>"; 
echo "Le périmètre de mon cercle est de ". $perimetre . "cm. <br>"; 
echo "La surface de mon cercle est de ". $surface . "cm2. <br>"; 

?>
```

---

## Solution

```php
<?php

$rayonAleatoire = rand(1, 100);
$perimetre = 2 * pi() * $rayonAleatoire;
$surface = pi() * $rayonAleatoire * $rayonAleatoire;

echo "Mon rayon est de ". $rayonAleatoire . " cm. <br>"; 
echo "Le périmètre de mon cercle est de ". $perimetre . " cm. <br>"; 
echo "La surface de mon cercle est de ". $surface . " cm2. <br>"; 

?>
```

Est-ce qu'il est possible d'**améliorer l'affichage** du périmètre et de la surface ? 

*Indice : la fonction `round(...)`*

---

class: middle

# Merci pour <br>votre <span class="secondary-color">travail</span><br> et à la <br>semaine <br><span class="secondary-color">prochaine</span> !

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">