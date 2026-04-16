---
name: Akash Network - Provider de Calcul Décentralisé
category: kimsufi
setup_complexity: high
time_investment: "4-6h setup (Kubernetes + configuration provider) + 30 min/mois supervision"
estimated_income_monthly: "10-50 $ (CPU-only, 4-8 cœurs, utilisation 15-40%)"
hourly_rate: "20-100 $/h net (calculé sur 30 min de maintenance mensuelle, très variable)"
risks: medium
legal_status: clear
sources:
  - https://messari.io/report/state-of-akash-q3-2025
  - https://messari.io/report/state-of-akash-q1-2025
  - https://docs.praetorapp.com/akash-provider/single-server-provider
  - https://coinmarketcap.com/currencies/akash-network/
  - https://openmetal.io/resources/blog/why-depin-compute-networks-require-bare-metal-infrastructure-to-function-correctly
  - https://akash.network/pricing/provider-calculator/
last_updated: 2026-04-17
added: 2026-04-17
---

## Résumé

Akash Network est une place de marché décentralisée de calcul cloud : les providers louent leur CPU, RAM et stockage à des déployeurs (développeurs, startups, workloads IA légers). Un serveur dédié bare-metal OVH est particulièrement adapté par rapport à un VPS : meilleures performances, bande passante non plafonnée, accès root complet. Le réseau a atteint un ATH de 5 M$ de compute spend au T1 2026, en croissance constante depuis 2024.

## Prérequis

- Kimsufi avec accès root SSH, minimum recommandé : 4 CPU threads, 16 Go RAM, 200 Go stockage libre
- OS : Ubuntu 20.04 ou 22.04 LTS
- Nom de domaine ou sous-domaine dont on contrôle les DNS (pour l'ingress Kubernetes)
- Wallet Keplr (extension navigateur Chrome/Firefox) avec 5-50 AKT (~2,35-23,50 $ au cours d'avril 2026)
- Ports ouverts : 8443 (provider API), 80 et 443 (ingress Kubernetes)

## Mise en place

1. Créer un wallet Keplr et l'alimenter avec 5-50 AKT (nécessaire pour les frais de transaction et la création du provider).
2. Accéder à Provider Console (anciennement Praetor App) via praetorapp.com ou console.akash.network/provider.
3. Dans le wizard, entrer les identifiants SSH du Kimsufi et l'IP publique.
4. Laisser Provider Console installer automatiquement k3s (distribution Kubernetes allégée) et le démon Akash provider en 15-20 minutes.
5. Configurer deux entrées DNS vers l'IP du Kimsufi : un A record pour le domaine ingress (ex. `ingress.mondomaine.com`) et un wildcard (`*.ingress.mondomaine.com`).
6. Dans Provider Console, définir les prix de location : prix par CPU thread/mois, par Go RAM/mois, par Go stockage/mois. Se référer aux prix courants du marché Akash via akash.network/pricing/provider-calculator/.
7. Valider et activer le provider. Les premières offres (bids) apparaissent dans les heures qui suivent si les prix sont compétitifs.
8. Surveiller le tableau de bord Provider Console pendant les 48 premières heures pour vérifier que les leases s'ouvrent normalement.

## Rendement réaliste

Hypothèse : Kimsufi KS-3 ou équivalent, 4 CPU threads, 32 Go RAM, 1 To stockage disponible, bande passante 100 Mbps non limitée.

**Contexte réseau (sources Messari 2025-2026) :**
- T1 2025 : 1 M$ de revenus locatifs (+38 % QoQ)
- T3 2025 : 852 000 $ de revenus locatifs, ~63-71 providers actifs
- T1 2026 : ATH à 5 M$ de compute spend sur le trimestre
- Usage CPU du réseau : 5 500 unités (T2 2025, +14 % QoQ), en croissance

**Estimation pour un provider CPU-only (hors GPU) :**
- Fourchette basse : 10 $/mois (utilisation 10-15 %, concurrence élevée sur le segment CPU)
- Fourchette médiane : 25 $/mois (utilisation 25-35 %, pricing compétitif)
- Fourchette haute : 50 $/mois (utilisation 40-50 %, workloads non-IA actifs)

Revenus versés en AKT (cours avril 2026 : ~0,47 $, market cap 137 M$). Le BME (Burn-Mint Equilibrium) activé en mars 2026 lie la destruction de tokens à la demande de compute, ce qui tend à soutenir le prix de l'AKT à mesure que l'utilisation augmente.

Temporalité : tendance haussière de la demande réseau. Les providers GPU captent la majorité des revenus actuels ; les workloads CPU représentent une part minoritaire mais stable.

## Ratio temps / revenu

Temps de setup : 4-6h (non récurrent).
Temps mensuel de maintenance : 30 min (vérification du tableau de bord, correctifs si k3s crash, mise à jour logicielle ponctuelle).

- Fourchette basse : 10 $ / 0,5h = **20 $/h**
- Fourchette médiane : 25 $ / 0,5h = **50 $/h**
- Fourchette haute : 50 $ / 0,5h = **100 $/h**

La fourchette médiane atteint exactement l'objectif de 50 $/h. Le setup initial de 5h amortit sur quelques mois seulement.

## Risques

- **Utilisation non garantie** : les providers CPU-only sont moins demandés que les providers GPU (workloads IA dominant le marché Akash). Revenu nul possible si les prix sont trop élevés ou si la région est saturée.
- **Volatilité AKT** : le cours a oscillé entre 0,10 $ (creux 2024) et 2,50 $ (ATH). Un effondrement divise les revenus USD en proportion.
- **Complexité Kubernetes** : k3s sur serveur unique peut être instable après certaines mises à jour noyau ou système. Un crash non détecté interrompt les leases et nuit à la réputation du provider.
- **Concurrence croissante** : le nombre de providers actifs croît ; la pression sur les prix de marché peut éroder les marges.
- **Cohabitation sur le Kimsufi** : si Storj ou d'autres services tournent en parallèle, les ressources allouables à Akash sont réduites. Bien dimensionner les allocations (laisser 1-2 threads et 2-4 Go RAM pour l'OS et les autres services).
- **Nom de domaine** : requis, coût additionnel ~10-15 $/an si pas déjà détenu.

## Sources

- Messari, « State of Akash Q3 2025 » (novembre 2025) — revenus et nombre de providers
- Messari, « State of Akash Q1 2025 » (mai 2025) — croissance CPU usage
- Praetor App Docs, « Single Server Provider » (consulté avril 2026)
- CoinMarketCap, cours AKT (consulté 16 avril 2026 : 0,47 $, market cap 137 M$)
- OpenMetal, « Why DePIN Compute Networks Require Bare Metal Infrastructure to Function Correctly » (2025)
- Akash Network, Provider Earn Calculator — akash.network/pricing/provider-calculator/

## Notes additionnelles

Cumuler avec Storj sur le même Kimsufi est viable : Storj exploite le stockage inactif, Akash loue le CPU et la RAM. Prévoir une allocation Akash d'au maximum 80 % des ressources physiques pour garantir la stabilité du système hôte. L'ATH de compute spend du T1 2026 et le BME de mars 2026 sont des signaux favorables à la demande, mais ne garantissent pas un revenu stable pour un provider CPU-only de petite taille.
