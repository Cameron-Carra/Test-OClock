# Explications fetch

Pour faire simple, `fetch` est une méthode qui permet d'effectuer des requêtes. Cela peut être des requêtes à une base de données, à une API, un site web, etc.

`fetch` effectue une `Request` et en reçoit une `Response`.
De manière générale, la request va être constituée :
- d'une URL (aussi appelé endpoint)
- d'un type de méthode (POST, GET, ...) qui va définir le comportement de la requête (va-t-elle chercher des données, va-t-elle ajouter du contenu à une base de données, etc).
- et de paramètres (pour préciser le comportement de la requête).

On a aussi beaucoup d'options que l'on peut ajouter, mais les trois au-dessus sont les principales.

Ainsi, une request typique ressemblera à ça (telle que décrite dans la [documentation](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) :

```js
const response = await fetch("https://catfact.ninja/fact);
const jsonData = await response.json();
console.log(jsonData);
```

Ce programme :
- effectue une request avec fetch vers une API publique (cat fact" qui renvoie du contenu en format JSON)
- store l'objet reçu dans la variable `response`
- transforme la response en JSON afin de pouvoir être en lire le contenu
- affiche le résultat avec `console.log`

Par défaut, les requêtes fetch sont des requêtes "GET", ce qui signifie que le but est de récupérer de l'information. J'ai également parlé des requêtes "POST", dont le but est d'envoyer de l'information. Par exemple, si on fait un parallèle avec notre jeu de carte, on pourrait utiliser GET pour récupérer l'ensemble de nos cartes, mais POST pour appeler une route qui en créerait de nouvelles.


Une méthode fetch avec POST typique ressemblerait à ça :
```js
// on précise que la cible est l'URL 'https://example.com/profile'
const response = await fetch("https://example.com/profile", {
	  // on utilise une méthode POST, donc le but est "d'envoyer"
      method: "POST",
      // le contenu envoyé est sous format JSON
      headers: {
        "Content-Type": "application/json",
      },
	  // on envoie un objet data sous format JSON au body de la requête
      body: JSON.stringify(data),
 });
```

Pour revenir sur un exemple concret, avec notre jeu de carte, une requête vers une méthode de recherche aurait pu ressembler à ça :

```js
// on cherche les cartes qui n'ont pas d'élement, et dont le niveau est de 3
const data = {
	element: null,
	level: 3,
}
const response = await fetch("/search/element", {
	  // on veut récupérer les cartes, donc c'est une méthode GET
      method: "GET",
      // le contenu envoyé est sous format JSON
      headers: {
        "Content-Type": "application/json",
      },
	  // on envoie la data sous format JSON au body de la requête
      body: JSON.stringify(data),
 });
```

Encore une fois, il existe beaucoup d'autres méthodes et options, mais ce sont les cas d'utilisation les plus élémentaires de fetch.

Une dernière chose, fetch est une fonction **asynchrone**. Si vous vous ne vous souvenez pas de ce que c'est, les fonctions async mettent du temps à s'exécuter (une requête, par exemple, met du temps à se faire). Utiliser `await` permet **d'attendre que la requête se finisse pour continuer le déroulement du programme**.

Pour une meilleur compréhension de cette méthode, je vous encourage vivement à tester les exemples donnés par la documentation par vous même (en utilisant par exemple l'api des cat facts ou la PokeApi)
