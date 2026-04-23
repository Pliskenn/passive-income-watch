# passive-income-watch

Base de connaissance sur les opportunités de revenus passifs et semi-passifs pour Laurent.
Veille quotidienne automatisée. Commit direct sur `main`.

**Objectif :** 3 000 $/mois pour un maximum de 2h de travail quotidien (ratio cible : 50 $/h).

---

## Tableau de bord

- **Objectif :** 3 000 $/mois pour <= 2h/jour (ratio cible 50 $/h)
- **Revenu mensuel cumulé estimé (fourchette basse) :** 253 $ (231 $ existant + 22 $ parking/box nets après impôts, conditionnel à la possession d'un espace)
- **Progression vers l'objectif :** 8,4 %
- **Temps de maintenance quotidien total estimé :** ~52 min/jour (30 min Prolific + 10 min Respondent + 4 min User Interviews + 1 min Storj + 1 min Akash + ~0 min Repocket + ~0 min Earn.FM + 5 min tests cosmétiques + 1 min parrainages + ~0 min parking)
- **Nombre d'opportunités documentées :** routines=6, kimsufi=5

---

## Routines

Opportunités activables sans serveur dédié, intégrables dans une routine quotidienne.

| Nom | Complexité | Revenu mensuel | Temps/mois | Ratio $/h | Dernière MAJ |
|-----|-----------|----------------|------------|-----------|-------------|
| [Parrainages Bancaires Haut Rendement](routines/parrainages-bancaires.md) | low | 30-300 € | 20-30 min | 120-400 €/h | 2026-04-20 |
| [Location Parking et Box](routines/location-parking-box.md) | low | 20-100 € nets* | 15 min | 120-400 €/h | 2026-04-22 |
| [Respondent.io](routines/respondent-etudes.md) | low | 75-600 $ | 2-5h | 80-200 $/h | 2026-04-16 |
| [User Interviews - Études UX](routines/user-interviews-etudes.md) | low | 25-300 $ | 2-4h | 50-150 $/h | 2026-04-21 |
| [Tests Cosmétiques Cliniques Domicile](routines/tests-cosmetiques-domicile.md) | low | 50-200 €/mois | 3-5h/étude | 15-80 €/h | 2026-04-19 |
| [Prolific - Études Académiques Rémunérées](routines/prolific-etudes-remunereees.md) | low | 30-150 $ | 5-15h | 8-15 $/h** | 2026-04-16 |

*Location parking : conditionnel à la possession d'un espace sous-utilisé. Net après commission plateforme (20 %) et impôts (TMI 30 %, micro-foncier).
**Prolific : ratio sous le seuil de 10 $/h. Documenté comme socle de volume (études fréquentes, peu sélectives) en complément de Respondent.io.

---

## Kimsufi

Opportunités exploitant le serveur dédié bare-metal OVH (IP fixe, 100 Mbps+, accès root).

| Nom | Complexité | Revenu mensuel | Temps/mois | Ratio $/h | Dernière MAJ |
|-----|-----------|----------------|------------|-----------|-------------|
| [Site Niche Affiliation Finance](kimsufi/niche-affiliation-finance.md) | medium | 0 → 800-2 000 €** | 15-25h setup + 2-4h/mois | 150-1 000 €/h*** | 2026-04-23 |
| [Akash Network - Provider Calcul](kimsufi/akash-provider-compute.md) | high | 10-50 $ | 30 min | 20-100 $/h | 2026-04-17 |
| [Storj Nœud Stockage](kimsufi/storj-noeud-stockage.md) | low | 5-25 $ | 15 min | 20-100 $/h | 2026-04-16 |
| [Earn.FM - Partage Bande Passante](kimsufi/earnfm-bandwidth.md) | low | 1-5 $ | 0 min | >60 $/h* | 2026-04-19 |
| [Repocket - Partage Bande Passante](kimsufi/repocket-bandwidth.md) | low | 2-6 $ | 5 min | 24-72 $/h | 2026-04-17 |

*Earn.FM : ratio élevé car maintenance = 0. Revenu absolu très faible (1-5 $/mois). Note : Earn.FM et Repocket partagent la même IP, les gains ne sont pas additifs. Voir fiche pour détail du cumul.
**Site affiliation finance : 0 € les 6 premiers mois, puis 50-200 € (mois 4-6), 400-900 € (mois 7-9), 800-2 000 € (mois 12+). Non comptabilisé dans le revenu cumulé actuel.
***Ratio calculé en phase stable (mois 12+) sur 2-4h/mois de maintenance. Phase de lancement non rémunérée (investissement 15-25h).

---

## À creuser

- **Revolut Back / cashback (routines)** : Revolut Metal à 16,99 €/mois, cashback 0,1 % en zone euro et 1 % hors Europe. Marge nette positive uniquement pour des dépenses hors-Europe >1 700 €/mois. Peu pertinent si Laurent dépense principalement en France. À documenter uniquement si dépenses internationales significatives.
- **TraffMonetizer (kimsufi)** : accepte les IPs datacenter, 1-5 $/mois sur IP unique, installation Docker. Modèle identique à Repocket et Earn.FM. Documenter uniquement si confirmé qu'il ajoute du trafic non capté par les deux autres (scénario peu probable sur une IP unique).
- **Lava Network (kimsufi)** : fournisseur de nœuds RPC payants, connexion entre développeurs et fournisseurs d'infrastructure blockchain. LAVA à 0,03 $ en avril 2026, market cap 15 M$ (flag « immature »). Nécessite de faire tourner un nœud blockchain complet (NEAR : ~500 Go, Ethereum : ~2 To). Potentiel à réévaluer si le market cap progresse au-delà de 50 M$.
- **Nodepay (routines/kimsufi)** : réseau de bande passante DePIN, 1,8 M de nœuds, partenaires entreprises dont IDG Capital et Animoca. Roadmap 2025 : client NodeOS Desktop prévu avec support headless. Trafic valorisé en tokens NC non encore convertibles en USD. Compatibilité IP datacenter non confirmée. À réévaluer à la sortie de NodeOS Desktop.
- **Essais pharmaceutiques CIC (routines)** : indemnisations 200-3 500 € par étude en France (Code de la santé publique, plafond 4 500 €/an). Quasi-systématiquement en présentiel (Centre d'Investigation Clinique). Pistes distancielles non confirmées à ce jour. À creuser si protocoles cognitifs ou dermatologiques distanciels se développent.
- **CrowdGen by Appen (routines)** : plateforme d'annotation IA, héritière d'Appen Connect (lancée 2024), disponible dans 170+ pays. France techniquement éligible. Taux affiché : $14-25/h. Disponibilité réelle des tâches en France non confirmée par des retours terrain en avril 2026. À documenter uniquement si des utilisateurs français confirment un flux régulier de tâches. Chercher sur r/beermoney et le forum officiel.
- **Parasite SEO affiliation (routines/kimsufi)** : avant de lancer le site de niche Kimsufi, tester le positionnement d'articles comparatifs sur LinkedIn Articles, Medium ou Substack gratuit (autorité de domaine élevée, zéro coût). Premiers résultats en 4-8 semaines. Permet de valider la demande avant d'investir 15-25h sur un domaine propre.
- **DataAnnotation.tech (routines)** : éliminé. Marchés actifs : US, Canada, UK, Irlande, NZ, Australie uniquement. France hors zone opérationnelle en avril 2026 (confirmé sur la page officielle FAQ). Création de compte possible mais revenus indisponibles. Ne pas documenter tant que la France n'est pas incluse dans la liste des pays actifs.
- **Clickworker (routines)** : éliminé. Micro-tâches disponibles en France, mais ratio effectif < 5 $/h selon les retours utilisateurs (tâches peu disponibles, temps de sélection non rémunéré, rejets sans explication). Ratio inférieur au seuil de 10 $/h. Ne pas documenter.
- **Honeygain server-side (kimsufi)** : éliminé. IP datacenter OVH bloquées par ToS Honeygain (confirmé 2026). Ne pas documenter.
- **EarnApp (kimsufi)** : éliminé. IP datacenter strictement bloquées par ToS. Ne pas documenter.
- **Mysterium Network (kimsufi)** : éliminé. MYST à 0,03 $ en avril 2026 ; un nœud datacenter génère 2-5 MYST/mois = 0,06-0,15 $/mois. Revenu nul en pratique. Ne pas documenter.
- **io.net (kimsufi)** : éliminé pour configuration CPU-only. La plateforme est exclusivement orientée GPU pour les revenus significatifs. Ne pas documenter pour Kimsufi sans GPU.
- **Filecoin (kimsufi)** : éliminé. Revenu consistant nécessite >500 TiB de stockage, incompatible avec le Kimsufi.
- **Render Network (kimsufi)** : éliminé. GPU exclusivement requis pour les nœuds workers.
- **Flux Network Cumulus (kimsufi)** : éliminé au prix actuel. Un nœud Cumulus rapporte 30-50 FLUX/mois. Au cours du FLUX en avril 2026 (0,055 $), cela représente 1,65-2,75 $/mois pour ~2h de setup. Ratio < 2 $/h. À réévaluer si le FLUX dépasse 0,20 $.
- **PacketStream (kimsufi)** : éliminé. Accepte uniquement les IPs résidentielles, pas les IPs datacenter. Confirmé 2026.
- **Meson Network (kimsufi)** : éliminé. Projet mort : canaux sociaux inactifs depuis 2024, market cap 180 K$ (avril 2026). Ne pas documenter.
- **Génér8 (routines)** : éliminé. Extension navigateur disponible principalement au Royaume-Uni. Revenus hors UK non fonctionnels ou inférieurs à £5/mois. Ne pas documenter pour la France.
- **Grass DePIN (kimsufi)** : éliminé. Les IPs datacenter sont déprioritisées par la plateforme, qui valorise uniquement les IPs résidentielles pour le web scraping. Revenu en pratique nul sur IP OVH.
- **Pocket Network / POKT (kimsufi)** : éliminé. Un nœud nécessite 150 000 POKT stakés = ~1 872 $ au prix d'avril 2026. Dépasse le seuil de 500 € d'investissement. Coûts d'hébergement multi-chain ($200-300/mois) également incompatibles avec un Kimsufi en nœud unique. Ne pas documenter.
- **Bitping (kimsufi)** : éliminé. Paie en Bitcoin SV (BSV), revenu mesuré à 0,1 cent/jour/nœud = ~0,03 $/mois. Revenu nul en pratique. Ne pas documenter.
- **Tapestri (routines)** : éliminé. Maximum $25/mois, disponibilité France non confirmée pour 2026. Avis utilisateurs négatifs. Ratio inférieur à 10 $/h. Ne pas documenter.
- **Presearch (kimsufi)** : éliminé. Token PRE à 0,0022 $ en avril 2026, volume de trading 24h de 1 198 $ (quasi-illiquide). Revenu d'un nœud non quantifiable faute de données 2026. Market cap < 5 M$. Ne pas documenter.

---

## Journal quotidien

| Date | Mode | Action | Impact revenu |
|------|------|--------|--------------|
| [2026-04-23](daily/2026-04-23.md) | nouvelle-opportunite | Fiche site niche affiliation finance sur Kimsufi (revenu différé 6+ mois) | 253 $ → 253 $/mois |
| [2026-04-22](daily/2026-04-22.md) | nouvelle-opportunite | Fiche location parking/box (Yespark/Zenpark, revenu passif conditionnel) | 231 $ → 253 $/mois |
| [2026-04-21](daily/2026-04-21.md) | nouvelle-opportunite | Fiche User Interviews (études UX rémunérées, France confirmée) | 206 $ → 231 $/mois |
| [2026-04-20](daily/2026-04-20.md) | nouvelle-opportunite | Fiche parrainages bancaires (BoursoBank + Fortuneo) | 173 $ → 206 $/mois |
| [2026-04-19](daily/2026-04-19.md) | nouvelle-opportunite (x2) | Fiches tests cosmétiques + Earn.FM | 122 $ → 173 $/mois |
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
