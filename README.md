# Jour 8 - Responsive design et utilisation des balises a 

## Les différentes balises <a>

### Le lien vers une page d'un autre site

```html
<a href="https://www.marmiton.org/recettes/recette_brownie-fondant-chocolat-bananes_53461.aspx" target="_blank" class="btn-pink">En savoir plus</a>
```

### Le lien vers une autre page de son propre site
```html 
<a href="team.html" class="link">Team</a>
```

### Lien vers une ancre dans la page

Il faut au préalable identifier la position dans la page où le lien doit renvoyer. Pour cela on utilise l'attribut "id".

Ex : 

```html
<div id="presentation"></div>
```

On utilise alors cette ancre dans la valeur de href du lien en mettant un "#" devant le nom :

```html
 <a href="#presentation" class="link">Présentation</a>
 ```

 ### Le lien vers une messagerie email

 Il est possible de diriger vers le système de mail par défaut  de votre système d'exploitation en ajoutant mailto: dans la valeur de l'attribut, ainsi que le destinataire.

 ```html
 <a href="mailto:contact@mihivai.com" target="_blank" class="footer-link">
```

### Le lien vers un appel téléphonique
Il est également possible de lancer un appel téléphonique via la balise a

```html
<a href="tel:0606060606" target="_blank" class="footer-link">
````

Voici un exemple d'utilisation dans un footer de page : 

```html
  <div class="footer">
    <h3 class="text-center">Nous contacter</h3>
    <div class="footer-infos">
      <a href="mailto:contact@mihivai.com" target="_blank" class="footer-link">
        <span class="material-symbols-outlined">
          mail
        </span>
        Par mail
      </a>
      <a href="tel:0606060606" target="_blank" class="footer-link">
        <span class="material-symbols-outlined">
          call
        </span></i>
        Par téléphone
      </a>
    </div>
  </div>
```

Et le css dans un component footer : 

```css
.footer {
  background-color: #E2F2DC;
  padding-bottom: 50px;
  padding-top: 10px;
  margin-top: 20px;
}

.footer-infos {
  display: flex;
  justify-content: center;
  gap: 20px
}


.footer-link {
  display: flex;
  align-items: center;
  gap: 5px;
  text-decoration: none;
  color: #9F3442;
}

```
## Responsive design
Les pages web sont principalement visitées sur des formats mobiles. Il convient donc d'adapter le design de notre site pour convenir à ces écrans.

Dans un premier temps, nous aurons besoin d'ajouter cette balise dans la head : 

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

Voici une explication des éléments clés de cette balise :

name="viewport" : Cela indique que cette balise meta est utilisée pour configurer le viewport, qui est la zone visible de la page web.

content="width=device-width, initial-scale=1" : Cette partie spécifie les paramètres de configuration du viewport.

width=device-width : Cela signifie que la largeur du viewport doit être égale à la largeur de l'écran de l'appareil. En d'autres termes, la page s'ajustera automatiquement pour s'adapter à la largeur de l'écran de l'utilisateur.
initial-scale=1 : Cela fixe le niveau de zoom initial lorsque la page est chargée pour la première fois. Une valeur de 1 signifie que la page est affichée à un zoom de 100 %, sans être agrandie ou réduite.



## Les Media Queries

Le CSS récent nous permet d'adapter le style selon le type et la taille d'écran grâce à des medias queries. 

Voici un exemple : 

```css
@media (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

@media : Cette directive indique le début d'une media query. Elle informe le navigateur que les styles contenus dans le bloc doivent être appliqués uniquement si certaines conditions sont remplies.

(max-width: 600px) : C'est la condition ou l'expression de la media query. Elle spécifie que les styles définis à l'intérieur du bloc doivent être appliqués uniquement si la largeur du viewport (zone visible de la page web) est de 600 pixels ou moins.

max-width : Propriété qui limite la largeur maximale du viewport pour laquelle les styles sont applicables.
600px : Valeur de la largeur maximale en pixels.
{ ... } : Les accolades délimitent le bloc de styles CSS qui seront appliqués lorsque la condition de la media query est remplie.

Voici un référentiel à suivre selon les écrans : 

- max-width 320px	Smartwatches
- max-width 420px	Smaller devices
- max-width 600px	Phones
- min-width 600px	Tablets and Large Phones
- min-width 768px	Tablets
- min-width 992px	Laptops and Desktops
- min-width 1200px	Monitors, Desktops


## Exemple de media query sur la page Muffin
Dans notre cas de figure, on remarque les marges initialement prévues pour un écran d'ordinateur ne sont plus adaptées en version mobile.

Voici comment on peut appliquer une media query sur notre classe .section : 

```css
@media (max-width: 768px) {
  .section {
    margin: 20px 10px
  }
}
```
