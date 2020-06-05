# Exploration des données du COVID-19 (SarS-CoV-2) #

| Nom / Prenom   | Numéro Etudiant |
| -------------- | --------------- |
| Sheikh Rakib   | 11502605        |
| Daudin Louise  | 11606555       |

## Remercients ##

>  Nous tenons principalement à remercier le gouvernement sud-coréen pour la mise à dispositions des données de leur patients en open data qui est disponible (à cette adresse) [à cette addresse](https://github.com/jihoo-kim/Data-Science-for-COVID-19) et [à cette adresse officiel](http://www.cdc.go.kr/)


## Introduction ##

>Ceci est un rapport dans un contexte du devoir universitaire pour l'Institut Galilée pour le module nommé Visualisation de données supervisé par Monsieur GROZAVU Nistor, enseignant rattaché au laboratoire LIPN.
>
>Les données utilisées proviennent de la mise à disposition en open data des données détaillées et anonymisés de la pandémie actuelle nommée Covid-19 (Virus SarS-Cov-2) plus particulièrement connu sous le nom médiatique "Corona Virus".
>
>Une série de graphique sera introduit au fur et à mesure de l'analyse de ces données suite à l'exploration des données par l'outil KNIME.
>
>Etant donnée de l'évolution rapide de l'épidémie, dans le cas où le lecteur tente de reproduire les résultats obtenus, la date de la production des données pour le-dit projet est le 1er Juin 2020.

Au mois de Décembre 2019, une épidémie d'une maladie émergente (Covid-19) due au SARS-CoV-2 a débuté à Wuhan, en Chine, puis s'est rapidement propagée en Chine, et a été déclarée pandémie le 12 mars 2020 par l'OMS. Actuellement, le taux global de mortalité est d'environ 2,3 % en Chine, ce qui est probablement une surestimation car la plupart des patients présentent des symptômes bénins et ne sont donc pas testés. Ce virus s'est propagé dans le monde entier au fil du temps et les Etat-Unis est le pays devenu le cluster principal de la pandémie, suivit de l'Europe. La Chine à recontrée une forte baisse de nouveau cas de la pandémie à partir du 18 Février 2020.

Les symptomes du Covid-19 sont identifiés principalement par les infections des voies respiratoires, les symptômes sont divers et variés. Les patient ont principalement de la fièvre supérieure à 39°C, toux, courbatures, asthénie, céphalées, myalgies, rhinorrhée, dysfonction gustative, perte de l'odorat, obstruction nasale.

Ce devoir pour le cours de Visulalisation de Données se concentrera sur l'évolution de la pandémie au sein de la Corée du Sud avec les données de la KCDC (Korea Centers of Disease Control & Prevention).

## Exploration initiale des données et interpretation graphique ##

--- Partie VDD Analyse des données brute Knime, Analyse des résultats obtenus

*   Pour commencer, nous souhaitons connaitre le taux de cas positifs en fontion de leurs âge (par dizaine d'années) afin de nous donner une idée globale de la tranche d'âge des personnes qui pourraient être considérées les plus vulnérables.

Nous supposons tout d'abord (dans le bût de l'analyse) que la tranche d'âge les plus vulnérables soient les nourrissons (0-10 ans) et les personnes âgées (50+).

![graphe 0](img/Chart0.jpg)

D'après le graphique de données brutes générées, nous remarquons que les personnes ayant une tranche d'âge de 20 ans sont les plus touchées par cette pandémie avec un chiffre total de 824.
De plus, le nombre total des personnes infectées pour les plus de 50 ans est de 1366 avec le calcul suivant

```
600 + 405 + 204 + 156 + 1 = 1366
```

Tandis que pour les moins de 50 ans, ce chiffre s'élève à 1942 par le calcul suivant :

```
56 + 150 + 824 + 452 + 460 = 1942
```

Ces chiffres démontrent que la contamination du virus ne dépend absolument pas de la tranche d'âge liée à l'imunologie de ces personne.

Il est important de noter que le nombre de nourissons infectés (tranche d'âge 0s) est quand même de 56. Nous nous interessons donc aux dates auxquelles ces personnes ont été déclarée positive au virus.

A titre de référence d'après les données, la Corée du Sud à déclaré le premier patient positive le 23 janvier 2020.

Le premier cas du nourrison à été déclarée le 24 Février 2020 avec le motif suivant : Contact avec un patient. (Patient : 2000000027)

En remontant la trace de ce patient, le motif principal de cette infection est dû à l'Eglise Shincheonji Church par l'intermédiaire de deux hôtes. (Le premier hote 2000000013 surement la mère du nourrisson, classé 30s en age, et le deuxième 1200000031 classé 60s en âge, issu de l'église en question).

*   Nous souhaitons connaître également la répartition géographique par province de l'épidémie des cas confirmées.

![graphe 1](img/Chart1.jpg)

*Graphe 1 : Total case confirmed by provinces*

D'après les résultats de cette analyse, nous remarquons que la province de Daegu est la plus touchée avec un nombre total de 6650 cas confirmés. (Données récoltées et générées le 1er juin 2020).

La province de Daegu est composée de 2,463 millions d'habitant (2017) avec une densité de 2812/km² (pour une superficie de 883.5 km²). Ce qui pourrait supposer la propagation du virus favorable à une vitesse considérable (exponentielle).

Nous pouvons supposer que c'est essentiellement aux personnes qui pourraient s'enfuir de la Chine ou bien des expatriés coréens qui sont de retour. Le point de contact principal probable serait l'aéroport International de Daegu de avec les contacts des surfaces et aussi l'échange verbal entre autrui.

Nous disposons néanmoins des données sur la source de la contamination pour les provinces et on peut affirmer que les sources de contamination pour la province de Daego sont les suivantes :

*   L'Eglise de Shincheonji
*   Deuxième Hopital de Mi-Ju
*   L'Hopital Hansarang Convalescent
*   L'Hopital Daesil
*   Fatima Hospital
*   Cheongdo Daenam Hospital
*   Etrangers de passages
*   Contact Patient

Afin de confirmer ou non notre supposition, nous nous intéressons sur la répartition du nombre de cas confirmés entre ces sources de contamination.

![graphe 2](img/Chart2.jpg)

*Graphe 2 : Percentage of confirmed case of the Daegu province source origin*

Avec 68 % du nombre de personnes infectée ayant comme source d'infection l'Eglise de Shincheonji, on peut affirmer que c'est l'Eglise qui est la principale source d'infection au sein de la province de Daegu.

Et c'est seulement avec 0.3 % du nombre de personnes infectées par une entrée sur le territoire depuis l'extérieur ce qui contredit absolument la supposition posée concernant l'entrée sur le territoire sur la raison de la propagation, même si cela reste la raison principale de l'importation de celle-ci.

Nous voulons maintenant savoir si la propagation du virus par l'église Shincheonji à joué un rôle principal sur le temps.

On remarque une entrée importante de cas positive sur la période du 18 Février 2020 au 15 Avril 2020. Les valeurs d'entrée ont une flucturation de 18 à 83 personne positif par jour (avec une moyenne de 39 positive par jour sur 57 jours).

En reprenant les données du *Graphe 2* et celle du *Tableau 1*, la région qui recense le moins de cas positif de la pandémie est Jeju-do. Le nombre de cas positive est évaluée à 14.

![Tableau 1](img/Tableau1.jpg)
*Tableau 1: Nombre de cas confirmé par province*

Intéressons-nous sur l'évolution de la pandémie avant que le nombre de cas augmente de manière exponentiel suite au cluster liée à l'Eglise de Shincheonji.

On rappel les deux dates clées suivantes :

*   La date du premier cas recensé sur le teritoire coréen est le 20 Janvier 2020
*   La date du premier cas recensé suite au cluster de l'Eglise de Shincheonji est le 18 Fevrirer 2020.

L'analyse suivante se portera donc sur l'évolution entre 20 Janiver 2020 et le 18 Fevrier 2020.

Durant cette période, il y a 39 cas confirmés liée à la pandémie dont 5 personnes directement liée au cluster du Shincheonji (cf *Tableau 2 en Annexe*).
La date du 18 Fevrier sera donc exclu, et l'analyse se portera donc sur la période du 20 Janvier 2020 au 17 Février 2020.

Comme avec l'analyse sur les données générales brute en début de ce rapport, nous devons connaitre quel est la province la plus touchée durant cette période.

![Chart 3](img/Chart3.jpg)
*Graphe 3: Number of case from 20/01/2020 to 17/02/2020 by provinces*

Nous remarquons que 2 province se distingue des autres province à savoir :
*   Seoul avec 14 cas confirmées
*   Gyeonggi-do avec 11 cas confirmées.

Nous remarquons clairement que la province de Daegu ne figure pas sur le *Graphe 3* puisque son nombre de cas est nulle. 

*   Comment se fait-il que la province de Seoul soit à 646 patients confirmées étant donnée qu'elle fait partie du cluster sur la période 20/01/2020 - 17/02/2020 ?

Tout d'abord, il faut étudier le motif de la contamination de cette période pour pouvoir comprendre la provenance de la pandémie avec tout les province d'une part, Seoul d'autre part.

![Chart 4](img/Chart4.jpg)

![Chart 5](img/Chart5.jpg)

Nous remarquons que seule 2 motifs de contamination sont mentionnés :
*   Entrée sur le territoire depuis l'exterieur.
*   Contact par patient.

On s'interesse à la propagation du virus au sein de la provence de Seoul.
Durant cette période du 20/01/2020 au 18/02/2020, la provence de Seoul comptabilise 14 cas positifs au virus. Elle sont réparties sous formes de deux motifs que l'on a énoncé ci-dessus (à savoir, Flux étrangers et Contact Patient), avec 7 cas respectivement dans ces deux motifs (*Graphe 5*).

En analysants les données donnée par le *Tableau 2*, nous remarquons que les autoritées ont codifier les identifiants des patient selon la provenance de la provence. Ici nous nous interresons à celui de Seoul qui est codifier par 1 000 xxx xxx.

Nous cherchons à trouver une chaîne de contamination la plus important au sein de cette provence. Nous remarquons donc en triant par ordre croissant du *tableau 2* en ommettant les patient issue de l'Eglise Shincheonji, sur les valeurs de infected_by, le Patient 1 000 000 003 est mentionné 3 fois.

En mettant en lien les sources de contamination au niveau +1 à Seoul.
3 patients ont été contaminés par l'identifiant 1 000 000 003 issue du contact avec le patient lui même identifié par 2 002 000 001 (*Annexe du tableau 3*).

L'identifiant 2 002 000 001 est en faite une erreur d'entrée qui représente finalement l'identifiant 2 000 000 001. Ce patient fait partie du groupe de contamitation de la province du Gyeonggi-do issue d'entrée sur le territoire.

Nous disposons des données d'historique de lieu visitées. Ce patient à visité l'Hopital de Seoul, situé à Gangnam-gu, un magasin dans la même ville et a ensuite fait un déplacement vers la ville de Goyang-si, en Gyeonggi-do dans un restaurant.

Nous pensons que ce patient à contaminé le patient 1 000 000 003 par l'intermédiare des déplacement en transport au commun de type métro (Ligne 3) au sein de la ville de Seoul durant le déplacement de l'hopital de Gangnam vers la ville de Goyang-si.

Pour arriver à ce résultat, nous avons du placer ces points sur une carte, et les superposer sur une carte de métro. Et nous remarquons qu'en effet, la ligne 3 passe près de deux points de contact, l'hopital de gangnam et le restaurant situé à Jongno-ju. Les points qui sont données dans la base de données sont des coordonnées GPS latitude/longitude.

Nous pouvons dorénavant affirmer que la transmission s'est fait en déplacement par utilisation des transport en communs.

Cependant nous n'avons pas d'information si le patient 2 000 000 001 est passé par l'Aéroport ou bien par un port naval. En effet, le motif de ce patient à été déclarée en tant que flux étrangée (Entrée sur le territoire). On peut seulement supposer que c'est le cas.

En reprenant les données de la répartition des cas d'infection du *Graph 4* et en les mettant en lien avec la trace des lieu visités (*Tableau 4 en annexe*). Les 16 patients ont été contaminé par l'intermédiaire des services hospitaliers qui ont acceuilli les patients du flux étrangers.

*   Quel est l'évolution de la pandémie pour la province de Gyeonggi-do durant cette période ?

La province de Gyeonggi compte 11 patients positives au virus pour la période du 20/01/2020 au 17/02/2020. Elle se répartie sur deux motifs de contamination qui sont les mêmes que celle cité pour Séoul (à savoir Flux étrangers, Contact avec Patient).

![Chart 6](img/Chart6.jpg)

On remarque qu'il y a plus de patient contaminé par contact patient que par les flux étrangers.

En appliquant le même procédé de l'analyse effectuée sur Seoul, nous remarquons qu'il y a une chaine de contamination issue directement du flux étranger chinois.

Il s'agit du patient 2 000 000 010 en provenance de la Chine qui à contaminé deux autre patient par contact patient. (*Tableau 5*).

![Tableau 6](img/Tableau6.jpg)
*Tableau 6 : Mise en évidence du lieu de contamination formée par la chaine 20-8 20-9 et 20-10*

Le lieu de la contamination est encore une fois le service hospitalier en faisant la trace des lieu visitées.

Ces analyse permettent de déduire que la cause de la formation d'une chaine de contamination est du au patient qui se retrouve au service hospitalier au contact direct avec d'autre patient. On peut suppposer que le service hospitalier est soit de nature d'une consulation bénin, soit sur présentation au service des Urgences.

*   Comment l'Eglise Shicheonji est devenu en une journée, un cluster ayant entrainée comme conséquence la propagation rapide au sein du pays ?

Nous savons que le 18/02/2020, 5 patients issue de l'Eglise Shincheonji sont positives au virus. L'analyse se portera donc sur ces 5 personnes particulèrement.

Nous rappelons les données qui sont à disposition pour l'analyse concernant ces patient dans le Tableau 7 suivant :

![Tableau 7](img/Tableau7.jpg)
*Tableau 7 : Liste des patient qui sont positive à la date de 18/02/2020 issue de l'Eglise Shincheonji.*

Nous remarquons que nous avons pas d'information si ces 5 patient ont été contaminés par des patients déjà connu antérieur à cette date. En revanche, le patient 6 015 000 002 attire notre attention car elle n'est pas en provenance de la provence de Daegu mais de Gyeongsangbuk-do.

En voulant retracer l'historique des lieux visitée, nous possedons aucune information concernant celle-ci.

En regardant les numéro des patient depuis le début de l'épidémie, la patient 31 (12 000 000 031) est la première à être positive test faisant partie à l'Eglise.

Son historique des lieux visité (*Tableau 8*) ne correspond à aucune information qui peut être utilisée pour remonter son lieu de contamination.

Nous somme donc toujours sur le flou sur l'origine de la contamination massive a partir de l'église. Nous savons juste que c'est à partir de la patiente 31 que la propagation s'est accelerée. Ceci c'est une situation très similaire dans le cas de la France impliquant l'Eglise de la Porte Ouverte église dans le cadre d'un rassemblement religieux.

Reprenons l'analyse de la propagation à partir du moment où l'Eglise est devenu le cluster principale le 18/02/2020.

![Chart 7](img/chart7.png)

Le pic des patients positifs à été atteinte le 5 mars 2020, étudions l'évolution rapide entre la période du 18/02/2020 au 5/03/2020.

Nous remarquons qu'il y a une augmentation de 1463 de cas positives sur cette période, ce qui porte au nombre totale de 1493 de cas positif depuis le premier cas recensé.

![Chart 8](img/chart8.jpg)

L'augmentation considérable du nombre de cas positives est du à ces deux raisons suivantes :
*   Contact avec un patient
*   etc.

![Chart 9](img/chart9.jpg)

Les provences qui ont contribuée fortement à ces résultats sont :
*   Gyeongsangbuk-do (203)
*   Gyeonggi-do (99)

![Tableau 9](img/Tableau9.jpg)
![Tableau 10](img/Tableau10.jpg)

En étudiant les données de Gyeongsangbuk-do avec tout les motifs recensées, nous remarquons que l'origine de la propagation du virus est issue de l'Eglise Shincheonji Church. Il en est de même pour Gyeonggi-do. Les contacts patient ont repris le relais pour accelerer la contanimation locale.

![Cumulated 1](img/Cumulated.png)
*Graph des motifs de contamination*

Le virus à une léthalité de 71 personnes parmis les  personnes infectées, ce qui donne un ration de 0.01% de taux de mortalitée. Cependant, les chiffres ne sont pas exacte lorsque l'on compare au données du gouvernement. Nous suspectons qu'il y a un problème de mise à jour de leur part, ce qui explique la différence entre les données disponibles et les données communiniquées par la voie de la presse.

--- Partie VDD Simulation des données Knime, Analyse des résultats des simulation


## Conclusion de l'Analyse ##

La Corée du Sud est touché par cette pandémie quelque semaine après la Chine le 20 Janvier 2020 par l'intermediaire l'entrée sur le territoire Coréen en provenance de Chine. La propagation du virus était au ralenti puisque les contamination se fesait au niveau des services hospitaliers. La pandémie s'est accélérée au sein du pays de manière exponentiel suite à l'infection par l'Eglise de Shincheonji. La province de Daegu par la suite est devenu le cluster principal de la pandémie au sein du pays, et le reste toujours aujourd'hui. Cependant, la Corée du Sud ont réussi à controller la propagation du virus.

La pandémie touche toutes les tranches d'âges, plus particulièrement la tranche d'âge de 20 ans.

La recente évolution de la pandémie laisse penser que la Corée du Sud est au stade de la décrue. En effet, la forte vague de cas positifs s'est déroulée du 18 Févriér au 15 avril pour une durée totale de 57 jours.




# Annexes #

![graphe 1](img/FlowChart1.jpg)

*Flow Chart  du graphe 1*

![graphe 2](img/FlowChart2.jpg)

*Flow Chart  du graphe 2*

![Tableau 2](img/Tableau2.jpg)
*Tableau 2 : Liste des patients contaminées avec les mentions Shincheonji du 18 Fevrier 2020.*

![Tableau 3](img/Tableau3.jpg)
*Tableau 3 : Liste des patient dont le nombre contamination par le même contact patient est le plus élevée*

![Tableau 4](img/Tableau4.jpg)

*Tableau 4 : Mise en valeur de 'L'Hopitale' comme lieu de passage principale favorisant la contamination du virus.*

![Tableau 5](img/Tableau5.jpg)
*Tableau 5 : Mise en évidence d'une chaine de contamination au sein de la provence de Gyeonggi-do avec un flux étranger chinois*.

![Flow Chart3](img/FlowChart3.jpg)

*Flow Chart 3 : workflow pour les données de Seoul et Gyenggi-do respectivement*

![Tableau 8](img/Tableau8.jpg)
*Tableau 8 : Historique des lieux visité de la part du patient 31 (12000000031)*