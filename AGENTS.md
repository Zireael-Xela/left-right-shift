# Brief pour Codex — projet Game Off 2026 (thème SHIFT)

## Contexte

Jeu de puzzle coopératif solo : deux personnages, un par touche Shift (voir `GAME_DESIGN.md`, qui fait foi).
Moteur : Godot 4 (dernière version stable), GDScript. Cible : export web (itch.io).
Alex est débutant sur Godot et veut **comprendre** ce que tu écris.

## Règles de collaboration

1. **Alex décide du gameplay.** N'invente ni mécanique, ni niveau, ni fonctionnalité. Si le brief ne dit pas quelque chose, pose la question ou propose 2 options sans les implémenter.
2. **Petits pas.** Une tâche = un commit court, en français. Ne fais rien au-delà de la tâche demandée (pas de refactor, pas de bonus).
3. **Code lisible pour un débutant :** GDScript typé, fonctions courtes, commentaires en français qui expliquent le *pourquoi*, identifiants en anglais. Pas de plugin, pas de pattern sophistiqué, pas d'autoload sans raison.
4. **Après chaque tâche**, termine par 5 lignes maximum : ce que tu as fait, pourquoi, comment le tester.
   **Avant de coder**, si un choix structurant a plusieurs options réalistes (organisation des scènes, gestion des entrées, architecture), expose-les en 3 lignes avec leurs compromis et attends le choix d'Alex et Claude. Pour les détails mineurs, décide seul et explique-toi en une ligne.
5. **Règles du jam :** tout le code est écrit pendant novembre, dans un dépôt GitHub public. Les assets sont créés par nous ou libres de droits, avec une ligne par asset dans `CREDITS.md`. Ces règles reprennent celles de l'an dernier : à revérifier sur la page du jam.
6. **Clavier :** utiliser les touches **physiques** (`physical_keycode`) pour le déplacement, afin que l'AZERTY et le QWERTY marchent pareil. Toutes les actions passent par l'InputMap (jamais de touche codée en dur).

## Tâches (dans l'ordre, ne pas anticiper la suivante)

### Tâche 1 — Squelette du projet
- Projet Godot 4, renderer Compatibility (requis pour le web), `.gitignore` Godot, `README.md` minimal, `CREDITS.md` vide, licence MIT.
- Fin : le projet s'ouvre et affiche une scène vide.

### Tâche 2 — Scène de test des touches (`input_test.tscn`)
- Affiche en direct l'état de Shift gauche et de Shift droit (enfoncé / relâché), en utilisant `InputEventKey.location`.
- Affiche un compteur de pressions pour chaque Shift et un indicateur « les deux tenus ».
- Journal des 10 derniers événements (touche, location, pressed).
- Fin : Alex peut tenir les deux Shift, en relâcher un seul, et lire un état correct.

### Tâche 3 — Test sur navigateur
- Export web, lancement en local, et note courte (`NOTES_INPUT.md`) : le comportement est-il identique à l'éditeur ? Où ça diffère ?
- Indique comment servir le build en local pour que le test soit reproductible.

### Tâche 4 — Actions remappables
- Actions InputMap : `l_left`, `l_right`, `l_up`, `l_down`, `l_hold`, `r_left`, `r_right`, `r_up`, `r_down`, `r_hold`.
- `l_hold` = Shift gauche, `r_hold` = Shift droit, plus une **liaison alternative** pour chacune (par exemple Ctrl gauche / Ctrl droit). Propose ton choix, Alex tranchera.

**STOP ici.** Le prototype de salle ne se code qu'après validation par Alex et Claude des résultats des tâches 2 à 4.
