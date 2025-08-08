# 🎙️ Podcast Creator - Générateur de podcasts à partir d'un script texte

[![Ouvrir dans Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Gandulf78/generate_podcast/blob/main/podcast_creator.ipynb)

Ce notebook interactif permet de **générer automatiquement un fichier audio de type podcast** à partir d’un **script de dialogue texte** en anglais, avec des voix synthétiques réalistes grâce à [Bark](https://github.com/suno-ai/bark).

---

## ✨ Fonctionnalités

- 🎧 Synthèse vocale multi-voix (ex: John & Samantha)
- 📄 Chargement facile d’un script texte via interface
- 🎚️ Ton de voix personnalisable via les indications
- 🔊 Génération d’un fichier `.wav` directement téléchargeable
- 📁 Support de Google Drive pour stocker les sorties
- ✅ Barre de progression et journalisation via log

---

## 📜 Format attendu du script

Votre fichier `.txt` doit suivre ce format :

```text
John: [serious tone] Welcome to our journey through English history. A story of conquests, of kings and sometimes of heads that roll.
Samantha: [intrigued] I have a feeling we're going to talk about William the Conqueror, right?
John: [informative] Exactly. 1066. The Battle of Hastings...
Samantha: Thank you John!
```

Chaque ligne doit commencer par un prénom (`John` ou `Samantha`), suivi d’un deux-points, puis du texte.

---

## 🚀 Utilisation rapide

### Sur Google Colab (recommandé)

1. Cliquez ici pour l’ouvrir dans Colab :  
   👉 [Ouvrir dans Colab](https://colab.research.google.com/github/Gandulf78/generate_podcast/blob/main/podcast_creator.ipynb)

2. Cliquez sur **"Exécuter tout"** dans le menu Colab.

3. Une fois les widgets affichés :
   - Téléversez votre script `.txt`
   - Cliquez sur **"🎙️ Générer le podcast"**

4. Le fichier audio sera généré et téléchargeable (`podcast_output.wav`).

---

## 🛠️ Environnement et dépendances

Le notebook installe automatiquement :

- `bark` (via GitHub)
- `soundfile`, `ipywidgets`, `torch`
- `tqdm.notebook` (progression dans Colab)
- Utilise `Bark` avec modèles réduits (`SUNO_USE_SMALL_MODELS=True`)
- Logging des warnings vers `bark_generation.log`

---

## 📂 Stockage Google Drive (optionnel)

Si vous souhaitez stocker le podcast dans votre Google Drive :

1. Définissez un secret visible du Notebook dans Colab :
   ```
   USE_DRIVE=True
   ```
2. Le script montera automatiquement votre Drive et enregistrera les fichiers générés dans `/MyDrive/BarkOutputs`.

---

## 🔒 Remarques

- Le modèle Bark nécessite un GPU (par ex. `T4`, `A100` sur Colab).
- Les voix sont définies statiquement :
  - `John` → `v2/en_speaker_1`
  - `Samantha` → `v2/en_speaker_9`

Vous pouvez modifier ces paramètres dans le dictionnaire `voice_prompts` dans le code.

---

## 📃 Licence

Ce projet est sous licence **MIT**.  
Le modèle Bark est sous licence Apache 2.0. Voir le [repo officiel](https://github.com/suno-ai/bark) pour plus de détails.

---

## 🙌 Merci

Créé par [Gandulf78](https://github.com/Gandulf78) – Contributions bienvenues !
