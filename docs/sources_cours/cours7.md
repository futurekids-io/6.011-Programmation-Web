class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 7

#### PHP

#### Créé par Mikaël Ruffieux, 06.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---
class:middle

## Récapitulatif

Qu'est-ce que **vous** avez vu la semaine passée avec Tristan ? 

---

## L'exercice de la <span class="secondary-color">dernière fois</span>

```php
<?php
$res = 0;

for ($nb_lignes = 1; $nb_lignes <= 12; $nb_lignes += 1) {
    $res = $nb_lignes*2;
    echo "$nb_lignes * 2 = $res<br />";
}
?>
```

---

## <span class="secondary-color">Exercice</span>

En vous basant sur le code de l'exercice précédent, modifiez-le pour affichez une **table de multiplication**, en utilisant cette fois une **variable** que vous pourrez modifier dans votre code pour modifier la table en question.

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

---
class:middle

## Et <span class="secondary-color">HTML</span> dans tout ça ?

Jusqu'à maintenant, les pages que nous avons créées n'étaient pas très jolies, mais uniquement fonctionnelles.

Il est temps de changer cela, et de **combiner** PHP et HTML (et un peu de CSS).

---

## Exemple <span class="secondary-color">concret</span>

```php
<?php $eleves = ["Matin", "Sheyda", "Ozan", "Mohammad"] ?>

<table>
    <tr><td>Num.</td><td>Prénom</td></tr>
    <?php
    for ($index = 0; $index < 4; $index++) {
        echo "<tr><td>$index</td><td>$eleves[index]</td></tr>";
    }
    ?>
</table>
```

*Exemple avancé sur Repl.it*


---

## <span class="secondary-color">Exercice</span>

En combinant le code de la table de multiplication (avec la boucle simple) et cet extrait de code HTML, faites en sorte d'afficher votre table de multiplication sous forme de **liste** :

```php
<html>
  <head>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
  </head>
  <body>
    <ul>
        <?php 
        $res = 0;
        for ($nb_lignes = 1; $nb_lignes <= 12; $nb_lignes += 1) {
            $res = $nb_lignes*2;
            echo "$nb_lignes * 2 = $res";
        } 
        ?>
    </ul>
  </body>
</html>
```