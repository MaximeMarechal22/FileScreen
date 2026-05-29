# FileScreen

**FileScreen** est une application Windows qui permet d'afficher des images, vidéos ou textes en overlay sur l'écran, déclenchés en temps réel depuis un salon Discord.

---

## Fonctionnalités

- **Overlay en temps réel** — un bot Discord écoute un salon et affiche le média sur l'écran de l'hôte
- **Images & vidéos** — lecture via ffmpeg embarqué (pas d'installation séparée requise)
- **Animations d'entrée** — chute, spin, glitch, tremble, zoom, yeet, fondu, flou
- **Modificateurs visuels** — grand, petit, retourne, miroir, noir & blanc
- **Ciblage par pseudo** — un overlay peut ne s'afficher que pour un utilisateur précis (`@pseudo`)
- **Son d'annonce** — bip sonore configurable à l'arrivée d'un overlay
- **Couleur d'accent personnalisable** — interface adaptée à ta charte
- **Historique des overlays** — les 200 derniers affichages sont conservés
- **Auto-update** — si une nouvelle version est publiée sur GitHub, une pop-up propose la mise à jour et installe automatiquement

---

## Syntaxe des commandes Discord

Les commandes s'écrivent directement dans le message Discord, avec le lien ou texte à afficher.

| Commande | Effet |
|---|---|
| `@pseudo` | Cible un utilisateur précis (sans `@` = tout le monde) |
| `!chute` `!spin` `!glitch` `!tremble` `!zoom` `!yeet` `!fondu` `!flou` | Animation d'entrée |
| `#grand` `#petit` | Taille de l'overlay |
| `#retourne` `#miroir` | Transformation visuelle |
| `#nb` | Noir & blanc |
| `!fort` | Volume au maximum |
| `!muet` | Coupe le son |
| `!long` | Durée étendue (30 s) |
| `!flash` | Durée très courte (1 s) |
| `!clear` | Efface l'overlay en cours et vide la file d'attente |

**Exemples :**
```
https://exemple.com/image.png @alice !chute #grand
Une blague en texte @bob !glitch
https://exemple.com/clip.mp4 !muet !long
```

---

## Installation

1. Télécharge le dernier installeur `.exe` depuis la page [Releases](../../releases)
2. Lance l'installeur et suis les étapes
3. Au premier démarrage, renseigne dans les paramètres :
   - le **token** de ton bot Discord
   - l'**ID du salon** à écouter
   - ton **pseudo** (pour le ciblage `@pseudo`)

> Le bot Discord doit avoir les permissions **Lire les messages** et **Lire l'historique** sur le salon configuré.

---

## Mise à jour

FileScreen vérifie automatiquement au démarrage si une nouvelle version est disponible. Si c'est le cas, une pop-up s'affiche. Clique sur **Mettre à jour** : l'installeur est téléchargé et lancé, puis l'app se ferme et se réinstalle toute seule.

Tu peux aussi télécharger manuellement le dernier installeur sur la page [Releases](../../releases).

---

## Lancer depuis le code source

### Prérequis

- Python 3.10+
- Les dépendances suivantes :

```
pip install customtkinter discord.py requests pillow pygame opencv-python static-ffmpeg numpy
```

### Lancer

```bash
python main.py
```

---

## Publier une mise à jour (pour les développeurs)

1. Incrémente `APP_VERSION` dans `main.py` (ex: `"2.4.0"`)
2. Compile l'installeur `.exe` (Inno Setup ou NSIS)
3. Sur GitHub, crée une **Release** avec le tag `v2.4.0`
4. Upload le fichier `.exe` en tant qu'**asset** de la release
5. FileScreen détectera automatiquement la nouvelle version au prochain démarrage des utilisateurs

---

## Dépendances

| Librairie | Rôle |
|---|---|
| `customtkinter` | Interface graphique moderne |
| `discord.py` | Bot Discord |
| `requests` | Téléchargements HTTP |
| `Pillow` | Traitement des images |
| `pygame` | Son d'annonce |
| `opencv-python` | Lecture vidéo frame par frame |
| `static-ffmpeg` | ffmpeg embarqué (son vidéo) |
| `numpy` | Génération du bip sonore |

---

## Licence

Ce projet est distribué sans licence particulière — usage personnel uniquement.
