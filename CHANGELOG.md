# Changelog

Toutes les évolutions notables du projet sont documentées ici. Chaque
version correspond à un tag Git (`v0.1`, `v0.2`, ...) et à un commit dédié.

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
