# Feedback de l'apprenant 1

## Commentaire général

Bon travail sur ce projet ! Vous avez réussi à finir les étapes et vous êtes allé au bout des bonus du sujet. Le code est propre et commenté, et les notions semblent acquises, bravo.

## Les bons points

- La **const correctness** parait être acquise, c'est un très bon réflexe à avoir en Javascript.
- La **page 404**, très bonne practice en termes de gestion d'erreur !
- C'est une bonne chose que d'avoir fait attention à **l'architecture**, et d'avoir divisé le code en dossiers. Peut-être en revanche que le fichier `cardList.ejs` serait plus à sa place dans le dossier `card/`.

## Quelques pistes d'amélioration

### Projet
- De manière générale, évitez de mélanger le français **et** l'anglais. Vous pouvez choisir l'un ou l'autre, puisque les consignes ne semblent pas le préciser, mais une fois le choix fait, il faut s'y tenir.
- Je n'aime pas trop l'utilisation de **"empty"** pour signifier que la carte n'a pas d'élément. Peut-être que **"Aucun"** (comme dans le formulaire) ou **"---"** serait plus approprié ?
- Même réflexion pour la recherche, une recherche qui ne retourne rien devrait avoir un affichage plus explicite (**"Pas de résultats"** par exemple).

###  Code

- Pensez à ajouter les **variables d'environnement** dans le `.env.example` au fur et à mesure qu'elles sont utilisées dans le code (`SESSION_SECRET` devrait y être).
-  Attention à certains éléments de **norme** (notamment des espaces qui manquent à droite et à gauche).
- Évitez **le code désactivé par commentaire** dans un rendu final. De manière générale, tout ce qui est inutile doit être retiré pour aider à la lisibilité du code.
