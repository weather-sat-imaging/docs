# Weather satellites imaging

## Objectifs

Ce projet a pour but de développer et de mettre en œuvre un système autonome de capture d’images de satellites météorologiques. L’objectif final est de créer toute la chaîne d’acquisition : de l’antenne, aux systèmes de traitement du signal, jusqu’à l’affichage des images reçues sur un site web.

Le projet est divisé en plusieurs sous-parties, dont certaines sont facultatives, afin de réaliser la chaîne complète. Certaines des parties les plus complexes peuvent être remplacées par des alternatives open-source déjà existantes. L’intérêt principal de les refaires est d’apprendre à les réaliser et de comprendre leurs fonctionnements.

![System overview](./images/System%20overview.png)

Présentation de chaque partie :

- **Antenne** : Conception et fabrication d’une antenne pour la réception des signaux RF.
- **Réception** : Conception et fabrication d’un récepteur RF a bande fixe pour la réception des signaux, incluant les filtres et la conversion analogique-numérique.
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

La qualité du résultat est convenable mais pas optimale. Il est donc nécessaire de concevoir un système plus performant. Ce premier à aussi permis de faire émerger certains points critiques à prendre en compte : 

- l'orientation de nord - sud de l'antenne
- la hauteur de l'antenne pour permettre aux signaux de rebondir sur le sol
- les dimensions de l'antenne, qui doivent être adaptées à la longueur d’onde du signal
- la qualité de la chaine de transport entre l'antenne et le récepteur

### Axes d’améliorations

L’antenne actuelle ne permet pas d’obtenir une excellente qualité et reste très sensible aux perturbations et à son orientation. Il est nécessaire de la remplacer par une antenne plus performante afin de réduire le bruit et d’améliorer la qualité des images.

La connexion entre le câble coaxial et l’antenne ne prend pas en compte l’impédance de l’antenne, ce qui peut provoquer des réflexions et des pertes de signal. Il faut donc utiliser un connecteur adapté à l’impédance de l’antenne.

La connexion entre le câble coaxial et le récepteur n’est pas optimale ; il est nécessaire d’utiliser un connecteur adapté à l’impédance du récepteur.

La réception du signal avec le logiciel n’est pas automatisée, tout comme le traitement du signal pour obtenir une image. Il est donc important d’automatiser la réception et le traitement du signal afin d’obtenir une image automatiquement.

## Objects détaillé

![Goal - version 1](./images/Goal%20-%20version%201.png)

## Découpages des différentes parties

### 📡​ Antenne

L'antenne est actuelle de type V-dipole est fonctionnelle mais pas la meilleur option. L'utilisation d'une antenne QHA plus performante permettra de regler de nombreux problèmes de réception.

Guide de fabrication de l'antenne et mesure de performances : [QHA antenna guide](http://metsat.gogan.org/ant_qha.htm)

![QHA antenna](./images/QHA%20antenna.jpg)

**Note :** cette nouvelle antenne est assez imposante et difficielement transportable en l'état. L'idée serai de concevoir une version demontable pour la transporter plus facilement. Il faut toutefois penser à l'intégrité du signal versus une version fixe.

### Réception

**TODO**

