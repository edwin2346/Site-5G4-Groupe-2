+++
title = "Partie 1"
weight = 1
+++


## 1. Introduction 

Le Voice-to-Text, ou reconnaissance vocale, est une technologie qui transforme la parole humaine en texte. Lorsqu'une personne parle dans un micro, le système enregistre le son, l'analyse, identifie les mots puis les convertit en texte exploitable. Le Voice-to-Text est devenu extrêmement présent dans notre quotidien. On le retrouve dans les téléphones intelligents à travers des assistants vocaux comme Siri (Apple), Google Assistant, Alexa (Amazon) ou Bixby (Samsung). On l'utilise aussi dans les sous-titres automatiques sur YouTube, TikTok ou dans les réunions en ligne via Zoom et Microsoft Teams. Elle est devenue essentielle pour les personnes ayant des limitations physiques ou visuelles, car elle permet de dicter du texte ou de contrôler un appareil uniquement avec la voix.Cette technologie paraît super simple pour les gens qui l'utilisent : on parle, et le texte apparaît. En réalité, plusieurs étapes complexes se déroulent en quelques secondes. Le cœur de cette technologie repose sur un domaine spécifique de l'intelligence artificielle qu'on appelle le deep learning.




## 2. Le rôle du Deep Learning dans la reconnaissance vocale
### 2.1 Pourquoi le deep learning est indispensable

Avant l’arrivée du deep learning, les systèmes de reconnaissance vocale utilisaient des règles très strictes. Il fallait créer manuellement des modèles basés sur les caractéristiques du son. Ces systèmes marchaient mal : ils étaient très sensibles au bruit, aux accents et aux différences naturelles dans la manière de parler. Ils demandaient même parfois que l’utilisateur s’habitue à prononcer certains mots d’une façon précise pour que la machine réussisse à les comprendre et r econnaitre les mots prononcer.

Le deep learning a complètement changé ce domaine. Contrairement aux anciens systèmes, un modèle de deep learning n’a pas besoin que’on lui écrivent toutes les règles. Il apprend ces règles tout seul en observant de très grandes quantités de données audio et les textes qui correspondent à ces audios. Le modèle apprend ainsi à repérer les sons importants, à différencier des mots très proches et à reconnaître plusieurs manières différentes de parler. 

### 2.2 Comment le modèle apprend

Pour entraîner un modèle de reconnaissance vocale, les chercheurs utilisent des milliers, parfois des millions d'heures d'enregistrements de voix. Chaque enregistrement est accompagné du texte correspondant. Le modèle écoute et compare :

- Les enregistrements audios (les ondes et signal sonores).
- Le texte qui est prononcé dans cet audio.

Avec le temps, il apprend à associer les ondes sonores des enregistrements qu'il reçoit à des lettres, puis à des syllabes, à des mots et finalement après de plusieurs calculs, il réussit à faire des phrases complètes.

Les données utilisées prennent en compte : différentes langues, divers accents, des voix d'hommes, de femmes et d'enfants, des enregistrements réalisés dans des endroit plutôt silencieux. Plus la diversité des données est grande, plus le modèle sera robuste et capable de comprendre n'importe qui et bien effectuer les tâches qui lui ont été demandée.

### 2.3 L'importance des GPU et de la puissance de calcul dans les systèmes de Voice-to-texte

Pour entraîner un modèle de reconnaissance vocale il faut beaucoup de puissance informatique importante. Les réseaux neuronaux actuels peuvent avoir des milliards de paramètres, qui sont des valeurs que le modèle ajuste constamment pendant l'entraînement. 

Les GPU (Graphics Processing Units) sont des processeurs spécialisés capables d'effectuer de nombreux calculs en même temps. À la base ils sont conçus pour afficher les images des jeux vidéo, mais aujourd'hui, ils sont beaucoup utilisés en intelligence artificielle grâce à leur rapidité et leur capacité à traiter de grandes quantités de données en même temps.

Les GPU sont très importants car :

- ils effectuent d'immenses quantités de calculs en parallèle.
- ils réduisent l'entraînement des systeme de voice-to-text de plusieurs mois à quelques jours.
- ils permettent de tester des modèles plus grands et plus précis.
- ils autorisent des mises à jour fréquentes.

Sans GPU et sans cloud computing, la reconnaissance vocale moderne n'existerait tout simplement pas.


## 3. Deux phases : apprentissage et utilisation 
### 3.1 Phase 1 — L'apprentissage (training)

L'apprentissage est l'étape la plus importante. C'est aussi la plus longue et la plus difficile à réaliser, car c'est l'étape où le modèle doit écouter une énorme quantité d'exemples pour comprendre comment les humains parlent. Dans cette phase :

Le modèle reçoit des milliers d'exemples audio accompagnés du texte. Par exemple, Par exemple, il écoute une personne dire « Bonjour » et voit que le texte correspondant est « Bonjour ». Ensuite, Il compare le son et le texte pour comprendre la relation entre les deux. Il essaie de repérer les sons, la prononciation et les caractéristiques communes dans les enregistrements. A la fin , Il apprend les structures de notre langage. Cela inclut les mots, la façon dont les phrases sont faites, les intonations et il essaye même d'apprendre les variations naturelles dans la voix humaine.

Même avec des GPU très puissants, cette phase peut durer plusieurs jours, même plusieurs semaines, car l'IA doit analyser des millions de données avant d'être prête à fonctionner correctement. Alors imaginer le temps que cela prendrait sans les GPU.

### 3.2 Phase 2 — L’utilisation 

Une fois que l’apprentissage est terminé, le modèle est prêt à être utilisé. La version finale est installée sur un téléphone, dans un ordinateur, ou dans un service cloud comme Google ou Amazon. Cette phase est beaucoup plus rapide, car l’IA fait juste appliquer ce qu’elle a déjà appris. Lorsqu’on lui parle, elle doit réagir en quelques secondes. Elle va alors effectuer 5 étapes pour répondre aux attentes. 


