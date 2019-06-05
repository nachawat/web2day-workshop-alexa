# Workshop Alexa Web2Day


C'est un tutoriel pas à pas pour montrer les fonctionnalités de bases de l'Alexa Skill Kit (ASK) tout en utilisant le ASK SDKv2 Node.js

#### Démarrez ce tutorial ==> [START](./instructions/01-frontend.md)

## Définition

Chaque Skill est consistée de deux parties :
* une partie `Front-End` : une interface vocale ou VUI qui correspond à la définition d'un modèle d'interaction.
* une partie `Back-End` : la logique de programmation (code) où la Skill définit son comportement en réponse à l'utilisateur selon un échange de requête-réponse au format JSON entre le service Alexa et votre code.

### Fonctionnalités de l'Alexa Skill Kit utilisées

* Invocation Name : nom d'appel d'une Skill Custom
* Built-in Intents : intentions prédefinies mis à disposition par Alexa (annule, arrête, aide, oui, non, suivant, précédent, recommence, ...)
* Custom Intents : intentions crées par le développeur
* Utterances : phrases d'examples associées à une intention pour reconnaître l'intention
* Slots : paramètre pour collecter une valeur depuis une intention
* Built-in Slot Types : catalogue de valeurs prédéfinies mis à disposition par Alexa
* Speech Synthesis Markup Language (SSML) : markup pour modifier la prosodie et/ou la voix d'Alexa
* Alexa Presentation Language (APL) : Langage de templating pour gérer les écrans.


### Fonctionnalités du SDK utilisées

* Handler : comment gérer différents types de requêtes
* Error handler : comment gérer les exceptions
* Persistent Attributes : comment gérer la persistence au dela d'une session de Skill

## Instructions

#### Démarrez ce tutorial ==> [START](./instructions/01-frontend.md)

## Ressources
### Communauté
* [Forums développeur Amazon Alexa](https://forums.developer.amazon.com/spaces/23/index.html)
* [Slack](https://amazonalexa.slack.com/) ([page de signup](http://www.alexaslack.com/)) 

### Tuto et Guide
* [Le guide du design vocale](https://developer.amazon.com/designing-for-voice/)

* [Série video pour construire une Skill Alexa](http://alexa.design/videotutorial)

### Documentation
* [Alexa Skills Kit SDK pour Node.js](http://alexa.design/node-sdk-docs)

* [Documentation Alexa Skills Kit](https://developer.amazon.com/docs/ask-overviews/build-skills-with-the-alexa-skills-kit.html)