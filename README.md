## [Retour au menu principal](https://github.com/Rjumeau/courses-of-html-css?tab=readme-ov-file)

# Jour 6 - Services

Dans le développement web, il est possible d'intégrer des services externes dans notre site, comme par exemple l'intégration d'une font personnalisée comme nous avons pu le faire précédemment avec Google Fonts.

Google met également à disposition d'autres services qui peuvent être utilisés.

## [Google Maps](https://www.google.fr/maps)

Pour intégrer une map, il faut d'abord effectuer une recherche sur Google Maps, par exemple Bordeaux muffin pour avoir toutes les adresses proposant des muffins.

![Intégration Google Maps](https://github.com/Rjumeau/muffin/blob/muffin-with-services/images-readme/google-map-integration-link.png)

Ensuite, il faut cliquer sur les trois traits horizontaux en haut à gauche de l'écran puis :

- Choisir Partager ou intégrer une carte
- Sélectionner intégrer une carte
- Copier le contenu HTML
- Coller le contenu sur votre page web

La balise <iframe> en HTML permet d'intégrer une autre page web à l'intérieur de la page actuelle. Pensez-y comme à une "fenêtre" dans votre page web qui montre le contenu d'une autre page web

![Balise HTML générée](https://github.com/Rjumeau/muffin/blob/muffin-with-services/images-readme/google-map-integration.png)

Il est possible de modifier le style de la map en lui ajoutant uen classe ou encore en inspectant la map depuis son navigateur, et en regardant le HTML généré pour manipuler les classes existantes.

## [Vidéo Youtube](https://www.youtube.com/)

L'intégration d'une vidéo Youtube suit le même principe que Google Maps. Il suffit de choisir la vidéo que vous souhaitez intégrer et ensuite appuyer sur Share

![Share vidéo youtube](https://github.com/Rjumeau/muffin/blob/muffin-with-services/images-readme/youtube-integration.png)

Il faudra ensuite :

- Sélectionner "Embed"
- Copier le code fourni (il est possible de sélectionner un moment précis où démarre la vidéo avec l'option Start at)
- Coller le code dans votre fichier HTML à l'endroit souhaité

![Résultat intégration vidéo youtube](https://github.com/Rjumeau/muffin/blob/muffin-with-services/images-readme/youtube-integration-result.png)

## [Material Icons](https://fonts.google.com/icons?icon.size=8&icon.color=%23e8eaed)

Google propose également une librairie d'icons gratuits, au même titre que ses fonts, via son service Material Icons.

Pour se faire, il faut d'abord intégrer le service dans notre page afin de pouvoir utiliser le style de chacun des icons avec cette ligne dans la balise head :

```html
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css2?family=Material +Symbols+Outlined:opsz,wght,FILL,GRAD@20,400,0,0"
/>
```

Ensuite, il est possible de rechercher des icons selon un thème (en anglais), par exemple, ingredients.

Une fois l'icon trouvé, il suffit de copier le code se trouvant en dessous de Inserting Icon et de l'intégrer dans votre page.

![Lien icon material icon](https://github.com/Rjumeau/muffin/blob/muffin-with-services/images-readme/material-icons-integration.png)

Les icons sont intégrés dans une balise span.
Vous utilisez span lorsque vous souhaitez affecter une partie d'un texte avec un style particulier, sans perturber le flux du texte. Contrairement à une balise de niveau bloc comme div, une balise span ne provoque pas de retour à la ligne avant et après elle.
