# passive-income-watch

Base de connaissance sur les opportunités de revenus passifs et semi-passifs pour Laurent.
Veille quotidienne automatisée. Commit direct sur `main`.

**Objectif :** 3 000 $/mois pour un maximum de 2h de travail quotidien (ratio cible : 50 $/h).

---

## Tableau de bord

- **Objectif :** 3 000 $/mois pour <= 2h/jour (ratio cible 50 $/h)
- **Revenu mensuel cumulé estimé (fourchette basse) :** 122 $
- **Progression vers l'objectif :** 4,1 %
- **Temps de maintenance quotidien total estimé :** ~42 min/jour (30 min Prolific + 10 min Respondent + 1 min Storj + 1 min Akash + ~0 min Repocket)
- **Nombre d'opportunités documentées :** routines=2, kimsufi=3

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
| [Repocket - Partage Bande Passante](kimsufi/repocket-bandwidth.md) | low | 2-6 $ | 5 min | 24-72 $/h | 2026-04-17 |

---

## À creuser

- **Earn.FM (kimsufi)** : service de partage de bande passante, datacenter compatible selon pincto.com (avril 2026). Stackable avec Repocket et TraffMonetizer sur le même Kimsufi. À documenter dès confirmation des revenus sur IP OVH (estimation : 1-3 $/mois).
- **TraffMonetizer (kimsufi)** : accepte les IPs datacenter, 1-5 $/mois sur IP unique, installation Docker. Mentionné dans les notes de la fiche Repocket. À documenter en mini-fiche une fois Repocket en production pour valider l'empilement.
- **Lava Network (kimsufi)** : fournisseur de nœuds RPC payants, connexion entre développeurs et fournisseurs d'infrastructure blockchain. LAVA à 0,03 $ en avril 2026, market cap 15 M$ (flag « immature » selon le seuil de 10 M$). Nécessite de faire tourner un nœud blockchain complet (NEAR : ~500 Go, Ethereum : ~2 To). Potentiel à réévaluer si le market cap progresse au-delà de 50 M$.
- **Nodepay (routines/kimsufi)** : réseau de bande passante DePIN, 1,8 M de nœuds, partenaires entreprises dont IDG Capital et Animoca. Roadmap 2025 : client NodeOS Desktop prévu avec support headless. Trafic valorisé en tokens NC non encore convertibles en USD. Compatibilité IP datacenter non confirmée. À réévaluer à la sortie de NodeOS Desktop.
- **Études médicales / cliniques (routines)** : indemnisations 200-3 500 € par étude en France, plafond légal 6 000 €/an. La plupart exigent une présence physique. Pistes distancielles à creuser : Science.io, plateformes CIC CHU proposant des protocoles cognitifs en ligne.
- **Honeygain server-side (kimsufi)** : éliminé. IP datacenter OVH bloquées par ToS Honeygain (confirmé 2026). Ne pas documenter.
- **EarnApp (kimsufi)** : éliminé. IP datacenter strictement bloquées par ToS. Ne pas documenter.
- **Mysterium Network (kimsufi)** : éliminé. MYST à 0,03 $ en avril 2026 ; un nœud datacenter génère 2-5 MYST/mois = 0,06-0,15 $/mois. Revenu nul en pratique. Ne pas documenter.
- **io.net (kimsufi)** : éliminé pour configuration CPU-only. La plateforme est exclusivement orientée GPU pour les revenus significatifs. Ne pas documenter pour Kimsufi sans GPU.
- **Filecoin (kimsufi)** : éliminé. Revenu consistant nécessite >500 TiB de stockage, incompatible avec le Kimsufi.
- **Render Network (kimsufi)** : éliminé. GPU exclusivement requis pour les nœuds workers.

---

## Journal quotidien

| Date | Mode | Action | Impact revenu |
|------|------|--------|--------------|
| [2026-04-17](daily/2026-04-17.md) | nouvelle-opportunite (x2) | Fiches Akash + Repocket (kimsufi) | 110 $ → 122 $/mois |
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
