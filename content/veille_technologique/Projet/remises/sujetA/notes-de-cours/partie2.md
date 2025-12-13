+++
title = "Partie 2"
weight = 2
+++

## 4. Les étapes du pipeline Voice-to-Text 
##### 1- Détection de la parole 

Durant cette étape, le système doit identifier le moment où la personne commence et finit de parler. Dès que la personne commence à parler, le système se met en marche. 

##### 2- Transformation du son en texte 

Cette étape est aussi appelée speech recognition et c’est la plus difficile. 
C’est durant cette étape que le son est changé en spectrogramme, une image qui montre comment le son varie dans le temps. Les modèles de deep learning ne lisent pas le son directement : ils utilisent ces images. Le modèle regarde ensuite le spectrogramme et trouve quels mots ont été dits. 

##### 3- Compréhension du texte — NLP / TAL 

Une fois le texte obtenu, le système va maintenant essayer de comprendre la demande. C'est là que cette methode intervient : **NLP (Natural Language Processing)/ TAL (traitements automatiques des langues)** . Cette méthode sert à identifier les mots importants, comprendre l'intention de la personne qui parle et analyser le contexte.

Exemple : si je demande au système : « Mets une alarme demain à 7 h » 
le système va comprendre que mon intention est de créer une alarme. 

##### 4- Génération de la réponse 

C'est le moment où le système va choisir la meilleure réponse ou la bonne action à exécuter selon ce qu'il a analysé.

##### 5- Synthèse vocale (Text-to-Speech) 

Enfin, si nécessaire, la réponse est transformée en voix. Cette étape utilise un autre type de modèle, le Text-to-Speech, qui convertit du texte en son. 

## 5. Cloud vs Local : où se fait le traitement ? 
### 5.1 Pourquoi le cloud ? 
De nombreux assistants vocaux mettent l’audio dans le cloud pour être analysé. Cela veut dire que l’audio quitte l’appareil et est traité sur des serveurs à distance. Ces serveurs sont très puissants et utilisent des modèles beaucoup plus gros que ceux qui se retrouvent dans un téléphone ou un ordinateur personnel. Le cloud est utilisé parce qu’il offre plusieurs avantages importants : 

- Les serveurs ont beaucoup plus de puissance, ce qui permet d’analyser la voix plus rapidement et plus précisément.
- La précision est souvent meilleure, car les modèles sont mis à jour régulièrement.
- Les mises à jour sont automatiques, donc le système devient meilleur sans que l’utilisateur fasse quoi que ce soit. 

Cependant, utiliser le cloud a aussi des inconvénients : 

- Il faut absolument une connexion Internet, sinon la reconnaissance vocale ne fonctionne pas. 
- La confidentialité cause des problèmes, car la voix doit quitter l’appareil et être envoyée sur un serveur externe, ce qui peut inquiéter certains utilisateurs. 

### 5.2 Pourquoi le local ? 
De plus en plus de systèmes commencent maintenant à fonctionner localement, c'est-à-dire directement sur l'appareil, sans envoyer les données dans le cloud. Des modèles comme Whisper, Vosk ou des systèmes directement intégrés dans certains téléphones récents permettent cela. Utiliser le local offre plusieurs avantages : 

- La confidentialité est meilleure, car les données restent sur l'appareil.
- Il n'y a pas besoin d'Internet, ce qui permet d'utiliser le système n'importe où.
- Il n'y a pas de latence, car l'appareil n'a pas besoin d'envoyer les données et d'attendre une réponse, tout se fait sur place.

Mais cette approche a aussi ses limites : 

- Il faut un appareil assez puissant pour que la reconnaissance vocale soit fluide.
- Les modèles locaux sont souvent plus petits, donc parfois moins précis que les modèles utilisés dans le cloud.


## 6. Limites actuelles du Voice-to-Text
Même si la technologie de reconnaissance vocale a beaucoup progressé grâce au Deep Learning, elle reste encore imparfaite. Plusieurs limites font en sorte que les systèmes de Voice-to-Text ne comprennent pas toujours correctement ce que la personne dit, même avec un bon microphone et un modèle avancé. 

##### 1- Accents
Les accents sont l’un des plus grands défis. Lorsqu’une personne a un accent, certains sons ne sont pas prononcés de la même manière que dans les données utilisées pour entraîner le modèle. Cela peut changer complètement la façon dont un mot est entendu par l’IA. Par exemple, un même mot peut être prononcé différemment selon les régions, ce qui peut facilement tromper le modèle et provoquer des erreurs de la part du système. 

##### 2- Dialectes et variations régionales 
En plus des accents, plusieurs régions ont leurs propres expressions ou façons particulières de parler, comme le joual au Québec par exemple. Ces expressions ne sont pas présentes dans les bases de données des systèmes. Le modèle ne reconnaît pas les mots typiques des régions ou ils ont du mal à comprendre une phrase qui utilise un dialecte. 

##### 3- Langues rares 
Les langues peu parlées sont aussi un défi, car les chercheurs ont moins d'enregistrements audio pour entraîner les modèles. Puisqu'il y a moins de données, l'IA n'apprend pas correctement, et cela entraîne une moins bonne précision.

##### 4- Hésitation réelle  
Dans la vraie vie, les gens ne parlent pas comme lorsqu'ils font l'enregistrement. Ils hésitent, ils répètent, parfois ils coupent leurs phrases ou ils parlent trop vite. Ce sont des comportements naturels d'être humain qui peuvent compliquer le travail du modèle qui n'est pas habitué à ça. Il va essayer de deviner ce qui est réellement dit ou essayer de déterminer si le mot existe ou pas.

##### 5- Bruit autour 
Enfin, le bruit autour de la personne peut affecter la qualité du Voice-to-Text. Que ce soit dans un environnement bruyant, comme dans la rue, dans une voiture ou dans une pièce avec plusieurs personnes, cela peut rendre la reconnaissance vocale beaucoup moins efficace. Même les meilleurs modèles peuvent se tromper lorsque le son de la voix est mélangé au bruit. 


## 7. Conclusion 
La technologie Voice-to-Text est un mélange de traitement du son, de deep learning et de grande puissance de calcul pour que les machines comprennent la voix humaine. Grâce aux GPU et aux énormes quantités de données utilisées pour entraîner les modèles, la reconnaissance vocale est devenue beaucoup plus précise qu’avant. Elle peut maintenant comprendre la majorité des phrases du quotidien et répondre rapidement aux demandes des utilisateurs. Même si cette technologie fonctionne bien, elle reste imparfaite. Il reste encore des certains trucs à améliorer pour cette technologie puisse prendre un autre niveau comme mentionnée plus haut.  

Malgré ces défis, le Voice-to-Text fait maintenant partie de la vie de tous les jours. Dans les prochaines années, on peut s'attendre à ce que ces systèmes deviennent encore plus rapides, plus privés et meilleurs pour comprendre toutes les façons de parler.


##### Sources :
- https://www.youtube.com/watch?v=5meAZFpjJ2g&t=870s
- https://www.ibm.com/fr-fr/think/topics/speech-recognition#1197505100
- https://www.ringover.fr/blog/automatic-speech-recognition