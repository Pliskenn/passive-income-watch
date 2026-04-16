---
name: Storj Nœud Stockage
category: kimsufi
setup_complexity: low
time_investment: "2h setup + 15 min/mois"
estimated_income_monthly: "5-25 $ (nœud établi 12+ mois, 2 To alloués)"
hourly_rate: "20-100 $/h net (calculé sur 15 min de maintenance mensuelle)"
risks: medium
legal_status: clear
sources:
  - https://storj.dev/node/payouts
  - https://forum.storj.io/t/update-to-storj-object-storage-pricing-what-node-operators-need-to-know/30725
  - https://storj.dev/node/faq/held-back-amount
  - https://forum.storj.io/t/what-is-the-new-vetting-time/31226
last_updated: 2026-04-16
added: 2026-04-16
---

## Résumé

Storj est un réseau de stockage décentralisé où les opérateurs de nœuds louent leur espace disque et leur bande passante à des clients entreprise et grand public. Sur un Kimsufi déjà payé, c'est du revenu marginal pur avec une maintenance quasi nulle une fois le nœud lancé.

## Prérequis

- Serveur avec adresse IPv4 fixe (le Kimsufi répond à ce critère)
- Espace disque disponible : minimum 550 Go, recommandé 2 To ou plus
- Bande passante : minimum 2 To/mois, recommandé 16 To/mois (le Kimsufi 100 Mbps couvre largement)
- Port TCP et UDP ouvert (configurable via iptables ou UFW)
- Docker installé sur le serveur
- Wallet compatible Ethereum pour recevoir les tokens STORJ (ex. MetaMask)

## Mise en place

1. Installer Docker sur le Kimsufi si absent (`apt install docker.io` sur Debian/Ubuntu).
2. Générer une paire de clés d'identité Storj avec l'outil officiel (`storagenode setup`).
3. Soumettre la clé publique pour activation (délai de 24-48h côté Storj Labs).
4. Lancer le conteneur Docker avec les paramètres : chemin de stockage, wallet, port externe.
5. Ouvrir le port 28967 (TCP + UDP) dans le pare-feu.
6. Vérifier le dashboard local (port 14002) : uptime, espace alloué, statut de vetting.
7. Configurer une alerte simple (cron + curl healthcheck) pour détecter toute panne.

## Rendement réaliste

Taux officiels en vigueur (confirmés stables après mise à jour septembre 2025) :

| Type | Taux opérateur |
|------|---------------|
| Stockage | 1,50 $/To/mois |
| Egress (téléchargement client) | 20 $/To |
| Repair bandwidth | 10 $/To |

Hypothèse : 2 To alloués sur Kimsufi KS-3 ou équivalent.

**Fourchette basse (mois 1-9, held amounts + faible utilisation) :**
- Stockage : 2 To × 10 % utilisation × 1,50 $ = 0,30 $ (25 % payé en mois 1-3, 50 % en mois 4-6)
- Egress : 50 Go × 20 $/To = 1 $
- Effectif encaissé : 0,30-1,30 $/mois

**Fourchette médiane (mois 10-15, nœud établi) :**
- Stockage : 2 To × 40 % utilisation = 1,20 $
- Egress : 200 Go × 20 $/To = 4 $
- Total : 5-8 $/mois

**Fourchette haute (nœud établi 18+ mois, forte utilisation) :**
- Stockage : 2 To × 80 % utilisation = 2,40 $
- Egress : 1 To × 20 $/To = 20 $
- Total : 20-25 $/mois

Les gains dépendent fortement du trafic réseau global Storj, qui fluctue. Le token STORJ est coté en bourse : la valeur en USD peut varier de ±50 % sur 3 mois.

## Ratio temps / revenu

- Temps de setup : 2h (une seule fois)
- Maintenance mensuelle : 15 min (vérification dashboard, monitoring)
- Revenu mensuel fourchette basse (nœud établi) : 5 $
- Revenu mensuel médian : 8 $

Ratio sur maintenance seule : 5 $/0,25h = **20 $/h minimum**, jusqu'à 100 $/h côté haut.

Le ratio $/h est élevé car la maintenance est quasi nulle. En revanche, le revenu absolu reste modeste. Sur 12 mois de montée en charge, le total encaissé sera probablement inférieur à 50 $.

**Ce nœud est intéressant non pas comme source de revenu principale mais comme brique passive à lancer une fois et oublier.**

## Risques

- **Held amounts** : 75 % des gains retenus les 3 premiers mois, 50 % les mois 4-6, 25 % les mois 7-9. Trésorerie quasi nulle pendant les 9 premiers mois.
- **Exposition au cours du token STORJ** : paiements en STORJ, pas en USD. Forte volatilité possible.
- **Faible utilisation réseau** : Storj a un problème chronique de surcapacité côté nœuds. Moins d'entreprises clientes = moins de données à stocker = revenus faibles.
- **Risque plateforme** : Storj Labs est une entreprise centrale dans un protocole « décentralisé ». Si Storj Labs ferme ou pivote, les paiements s'arrêtent.
- **Consommation ressources serveur** : le nœud consomme quelques % de CPU et de RAM en continu. À surveiller si d'autres services tournent sur le Kimsufi.
- **Port ouvert** : nécessite une exposition réseau supplémentaire. À sécuriser correctement.

## Sources

- [Storj Docs - Payout](https://storj.dev/node/payouts) (consulté 2026-04-16)
- [Forum Storj - Mise à jour tarifs novembre 2025](https://forum.storj.io/t/update-to-storj-object-storage-pricing-what-node-operators-need-to-know/30725) (consulté 2026-04-16)
- [Storj Docs - Held Back Amount](https://storj.dev/node/faq/held-back-amount) (consulté 2026-04-16)
- [Forum Storj - Vetting period 2025](https://forum.storj.io/t/what-is-the-new-vetting-time/31226) (consulté 2026-04-16)

## Notes additionnelles

Combiner Storj avec d'autres services sur le même Kimsufi (Mysterium, autre DePIN) est possible. Surveiller les conflits de ressources (RAM, CPU, bande passante). Storj est compatible Docker et peut tourner en parallèle d'autres conteneurs sans configuration complexe.
