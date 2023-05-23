# Feedback de l'apprenant 3

## Commentaire général

Beaucoup de confusions sur ce projet, qui ont conduit à des difficultés sur le rendu final. La notion d'utilisation des objets dans les vues (versus les tableaux) est à revoir. Pour ce qui est de la constitution de vos vues, n'hésitez pas à davantage tester votre code, ce qui permet de voir les problèmes plus rapidement, et donc de mieux réussir à les résoudre. De la même manière, servez-vous du retour d'erreur du terminal, et de davantage de `console.log` de vos variables afin de plus facilement debugger votre code. Ne vous découragez pas, avancez plus doucement en testant plus pour mieux comprendre vos erreurs.

## Quelques pistes d'amélioration

### Projet

- Pour ce qui est de la page d'accueil, on a visiblement des **problèmes au niveau de l'affichage**. C'est dommage, car dans `cardList.ejs` vous aviez bien utilisé la classe css `cardName` telle qu'elle était conçue, et c'était probablement le seul affichage du nom dont vous aviez besoin.
	- Par ailleurs, en fermant la balise `<a>` prématurément à l'intérieur de `<div  class="card">` (ligne 11), vous retirez la balise lien qui aurait dû s'appliquer sur l'image juste en dessous. Cette balise était par ailleurs déjà fermée à la ligne 16.
- Pour ce qui est du `cardDetail.ejs`, vous utilisez une boucle **for** (`<% for (const singleCard of card) { %>`). Cette vue utilise un **simple objet**, ici nommé `card`. Une boucle serait plutôt utilisée, par exemple, pour **un tableau**, qui possède plusieurs éléments. Il faudra peut-être revoir les différents formats de données, notamment la **différence entre un tableau et un objet**, et les différentes manières de les utiliser (n'hésitez pas à revenir vers moi si vous souhaitez davantage d'éclaircissement sur ce point, sinon vous pouvez jeter un petit coup d'œil à la **documentation Mozilla**).
	- Au niveau de la vue, on a également quelques petites étourderies :
		- Vous avez voulu faire un `.toLowerCase()` sur le visual name et y ajouter un `.jpg` mais le visual name contient déjà le nom correct du fichier image donc pas besoin de l'éditer. Pour vous assurer de ce genre de choses, je vous conseille d'ajouter du debug (avec quelques console.logs) afin de vérifier la valeur de vos variables.
		- Vous avez ajouté plusieurs fois le nom de la carte, mais une fois aurait surement suffit. Typiquement, reprendre le format utilisé dans la liste aurait été préférable.
- Au niveau de la **recherche** maintenant, on retrouve quelques problèmes :
	- On retombe sur une erreur plutôt directe (`dataMapper is not defined`) quand on essaie d'utiliser le `searchElement`. L'erreur signifie que la variable `dataMapper` n'est pas reconnue. Regardez dans le reste de votre code à quoi correspond `dataMapper`, et vérifiez pourquoi elle n'est pas reconnue par la fonction.
	- Le sujet conseillait d'utiliser `req.query` au lieu de `req.params`, regardez sur la documentation d'Express leur différence, et voyez comment vous pouvez appliquer ça à `searchElement`. 
	- On retrouve dans la vue `element.ejs` la même confusion entre tableau et objet.

###  Code
- Le dossier `.vscode`, qui ne sert que pour votre config locale, devrait être ajouté au `.gitignore` afin de ne pas se retrouver sur le dépôt final. Bien qu'il soit très joli, je n'ai pas besoin de votre IDE et de ses couleurs personnalisées pour vous corriger.
- Pensez à ajouter les **variables d'environnement** dans le `.env.example` au fur et à mesure qu'elles sont utilisées dans le code (`SESSION_SECRET` devrait y être).
