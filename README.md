
# Jour 5 - Composant Card

Nous allons améliorer notre recette de brownie en ajoutant un composant card qui nous permettra d'afficher les meilleures recettes autour du brownie.

Pour se faire, il faudra repartir de notre code de la dernière fois.

Sinon, voici [le dossier à télécharger](https://github.com/Rjumeau/muffin/blob/muffin-cards/muffin-without-card.zip)


## La structure HTML d'une Card

On peut imaginer une card qui se compose d'une image, d'un sous titre, d'un paragraphe et d'un lien. Le tout dans une boîte, donc une div.




```html
<div>
  <img src="images/production1.jpg" alt="Recette">
  <h4>Muffins moelleux à la banane</h4>
  <p>Recette délicieuse</p>
  <a href="https://www.marmiton.org/recettes/recette_brownie-fondant-chocolat-bananes_53461.aspx">Voir plus</a>
</div>
```


## Composant et CSS

Il faudra ensuite créer un nouveau composant card qui contiendra tout le style pour toutes nos card

- Créer un fichier card.css dans le dossier components
- Importer le composant le fichier style.css

Voici un exemple de css que l'on pourrait appliquer à notre card :

Le HTML :


```html
<div class="muffin-card">
  <img src="images/production1.jpg" alt="Recette" class="muffin-card-img">
  <h4>Muffins moelleux à la banane</h4>
  <p>Recette délicieuse</p>
  <a href="https://www.marmiton.org/recettes/recette_brownie-fondant-chocolat-bananes_53461.aspx" class="btn-primary">Voir plus</a>
</div>
```

Et le CSS :


```css
.muffin-card {
  /* Définir une largeur de la card */
  width: 220px;
  /* Couleur d'arrière plan */
  background-color: white;
  /* Rend la div flexible pour positionner les éléments enfants */
  display: flex;
  /* Met la direction en column (row donc horizontal par     défaut avec display flex) */
  flex-direction: column;
  /* Centre horizontalement les éléments enfants */
  align-items: center;
  /* Ajouter un espace intérieur de 20px sur le bas de la card */
  padding-bottom: 20px;
  /* Arrondi les angles de 5px */
  border-radius: 5px;
  /* Ajoute une ombre grise avec du flou sur la card */
  box-shadow: 2px 2px 10px grey
}

.muffin-card-img {
  /* Permet à l'image de prendre 100* de la largeur de la card */
  width: 100%;
  /* Hauteur de 150 px */
  height: 150px;
  /* Couvre entièrement la largeur dispo tout en maintenant les dimensions */
  object-fit: cover;
}
```



## Dupliquer les cards

On a maintenant le design de notre card terminé, mais on aimerait afficher plusieurs cards. Si l'on duplique le code, on se rend compte que les cards s'affichent verticalement les unes après les autres.

Il nous faut donc de nouveau positionner ces éléments dans une boîte parente et la rendre flexible. On l'appellera "muffin-card-container"

HTML :


```html
    <div class="muffin-card-container">
      <div class="muffin-card">
        <img src="images/production1.jpg" alt="Recette" class="muffin-card-img">
        <h4>Muffins moelleux à la banane</h4>
        <p>Recette délicieuse</p>
        <a href="https://www.marmiton.org/recettes/recette_brownie-fondant-chocolat-bananes_53461.aspx" class="btn-primary">Voir plus</a>
      </div>
      <div class="muffin-card">
        <img src="images/production2.jpg" alt="Recette" class="muffin-card-img">
        <h4>Muffins au caramel fondant</h4>
        <p>Recette délicieuse</p>
        <a href="https://www.marmiton.org/recettes/recette_brownie-fondant-chocolat-bananes_53461.aspx"
          class="btn-primary">Voir plus</a>
      </div>
      <div class="muffin-card">
        <img src="images/production3.jpg" alt="Recette" class="muffin-card-img">
        <h4>Muffins nature</h4>
        <p>Recette délicieuse</p>
        <a href="https://www.marmiton.org/recettes/recette_brownie-fondant-chocolat-bananes_53461.aspx"
          class="btn-primary">Voir plus</a>
      </div>
      <div class="muffin-card">
        <img src="images/production3.jpg" alt="Recette" class="muffin-card-img">
        <h4>Muffins nature</h4>
        <p>Recette délicieuse</p>
        <a href="https://www.marmiton.org/recettes/recette_brownie-fondant-chocolat-bananes_53461.aspx"
          class="btn-primary">Voir plus</a>
      </div>
    </div>
```

Et le CSS :


```css
.muffin-card-container {
  display: flex;
  /* Espace les éléments entre eux en laissant un espace à gauche et à droite à l'intérieur de la div*/
  justify-content: space-around;
}
```
## La checklist pour le début des projets

[Checklist](https://docs.google.com/spreadsheets/d/1wh6dVkrdQ3tYMyEV4-WfOaJRsLrCZjdpYyDVmWqNCaQ/edit#gid=0)
