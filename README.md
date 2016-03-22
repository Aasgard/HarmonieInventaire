#Compte rendu du projet de MPC
####Etudiants: CHEMIN Paul & LANCIEN François-Régis

###Objectif du projet

L'objectif principal du projet est d'être capable de prédire les évolutions futures d'un jeu données.

###Provenance des données

Les données que nous avons choisies proviennent de la Bibliothèque Universitaire de Beaulieu.
La personne rencontrée sur place pouvait alors nous fournir plusieurs jeux de données.
Après réflexion, nous avons choisi de prendre les entrées par jour à la BU que nous avons regroupées par mois.

###Données initiales

Voici les données brutes de notre jeu de données.

![Jeu de données brutes](http://img11.hostingpics.net/pics/625311plotdonneesbrut.png)

###Corrélogramme

Le corrélogramme de la série est le suivant.

![Corrélogramme](http://img11.hostingpics.net/pics/430950correlogramme.png)

On distingue ici une saisonnalité mais pas de tendance. Le corrélogramme ci-dessus n'est pas parfait (beaucoup de données se trouvent entre les pointillés), mais l'alternance de données groupées positives-négatives nous confirme bien une saisonnalité.

Nous avons alors appliqué le test d'analyse de la variance. Il nous confirme la saisonnalité, mais la tendance est absente.
(cf script R)

###Filtrage par moyenne mobile

![FPMM](http://img11.hostingpics.net/pics/695099moymobile.png)

###Estimation des coefficients saisonniers

On a estimé les coefficients saisonniers sur la série. Voici l'illustration des coefficients :

![CS](http://img11.hostingpics.net/pics/668821unesaisonnalite.png)

###Prévisions de la 4ème année

####Par régression linéaire

Dans un premier temps, on désaisonnalise la série.

#####Régression simple

Représention de la régression simple (estimation de la tendance) :

![RLS1](http://img15.hostingpics.net/pics/725599prevregtotsimple.png)

L'erreur quadratique de ce modèle est de 104162831 ce qui est quand même assez élevé.

Représentation de la prévision de la 4ème année selon la régression simple :

![RLS1](http://img11.hostingpics.net/pics/538752prevregsimple.png)

#####Régression multiple

Ici, on utilise la même méthode que précédemment mais avec un polynôme de degré 2.

Représentation de la tendance :

![RM1](http://img15.hostingpics.net/pics/521688prevregtotmult.png)

L'erreur quadratique de ce modèle est de 109312625. Ce qui est encore plus élevé que la valeur précédente.

Représentation de la prévision de la 4ème année selon la régression simple :

![RM2](http://img11.hostingpics.net/pics/306034prevregmultiple.png)

####Par lissage exponentiel triple

Voici la prévision par lissage exponentiel triple :

![LET1](http://img11.hostingpics.net/pics/625667prevlissexpotriple.png)

L'erreur quadratique est de 10049081. Qui correspond alors au meilleur modèle ici présent.


###Conclusion

Notre meilleur modèle prévisionnel est donc le troisième modèle, optenu à partir du lissage exponentiel triple.
