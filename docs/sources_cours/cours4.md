class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 4

#### PHP

#### Créé par Mikaël Ruffieux, 05.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---

## La semaine dernière : les <span class="secondary-color">booléens</span>

-  Quels sont les 2 états possibles d'un booléen ? 

- Quelle est la différence entre `=` et `==` ?

- Quelle est la différence entre `a > b` et `a >= b` ?

- Que retourne la comparaison : `1 != 10` ?

- Que retourne la comparaison : `1 != 10 OR 5 > 3` ?

---

## Les <span class="secondary-color">booléens</span>

-  Quels sont les 2 états possibles d'un booléen ? 

`true` et `false`.

- Quelle est la différence entre `=` et `==` ?

Le `=` est utilisé pour l'attribution d'une valeur à une variable : `$a = 5`.
Le `==` est utilisé comme comparateur, et retourne un booléen : `1 == 5 // retourne false`.

- Quelle est la différence entre `a > b` et `a >= b` ?

Le premier signifie **a est plus grand que b**, et le second **a est plus grand ou égal à b**.

- Que retourne la comparaison : `1 != 10` ?

`true`

- Que retourne la comparaison : `1 == 10 OR 5 > 3` ?

`true`

---

## Les <span class="secondary-color">fonctions conditionnelles</span>

- Quels sont les 3 termes utilisés pour mettre en place une fonction conditionnelle ? 

- Dans le code suivant, quelle phrase sera affichée ?

```php
$a = 5 ;
$b = 10 ;

if($a > $b) {
    echo "Hello";

} elseif($a == $b) {
    echo "Salut";

} else {
    echo "Bonjour";

}
```

---

## Les <span class="secondary-color">fonctions conditionnelles</span>

- Quels sont les 3 termes utilisés pour mettre en place une fonction conditionnelle ? 

`if`, `elseif` et `else`.

- Dans le code suivant, quelle phrase sera affichée ?

```php
$a = 5 ;
$b = 10 ;

if($a > $b) {
    echo "Hello";

} elseif($a == $b) {
    echo "Salut";

} else {
    echo "Bonjour"; // <-- Solution

}
```

---

## Les <span class="secondary-color">tableaux</span>

Il n'est malheureusement pas possible de ranger **plusieurs éléments**.

Si on voulait enregistrer **plusieurs données** sur les gens de la classe, on devrait faire comme ceci : 

```php
$monPrenom = "Mikael";
$monAge = 24;
$monAdresse = "Rte du Test 12";
$monTelephone = "079 123 45 67";

$monVoisin_Prenom = "Denis";
$monVoisin_Age = 30;
$monVoisin_Adresse = "Rte du Test 14";
$monVoisin_Telephone = "079 000 00 00";

// ...
``` 

C'est **pas très pratique**, et très **répétitif** ...

---

## Les <span class="secondary-color">tableaux</span>

Vous vous en doutez, il existe un outil qui permet de créer des éléments capables de stocker plusieurs données : les **tableaux** *(ou `array` en anglais)*.

Il existe **3 types** de tableaux : les tableaux **indexés**, les tableaux **associatifs** et les tableaux **multidimensionnels**.

Dans un tableau, on peut ranger un nombre illimité de données

```php
$monTableauSimple = [1, 2, 3, 4, 5, 6];

echo $monTableauSimple[4]; // retourne 5, car commence à zéro
```

```php
$monTableauAssociatif = [
    "prenom" => "Mikael",
    "age" => 24,
    "adresse" => "Rte du Test 12",
    "telephone" => "079 123 45 67"
];

echo $monTableauAssociatif["age"]; // retourne 24
```

---

## Les <span class="secondary-color">tableaux</span> multidimensionnels

On peut aussi utiliser des tableaux **dans** un tableau, en imbriquant des tableaux associatifs ou indexés les uns dans les autres : 

```php
$monTableauAssociatif = [
    "prenom" => "Mikael",
    "age" => 24,
    "adresse" => [
        "rue" => "Rte du Test 12",
        "ville" = > "Lausanne",
        "npa" => "1000"
    ],
    "telephone" => "079 123 45 67"
];

echo $monTableauAssociatif["adresse"]["npa"]; // retourne "1000".
```

