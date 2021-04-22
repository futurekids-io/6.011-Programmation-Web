class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 1

#### PHP

#### Créé par Mikaël Ruffieux, 04.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---

## Définition d'un <span class="secondary-color">langage de programmation</span>

Selon vous, c'est quoi la **programmation** ?

---

## Définition d'un <span class="secondary-color">langage de programmation</span>

Selon vous, c'est quoi la **programmation** ?

*Ensemble des activités liées à la définition, l'écriture, la mise au point et l'exécution de programmes informatiques ; séquence des ordres auxquels doit obéir un dispositif.<br/><br/>
-- Dictionnaire Larousse*

---

## Définition d'un <span class="secondary-color">langage de programmation</span>

Et qu'est-ce qu'un **langage de programmation** ? 

---

## Définition d'un <span class="secondary-color">langage de programmation</span>

Et qu'est-ce qu'un **langage de programmation** ? 

*Un langage de programmation est une notation conventionnelle destinée à formuler des algorithmes et produire des programmes informatiques qui les appliquent.*

*D'une manière similaire à une langue naturelle, un langage de programmation est composé d'un alphabet, d'un vocabulaire, de règles de grammaire, de significations, mais aussi d'un environnement de traduction censé rendre sa syntaxe compréhensible par la machine.*

*Ils [...] permettent de décrire de manière concise et facile à saisir les opérations de manipulation de données et l'évolution du déroulement du programme en fonction des situations.*

(Source: Wikipedia)

---

## Définition d'un <span class="secondary-color">langage de programmation</span>

Et qu'est-ce qu'un **langage de programmation** ?  

*Un langage de programmation est une notation conventionnelle destinée à **formuler des algorithmes** et produire des **programmes informatiques** qui les appliquent.*

*D'une manière similaire à une **langue naturelle**, un langage de programmation est composé d'un alphabet, d'un **vocabulaire**, de **règles de grammaire**, de significations, mais aussi d'un environnement de traduction censé rendre sa syntaxe **compréhensible par la machine**.*

*Ils [...] permettent de décrire de manière concise et facile à saisir les **opérations de manipulation de données** et l'évolution du déroulement du programme **en fonction des situations**.*

(Source: Wikipedia)

---

## Pour <span class="secondary-color">simplifier</span>...

Un langage de programmation est un langage qui permet de communiquer avec une machine, de lui transmettre des actions dans un ordre précis.

Un langage de programmation possède, comme une langue, des règles de vocabulaire, de grammaire et de significations.

On peut, à travers ces langages, modifier des données et adapter un programme en fonction des situations.

---

## Comment fonctionne une <span class="secondary-color">page web</span>

<img style="max-height: 100px; width: auto;" src="../sources_cours/img/openclassroom.png">

### Concrètement ...

Quand vous allez sur la page [wikipedia.org/wiki/Roger_Federer](https://fr.wikipedia.org/wiki/Roger_Federer), vous demandez au serveur de Wikipedia d'afficher la page `Roger_Federer`.

Le serveur va chercher la page en question, et vous l'affiche.

---

## <span class="secondary-color">PHP</span>, c'est quoi ?

PHP, c'est le nom raccourci de `PHP : Hypertext Preprocessor`.

C’est une langage “open-source” utilisé comme langage de script. C’est un langage gratuit.

PHP s’exécute sur un **serveur** *(contrairement à HTML / CSS qui sont executés par votre navigateur)*.

Exemples de sites qui utilisent PHP : 

<table>
    <tr>
        <td style="width: 33%; text-align:center;">
            <img style="max-width: 90%;" src="../sources_cours/img/wikipedia.png">
        </td>
        <td style="width: 33%; text-align:center;">
            <img style="max-width: 90%;" src="../sources_cours/img/fb.jpg">
        </td>
        <td style="width: 33%; text-align:center;">
            <img style="max-width: 90%;" src="../sources_cours/img/wp.png">
        </td>
    </tr>
</table>

---

## Qu'est-ce que <span class="secondary-color">PHP</span> peut faire ?
PHP fonctionne sur de nombreuses plateformes : Windows, Linux, UNIX, MacOS, etc. 

Il fonctionne très bien avec des **bases de données**.

PHP permet :

- La génération dynamique de contenu sur une page
- La lecture et écriture de fichiers sur le serveur
- La gestion de formulaire
- … et bien plus encore !

---

## Votre premier <span class="secondary-color">script</span> PHP

Sur repl.it, créez un nouveau dossier, que vous nommerez *PHP*, et créez un nouveau projet, en choissisant comme type de projet : *PHP Web Server*.

```php+html
<html>
  <head>
    <title>PHP Test</title>
  </head>
  <body>
    <?php echo "Mon premier script PHP !"; ?> 
  </body>
</html>
```

---

## La <span class="secondary-color">syntaxe</span> de base

Un peu comme en HTML, on doit dire où commence notre code, et où il se termine :

```php+html
<html>
  <head>
    <title>PHP Test</title>
  </head>
  <body>
    <?php echo "Mon premier script PHP !"; ?> 
  </body>
</html>
```

Pour indiquer qu’une commande est terminée, il faut terminer la ligne par `;`.

---

## Les <span class="secondary-color">commentaires</span>

Pour éviter de se perdre dans notre code, ou pour désactiver une partie sans la supprimer, on peut ajouter des commentaires :

```php
<?php 
// Ceci est un commentaire sur une ligne.

/*
Ceci est un commentaire
sur plusieurs lignes
*/
?> 
```

---

## Les <span class="secondary-color">variables</span>
Est-ce qu’il vous est déjà arrivé de devoir toujours écrire la même chose, et de vous dire qu’il y avait sûrement une méthode plus efficace ? 

---

## Les <span class="secondary-color">variables</span>
Est-ce qu’il vous est déjà arrivé de devoir toujours écrire la même chose, et de vous dire qu’il y avait sûrement une méthode plus efficace ? 

*- Formulaires d'inscription, exercices d'écriture à l'école, punitions...*

---

## Les <span class="secondary-color">variables</span>
Un des éléments fondamentaux communs à tous les langages de programmation : la **variable**.

Une variable est une **boîte** sur laquelle on met une **étiquette**, et dans laquelle on peut mettre ce qu’on veut : 
- un nombre, 
- une chaîne de caractère *(un mot, une phrase)*, 
- un booléen (`true` ou `false`),
- ...

La force d’une variable est qu’on peut l’utiliser autant de fois qu’on veut ! ça nous évite du travail à l’écriture ... 

---

## <span class="secondary-color">echo</span>
Dans PHP, il existe deux commandes pour afficher du contenu : echo et print.
On peut l’utiliser pour afficher du texte :
```php
<?php
echo "<h2>PHP is Fun!</h2>";
echo "Hello world!<br>";
echo "This ", "string ", "was ", 
    "made ", "with multiple parameters.";

?>
```

---

## <span class="secondary-color">echo</span>

… pour afficher ce qu’on a rangé dans nos variables : 

```php
<?php
$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";
$x = 5;
$y = 4;

echo "<h2>" . $txt1 . "</h2>";
echo "Study PHP at " . $txt2 . "<br>";
echo $x + $y;
?>
```

Il est possible d’afficher plusieurs éléments à la suite grâce au `.`, comme montré ci-dessus.

---

## Mise en <span class="secondary-color">pratique</span>

- Afficher votre première de caractère;
- Afficher une phrase en insérant votre prénom via une variable;
- Afficher un calcul, en mettant les deux chiffres dans deux variables, et en affichant le résultat du calcul.



<!-- ### Fin du document ### -->