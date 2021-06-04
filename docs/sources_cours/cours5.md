class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 5

#### PHP

#### Créé par Mikaël Ruffieux, 06.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---

## Rappel :  Les <span class="secondary-color">boucles</span>

Vous avez pu le remarquer dans les cours précédents : c'est très répétif de chaque fois devoir écrire `echo $monTableau[0];`, `echo $monTableau[1];`, ... pour afficher tous les composantes de votre tableau.

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

## Rappel : Les <span class="secondary-color">boucles</span>

Les boucles nous servent à faire à notre place **X fois** la même opération, et nous devons uniquement l'écrire **une fois** !

Il existe 2 types de boucles : 

- Les boucles `while`, que l'on utilise quand **on ne connait pas** le nombre de répétition à faire;

- Les boucles `for`, que l'on utilise quand **on connait** le nombre de répétition *(itérations)* que l'on doit faire.

**Par exemple :** 

- J'ai une punition, et je dois écrire 100 fois la phrase `Je ne dois pas discuter en cours.`. Quelle boucle utiliser ?

---

## Rappel : Les boucles <span class="secondary-color">while</span>

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

## Rappel : Les boucles <span class="secondary-color">while</span>

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

## Rappel : Une variante de <span class="secondary-color">for</span> : <span class="secondary-color">foreach</span>

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

## Rappel : Une variante de <span class="secondary-color">for</span> : <span class="secondary-color">foreach</span>

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

Pour mieux comprendre l'utilité de cette boucle, nous allons utiliser un gros volume de données.

Copiez-collez les données de la page suivante dans votre code, et affichez ensuite chaque `array` dans un tableau HTML.

Vous pouvez vous aider du squelette de code suivante : 

```php
<?php 
$productionTotale = ... ;

echo "<table><tr><th>Année</th><th>Entreprise</th><th>Production [kWh]</th></tr>";

foreach($productionTotale as $production) {
    echo "<tr>"
    ."<td>...</td>"
    ."<td>...</td>"
    ."<td>...</td>"."</tr>";
}

echo "</table>";
?>
```

---

## <span class="secondary-color">Exercice</span>

```php
<?php $production = [
    [ "xtf_id" => "production_ALL_2018", "year" => "2018", "production" => "10188", "facility" => "facility_ALL" ], [ "xtf_id" => "production_ALL_2019","year" => "2019","production" => "11229","facility" => "facility_ALL" ], [ "xtf_id" => "production_ALL_2020","year" => "2020","production" => "11540","facility" => "facility_ALL" ], [ "xtf_id" => "production_BEG_2003","year" => "2003","production" => "2647","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2004","year" => "2004","production" => "7076","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2013","year" => "2013","production" => "4155","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2014","year" => "2014","production" => "3509","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2015","year" => "2015","production" => "5187","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2016","year" => "2016","production" => "5832","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2017","year" => "2017","production" => "5434","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2018","year" => "2018","production" => "4473","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2019","year" => "2019","production" => "6424","facility" => "facility_BEG" ], [ "xtf_id" => "production_BEG_2020","year" => "2020","production" => "5302","facility" => "facility_BEG" ], [ "xtf_id" => "production_BER_1997","year" => "1997","production" => "1113","facility" => "facility_BER" ], [ "xtf_id" => "production_BER_1998", "year" => "1998", "production" => "1792", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_1999", "year" => "1999", "production" => "1923", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2000", "year" => "2000", "production" => "1814", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2001", "year" => "2001", "production" => "2600", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2002", "year" => "2002", "production" => "2950", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2003", "year" => "2003", "production" => "2250", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2004", "year" => "2004", "production" => "2294", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2005", "year" => "2005", "production" => "1860", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2006", "year" => "2006", "production" => "1430", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2007", "year" => "2007", "production" => "1702", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2008", "year" => "2008", "production" => "1973", "facility" => "facility_BER" ], [ "xtf_id" => "production_BER_2009", "year" => "2009", "production" => "219", "facility" => "facility_BER" ], [ "xtf_id" => "production_BRT_2001", "year" => "2001", "production" => "4351", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2002", "year" => "2002", "production" => "11200", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2003", "year" => "2003", "production" => "8329", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2004", "year" => "2004", "production" => "7322", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2005", "year" => "2005", "production" => "4939", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2006", "year" => "2006", "production" => "7371", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2007", "year" => "2007", "production" => "12955", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2008", "year" => "2008", "production" => "11342", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2009", "year" => "2009", "production" => "9480", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2010", "year" => "2010", "production" => "7220", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2011", "year" => "2011", "production" => "5324", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2012", "year" => "2012", "production" => "9500", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2013", "year" => "2013", "production" => "8035", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2014", "year" => "2014", "production" => "7463", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2015", "year" => "2015", "production" => "7490", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2016", "year" => "2016", "production" => "8922", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2018", "year" => "2018", "production" => "7348", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2019", "year" => "2019", "production" => "10857", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRT_2020", "year" => "2020", "production" => "10007", "facility" => "facility_BRT" ], [ "xtf_id" => "production_BRU_2002", "year" => "2002", "production" => "5146", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2003", "year" => "2003", "production" => "10850", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2004", "year" => "2004", "production" => "11241", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2005", "year" => "2005", "production" => "10104", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2006", "year" => "2006", "production" => "10754", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2007", "year" => "2007", "production" => "11634", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2008", "year" => "2008", "production" => "11200", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2009", "year" => "2009", "production" => "9846", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2010", "year" => "2010", "production" => "5980", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2011", "year" => "2011", "production" => "6378", "facility" => "facility_BRU" ], [ "xtf_id" => "production_BRU_2012", "year" => "2012", "production" => "10462", "facility" => "facility_BRU" ]
];
```

Les 3 identifiants dont vous aurez besoin :

- `year`
- `facility`
- `production`



---

## Les boucles <span class="secondary-color">for</span>

Cette fois, utilisons la boucle `for` pour notre punition.

Vu que **nous savons combien de fois** nous allons devoir écrire la phrase, c'est la bonne boucle à utiliser.

```php
<?php
for ($nb_lignes = 1; $nb_lignes <= 100; $nb_lignes += 1) {
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

for ($nb_lignes = 1;$nb_lignes <= 100; $nb_lignes += 1) {

    // dans les accolades, on définit l'action 
    // que nous allons effectuer à chaque itération.
    echo 'Je ne dois pas discuter en cours.<br />';

}
?>
```

---

## <span class="secondary-color">Exercice</span>

- Affichez, à l'aide d'une boucle `for`, tous les chiffres de 1 à 100.

---

## <span class="secondary-color">Exercice</span>

Affichez une **table de multiplication**, à l'aide d'une boucle `for`.

Utilisez une **variable** que vous pourrez modifier dans votre code pour modifier la table en question.

Votre résultat devrait ressembler à ça : 

```php
1 * 8 = 8
2 * 8 = 16
3 * 8 = 24
4 * 8 = 32
5 * 8 = 40
6 * 8 = 48
7 * 8 = 56
8 * 8 = 64
9 * 8 = 72
10 * 8 = 80
11 * 8 = 88
12 * 8 = 96
```

---

## Exercice <span class="secondary-color">avancé</span>

Affichez les tables de multiplication de 2 à 12 en utilisant : 

- Une boucle `for`.

Aidez-vous de ce **squelette de code** pour commencer : 

```php
for ($index = ...; $index <= ...; $index++) {
    for(...) {
        ...
    }
    ...
}
```

*Indice : nous devons utiliser **2 boucles** l'une dans l'autre !*