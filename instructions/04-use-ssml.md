# Modifier le rendu vocal de vos prompts.

> ## Objectif : Vous allez utiliser [SSML](https://developer.amazon.com/docs/custom-skills/speech-synthesis-markup-language-ssml-reference.html) pour modifier la prosodie d'Alexa et la/les voix utilisées dans votre Skill

## Temps nécessaire : 5 minutes

## Description

Dans certains cas, vous souhaiterez avoir un contrôle supplémentaire sur la manière dont Alexa génère les prompts à partir du texte de votre réponse. Par exemple, vous souhaiter rajouter une pause plus longue dans le discours, changez de voix ou de langue. Le Alexa Skills Kit (ASK) fournit ce type de contrôle avec la prise en charge du langage SSML (Speech Synthesis Markup Language). Il s'agit d'une système de balises que l'on rajouter dans ses prompts pour impacter le rendu vocal. Par exemple, pour faire une pause on va rajouter la balise `<break>` avec la durée souhaitée de cette manière :"`Attention, je vais vous faire peur, préparez-vous! <break time="3s"> Bouh!`"

En complément Alexa propose une bibliothéque de sons mp3 ([ASK Sound Library](https://developer.amazon.com/docs/custom-skills/ask-soundlibrary.html)) et des interjections ([Speechcons](https://developer.amazon.com/docs/custom-skills/speechcon-reference-interjections-french.html)) que vous pouvez aussi rajouté dans vos prompts en utilisant SSML.

## Etapes

1. Allez à l'onget `Custom` et localiser la propriété `speechText` dans  le Handler `LaunchRequestHandler`. Le prompt originel devrait ressembler à quelque de similaire :

``` javascript
let speechText = `Bienvenue sur la Skill du workshop Alexa pour le Web2Day! Dites-moi bonjour et je vous répondrais`;
```

Sur ce prompt, on va rajouter différents tags SSML pour modifier sa prononciation : 
- Ajouter un audio au début 
La balise SSML pour cela est `<audio>` et nous permet d'ajouter des MP3 d'une durée maximum de 4 minutes. Ici, on va utiliser le cri du lion fourni par la bibliothèque de sons Alexa. 

``` javascript
<audio src='soundbank://soundlibrary/animals/amzn_sfx_lion_roar_02'/>
```

- Murmurer la partie du texte `workshop Alexa`
La balise SSML pour cela est `<amazon:effect>` où l'on veut rajouter le mode murmure `whispered`.

``` javascript
<amazon:effect name="whispered">workshop Alexa</amazon:effect> 
```

- Utilisez une autre voix dans une autre langue pour la partie texte `Web2Day!`
Pour utiliser l'une des 27 voix de Amazon Polly disponible sur Alexa, il faut utiliser le balise `<voice>` avec le nom de la voix souhaitée.
Si vous choisissez, une langue différente de la langue de l'utilisateur, il vous faudra d'abord encapsuler le texte souhaité avec la balise `<voice>` avec le nom de la locale souhaitée (en-US, it-IT, ja-JP, ...)


``` javascript
<voice name="Justin"><lang xml:lang="en-US">Web2Day</lang></voice>
```

Une fois tous ces changements effectuées, vous devriez avoir un prompt similaire à celui-ci

``` javascript
        let speechText = `<audio src='soundbank://soundlibrary/animals/amzn_sfx_lion_roar_02'/>
        Bienvenue sur la Skill du <amazon:effect name="whispered"><voice name="Kimberly"><lang xml:lang="en-US">workshop Alexa</lang></voice></amazon:effect> 
        pour le <voice name="Justin"><lang xml:lang="en-US">Web2Day</lang></voice>!
        Dites-moi bonjour et je vous répondrais`;
```

2. Sauvegarder vos changements

![save_backend](./images/save_backend.png)

>  **Important**: La console Developer Alexa ne fait pas de sauvegarde automatique des changements effectués. N'oubliez de sauvegarder vos modifications avant de fermer votre browser !

3. Déployez votre code

![deploy_backend](./images/deploy_backend.png)

> **Important**: Dès que vous faites une modification que vous souhaitez tester, n'oubliez jamais de déployer votre code. 

4. Allez à l'onglet `Test` pour tester le rendu final du prompt en invoquant votre Skill `ouvre web to day` 

5. Vous pouvez tester différents effets avec des balises SSML différentes. A chaque fois n'oublie pas de sauvegarder et déployer votre code avant de tester.


## Suivant : [Ajouter une intention](./05-add-intent.md)