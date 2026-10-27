# Contribuer

Les propositions sont bienvenues : explique le problème rencontré, les étapes pour le reproduire et le navigateur utilisé. Évite d’inclure des textes, images ou données privées dans un signalement.

Pour tester localement : installer les dépendances de développement avec `npm install`, puis les navigateurs de test avec `npx playwright install chromium firefox webkit`. Démarrer un serveur local avec `python -m http.server 8765 --bind 127.0.0.1` et, dans un autre terminal, lancer `npm test`. Le logiciel lui-même n’a pas de dépendance npm de production.

Toute proposition doit conserver la confidentialité locale des données et la possibilité de sauvegarder et récupérer les repères visuels.
