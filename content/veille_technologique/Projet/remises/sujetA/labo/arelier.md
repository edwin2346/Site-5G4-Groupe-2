+++
title = "Exercices "
weight = 3
+++

## Exercice 1 — Transcription de base

### Objectif :
Vérifier que Whisper fonctionne correctement.

### Instructions :

**1.** Construire l'image Docker :

```bash
docker build -t atelier-whisper .
```

#### Explication :
- `docker build`  
  - Demande à Docker de **construire une image** à partir d'un Dockerfile.

- `-t atelier-whisper`  
  - Donne un **nom** à l'image Docker créée.  
  Dans notre context, l'image s'appellera `atelier-whisper`.

- `.` **(le point)**  
  - Indique à Docker d'utiliser le **Dockerfile présent dans le dossier courant**.

**2.** Lancer la transcription avec le script Python :

```bash
docker run --rm -v "%cd%":/app whisper-lab whisper audio.wav --language fr
```

#### Explication :
- `docker run`  
  - Lance un **conteneur Docker** à partir d'une image.

- `--rm`  
  - Supprime automatiquement le conteneur une fois la commande terminée.  
  Cela évite d'accumuler des conteneurs inutiles.

- `-v "%cd%":/app`  
  - Partage un dossier entre l'ordinateur et le conteneur.
  - `%cd%` : le dossier courant sur l'ordinateur (Windows)
  - `/app` : le dossier de travail dans le conteneur  
  Grâce à cela, le conteneur peut accéder au fichier `audio.wav`.

- `atelier-whisper`  
  - Nom de l'image Docker utilisée.

- `whisper`  
  - Lance l'outil Whisper à l'intérieur du conteneur.

- `audio.wav`  
  - Fichier audio à analyser et à transcrire en texte.

- `--language fr`  
  - Indique à Whisper que la langue de l'audio est le **français**, ce qui améliore la précision.

### Résultat attendu :
- Le texte contenu dans `audio.wav` s'affiche dans le terminal.

![Résultat de la transcription](/images/Res.PNG)

- Il y a également ces fichiers qui vont apparaitre :

 ![Résultat 2 de la transcription](/images/res2.PNG)


 ## Exercice 2 — Exécuter le script Python 

### Étape 1 — Créer le fichier `transcribe.py`

**1.** Dans le dossier du laboratoire (`ATELIER-WHISPER`), créer un fichier nommé :

```text
transcribe.py
```

**2.** Ajouter le code suivant dans le fichier :

```python
import whisper

# Charger le modèle Whisper
model = whisper.load_model("small")

# Transcrire le fichier audio
result = model.transcribe("audio.wav", language="fr")

# Afficher le texte transcrit
print("Texte transcrit :")
print(result["text"])
```

### Étape 2 — Exécuter le script Python avec Docker

Lancer la commande suivante :

```bash
docker run --rm -v "%cd%":/app whisper-lab python transcribe.py
```

#### Explication :
- `python transcribe.py`  
  - Indique au conteneur d'exécuter le fichier `transcribe.py` avec Python.


Vérifier que le texte transcrit s'affiche dans le terminal est bien celui-ci :
![Résultat exercice 2 de la transcription](/images/res3.PNG)

## Exercice 3 — Comparer les modèles Whisper

### Étape 1 — Modifier le script Python

**1.** Ouvrir le fichier `transcribe.py`.

**2.** Modifier la ligne suivante :

```python
model = whisper.load_model("small")
```

par :

```python
model = whisper.load_model("medium")
```

### Étape 2 — Exécuter le script avec Docker

Lancer la commande suivante :

```bash
docker run --rm -v "%cd%":/app whisper-lab python transcribe.py
```

### Ce que vous devez remarquer :
- Le modèle `medium` fournit une transcription plus précise.
- Le temps de traitement est plus long.
- Les modèles plus grands analysent plus de données, ce qui augmente le temps de calcul.

## Exercice 4 (Bonus) — Comprendre les limites du Voice-to-Text

### Étape 1 — Modifier l'audio (optionnel)

Si possible, enregistrer un **nouveau fichier audio** contenant :
- du bruit de fond,
- un accent plus marqué,
- une phrase prononcée plus rapidement.

Remplacer l'ancien fichier `audio.wav` par ce nouveau fichier.

### Étape 2 — Relancer la transcription

Lancer la commande suivante :

```bash
docker run --rm -v "%cd%":/app whisper-lab python transcribe.py
```

### Ce que vous devez remarquer :
- La transcription peut contenir plus d'erreurs si l'audio est de moins bonne qualité.
- Le bruit de fond, les accents prononcés et la vitesse d'élocution affectent la précision du modèle.
- Même les meilleurs modèles ont des limites face à des conditions audio difficiles.
