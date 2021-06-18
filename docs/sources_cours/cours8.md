class: middle

<h1><span class="secondary-color">Programmation</span><br/>web</h1>

### Cours 8

#### PHP

#### Créé par Mikaël Ruffieux, 06.2021

<img class="first-slide-image" src="../sources_cours/img/first_slide.jpg">

---

## Récapitulatif

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

---
class: center

## Retour en arrière : <span class="secondary-color">formulaire HTML</span>

<img src="../sources_cours/img/login.png" style="max-height: 300px; width: auto;">

---
class:middle

## Un formulaire <span class="secondary-color">en détails</span>

<table>
    <tr>
        <td><img src="../sources_cours/img/login.png" style="max-height: 300px; width: auto;"></td>
        <td>
            <ul>
                <li>Champ de texte</li>
                <li>Champ de mot de passe</li>
                <li>Liens</li>
                <li>Bouton</li>
            </ul>
        </td>
    </tr>
</table>

---
class:middle

## Côté <span class="secondary-color">HTML</span>

```html
<form action="resultat.php" method="post">

    <p>Votre pseudo : <input type="text" name="nom" /></p>

    <p>Votre mot de passe : <input type="password" name="mot-de-passe" /></p>

    <p><input type="submit" value="Se connecter"></p>

</form>
```

---

## 2 nouvelles <span class="secondary-color">balises</span>

La balise de formulaire : 

```html
<form action="..." method="post"> ... </form>
```

La balise d' "entrée" : 

```html
<input type="..." name="...">
```

---

## <<span class="secondary-color">form</span>>

```html
<form action="mon-fichier.php" method="post"> ... </form>
```

**2 attributs** : 

- `action` : cet attribut définit la cible de notre formulaire, la page ou le script que sera exécuté lorsqu'on valide notre formulaire *(= qu'on appuie sur le bouton)*.

- `method` : il existe 2 méthodes : `post` et `get`. Nous verrons la différence entre ces 2 méthodes sur `repl.it`.

---

## <<span class="secondary-color">input</span>>

```html
<input type="..." name="...">
```

**Les attributs** : 

- `type` : il existe beaucoup de types de champ d'entrée, mais en voici une liste des plus utilisés : 
    - `text`
    - `number`
    - `email`
    - `password`
    - `submit`

- `name` : Le nom du champ, qui sera transmis au script de traitement du formulaire.

- `placeholder` : Une valeur "exemple", qui peut indiquer à l'utilisateur ce qu'il doit mettre dans le champ.

*Il est bien entendu possible d'y ajouter des classes, identifiant, etc.*

---

## <span class="secondary-color">Exercice</span>

Dans un document `.php`, créez un **formulaire**.

Ce formulaire doit contenir :

- Un champ de **texte** *(p.e. un pseudo)* ;
- Un champ d'**e-mail** ;
- Un champ de **mot de passe** ;
- Un bouton `submit`.

---
class:middle, center

### Maintenant que votre formulaire est créé ...

## Comment récupérer les <span class="secondary-color">informations</span> du formulaire ?

---

## action="<span class="secondary-color">resultats.php</span>"

C'est là qu'entre en jeu le fichier indiqué dans le `action="..."` de notre formulaire.

Ce fichier va recevoir les informations transmises à travers notre formulaire.

```php
Bonjour, <?php echo htmlspecialchars($_POST['nom']); ?>.
Tu as <?php echo (int)$_POST['age']; ?> ans.
```

---

## method : <span class="secondary-color">POST</span> ou <span class="secondary-color">GET</span> ?

La méthode d'un formulaire se réfère à une **méthode HTTP**.

<table class="unstyled-table">
    <tr>
        <th><h3>POST</h3></th>
        <th><h3>GET</h3></th>
    </tr>
    <tr>
        <td>
            <ul>
                <li>Données transmises directement au serveur</li>
                <li>Plus "abstrait", mais plus sécurisé</li>
            </ul>
        </td>
        <td>
            <ul>
                <li>Donnée transmises via l'URL</li>
                <li>Plus simple</li>
            </ul>
        </td>
    </tr>
</table>

Donc si on transmet des informations **standards** *(nom d'une page, résultat d'un calcul, ...)*, on peut utiliser la méthode `GET`. 

Mais si on transmet des informations **confidentielles** et/ou **personnelles** *(e-mail, mot de passe, ...)*, on utilisera la méthode `POST`.

---

## Récupérer les <span class="secondary-color">données</span> de notre formulaire

Selon la méthode utilisée, on utilisera une méthode différente pour récupérer les données en PHP :

### `POST`

```php
<?php
echo $_POST['pseudo'];
```

### `GET`

```php
<?php
echo $_GET['pseudo'];
```

Il est ensuite possible d'utiliser ces données comme des **variables**, et d'appliquer des **fonctions PHP** standards dessus.

---
class:middle

## <span class="secondary-color">Exercice</span>

Avec votre formulaire, créez un **fichier .php cible**, qui affichera **toutes les données récupérées** du formulaire. Utilisez la méthode `GET` dans un premier temps.


---
class:middle

## <span class="secondary-color">Exercice</span> (suite)

Une fois votre formulaire, et la récupération des données fonctionnels, afficher un résultat spécial si votre utilisateur s'appelle `admin`.