---

## <span class="secondary-color">Exercice</span>

Créez un tableau **indexé** qui contient votre **prénom**, votre **âge** et la **ville** dans laquelle vous habitez.

Affichez chaque élément du tableau en une phrase:

`Je m'appelle ..., j'ai ... ans et j'habite à ... .`.

Même exercice, mais avec un tableau **associatif**.

---

## Fonctions sur des <span class="secondary-color">tableaux</span>

Les fonctions les plus utilisées sont les suivantes : 

- `print_r($monTableau)` : affiche votre tableau;

- `array_push($monTableau, $var1...)` : ajoute à la fin du tableau les éléments mentionnés en paramètre *(ici, $var1)*;

- `unset($monTableau['prenom'])` : supprime du tableau l'élément `'prenom'`;

- `sizof($monTableau)` : retourne la **taille** du tableau, le nombre d'éléments inclus dedans;

- `sort($monTableau)` : trie votre tableau *(par ordre alphabétique, ou du plus petit au plus grand pour les chiffres)*;

---

## <span class="secondary-color">Exercice</span>

Continuez avec le code de l'exercice précédent.

- Ajoutez au **tableau indexé** votre numéro de téléphone;

- Idem pour le **tableau associatif**;

- Affichez le contenu de votre tableau avec `print_r()`;

- Supprimez votre âge des 2 tableaux *(2 commandes)*;

- Ré-affichez vos 2 tableaux avec `print_r()`.

---

## Les <span class="secondary-color">boucles</span>

Vous avez pu le remarquer dans le premier exercice : c'est très répétif de chaque fois devoir écrire `echo $monTableau[0];`, `echo $monTableau[1];`, ... pour afficher tous les composantes de votre tableau.

Imaginez maintenant avoir un tableau avec **100 données**, ou **1000 données**.

On va commencer à écrire le code : 

```php
$monTableau = [...];

echo $monTableau[0];
```

---

## Les <span class="secondary-color">boucles</span>

Vous avez pu le remarquer dans le premier exercice : c'est très répétif de chaque fois devoir écrire `echo $monTableau[0];`, `echo $monTableau[1];`, ... pour afficher tous les composantes de votre tableau.

Imaginez maintenant avoir un tableau avec **100 données**, ou **1000 données**.

On va commencer à écrire le code : 

```php
$monTableau = [...];

echo $monTableau[0];
echo $monTableau[1];
```

---

## Les <span class="secondary-color">boucles</span>

Vous avez pu le remarquer dans le premier exercice : c'est très répétif de chaque fois devoir écrire `echo $monTableau[0];`, `echo $monTableau[1];`, ... pour afficher tous les composantes de votre tableau.

Imaginez maintenant avoir un tableau avec **100 données**, ou **1000 données**.

On va commencer à écrire le code : 

```php
$monTableau = [...];

echo $monTableau[0];
echo $monTableau[1];
echo $monTableau[2];
```

... j'en ai déjà marre !

---

## Les <span class="secondary-color">boucles</span>

Les boucles nous servent à faire à notre place **X fois** la même opération, et nous devons uniquement l'écrire **une fois** !

Il existe 2 types de boucles : 

- Les boucles `while`, que l'on utilise quand **on ne connait pas** le nombre de répétition à faire;

- Les boucles `for`, que l'on utilise quand **on connait** le nombre de répétition *(itérations)* que l'on doit faire.

**Par exemple :** 

- J'ai une punition, et je dois écrire 100 fois la phrase `Je ne dois pas discuter en cours.`. Quelle boucle utiliser ?

---

## Les boucles <span class="secondary-color">while</span>

Pour l'exemple, nous allons faire notre punition avec les 2 types de boucles.

```php
<?php
$nombre_de_lignes = 1;

while ($nombre_de_lignes <= 100) {
    echo 'Je ne dois pas discuter en cours.<br />';
    $nombre_de_lignes++;
}
?>
```

