# Retours MCD

## Rendu

![](https://raw.githubusercontent.com/O-clock-tuteurs/bapteme-freelances/master/MCD/mcd_apprenant.png?token=GHSAT0AAAAAACCF3QGXQJUVTHZIFUXCWMRQZDNCMCA)

## Commentaire 

Bon début de travail sur ce MCD. On retrouve bien les différents jeux de données mentionnés par le sujet (user, order, address et product). 

Pour ce qui est des données, certains attributs nécessaires au fonctionnement du site manquent (notamment le prix de chaque produit, ou peut-être la date à laquelle la commande a été passée). Inspirez-vous du fonctionnement de sites d'e-commerce (Amazon par exemple) pour compléter les jeux de données dont vous avez besoin dans le MCD.

Attention, petite confusion au niveau des relations pour le système de like. Un produit peut être "liké" par plusieurs utilisateurs, et un utilisateur peut "liker" plusieurs produits. Adaptez les relations autour de like en conséquence, avec des 0,n pour signifier la présence d'un many-to-many.
Également, dans la mesure où une adresse peut être utilisée par plusieurs utilisateurs, il est peut-être plus judicieux d'adopter une relation 1,n pour cette table.
Le reste des relations est correct.

Personnellement, je vous conseille d'utiliser des logiciels comme MySQL Workbench pour réaliser vos MCDs.
