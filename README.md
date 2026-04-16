# passive-income-watch

Base de connaissance sur les opportunités de revenus passifs et semi-passifs pour Laurent.
Veille quotidienne automatisée. Commit direct sur `main`.

**Objectif :** 3 000 $/mois pour un maximum de 2h de travail quotidien (ratio cible : 50 $/h).

---

## Tableau de bord

- **Objectif :** 3 000 $/mois pour <= 2h/jour (ratio cible 50 $/h)
- **Revenu mensuel cumulé estimé (fourchette basse) :** 120 $
- **Progression vers l'objectif :** 4 %
- **Temps de maintenance quotidien total estimé :** ~42 min/jour (30 min Prolific + 10 min Respondent + 1 min Storj + 1 min Akash)
- **Nombre d'opportunités documentées :** routines=2, kimsufi=2

---

## Routines

Opportunités activables sans serveur dédié, intégrables dans une routine quotidienne.

| Nom | Complexité | Revenu mensuel | Temps/mois | Ratio $/h | Dernière MAJ |
|-----|-----------|----------------|------------|-----------|-------------|
| [Respondent.io](routines/respondent-etudes.md) | low | 75-600 $ | 2-5h | 80-200 $/h | 2026-04-16 |
| [Prolific - Études Académiques Rémunérées](routines/prolific-etudes-remunereees.md) | low | 30-150 $ | 5-15h | 8-15 $/h | 2026-04-16 |

---

## Kimsufi

Opportunités exploitant le serveur dédié bare-metal OVH (IP fixe, 100 Mbps+, accès root).

| Nom | Complexité | Revenu mensuel | Temps/mois | Ratio $/h | Dernière MAJ |
|-----|-----------|----------------|------------|-----------|-------------|
| [Akash Network - Provider Calcul](kimsufi/akash-provider-compute.md) | high | 10-50 $ | 30 min | 20-100 $/h | 2026-04-17 |
| [Storj Nœud Stockage](kimsufi/storj-noeud-stockage.md) | low | 5-25 $ | 15 min | 20-100 $/h | 2026-04-16 |

---

## À creuser

- **Mysterium Network (kimsufi)** : nœud VPN décentralisé payé en MYST. Les IPs datacenter génèrent ~2-5 $/mois (3x moins qu'une IP résidentielle). Revenu absolu faible, mais maintenance nulle. À documenter uniquement si besoin de compléter le portefeuille avec un service set-and-forget additionnel.
- **Lava Network / Pocket Network (kimsufi)** : nœuds RPC payés pour servir des requêtes blockchain. Nécessite de faire tourner un nœud complet (Ethereum, Cosmos, etc.), très coûteux en stockage. À évaluer selon l'espace disque disponible et les specs du nœud retenu.
- **Honeygain server-side (kimsufi)** : éliminé. IP datacenter OVH bloquées par ToS Honeygain (confirmé 2026). Ne pas documenter.
- **EarnApp (kimsufi)** : éliminé. IP datacenter strictement bloquées par ToS. Ne pas documenter.
- **TraffMonetizer (kimsufi)** : accepte les IPs datacenter, mais revenu 1-5 $/mois sur une IP unique. Contribution marginale. À documenter uniquement en complément d'autres services déjà en place.
- **io.net (kimsufi)** : DePIN calcul décentralisé principalement orienté GPU. Vérifier si une configuration CPU-only génère un revenu non nul.
- **Nodepay (routines/kimsufi)** : réseau de bande passante DePIN. Le client est une extension navigateur en priorité (peu adapté à un serveur headless). À vérifier si un client serveur natif existe et si les IPs datacenter sont acceptées.
- **Études médicales / cliniques (routines)** : indemnisations 200-3 500 € par étude en France, plafond légal 6 000 €/an. La plupart nécessitent une présence physique. À creuser pour identifier les études entièrement distancielles (rares mais existantes).

---

## Journal quotidien

| Date | Mode | Action | Impact revenu |
|------|------|--------|--------------|
| [2026-04-17](daily/2026-04-17.md) | nouvelle-opportunite | Fiche Akash Network Provider (kimsufi) | 110 $ → 120 $/mois |
| [2026-04-16](daily/2026-04-16.md) | nouvelle-opportunite (x3) | Init repo + fiches Storj, Prolific, Respondent.io | 0 → 110 $/mois |

---

## Structure du repo

```
passive-income-watch/
├── README.md              # Ce fichier, tableau de bord principal
├── routines/              # Fiches opportunités sans serveur dédié
├── kimsufi/               # Fiches opportunités exploitant le serveur Kimsufi
└── daily/                 # Logs quotidiens de veille
```
