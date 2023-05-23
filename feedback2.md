# Feedback de l'apprenant 2

## Commentaire général

Bon début de travail sur ce projet, les notions sont en cours d'acquisition. On sent un manque de temps, mais les bases sont là et la plupart des fonctionnalités demandées sont intégrées. Attention à la propreté du code qui laisse parfois un peu à désirer, et aux erreurs d'inattention par rapport aux consignes du sujet.

## Les bons points

- Bon travail avec la const correctness, les variables sont pour la plupart correctement initialisées.

## Quelques pistes d'amélioration

### Projet

- Attention, il manque **certaines informations** au détail de la carte ainsi que la légende de ces informations. C'est dommage, le plus dur était fait à ce niveau.
- Le sujet mentionne également que **la taille maximale d'un deck est de 5 cartes**. S'il s'agit d'un oubli, pensez à **relire plusieurs fois le sujet** au cours du projet, afin d'être certain de ne pas oublier certains détails comme celui-ci.
- La recherche est **fonctionnelle** (sauf un cas d'usage décrit juste en dessous), mais **la vue est incomplète** (pas d'image notamment). Ici, l'astuce aurait été de **réutiliser la vue** `cardList.ejs` dans le controller `getSearchResults` puisque celle-ci correspond déjà au format souhaité.
- Le cas d'usage qui ne fonctionne pas pour la recherche est **le cas où la carte n'a pas d'élément**. Ce que vous faites ici, dans votre requête à la base de données, c'est **lister les cartes qui ont pour élément "tonnerre", "terre", ... et "aucun"**. Puisqu'il n'y a pas de cartes qui possèdent l'élément "aucun", ça ne fonctionne pas. Je vous conseille de **retourner regarder dans la base de données**, quelle est la valeur correspondante à ce cas de figure et d'adapter le code en conséquence !

###  Code

- Pensez à ajouter les **variables d'environnement** dans le `.env.example` au fur et à mesure qu'elles sont utilisées dans le code (`SESSION_SECRET` devrait y être).
- Attention à la norme, on retrouve quelques ***étrangetés syntaxiques*** à plusieurs endroits (beaucoup de retours à la ligne inutiles dans `card.ejs` par exemple).
- Pensez également à **commenter votre code**, afin d'en expliquer certaines parties.
