# 🚴 Cyclo Zones — Test d'Effort Progressif à Vélo

Outil gratuit et open-source pour faire un **test de niveau à vélo** sur home
trainer, puis en tirer une **cible d'entraînement concrète** (fréquence
cardiaque, vitesse, cadence) pour les sorties régulières.

👉 **Utiliser l'outil en ligne :** https://gregoiremp.github.io/cyclo-zones/

Aucune installation, aucun compte, aucune donnée envoyée à un serveur : tout
tourne dans le navigateur (Chrome ou Edge, pour le support Bluetooth).

## Ce que ça fait

Le projet est une page HTML/JS autonome, sans backend, avec deux modules :

### 1. Test en direct
- Connexion à 3 capteurs Bluetooth indépendants : fréquence cardiaque,
  cadence et vitesse (profils BLE standards, testé avec des capteurs Magene
  sur un home trainer Tacx Boost à résistance manuelle)
- Protocole par paliers configurable (nombre, durée, résistance début/fin)
  avec avancement automatique et bip sonore
- Zones FC calculées en Karvonen (%FC de réserve) ou %FCmax
- Ressenti RPE (1-10), boutons symptômes avec alerte visuelle si la FC
  s'approche du maximum estimé
- Graphique live, résumé par palier, export CSV structuré

### 2. Analyse post-test (CSV)
- Charge le CSV exporté par le test en direct
- FC moyenne/max, cadence et vitesse moyennes, temps passé par zone
- Détection du palier de bascule vers l'effort seuil
- Détection d'incohérences entre FC mesurée et ressenti déclaré (RPE)
- Recommandation concrète : vitesse/cadence/FC à viser pour rester en
  zone d'endurance (Z2) lors des sorties normales, sans capteur

## ⚠️ Important

**Ce n'est pas un dispositif médical.** L'outil affiche et enregistre des
données brutes, et propose des repères d'entraînement généraux (zones FC
classiques). Il ne pose aucun diagnostic, ne calcule pas de VO2max, et ne
remplace pas l'avis d'un professionnel de santé — en particulier pour toute
personne avec un antécédent cardiaque. En cas de douleur thoracique, vertige
ou malaise pendant un test, arrêter immédiatement.

## Utilisation locale

Aucune dépendance à installer — juste ouvrir le fichier dans Chrome ou Edge :

```bash
git clone https://github.com/gregoiremp/cyclo-zones.git
cd cyclo-zones
python3 -m http.server 8934
# puis ouvrir http://localhost:8934/dashboard_test_cardiaque_velo.html
```

(ou double-cliquer directement sur `dashboard_test_cardiaque_velo.html` —
Chrome traite les fichiers locaux comme un contexte sécurisé, le Bluetooth
fonctionne aussi en `file://`.)

## Évolution du projet

Voir [CHANGELOG.md](CHANGELOG.md) pour le détail de chaque version, ou
l'historique Git (`git log`) et les tags `v0.1` à `v0.4`.
