
## Jour 4 - Récapitulatif
Le but de cette matinée est de revoir les différents concepts abordés durant les dernières semaines. Pour cela, nous allons reprendre l'exemple d'une page sur une enseigne de Brownie.
#### Important ! Cette page nous servira d'exemple pour les prochaines semaines, il faudra donc la conserver




### Avant de démarrer
Nous allons récupérer la structure HTML de la page réalisée lors du premier cours. Pour cela il faudra : 

```bash
  npm install my-project
  cd my-project
```
    
## Choisir une police
Pour utiliser une nouvelle police sur la page, voici la procédure : 
- Se rendre sur Google Fonts https://fonts.google.com/
- Choisir une police
- Appuyer sur Get Font
- Sélectionner Get Embedded Code
- Copier la balise link dans la head de la page
- Ensuite dans le fichier style.css, sélectionner les éléments sur lesquels on souhaite changer la police, ex : 



```css
h1, h2, h3, h4 {
  font-family: "Pacifico", cursive;
  font-weight: 400;
  font-style: normal;
}

```

Il est aussi possible d'agir sur la taille de police d'un élément avec la propriété font-size, ex:

```css
h3 {
  font-size: 21px;
}

```
## Couleurs
Pour ajouter la couleur sur du texte, il faudra utiliser la propriété color, ex : 
```css
h1, h2, h3, h4 {
  font-family: "Pacifico", cursive;
  font-weight: 400;
  font-style: normal;
  color: #448C2E; // code hexadécimal ou rgba 
}

```

Il est également possible d'ajouter une couleur d'arrière plan sur un élément. Pour cela, il faut générer un gradiant via un site tierce, comme Uigradients : https://uigradients.com/
Une fois votre choix fait, cliquez sur GetCss et récupérer le code généré.

Voici un exemple d'utilisation pour changer la couleur d'arrière plan de notre page : 

```css
body {
    background: #ee9ca7;
    background: -webkit-linear-gradient(to right, #ffdde1,      #ee9ca7);
    background: linear-gradient(to right, #ffdde1, #ee9ca7);
}

```

## Composant Section
![App Screenshot](https://github.com/Rjumeau/muffin/blob/master/images-readme/section-muffin.png)






La page est scindée en plusieurs blocs. On aimerait que ces blocs aient le même style. Pour cela, on va créer un nouveau composant nommé "section". Ce fichier sera responsable de conserver le style pour toutes les sections de notre page, voir de notre site si nous faisons plusieurs pages.

- Dans le dossier components, créer un fichier section.css
- Dans le fichier index.html, appliquez la classe "section" aux éléments souhaités
- Dans le fichier section.css, appelez le sélecteur ".section". Voici un exemple de style applicable sur cette section : 

```css
.section {
  background: #E2F2DC; // applique une couleur au background de la section
  padding: 20px 50px; // espace intérieur (20px vertical / 50px horizontal)
  margin: 10px 100px; // espace extérieur (10px vertical, 100px horizontal)
  border: 3px solid #C0E6B6; // applique une bordure visible (solid) de 3px avec une couleur
}

```
- Dans le fichier style.css, importez le fichier section.css. Pour rappel, le fait de diviser notre css dans des fichiers séparés permet d'importer toute cette logique dans le fichier style.css, qui sera le seul fichier appelé dans la balise head de notre page HTML.

```css
// Tout en haut du fichier style.css
@import url(components/section.css);

```

## Composant Picture

![App Screenshot](https://github.com/Rjumeau/muffin/blob/master/images-readme/main-muffin.png)

Nous aurons besoin de designer des images sur notre page (image principale, logo). Pour cela, on va donc créer un nouveau composant.

- Créer un fichier picture.css dans le dossier components
- Appliquer une classe "main-picture" à l'image
- Appeler le sélecteur .main-picture dans le fichier picture.css
- Appliquez du style à l'image, ex : 

```css
.main-picture {
  border-radius: 50%; // transforme l'image en cercle
  margin-bottom: 20px; // ajoute une marge extérieure vers le bas de l'image
}

```

- Importer le fichier picture.css dans le fichier style.css

```css
// En haut du fichier style.css avec les autres imports
@import url(components/picture.css);

```
## Composant Button
![App Screenshot](https://github.com/Rjumeau/muffin/blob/master/images-readme/button-muffin.png)

Nous aurons besoin de designer des boutons sur notre page afin de modéliser les liens. Pour cela, on va donc créer un nouveau composant.

- Créer un fichier button.css dans le dossier components
- Appliquer une classe "btn-primary" au lien "En savoir plus"
- Appeler le sélecteur .btn-primary dans le fichier button.css
- Appliquez du style au bouton, ex : 

```css
.btn-primary {
  background: #CE8087;
  padding: 15px 15px;
  color: white;
  font-weight: bold;
  text-decoration: none;
  border-radius: 5px;
}

```

- Importer le fichier button.css dans le fichier style.css

```css
// En haut du fichier style.css avec les autres imports
@import url(components/button.css);
```
## Composant Navbar
![App Screenshot](https://github.com/Rjumeau/muffin/blob/master/images-readme/navbar.png)

La navbar (barre de navigation) permet à l'utilisateur de naviguer facilement sur le site web via des liens. On retrouve généralement le logo.

Cette fois-ci, le HTML de cet élément de la page n'est pas fourni. Si on se base sur l'image, on sait que l'on aura besoin d'un logo (donc une image), ainsi que deux liens. 

Afin de pouvoir les placer correctement, il faudra utiliser les flexbox.

Pour rappel, les flexbox permettent de disposer les éléments enfants dans un bloc parent. Ici nous aurons donc besoin d'une div parente (la navbar), une image, et une div enfante contenant les deux liens.


```html
  <div class="navbar">
    <img src="images/logo.png" alt="logo" width=50 height=50>
    <div class="navbar-links">
      <a href="#" class="navbar-link">À propos</a>
      <a href="#" class="navbar-link">Nous contacter</a>
    </div>
  </div>
```

Pour styliser ces éléments, il faut créer un nouveau composant.

- Créer un fichier navbar.css dans le dossier components
- Dans le fichier navbar.css, ajoutez ce css : 

```css
.navbar {
  background-color: #E2F2DC; // ajoute une couleur à la navbar
  display: flex; // rend la div flexible pour disposer les enfants de celle-ci
  justify-content: space-between; // dispose les éléments enfants à l'opposé sur l'axe horizontal
  padding: 5px 20px; // ajoute une marge intérieure
}

.navbar-links {
  display: flex; // rend la div contenant les liens flexible
  align-items: center; // permet de centrer les éléments enfants (les liens) sur l'axe verticale
  gap: 20px; // ajoute un espace entre ces liens
}

.navbar-link {
  color: #9F3442; // change la couleur du texte du lien
  text-decoration: none; 
}
```

- Importer le fichier navbar.css dans le fichier style.css

```css
// En haut du fichier style.css
@import url(components/navbar.css);
```
