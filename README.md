# Jour 3

## Initiation à Flexbox
Dans un 1er temps, on créé une boite noire (qui sera par la suite transparante, d'où le nom de "line-transparent"). Dans cette boite, on pose 3 boites ("line-hard", "line-medium" et "line-light").

### Etape 0
Voici le code html et CSS avant de faire du flebox :

#### le html (l.11-15)
```html
  <div class="line-transparent">
    <div class="line-hard"></div>
    <div class="line-medium"></div>
    <div class="line-light"></div>
  </div>
```

#### le CSS
```css
.line-transparent {
  background: black;
  width: 100%;
}

.line-light {
  height: 50px;
  width: 20%;
  background: #EE9CA7;
}

.line-medium {
  height: 50px;
  width: 30%;
  background: #C86472;
}

.line-hard {
  height: 50px;
  width: 50%;
  background: #9F3442;
}
```
On obtient trois boites de tailles différentes, les unes en dessous des autes sur un fond noir.

### Etape 2
On introduit Flexbox. Le HTML ne change pas. Seul le CSS est modifié. Tout d'abord il faut définir une boite parente. Ici la boite parente (celle qui contient les boites que l'on souhaite aligner horizontalement) est biensûr "line-transparent". Pour la définir comme boite parente au sens flexbox il faut lui ajouter la propriété "display: flex;".

#### le CSS
```css
.line-transparent {
  background: black;
  width: 100%;
  display: flex;
}
```

### Etape 3
Pour choisir le type d'alignement horizontal, on utilise la propriété "justify-content" toujour sur la boite parent. Dans l'exemple nous avons choisi la proriété "justify-content: space-between;" mais ils en existent d'autres. Nous les verons par la suite.

#### le CSS (l.99-121)
```css
.line-transparent {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
```

### Etape 4
On peut également choisir la disposition verticale. Pour cela on utilise la propriété "align-items". Dans l'exemple nous avons choisi "align-items: center", mais ils en existent d'autres. Nous les verons par la suite.

### le CSS (l.99-121)
```css
.line-transparent {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.line-light {
  height: 5px;
  width: 20%;
  background: #EE9CA7;
}

.line-medium {
  height: 5px;
  width: 30%;
  background: #C86472;
}

.line-hard {
  height: 5px;
  width: 50%;
  background: #9F3442;
}
```



## <a href="https://flexboxfroggy.com/#fr" target="_blanck">Flexbox Froggy</a>
<a href="https://flexboxfroggy.com/#fr" target="_blanck">Flexbox Froggy</a> est un jeu en ligne permettant de s'exercer aux propiétés flexbox.


## Le composant Navbar
(Schema de conception vue en cours)

### le html (l.17-24)
```html
  <div class="navbar">
    <img src="images/logo.png" class="logo">
    <div class="links">
      <a href="" class="link">Présentation</a>
      <a href="" class="link">Team</a>
      <a href="" class="link">Contact</a>
    </div>
  </div>
```

### le CSS (l.77-96)
```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #E2F3DC;
}

.links {
  display: flex;
  justify-content: flex-end;
}

.link {
  margin: 10px 30px;
  color: #9F3442;
}

.link:hover {
  color: #458D2E;
}
```
