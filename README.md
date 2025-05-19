# Weather satellites imaging

## Objectifs

Ce projet vise à développer et mettre en œuvre un système autonome de capture d’images de satellites météorologiques. L’objectif final est de réaliser l’ensemble de la chaîne d’acquisition : de l’antenne aux systèmes de traitement du signal, jusqu’à l’affichage des images reçues sur un site web.

Le projet est divisé en plusieurs sous-parties, dont certaines sont facultatives, afin de couvrir toute la chaîne complète. Certaines des étapes les plus complexes peuvent être remplacées par des alternatives open source déjà existantes. L’intérêt principal de les refaire nous-mêmes est d’apprendre à les concevoir et de comprendre leur fonctionnement.

![System overview](./images/System%20overview.png)

Présentation de chaque partie :

- **Antenne** : Conception et fabrication d’une antenne pour la réception des signaux RF.
- **Réception** : Conception et fabrication d’un récepteur RF à bande fixe pour la réception des signaux, incluant les filtres et la conversion analogique-numérique.
- **Traitement du signal** : Logiciel embarqué d’acquisition du signal pour obtenir un enregistrement audio brut.
- **Traitement d’image** : Logiciel de traitement du signal audio pour obtenir une image.
- **Prédiction de trajectoire** : Logiciel de prédiction de la trajectoire des satellites pour savoir quand ils seront visibles.
- **Affichage** : Affichage des images et des trajectoires sur un site web.

## Proof of concept

Une première version de la chaîne d’acquisition a été réalisée avec des composants du commerce. Cette version a permis de valider la faisabilité du projet.

Images récupérées avec le setup du proof of concept :

![Proof of concept captured image](./images/Proof%20of%20concept%20captured%20image.png)

Pour cette première version, le montage se compose d’une antenne V-dipôle et d’un récepteur RTL-SDR. Le traitement et l’enregistrement du signal ont été réalisés avec SDR++, et le décodage des images avec Sat-dump.

Montage actuel :

![Proof of concept setup](./images/Proof%20of%20concept%20setup.png)

La qualité du résultat est convenable mais pas optimale. Il est donc nécessaire de concevoir un système plus performant. Ce premier essai a également permis de faire émerger certains points critiques à prendre en compte :

- l’orientation nord-sud de l’antenne
- la hauteur de l’antenne pour permettre aux signaux de rebondir sur le sol
- les dimensions de l’antenne, qui doivent être adaptées à la longueur d’onde du signal
- la qualité de la chaîne de transmission entre l’antenne et le récepteur

### Axes d’amélioration

L’antenne actuelle ne permet pas d’obtenir une qualité optimale et reste très sensible aux perturbations ainsi qu’à son orientation. Il est nécessaire de la remplacer par une antenne plus performante afin de réduire le bruit et d’améliorer la qualité des images.

La connexion entre le câble coaxial et l’antenne ne prend pas en compte l’impédance de cette dernière, ce qui peut entraîner des réflexions et des pertes de signal. Il est donc important d’utiliser un connecteur adapté à l’impédance de l’antenne.

De même, la connexion entre le câble coaxial et le récepteur n’est pas optimale ; il faut utiliser un connecteur correspondant à l’impédance du récepteur.

La réception du signal via le logiciel, ainsi que le traitement pour obtenir une image, ne sont pas automatisés. Il est donc essentiel d’automatiser ces étapes afin d’obtenir une image de manière automatique.

## Objectifs détaillés

![Goal - version 1](./images/Goal%20-%20version%201.png)

## Découpage des différentes parties

### 📡​ Antenne

L’antenne actuelle, de type V-dipôle, est fonctionnelle mais n’est pas la meilleure option. L’utilisation d’une antenne QHA, plus performante, permettra de résoudre de nombreux problèmes de réception.

Guide de fabrication de l’antenne et mesures de performances : [QHA antenna guide](http://metsat.gogan.org/ant_qha.htm)

![QHA antenna](./images/QHA%20antenna.jpg)

**Note :** cette nouvelle antenne est assez imposante et difficilement transportable en l’état. L’idée serait de concevoir une version démontable pour faciliter le transport, tout en veillant à préserver l’intégrité du signal par rapport à une version fixe.

### Réception

**TODO**

