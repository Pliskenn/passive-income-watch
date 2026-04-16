# passive-income-watch

Base de connaissance sur les opportunités de revenus passifs pour Laurent. Mise à jour quotidienne, commit direct sur `main`.

**Objectif :** 3 000 $/mois pour un maximum de 2h de travail quotidien (ratio cible : 50 $/h).

---

## Tableau de bord

- **Objectif :** 3 000 $/mois pour <= 2h/jour (ratio cible 50 $/h)
- **Revenu mensuel cumulé estimé (fourchette basse) :** 35 $
- **Progression vers l'objectif :** 1,2 %
- **Temps de maintenance quotidien total estimé :** 35 min/jour (30 min Prolific + 5 min monitoring Storj)
- **Nombre d'opportunités documentées :** routines=1, kimsufi=1

---

## Routines

Opportunités activables sans serveur dédié, intégrables dans une routine quotidienne.

| Nom | Complexité | Revenu mensuel | Temps/mois | Ratio $/h | Dernière MAJ |
|-----|-----------|----------------|------------|-----------|-------------|
| [Prolific - Études Académiques Rémunérées](routines/prolific-etudes-remunereees.md) | low | 30-150 $ | 5-15h | 8-15 $/h | 2026-04-16 |

---

## Kimsufi

Opportunités exploitant le serveur dédié bare-metal OVH (IP fixe, 100 Mbps+, accès root).

| Nom | Complexité | Revenu mensuel | Temps/mois | Ratio $/h | Dernière MAJ |
|-----|-----------|----------------|------------|-----------|-------------|
| [Storj Nœud Stockage](kimsufi/storj-noeud-stockage.md) | low | 5-25 $ | 15 min | 20-100 $/h | 2026-04-16 |

---

## À creuser

- **Mysterium Network (kimsufi)** : nœud VPN décentralisé payé en MYST. Les IPs datacenter sont valorisées moins que les IPs résidentielles (ratio 1/3), mais le service tourne 24/7 et la maintenance est nulle. À documenter après vérification des revenus réels sur IP OVH.
- **Respondent.io (routines)** : entretiens rémunérés 20-150 $/h pour des profils professionnels B2B. Ratio $/h potentiellement supérieur à Prolific si Laurent a un profil valorisable (tech, entreprise, secteur spécifique). À documenter en priorité.
- **Lava Network / Pocket Network (kimsufi)** : nœuds RPC payés pour servir des requêtes blockchain. Nécessite de faire tourner un nœud complet (Ethereum, etc.), ce qui consomme beaucoup de stockage. À évaluer selon l'espace disque disponible sur le Kimsufi.
- **Honeygain server-side (kimsufi)** : partage de bande passante. À tester si une IP OVH datacenter est acceptée (les IPs datacenter sont souvent bloquées ou limitées à un trafic très faible).
- **io.net (kimsufi)** : DePIN calcul décentralisé principalement orienté GPU. Vérifier si une configuration CPU-only génère un revenu non nul.
- **Nodepay (kimsufi/routines)** : réseau de bande passante DePIN. Vérifier compatibilité avec IP datacenter et revenus actuels.

---

## Journal quotidien

| Date | Mode | Action | Impact revenu |
|------|------|--------|--------------|
| [2026-04-16](daily/2026-04-16.md) | nouvelle-opportunite | Init repo + fiches Storj et Prolific | 0 → 35 $/mois |

---

## Structure du repo

```
passive-income-watch/
├── README.md              # Ce fichier, tableau de bord principal
├── routines/              # Fiches opportunités sans serveur dédié
├── kimsufi/               # Fiches opportunités exploitant le serveur Kimsufi
└── daily/                 # Logs quotidiens de veille
```
