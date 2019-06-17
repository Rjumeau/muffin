# Jour 3

## Initiation à Flexbox

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

### le CSS
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
