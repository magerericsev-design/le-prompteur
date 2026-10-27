# LE PROMPTEUR

**by ERIC MAGER — LAB**

Une édition publique en cours de préparation pour lire un texte à voix haute, organiser les prises et afficher des images associées aux passages. Elle est née d’un besoin rencontré pendant la préparation de l’épisode 002 de « Curiosité & IA ».

**État : préversion 0.1.0.** Le logiciel n’a pas encore fait l’objet de l’ensemble des tests nécessaires à une version stable.

## Essayer en local

Depuis ce dossier, lancer `python -m http.server 8765 --bind 127.0.0.1`, puis ouvrir `http://127.0.0.1:8765/`. Arrêter le serveur avec Ctrl+C. Python sert uniquement à lancer ce serveur de développement ; le logiciel est écrit en HTML, CSS et JavaScript, sans service distant obligatoire.

## Premiers pas

1. Le projet de découverte contient trois images d’exemple. Cliquer sur **Repères** pour afficher ou masquer le panneau ; utiliser les flèches pour parcourir les passages.
2. Cliquer sur **Préparer le texte**, puis coller son texte ou importer un fichier `.txt` en UTF-8. Une ligne vide sépare deux passages ; `## Titre` crée un chapitre.
3. Cliquer sur **Utiliser ce texte**, régler la taille et la vitesse, puis sur **Lire**. La barre d’espace met en pause ou reprend la lecture ; les flèches du clavier permettent de changer de passage.
4. Une ligne `[pause 2s]` introduit une pause de deux secondes. Une indication seule entre crochets est affichée comme repère à ne pas prononcer.

## Studio : images et prises

Dans **Préparer le texte → Studio**, sélectionner le passage, ajouter une image PNG, JPEG, WebP ou GIF, puis éventuellement une note de préparation ou de montage. Fermer la fenêtre et afficher **Repères** : l’image et la note suivent le passage à la ligne de lecture.

Après modification du texte, les passages inchangés et uniques conservent leurs images et notes. Lorsqu’une correspondance est incertaine, les anciens repères sont conservés dans **Repères à réassocier** : sélectionner l’ancien repère et son nouveau passage, puis cliquer sur **Associer au passage choisi**. Vérifier les associations avant l’enregistrement.

Dans **Projets**, enregistrer localement et exporter une sauvegarde `.json`. Elle contient le texte, les images et les repères à réassocier. L’import crée un nouveau projet. Les images sont limitées à 5 Mo chacune et la sauvegarde portable à 30 Mo. Les données restent dans le navigateur : les effacer, changer de navigateur ou d’appareil peut les rendre indisponibles. Conserver une copie exportée.

## Confidentialité et limites

L’application ne demande ni compte ni accès à la caméra ou au microphone. Le code ne transmet pas les textes et images importés à un serveur. Les fichiers et données sont stockés localement par le navigateur, sous réserve de ses capacités et de l’espace disponible. Une sauvegarde exportée peut contenir des données personnelles : la conserver et la partager avec soin.

Un test Chromium a couvert la lecture, la pause, les chapitres, la sauvegarde, l’association et réassociation d’une image, l’export, l’import et la synchronisation de repères. Ce n’est pas une validation complète sur tous les navigateurs et appareils. Le mode hors ligne après fermeture, les interruptions, les gros fichiers et les interfaces tactiles restent à vérifier davantage.

## Développement

Pour les tests de développement : installer Node.js, exécuter `npm install` puis `npx playwright install chromium`. Lancer le serveur local indiqué plus haut et exécuter `npm test` dans un second terminal. Les tests utilisent Chromium ; ils ne remplacent pas les essais sur des appareils réels et d’autres navigateurs. Les trois images d’exemple ont été générées pour le projet ; voir `exemples/README.md` pour leur statut.
