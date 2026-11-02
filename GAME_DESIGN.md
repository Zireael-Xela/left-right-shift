# LEFT · RIGHT — fiche de design (titre provisoire)

**Jam :** GitHub Game Off 2026, thème SHIFT. Fin le 1er décembre à 13h37 PST (22h37 à Paris).
**Moteur :** Godot 4, GDScript, export web pour itch.io.
**Qui décide :** Alex et Claude. Codex implémente, il ne conçoit pas le gameplay.

## Pitch (une phrase)

Un joueur, deux mains, deux personnages : chaque touche Shift pilote l'un des deux, et il faut les coordonner pour que chacun atteigne sa sortie.

## Pourquoi ça colle au thème

SHIFT est à la fois la touche et le mot d'ordre du jeu : on « shifte » les rôles. Celui qui tient le mécanisme laisse passer l'autre, puis on inverse.

## Pourquoi cette contrainte

La difficulté vient de la coordination des deux mains, pas de niveaux compliqués. Il faut donc peu de contenu pour que le jeu soit intéressant, ce qui est adapté à un jam solo d'un mois.

## Boucle de jeu

1. L'écran est coupé en deux : moitié gauche = personnage L (main gauche), moitié droite = personnage R (main droite).
2. Chaque personnage se déplace : main gauche avec ZQSD, main droite avec les flèches.
3. **Shift tenu** = « tenir » le mécanisme à portée. Tant que L tient son mécanisme, la porte liée dans le monde de R reste ouverte (et inversement).
4. R passe, puis les rôles s'inversent : R tient, L passe.
5. La salle est réussie quand les deux personnages sont sur leur sortie.

## Décisions prises

- Deux personnages contrôlés en même temps (et non une bascule de propriété du monde).
- Deux verbes par personnage : se déplacer et tenir. Pas de saut, pas d'attaque.
- Les Shift se **tiennent**, ils ne se martèlent jamais. Ça évite les « touches rémanentes » de Windows (5 pressions de Shift de suite).
- Les touches d'action sont remappables : alternative aux Shift pour l'accessibilité ou les claviers gênants.
- Touches physiques pour le déplacement, pour que l'AZERTY et le QWERTY marchent pareil.
- GDScript uniquement.

## Ce que le prototype doit prouver (go / no-go)

Prototype : deux signaux (carrés gris), deux Shift, une salle. Pas de graphismes, pas de scénario, pas de fonctionnalité en plus.

1. **Détection :** Shift gauche et Shift droit sont détectés indépendamment **et simultanément**, dans l'éditeur **et** dans l'export navigateur. Cas à tester : tenir les deux, puis en relâcher un seul.
2. **Coordination intéressante :** on réfléchit et on planifie, on ne se contente pas de maintenir deux touches sans y penser.
3. **Changements de rôle = vrais choix :** qui tient, qui passe, dans quel ordre ? Un joueur qui n'a pas la solution hésite entre plusieurs options. C'est probablement là que se trouve la mécanique distinctive du jeu.
4. **Confort et accessibilité :** testé avec de vrais joueurs (au moins 3, dont une personne qui n'a pas lu la fiche). Les deux mains en même temps fonctionnent sans touche fantôme (ghosting) et la liaison alternative aux Shift marche.
5. **Lisibilité :** un proche comprend la règle en moins d'une minute sans explication.

Si l'un des points 2, 3 ou 5 est non, on change de mécanique (plan B : Shift = décalage d'une ligne de nœuds, comme un registre à décalage) sans s'attacher au code existant.

## Habillage (pas avant le go)

Univers cyberpunk / terminal : les deux personnages deviennent deux signaux dans un réseau à deux couches, physique (gauche) et numérique (droite). On ne touche pas à ça avant le go.

## Hors périmètre tant que le go n'est pas donné

Menus, musique, ennemis, sauvegarde, plus d'un type de mécanisme, plus d'une salle.

## Calendrier indicatif

- **2-3 nov :** test des touches, prototype d'une salle, go/no-go.
- **4-15 nov :** 5 à 8 salles, qui introduisent une idée à la fois.
- **16-24 nov :** polish, sons, page itch.io, export web régulier.
- **25-30 nov :** tests, corrections, soumission **avant** le 1er décembre, pas à la dernière minute.
