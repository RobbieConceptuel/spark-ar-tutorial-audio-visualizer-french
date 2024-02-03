# Spark AR - Audio Visualizer - Tutoriel en Français

Ce tutoriel est la version en Français de mon entrée à la compétition: [2020 Developer Circles Community Challenge](https://developercircles2020.devpost.com/) organisé par Meta.

**Regional Winner** 🏅

## Aperçu

Bienvenue dans ce nouveau tutoriel pour Meta Spark Studio . 
Dans ce projet, nous allons apprendre à faire un **visualiseur audio** en utilisant les fonctionnalitées Audio de Meta Spark AR.
Ceci est un tutoriel destiné aux débutants.

À la fin de ce tutoriel, nous saurons comment faire un visualiseur audio comme sur l'image :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/AudioVisualizer_FinalResult.jpg" width="300">

Ce tutoriel couvre :
* Importer l'objet 3D
* Faire intéragir l'objet 3D avec l'audio

Dans ce tutoriel j'utilise la version 99 de Meta Spark AR Studio.

## Pourquoi utiliser Meta Spark Studio ? :bulb:

Avec plus de 400'000 créateurs dans plus de 190 pays, Spark AR est la **plus grosse plateforme de Réalité Augmenté sur mobile** .
Plus de 1,2 Millions d'effets AR ont été publiés sur Facebook et Instagram.

  <img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer/blob/main/images/sparkarinsights.png" width="500">


### **Et c'est qu'un début !**

Nous sommes encore dans les prémices de ces technologies. Chaque mise à jour est une surprise de nouvelles fonctionnalités.

Avec ou sans connaissances en programmation, Meta Spark AR Studio élargit vos champs de connaissances et d'experimentation dans vos compétences en création digitale.
Un logiciel puissant pour créer des effets en Réalité Augmenté.


### **Le meilleur outil pour atteindre une large audience!**


<a href="https://sparkar.facebook.com/ar-studio/download/">
  <img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer/blob/main/images/sparkarlogo.svg" width="200">
</a>

[Télécharger Spark AR Studio](https://sparkar.facebook.com/ar-studio/download/)

## Vidéos :clapper:

Voici une [Walkthrough Vidéo](https://www.youtube.com/embed/1JrhmM9n-BU) du tutoriel.

<a href="https://www.youtube.com/embed/1JrhmM9n-BU">
  <img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer/blob/main/images/thumbnailTutorial.png" width="200">
</a>


La vidéo suivante est une vidéo étape par étape du tutoriel.
La vidéo contient tout le processus de création de ce tutoriel.


<a href="https://www.youtube.com/embed/1JrhmM9n-BU">
  <img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer/blob/main/images/thumbnailVideoTutorial.png" width="500">
</a>

#### [Tutoriel Vidéo](https://youtu.be/1BcGiDr2FO4)

## Pour commencer

Pour ce projet nous avons besoin de :
* [Télécharger Spark AR](https://sparkar.facebook.com/ar-studio/download/)
* modele 3D dans le dossier 3D-model [lien du modele](https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/3D-model/audioBar.fbx)
* Avoir Spark AR Player installé sur son téléphone [lien pour Spark AR Player](https://sparkar.facebook.com/ar-studio/learn/downloads/)


Pour commencer ce tutoriel il faut **télécharger** le logiciel Meta Spark AR Studio puis l'**ouvrir** .
Nous avons aussi besoin du modele 3D '**audioBar.fbx**' dans le dossier '3D-model'.
Nous allons voir les éléments audio et comment les utiliser dans le Patch Editor.

## Mettre en place la scène

Commençons par :
1. Ouvrir Meta Spark AR
2. Nouveau Projet
3. Choisir Plane Tracking

Une fois le projet ouvert.
**Glisser** l'objet 3D (audioBar.fbx) dans le projet puis **Glisser sous 'Placer'**.

Selectionner audioBar dans la scène puis changer la valeur 'scale' à 0.1 sur la droite de votre écran.

Image de référence :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/ScaleaudioBar.png" width="200">

Une fois effectué, dupliquer audioBar et changer la valeur 'position' du second audioBar à 0.2 sur l'axe X .

Image de référence :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/PositionaudioBar2.png" width="200">
Répéter cette étape jusqu'à avoir **8 audioBar**.
La 'Scene' devrait ressembler à :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Scene.png" width="200">

### Material
Maintenant passons à la création du Material que nous allons appliquer au modele 3D (audioBar) .
Pour ce projet je vais créer **8 materials** avec des couleurs différentes.

Pour appliquer un Material :
* select the cube inside the audioBar
* on the right, create a material
* select your material on the left side of your screen

Image de référence :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/ApplyMaterial.png" width="600">

Une fois que nous avons notre Material, nous pouvons l'améliorer en :
* changer le 'Shader Type' et choisir 'Physically-Based'
* changer la couleur

Importer une image 'environment texture' :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Import_EnvironmentTexture.png" width="200">

Le material devrait ressembler à :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Material.png" width="250">

## Rendre les objets 3D réactifs au son
### Edit Properties
Les fonctionnalitées que nous allons utiliser ne sont uniquement disponible pour la platforme Instagram.
Nous devons désactiver Facebook comme plateforme.
Pour se faire : Project > Edit Properties > Uncheck Facebook

Image de référence :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/EditProperties.png" width="500">

### Audio Analyzer

Maintenant que notre scène est en place, nous ouvrons le Patch Editor :
| View > Show/Hide Patch Editor

Cela va ouvrir le Patch Editor.

Dans votre scène : 
1. glisser le Microphone dans le Patch Editor.
2. Click droit dans le Patch Editor et choisir sous Audio lélément Audio Analyzer
3. lier le microphone à Audio Analyzer ( Microphone à Audio)

Audio Analyzer est un élément qui nous rend possible de séparer le son en 8 channels différents.
Les fréquences vont de 0Hz à 12'000Hz.

Informations sur l'élément Audio Analyzer :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/AudioAnalyzer_Info.png" width="300">

### Agrandir l'objet 3D
Selectionner audioBar, à droite de votre écran et nous devons activer le 'scale' en cliquant sur la petite flèche :

Ici :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Scale_PatchEditor.png" width="300">

Clique droit dans le Patch Editor et ajouter un élément Transition.
Changer les valeurs de l'élément Transition comme ceci :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/TransitionPatch.png" width="300">

Lier : Audio Analyzer > Transition > audioBar '3D Scale'

### Ajouter un Speaker
Nous devons ajouter une sortie audio (Speaker) pour l'utiliser comme output audio.
Dans la Scene :
* cliquer sur 'Add Object' et ajouter Speaker
* selectionner le Speaker
* cliquer la flèche sous Audio 

Image de référence :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/ActivateSpeaker.png" width="300">


Lier le premier output du Audio Analyzer au Speaker output (élément jaune) :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Transition_1element.png" width="600">

Repeter cette étape avec audioBar2

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Transition_2elements.png" width="600">

Repeter cette étape pour tout vos objets audioBar .

Votre Patch devrait ressembler à :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Screenshot_SparkAR_Audio_Visualizer.png" width="600">

## Aperçu et Publication

Maintenant que nous avons fini ;
nous pouvons voir l'aperçu du fichier depuis l'app **Meta Spark AR Player** envoyer sur votre profile **Instagram** :

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Preview_effect.png" width="300">

Nous somme prêts à publier !

On bottom of your screen :
* cliquer sur Upload and Export
* suivre le process de publication du fichier

<img src="https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer-french/blob/main/images/Upload_and_Export.png" width="200">

## Vous en voulez plus ?

En apprendre plus sur Meta Spark AR :

Télécharger Meta Spark AR Studio ici : [Télécharger Meta Spark AR](https://sparkar.facebook.com/ar-studio/download/)

Lien du projet Github : https://github.com/RobbieConceptuel/spark-ar-tutorial-audio-visualizer

Lien pour en apprendre plus : https://sparkar.facebook.com/ar-studio/learn/

[**Rejoindre Spark AR Community**](https://www.facebook.com/groups/SparkARcommunity)


[**Rejoindre Spark AR Francophone**](https://www.facebook.com/groups/sparkarfr)

*écris avec :sparkling_heart: par Robbie Conceptuel - 2020*
