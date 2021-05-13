class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 3

#### PHP

#### Créé par Mikaël Ruffieux, 04.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---

## Petit <span class="secondary-color">rappel</span>

- Nous avons vu les semaines précédentes différents **types de données**, citez-moi ceux dont vous vous souvenez.

- Je souhaite compter le nombre de **mots** que j'ai dans une **chaîne de caractères**, quelle fonction dois-je utiliser : `strlen()` ou `str_word_count()` ?

- Je souhaite créer un nombre aléatoire entre 1 et 10. Quelle fonction vais-je utiliser : `pi()`, `max()`, `rand()` ou `round()` ?

---

## Solutions

- Nous avons vu les semaines précédentes différents **types de données**, citez-moi ceux dont vous vous souvenez.

*Les chaînes de caractères, les nombres, les booléens et les tableaux*.

- Je souhaite compter le nombre de **mots** que j'ai dans une **chaîne de caractères**, quelle fonction dois-je utiliser : `strlen()` ou `str_word_count()` ?

*`strlen()` retourne le nombre de caractères dans la chaîne, tandis que `str_word_count()` retourne le nombre de mots.*

- Je souhaite créer un **nombre aléatoire** entre 1 et 10. Quelle fonction vais-je utiliser : `pi()`, `max()`, `rand()` ou `round()` ?

*`pi()` retourne 3.14... , `max()` retournera le chiffre le plus grand donné en argument, et `round()` arrondira le chiffre donnée en argument à l'entier le plus proche (un entier est un nombre sans virgule).*

*`rand(1, 10)` nous retournera un chiffre aléatoire entre 1 et 10.*


---

## Les <span class="secondary-color">booléens</span>

Un booléen est un type de donnée à 2 états. Soit il est vrai, soit il est faux. Soit il est actif, soit il est inactif.

En programmation, on a 2 manières de noter un booléen : 

- Soit en utilisant les termes anglais : `true` ou `false`;
- Soit en utilisant les chiffres `0` et `1`. 

<img style="max-height: 200px; width: auto; margin-top: 30px;" src="https://image.freepik.com/free-vector/blue-power-button-icon-illustrator-vector_34950-566.jpg"><br>
<small><i>C'est de là que vient le bouton d'allumage : une combinaison d'un `0` et d'un `1`.</i></small>


---

## <span class="secondary-color">Comparer</span> des valeurs

Les booléens sont principalement utilisés pour **comparer des valeurs** :

- `a == b` : `a` et `b` sont-ils **égaux** ?
- `a != b` : `a` et `b` sont-ils **inégaux** ?

- `a > b` : `a` est-il plus grand que `b` ?
- `a >= b` : `a` est-il plus grand ou égal à `b` ?

- `a < b` : `a` est-il plus grand que `b` ?
- `a <= b` : `a` est-il plus grand ou égal à `b` ?

<br>

*Moins utilisés :*

- `a === b`: `a` et `b` sont-ils égaux aussi selon leurs **types** ? Par exemple, est-ce que `'1'` est égal à `1`?

---

## <span class="secondary-color">Comparer</span> des valeurs

### Exercice

- `1 > 2` ?
- `3 <= 10` ?
- `1 == 5` ?
- `1 != 10` ?

Et cela fonctionne aussi avec les chaînes de caractères : 

- `"Michel" == "Mikael"` ?

*On n'utilise que très peu les autres comparateurs sur du texte.*

---

## <span class="secondary-color">Comparer</span> des valeurs

### Exercice

- `1 > 2` ?   `false`
- `3 <= 10` ?   `true`
- `1 == 5` ?   `false`
- `1 != 10` ?   `true`

Et cela fonctionne aussi avec les chaînes de caractères : 

- `"Michel" == "Mikael"` ?   `false`

*On n'utilise que très peu les autres comparateurs sur du texte.*

---

## <span class="secondary-color">Combiner</span> des booléens

On a parfois besoin de comparer plus de **deux éléments**. On peut pour cela **combiner nos comparaisons**, à l'aide des symboles suivants :

- `&&` ou `AND` : seulement si les deux sont `true` : retourne `true` ;

- `||` ou `OR`: si l'un des deux est `true`: retourne `true`.

---

# Table de vérité : <span class="secondary-color">AND</span>

<table style="text-align: left;" class="styled-table">
    <tr>
        <th colspan="2">Entrées</th>
        <th>Sortie</th>
    </tr>
    <tr>
        <td>A</td>
        <td>B</td>
        <td>A ET B</td>
    </tr>
    <tr>
        <td>false</td>
        <td>false</td>
        <td>?</td>
    </tr>
    <tr>
        <td>false</td>
        <td>true</td>
        <td>?</td>
    </tr>
    <tr>
        <td>true</td>
        <td>false</td>
        <td>?</td>
    </tr>
    <tr>
        <td>true</td>
        <td>true</td>
        <td>?</td>
    </tr>
</table>

---

# Table de vérité : <span class="secondary-color">AND</span>

<table style="text-align: left;" class="styled-table">
    <tr>
        <th colspan="2">Entrées</th>
        <th>Sortie</th>
    </tr>
    <tr>
        <td>A</td>
        <td>B</td>
        <td>A ET B</td>
    </tr>
    <tr>
        <td>false</td>
        <td>false</td>
        <td>false</td>
    </tr>
    <tr>
        <td>false</td>
        <td>true</td>
        <td>false</td>
    </tr>
    <tr>
        <td>true</td>
        <td>false</td>
        <td>false</td>
    </tr>
    <tr>
        <td>true</td>
        <td>true</td>
        <td>true</td>
    </tr>
</table>

---

# Table de vérité : <span class="secondary-color">OR</span>

<table style="text-align: left;" class="styled-table">
    <tr>
        <th colspan="2">Entrées</th>
        <th>Sortie</th>
    </tr>
    <tr>
        <td>A</td>
        <td>B</td>
        <td>A OU B</td>
    </tr>
    <tr>
        <td>false</td>
        <td>false</td>
        <td>?</td>
    </tr>
    <tr>
        <td>false</td>
        <td>true</td>
        <td>?</td>
    </tr>
    <tr>
        <td>true</td>
        <td>false</td>
        <td>?</td>
    </tr>
    <tr>
        <td>true</td>
        <td>true</td>
        <td>?</td>
    </tr>
</table>

---

# Table de vérité : <span class="secondary-color">OR</span>

<table style="text-align: left;" class="styled-table">
    <tr>
        <th colspan="2">Entrées</th>
        <th>Sortie</th>
    </tr>
    <tr>
        <td>A</td>
        <td>B</td>
        <td>A OU B</td>
    </tr>
    <tr>
        <td>false</td>
        <td>false</td>
        <td>false</td>
    </tr>
    <tr>
        <td>false</td>
        <td>true</td>
        <td>true</td>
    </tr>
    <tr>
        <td>true</td>
        <td>false</td>
        <td>true</td>
    </tr>
    <tr>
        <td>true</td>
        <td>true</td>
        <td>true</td>
    </tr>
</table>


---

## Exercice <span class="secondary-color">pratique</span>

À l'aide des fonctions mathématiques et textuelles, créez un script qui permette de trouver quel mot vient en premier