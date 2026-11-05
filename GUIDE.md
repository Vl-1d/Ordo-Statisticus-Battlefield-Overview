# Ordo Statisticus — Battlefield Overview : guide de l'application

Capture une partie de Warhammer 40K jouée sur Tabletop Simulator (table **LCT**) à chaque phase :
positions, PV, score, secondaires, contrôle des objectifs. À la fin : un rapport HTML à rejouer phase par
phase, à annoter au pinceau, à publier sur Discord.

## 1. Installation (Windows)

1. Page GitHub du projet > **Releases** > dernière version > télécharger **`OrdoStatisticus_Battlefield_Overview.exe`**.
2. Le placer où vous voulez (Bureau, dossier Jeux…) et le lancer.
3. Windows peut afficher « Windows a protégé votre ordinateur » (programme non signé) :
   **Informations complémentaires > Exécuter quand même**.

Rien d'autre à installer : Python et toutes les bibliothèques sont **dans l'exécutable**. Le premier
lancement crée le dossier **`Documents/Ordo Statisticus`** :

| Élément | Rôle |
|---|---|
| `tts_extract.toml` | réglages (modifiables dans l'application, page **Réglages**) |
| `parties/` | une partie par dossier : captures, rapport `report.html`, images |
| `parties/.cache/` | formes des décors et des modèles 3D déjà calculées |
| `journal.txt` | journal de l'application (à joindre en cas de problème) |

L'application s'ouvre **dans votre navigateur** (adresse `http://127.0.0.1:8765/`). Relancer l'exécutable
alors qu'il tourne déjà rouvre simplement la page. Pour la fermer : bouton **Quitter** (refusé pendant une
partie en cours).

## 2. L'ordre à respecter

| # | Où | Quoi |
|---|---|---|
| 1 | TTS | **Créer la partie en hôte.** TTS n'exécute les commandes externes que chez l'hôte. |
| 2 | TTS | Charger la table **LCT (Warhammer 40,000)** et choisir la mission (primaire, déploiement, twist). |
| 3 | TTS | **Poser la table** : décors, empreintes, objectifs. |
| 4 | TTS | **Ajouter les armées** des deux joueurs (figurines LCT « [couleur]PV/PVmax[-] Nom »). |
| 5 | Application | Page **Vérifications** > **Vérifier la table** : aucune erreur ne doit rester. |
| 6 | Application | **Lancer la lecture**, *avant* de décider du premier joueur (le déploiement est capturé). |
| 7 | TTS | Jouer en passant **chaque phase et chaque tour avec les boutons du menu de la table** : une capture à chaque clic. |
| 8 | Application | Page **Partie en cours** > **Terminer la partie** (deux clics) : capture finale et rapport. |

> Ne sautez pas de phase dans TTS. En cas d'oubli : page **Partie en cours** > **Enregistrer la table**,
> en choisissant le tour et la phase ; les menus passent ensuite seuls à la phase suivante.

## 3. Les vérifications (failsafe)

Avant de lancer, l'application lit toute la table et contrôle :

| Vérification | Erreur bloquante si… |
|---|---|
| TTS répond, vous êtes l'hôte | TTS fermé, partie non chargée, ou vous êtes invité |
| Table LCT reconnue (menu de tour / phase) | la table n'est pas la table LCT |
| Décors et empreintes posés | aucun décor sur la table |
| Figurines détectées, pour **les deux** camps | aucune figurine, ou un camp sans figurine |
| Mission, zones de déploiement | *(avertissement seulement)* |
| Modèles 3D des grosses figurines (6 PV et plus) | *(avertissement)* modèle introuvable : socle seul |
| Plateaux des secondaires, feuille de score, OC | *(avertissement / information)* |
| Partie déjà commencée | *(avertissement)* le déploiement ne sera pas capturé |

**Lancer la lecture** reste grisé tant qu'une erreur subsiste. **Lancer malgré les erreurs** existe pour les
cas particuliers (deux clics pour confirmer).

Pendant la lecture, un bandeau rouge apparaît si TTS ne donne plus de nouvelles depuis 2 minutes (partie
fermée, hôte changé…). Le veilleur est relancé automatiquement, et chaque capture est enregistrée sur le
disque immédiatement.

## 4. Après la partie

Page **Parties enregistrées** :

- **Rapport** : ouvre le rapport. Les dessins du pinceau y sont enregistrés automatiquement quand vous
  quittez le mode pinceau.
- **Régénérer** : recalcule le rapport (après une mise à jour de l'application, par exemple).
- **Discord** : publie la partie (webhook à renseigner dans **Réglages**).
- **Reprendre** : une partie « En cours » qui n'est plus lue (application fermée, plantage) continue dans le
  même dossier. La partie lue en ce moment affiche « En cours · lecture » et un bouton **Suivre** ; son
  rapport peut être ouvert à tout moment sans interrompre la lecture.

## 5. En cas de problème

| Symptôme | Que faire |
|---|---|
| « TTS ne répond pas » | Lancer TTS, créer la partie **en hôte**, charger la table LCT, puis vérifier à nouveau. |
| « Port local occupé » | Une autre instance ou un éditeur avec l'extension TTS écoute le port 39998 : le fermer. |
| Aucune capture pendant la partie | Utiliser les **boutons du menu de la table** pour changer de phase (pas seulement le chat). |
| Le navigateur ne s'ouvre pas | Ouvrir `http://127.0.0.1:8765/` à la main. |
| Autre | Joindre `Documents/Ordo Statisticus/journal.txt` et le dossier de la partie. |

## 6. Mise à jour

Le numéro de la version utilisée est affiché en bas du menu de gauche, dans **Réglages > Version** et en pied de chaque
rapport (`tts-extract version` en ligne de commande). Au lancement, l'application compare ce numéro à la dernière version
publiée sur la page de téléchargement : si une version plus récente existe, un bandeau « Nouvelle version disponible »
s'affiche et mène directement au téléchargement. La vérification se désactive dans **Réglages** ; sans connexion, rien ne
bloque (la version est simplement indiquée « non vérifiée »).

Pour mettre à jour : télécharger le nouvel `OrdoStatisticus_Battlefield_Overview.exe` et remplacer l'ancien. Les réglages
et les parties (dans `Documents/Ordo Statisticus`) sont conservés.
