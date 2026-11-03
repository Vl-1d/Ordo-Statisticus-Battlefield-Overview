<p align="center"><img src="logo.png" width="140" alt="Ordo Statisticus"></p>

<h1 align="center">ORDO STATISTICUS — BATTLEFIELD OVERVIEW</h1>

<p align="center">Capture et rapports de parties de <strong>Warhammer 40,000</strong> jouées sur <strong>Tabletop Simulator</strong> (table LCT).</p>

<p align="center"><a href="../../releases/latest"><strong>⬇ Télécharger l'application Windows (dernière version)</strong></a></p>

<p align="center"><sub>Lien direct : <a href="../../raw/main/OrdoStatisticus_Battlefield_Overview.exe">OrdoStatisticus_Battlefield_Overview.exe</a></sub></p>

<p align="center"><sub>🐧 Linux (version de test) : <a href="../../releases/tag/v0.8.3-linux">archive Linux x86_64</a></sub></p>

---

## Ce que fait l'application

À chaque phase de la partie, l'application relève l'état de la table dans Tabletop Simulator :
positions des figurines, PV, pertes, déplacements et charges, score (primaires et secondaires par round),
secondaires tirées, marquées et défaussées, contrôle des objectifs (somme des OC), décors, empreintes et
zones de déploiement.

À la fin : un **rapport HTML** à rejouer phase par phase (plan de la table, ombre au sol des grosses
figurines, panneaux par joueur), à annoter au **pinceau**, et un message **Discord** avec le score et
l'image du plan.

## Installation

1. Ouvrir la page **[Releases](../../releases/latest)** et télécharger
   **`OrdoStatisticus_Battlefield_Overview.exe`**.
2. Le lancer : l'interface s'ouvre dans votre navigateur.
3. Windows peut afficher « Windows a protégé votre ordinateur » (programme non signé) :
   **Informations complémentaires > Exécuter quand même**.

**Linux (test)** : télécharger l'archive de la [version Linux](../../releases/tag/v0.8.3-linux), la décompresser,
puis lancer `./OrdoStatisticus_Battlefield_Overview` (ou `./install.sh` pour l'ajouter au menu des applications).
Tabletop Simulator doit être la version Linux native (Steam).

Rien d'autre à installer : tout est inclus dans l'exécutable. Les réglages et les parties sont rangés
dans `Documents/Ordo Statisticus`.

## En bref : l'ordre à respecter

1. Dans Tabletop Simulator, **créer la partie en hôte** et charger la table **LCT**.
2. **Poser la table** (décors, empreintes, objectifs) et **ajouter les armées** des deux joueurs.
3. Dans l'application : **Vérifications > Vérifier la table**, puis **Lancer la lecture**
   (avant de décider du premier joueur).
4. Jouer en passant **chaque phase et chaque tour avec les boutons du menu de la table** dans TTS.
5. **Terminer la partie** : le rapport s'ouvre.

Mode d'emploi complet : **[GUIDE.md](GUIDE.md)**.

## Mises à jour et problèmes

Télécharger la nouvelle version sur la page [Releases](../../releases) et remplacer l'ancien exécutable :
réglages et parties sont conservés. Pour signaler un problème : onglet **Issues**, en joignant
`Documents/Ordo Statisticus/journal.txt` et le dossier de la partie.

<sub>Projet indépendant de fans, sans lien avec Games Workshop ni avec les auteurs de Tabletop Simulator
ou de la table LCT. Logo : illustration « Art Brushray ».</sub>
