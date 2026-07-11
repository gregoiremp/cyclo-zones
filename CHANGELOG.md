# Changelog

Toutes les évolutions notables du projet sont documentées ici. Chaque
version correspond à un tag Git (`v0.1`, `v0.2`, ...) et à un commit dédié.

## v0.5 — Interface bilingue, auto-détection capteurs BLE, UX Protocol

- **Interface FR/EN complète** : tous les textes traduits, langue détectée
  automatiquement depuis le navigateur (mémorisée après premier changement)
- **Auto-détection du type de capteur BLE** : lecture de la caractéristique
  CSC Feature (0x2A5C) pour identifier vitesse vs cadence dès la connexion,
  watchdog 6 s en fallback, mémorisation par ID d'appareil (localStorage)
- **Objectif palier mis à jour en temps réel** : la plage bpm s'actualise
  immédiatement quand on modifie l'âge, FC max, FC repos ou les paramètres
  du protocole — même sans test lancé
- Labels de résistance `(1-10)` sur une seconde ligne (plus lisible dans
  les steppers étroits du protocole)
- Alignement des steppers Protocol corrigé (`align-items:flex-end` sur
  `.row` — les boutons ±  restent à la même hauteur même si le label voisin
  passe sur deux lignes)
- Barre de progression palier : couleur unie bleue (suppression du dégradé
  bleu→noir) ; récupération : gris neutre au lieu de noir
- Champ « Circonférence roue » retiré de l'UI (valeur 2105 mm hardcodée) ;
  hint « 3 capteurs en parallèle » et hint récupération retirés
- Valeurs profil par défaut révisées : âge 50, poids 75 kg, FC max 170

## v0.4 — Corrections graphique et affichage de la progression

- Fix du rendu du graphique (Chart.js) : conflit entre le ratio d'aspect
  auto-calculé et la `max-height` CSS qui écrasait/déformait l'affichage —
  résolu avec un conteneur à hauteur fixe et `maintainAspectRatio:false`
- Axe du temps du graphique live limité à ~8 repères lisibles au lieu d'une
  étiquette par seconde
- Nouvelle barre de progression segmentée par palier (une pastille par
  palier, colorée selon sa zone cible), avec pourcentage affiché
- La bannière d'alerte symptôme se referme désormais à l'arrêt/réinit. du
  test (l'événement reste dans le journal et l'export CSV)

## v0.3 — Refonte UX : contrôles et pilotage pendant l'effort

- Contrôles déplacés en haut de la colonne principale (au lieu du bas de
  la sidebar), plus visibles et accessibles pendant l'effort
- Boutons contextuels à l'état du test (Démarrer / Pause-Reprendre /
  Arrêter / Palier suivant activés-désactivés selon que le test tourne)
- Petit chrono de pause affiché pendant que le test est en pause
- Steppers +/- à la place des spinners natifs pour les champs à choix
  discrets (paliers, durée, résistance)
- Suppression a posteriori d'un événement RPE/symptôme mal cliqué
- Titre et objectif du test reformulés ; bannière générique retirée

## v0.2 — Module d'analyse post-test (CSV)

- Nouvel onglet : charge le CSV exporté par le test en direct
- FC moyenne/max, cadence, vitesse, résistance, RPE par palier
- Détection du palier de bascule vers l'effort seuil
- Détection d'incohérences FC/RPE
- Recommandation de vitesse/cadence/FC pour la zone d'endurance (Z2)
- Temps passé par zone, graphique et tableau détaillé par palier

## v0.1 — Dashboard live du test d'effort

- Première version : test de niveau à vélo piloté en direct
- Profil (âge, poids, taille, FC repos/max), IMC, 5 zones FC (Karvonen)
- Connexion à 3 capteurs Bluetooth indépendants (FC, cadence, vitesse)
- Protocole par paliers configurable, avancement auto, bip sonore
- RPE, boutons symptômes, graphique live, export CSV structuré
