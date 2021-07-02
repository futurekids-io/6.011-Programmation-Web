class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 10

#### PHP

#### Créé par Mikaël Ruffieux, 06.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---

## Les semaines <span class="secondary-color">passées</span>

- À quoi peut bien servir **un formulaire** sur un site internet ?

- Pourquoi on a besoin de **PHP** pour utiliser les données d'un formulaire ? 

- Nous avons découvert 3 nouveaux types d'`input` pour nos formulaires, est-ce que vous vous souvenez lesquels ?

---

## La semaine <span class="secondary-color">passée</span>

Les 3 types :

- Les choix multiples ;
- Les cases à cocher ;
- Les listes de sélections.

Ces `input` sont spéciaux car ils ont **plusieurs options prédéfinies**, et donc des **sous-éléments** HTML.

---

## La semaine <span class="secondary-color">passée</span>

```php
<form action="resultats.php" method="post">
    <input >
    <!-- Choix multiples, ou bouton "radio" -->
    <input type="radio" id="homme" name="genre" value="M">
    <label for="homme">Homme</label>
    <input type="radio" id="femme" name="genre" value="F">
    <label for="femme">Femme</label>

    <!-- Cases à cocher -->
    <input type="checkbox" id="vehicule1" name="vehicule1" value="velo">
    <label for="vehicule1"> Vélo</label><br>
    <input type="checkbox" id="vehicule2" name="vehicule2" value="voiture">
    <label for="vehicule2"> Voiture</label><br>

    <!-- Liste de sélection -->
    <select name="animaux">
        <option value="chien">Chien</option>
        <option value="chat">Chat</option>
        <option value="hamster">Hamster</option>
    </select>
</form>
```

---

## La nouveauté du jour : les <span class="secondary-color">fonctions</span>

En PHP, nous avons déjà eu l'occasion d'utiliser des fonctions.

Pourriez-vous en citer quelques unes ?

---

## La nouveauté du jour : les <span class="secondary-color">fonctions</span>

En PHP, nous avons déjà eu l'occasion d'utiliser des fonctions.

Pourriez-vous en citer quelques unes ?

*Exemples de fonctions :*

`strlen()`, `sizeof()`, `print_r()`, `pi()`, `echo()`, etc.

Ces fonctions sont des **fonctions intégrées** à PHP.

---

## Les <span class="secondary-color">fonctions</span>

S'il existe **plus de 1000 fonctions** intégrées à PHP, nous ne pouvons malheureusement pas tout faire avec. Nous devons parfois les combiner entre elles, créer notre propre code, pour arriver au résultat espéré.

Nous allons donc apprendre à créer nos propres fonctions, et à les utiliser.

Une **fonction** est similaire à une **variable** : c'est un élément dans lequel on peut **stocker** des choses, et qu'on appelle par un **nom**.

La différence avec une variable, c'est qu'on va y stocker une ou plusieurs **valeurs**.

Une **fonction** permet de stocker une série d'**opérations**, de **scripts** !

Selon Wikipédia, une fonction est : 

*... une partie de code recevant une ou plusieurs informations à partir desquelles elle retourne une ou plusieurs informations.*

---

## <span class="secondary-color">Anatomie</span> d'une fonction

On peut nommer notre fonction comme on veut. Les seules choses à respecter sont la première lettre en minuscule, et pas d'espace. *(On évite aussi d'y mettre des chiffres, mais ça n'est pas obligatoire)*

Le nom de la fonction devrait être **explicite** : on doit pouvoir comprendre ce que fait la fonction rien qu'en lisant le nom.

Une fonction peut avoir **0**, **1** ou **plusieurs arguments**.

Une fonction peut retourner **0** ou **1 résultat**.

```php
function maFonction() {
    // mon code
}

// pour appeler ma fonction :
maFonction();
```

---

## <span class="secondary-color">Exercice</span>

Codez les fonctions suivantes : 

- Une fonction qui affiche tout simplement `Hello World` ;

- Une fonction qui affiche `Bonjour Prénom !`, en faisant passer le prénom en argument ;

- Une fonction qui retourne un chiffre entré en argument, mais multiplié par 2.

---

## Exercice <span class="secondary-color">avancé</span>

Nous avons codé dans un cours prédécent un script qui permettait d'afficher une `array` sous la forme d'un tableau HTML.

Nous allons maintenant essayer de transformer ce script en fonction, pour pouvoir réutiliser le tout à chaque fois qu'on veut transformer une `array` en tableau HTML.

```php
<table>
    <tr>
    <th>Num.</th>
    <th>Prénom</th>
    </tr>
<?php 
    $eleves = ["Matin", "Sheyda", "Ozan", "Mohammad"];

    for($ligne = 1; $ligne <= 4; $ligne ++) {
    echo "<tr><td>$ligne</td><td>" . $eleves[$ligne-1] . "</td></tr>";
    }
?>
</table>
```


---

class: middle, center

## Avant la <span class="secondary-color">fin</span> ...

**PowerCoders**, l'association qui a co-organisé ces cours, aimerait en savoir un peu plus sur la façon dont vous avez vécu ces 10 cours, ce que vous avez appris, et quelle est la suite pour vous.

Merci de prendre le temps de répondre à [ce formulaire](https://docs.google.com/forms/d/e/1FAIpQLSdJNHF5SJDpAesXnpdcALQjH_OFPM_miFBByPGu_UZZClNh4A/viewform).

---

class: middle

<h1><span class="secondary-color">Merci</span> !</h1>

### Pour votre travail et votre intérêt

#### Bonne suite, et à bientôt, j'espère !

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">