Avec vos connaissances de PHP, essayez de me décrire ce qu'il se passe dans cet extrait de code.

---

## Les boucles <span class="secondary-color">while</span>

```php
<?php
// Nous définissons ici une variable, qui sera notre compteur, 
// notre index.
$nombre_de_lignes = 1;

// Nous avons ici une condition. 
// Tant que notre condition n'est pas vraie,
// on continue à exécuter notre boucle.

while ($nombre_de_lignes <= 100) {

    echo 'Je ne dois pas discuter en cours.<br />';

    // À chaque "tour", on ajoute 1 à notre variable
    $nombre_de_lignes++;
}
?>
```

---

## <span class="secondary-color">Exercice</span>

- Affichez, à l'aide d'une boucle `while`, tous les chiffres de 1 à 100.

---

## Les boucles <span class="secondary-color">for</span>

Cette fois, utilisons la boucle `for` pour notre punition. Vu que nous savons combien de fois nous allons devoir écrire la phrase, c'est la bonne boucle à utiliser.

```php
<?php
for ($nombre_de_lignes = 1; $nombre_de_lignes <= 100; $nombre_de_lignes++) {
    echo 'Je ne dois pas discuter en cours.<br />';
}
?>
```

Avec vos connaissances de PHP, essayez de me décrire ce qu'il se passe dans cet extrait de code.

---

## Les boucles <span class="secondary-color">for</span>

```php
<?php
// On commance par définir 3 éléments : 
// - l'index de départ
// - l'index d'arrivée
// - l'incrémentation de l'index à chaque itération

for ($nombre_de_lignes = 1; $nombre_de_lignes <= 100; $nombre_de_lignes++) {

    // dans les accolades, on définit l'action 
    // que nous allons effectuer à chaque itération.
    echo 'Je ne dois pas discuter en cours.<br />';

}
?>
```

---

## Une variante de <span class="secondary-color">for</span> : <span class="secondary-color">foreach</span>

`foreach` est spécialement conçue pour les tableaux, et permet de parcourir automatiquement **tous les éléments** de notre tableau.

```php
$monTableau = ["Mikael", 24, "Rte du Test 12", "079 123 45 67"];

foreach ($monTableau as $valeur) {
    echo "$valeur<br>";
}
```

Ici, pour chaque élément de notre tableau, nous allons afficher la valeur de ce dernier.

Cela nous évite de devoir écrire à chaque fois `$monTableau[0]`, `$monTableau[1]`, etc.

---

## <span class="secondary-color">Exercice</span>

- Affichez, à l'aide d'une boucle `for`, tous les chiffres de 1 à 100.

---

## Une variante de <span class="secondary-color">for</span> : <span class="secondary-color">foreach</span>

Il est aussi possible de parcourir un **tableau associatif**, et de récupérer la **clé** et la **valeur** : 

```php
$monTableau = [
    "prenom" => "Mikael",
    "age" => 24,
    "adresse" => "Rte du Test 12",
    "telephone" => "079 123 45 67"
];

foreach ($monTableau as $cle => $valeur) {
    echo "$cle : $valeur<br>";
}
```

Ici, pour chaque élément de notre tableau, nous allons afficher sa clé et sa valeur, par exemple : `prenom` (la clé) et `Mikael` (la valeur).

---

## <span class="secondary-color">Exercice</span>

Affichez le contenu de vos tableaux indexés et associatifs avec les 2 `foreach`: 

```php
foreach ($monTableauIndexe as $valeur) {
    echo "$valeur<br>";
}
```

```php
foreach ($monTableauAssociatif as $cle => $valeur) {
    echo "$cle : $valeur<br>";
}
```

---

## Exercice <span class="secondary-color">avancé</span>

*Nous le ferons au prochain cours.*

Affichez les tables de multiplication de 2 à 12 en utilisant : 

- Une boucle `while` ;
- Une boucle `for`.

Aidez-vous de ce **squelette de code** pour commencer : 

```php
$index = 2;

while($index <= 12) {
    echo "...";
}
```

*Indice : nous devons utiliser **2 boucles** l'une dans l'autre !*


