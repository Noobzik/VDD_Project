# Exploration des données du COVID-19 (SarS-CoV-2) #

| Nom / Prenom   | Numéro Etudiant |
| -------------- | --------------- |
| Sheikh Rakib   | 11502605        |
| Daudin Louise  | 1160xxxx        |

## Remercients ##

>  Nous tenons principalement à remercier le gouvernement sud-coréen pour la mise à dispositions des données de leur patients en open data qui est disponible (à cette adresse) [à cette addresse](https://github.com/jihoo-kim/Data-Science-for-COVID-19) et [à cette adresse officiel](http://www.cdc.go.kr/)


## Introduction ##

>Ceci est un rapport dans un contexte de devoir universitaire pour l'Institut Galilée pour le module nommé Visualisation de données supervisé par Monsieur GROZAVU Nistor, enseignant rattaché au laboratoire LIPN.
>
>Les données utilisées proviennent de la mise à disposition en open data des données détaillées et anonymisés de la pandémie actuelle nommée Covid-19 (SarS-Cov-2) plus particulièrement connu sous le nom médiatique "Corona Virus".
>
>Une série de graphique sera introduit au fur et à mesure de l'analyse de ces données suite à l'exploration des données par l'outil KNIME.
>
>Etant donnée de l'évolution rapide de l'épidémie, dans le cas où le lecteur tente de reproduire les résultats obtenus, la date de la production des données pour ce la-dite projet est le 1er Juin 2020.

Au mois de Décembre 2019, une épidémie d'une maladie émergente (Covid-19) due au SARS-CoV-2 a débuté à Wuhan, en Chine, puis s'est rapidement propagée en Chine, et a été déclarée pandémie le 12 mars 2020 par l'OMS. Actuellement, le taux global de mortalité est d'environ 2,3 % en Chine, ce qui est probablement une surestimation car la plupart des patients présentent des symptômes bénins et ne sont donc pas testés. Ce virus s'est propagé dans le monde entier au fil du temps et les Etat-Unis est le pays devenu le cluster principale de la pandémie, suivit de l'Europe. La Chine à recontrée une forte baisse de nouveau cas de la pandémie à partir du 18 Février 2020.

Les symptomes du Covid-19 sont identifiés par les infections des voies respiratoires principalement, les symptômes sont diverses et variées. Les patient ont principalement de la fièvre supérieur à 39°C, toux, courbatures, asthénie, céphalées, myalgies, rhinorrhée, dysfonction gustative, perte de l'odorat, obstruction nasale.

Ce devoir pour le cours de Visulalisation de Données se concentrer sur l'évolution de la pandémie au sein de la Corée du Sud avec les données de la KCDC (Korea Centers of Disease Control & Prevention).

## Exploration initiale des données et interpretation graphique ##

--- Partie VDD Analyse des données brute Knime, Analyse des résultats obtenues

*   Pour commencer, nous souhaitons connaitre la répartition l'âge des cas positifs afin de nous donner une idée globale de la tranche d'âge des personnes qui pourraient être considérées les plus vulnérables.

Nous supposons tout d'abord (dans le bût de l'analyse) que la tranche d'âge les plus vulnérables soient les nourrissons (0-10 ans) et les personnes âgées (50+).

![graphe 0](img/Chart0.jpg)

D'après le graphique de données brute généré, one remarquons que les personnes ayant une tranche d'âge de 20 ans sont les plus touchées par cette pandémie avec un chiffre totale de 824.
De plus, le nombre totale des personnes infectée pour les plus de 50 ans est de 1366 avec le calcul suivant

```
600 + 405 + 204 + 156 + 1 = 1366
```

Tandis que pour les moins de 50 ans, ce chiffre s'élève à 1942 par le calcul suivant :

```
56 + 150 + 824 + 452 + 460 = 1942
```

Ces chiffres démontre que la contamination du virus ne dépend absolument pas de la tranche d'âge liée à l'imunologie de ces personne.

Il est important de noter que le nombre de nourissons infectées (tranche d'âge 0s) est quand même de 56. Nous nous interessons donc à quand ces personnes ont été déclarée positive au virus.

A titre de référence d'après les données, la Corée du Sud à déclaré le premier patient positive le 23 janvier 2020.

Le premier cas du nourrison à été déclarée le 24 Février 2020 avec le motif suivant : Contact avec un patient. (Patient : 2000000027)

En remontant la trace de ce patient, le motif principale de cette infection est du à l'Eglise Shincheonji Church par l'intermédiaire de deux hôtes. (Le premier hote 2000000013 surment la mère du nourrisson, classé 30s en age, et le deuxième 1200000031 classé 60s en âge, issue de l'église en question).

*   Nous souhaitons connaître également la répartition géographique par province de l'épidémie des cas confirmées.

![graphe 1](img/Chart1.jpg)

*Graphe 1 : Total case confirmed by provinces*

D'après les résultats de cette analyse, nous remarquons que la province de Daegu est le plus touché avec un nombre totale de 6650 cas confirmés. (Données récoltés et généré le 1er juin 2020).

La province de Daegu est composée de 2,463 millions d'habitant (2017) avec une densité de 2812/km² (pour une superficie de 883.5 km²). Ce qui pourrait supposer la propagation du virus favorable à une vitesse considérable (exponentiel).

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

Afin de confirmer ou non notre supposition, nous nous intéressons sur le la répartition du nombre de cas confirmés entre ces sources de contamination.
![graphe 2](img/Chart2.jpg)

Avec 68 % du nombre de personnes infectée ayant comme source d'infection l'Eglise de Shincheonji, on peut affirmer que c'est l'Eglise qui est la principale source d'infection au sein de la province de Daegu.

Et c'est seulement avec 0.3 % du nombre de personnes infectées par une entrée sur le territoire depuis l'extérieur ce qui contredit absolument la supposition posée concernant l'entrée sur le territoire sur la raison de la propagation, même si cela reste la raison principale de importation de celle-ci.

Nous voulons maintenant savoir si la propagation du virus par l'église Shincheonji à joué un rôle principale sur le temps.

On remarque une entrée importante de cas positive sur la période du 18 Février 2020 au 15 Avril 2020. Les valeurs d'entrée ont une flucturation de 18 à 83 personne positif par jour (avec une moyenne de 39 positive par jour sur 57 jours).

--- Partie VDD Simulation des données Knime, Analyse des résultats des simulation


## Conclusion de l'Analyse ##

La Corée du Sud est touché par cette pandémie quelque semaine après la Chine le 20 Janvier 2020 par l'intermediaire l'entrée sur le territoire Coréen en provenance de Chine. La pandémie s'est accélérée au sein du pays de manière exponentiel suite à l'infection par l'Eglise de Shincheonji. La province de Daegu par la suite est devenu le cluster principale de la pandémie au sein du pays, et le reste toujours aujourd'hui.

La pandémie touche tout les tranches d'âges, plus particulièrement la tranche d'âge de 20 ans.

La recente évolution de la pandémie laisse penser que la Corée du Sud est au stade de la décrue. En effet, la forte vague de cas positifs s'est déroulée du 18 Févriér au 15 avril pour une durée totale de 57 jours.


# Annexes #

![graphe 1](img/FlowChart1.jpg)

*Flow Chart  du graphe 1*

![graphe 2](img/FlowChart2.jpg)

*Flow Chart  du graphe 2*