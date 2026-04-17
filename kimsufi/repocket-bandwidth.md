---
name: Repocket - Partage de Bande Passante
category: kimsufi
setup_complexity: low
time_investment: "30 min setup + 5 min/mois"
estimated_income_monthly: "2-6 $ (IP datacenter OVH, $0.20/Go, 10-30 Go/mois estimés)"
hourly_rate: "24-72 $/h (calculé sur 5 min de supervision mensuelle)"
risks: low
legal_status: clear
sources:
  - https://repocket.co
  - https://www.pincto.com/2026/01/4-paying-bandwidth-sharing-apps-allowed.html
  - https://mydailygadgets.com/blogs/news/repocket-review-2025-how-to-earn-passive-income-by-sharing-your-internet
  - https://earn4sure.com/repocket-review/
last_updated: 2026-04-17
added: 2026-04-17
---

## Résumé

Repocket est un service de partage de bande passante qui revend l'accès à votre IP en tant que nœud proxy. Contrairement à Honeygain, EarnApp ou Pawns.app, il accepte explicitement les IPs datacenter et VPS, avec une installation Docker disponible pour serveur headless. Sur un Kimsufi déjà actif, c'est un conteneur supplémentaire qui génère 2-6 $ par mois sans intervention quotidienne.

## Prérequis

- Kimsufi avec Docker installé (déjà présent si Storj tourne en parallèle)
- Compte Repocket créé sur repocket.co (inscription gratuite)
- Compte PayPal pour les retraits (seuil minimum : 20 $)
- Bande passante non rationnée (le Kimsufi 100 Mbps répond largement)

## Mise en place

1. Créer un compte sur repocket.co.
2. Dans le tableau de bord Repocket, copier le token d'authentification API.
3. Lancer le conteneur Docker :
   ```
   docker run --restart=always -d -e RP_API_KEY=<ton_token> repocket/repocket
   ```
4. Vérifier dans le tableau de bord Repocket que le nœud apparaît « en ligne » (délai de quelques minutes).
5. Configurer une alerte basique (cron + vérification `docker ps`) pour détecter un crash de conteneur.

## Rendement réaliste

Taux officiel confirmé : **0,20 $ par Go** de données servies via votre IP en tant que proxy.

Pour une IP datacenter OVH, la demande est plus faible que pour une IP résidentielle (les acheteurs de proxies préfèrent les IPs résidentielles pour certains usages). Estimation basée sur des retours utilisateurs serveurs headless 2025 :

| Scénario | Trafic mensuel | Revenu |
|---|---|---|
| Basse (faible demande datacenter) | 10 Go/mois | 2 $ |
| Médiane | 25 Go/mois | 5 $ |
| Haute (datacenter bien localisé, forte demande) | 30 Go/mois | 6 $ |

Pour référence : une IP résidentielle partageant 1 Go/jour génère ~6 $/mois (source : mydailygadgets, 2025). Une IP datacenter reçoit typiquement 30-50 % de ce volume de demande.

Temporalité : stable. Repocket verse en USD, pas en token crypto. Aucune volatilité de conversion.

## Ratio temps / revenu

- Temps de setup : 30 min (une seule fois)
- Maintenance mensuelle : 5 min (lecture tableau de bord, vérification uptime du conteneur)
- Revenu mensuel fourchette basse : 2 $
- Revenu mensuel médian : 5 $

Ratio sur maintenance seule :

- Basse : 2 / 0,083h = **24 $/h**
- Médiane : 5 / 0,083h = **60 $/h**

Le ratio $/h est supérieur à l'objectif de 50 $/h sur le scénario médian. La faiblesse est le revenu absolu (2-6 $/mois) : Repocket est une brique complémentaire à empiler sur un Kimsufi déjà actif, pas une source principale.

Seuil de retrait à 20 $ : il faut 3-10 mois avant le premier paiement selon le scénario. À anticiper pour la trésorerie.

## Risques

- **Revenu absolu très faible** : 2-6 $/mois contribue marginalement à l'objectif de 3 000 $/mois. La valeur est dans l'empilement avec d'autres services.
- **ToS changeantes** : Repocket peut restreindre les IPs datacenter à tout moment. Vérifier les CGU lors de chaque mise à jour de service.
- **Demande fluctuante** : les revenus dépendent de la demande des acheteurs de proxies, variable selon la saison, la concurrence et la région géographique du serveur.
- **Délai de premier paiement** : seuil de 20 $ atteint en 3-10 mois sur IP datacenter. Si Repocket ferme avant, les fonds accumulés sont perdus.
- **Ressources serveur** : le conteneur consomme quelques dizaines de Mo de RAM et génère du trafic réseau variable. Négligeable sur le Kimsufi, mais à surveiller si OVH impose des quotas de bande passante.

## Sources

- [Repocket - site officiel](https://repocket.co) (consulté 2026-04-17)
- [pincto.com - 4 Paying Bandwidth-Sharing Apps for Datacenters/VPS, janvier 2026](https://www.pincto.com/2026/01/4-paying-bandwidth-sharing-apps-allowed.html) (consulté 2026-04-17)
- [mydailygadgets - Repocket Review 2025](https://mydailygadgets.com/blogs/news/repocket-review-2025-how-to-earn-passive-income-by-sharing-your-internet) (consulté 2026-04-17)
- [earn4sure - Repocket Review, test honnête](https://earn4sure.com/repocket-review/) (consulté 2026-04-17)

## Notes additionnelles

Repocket se cumule sans conflit avec Storj et Akash sur le même Kimsufi. Chaque service tourne dans son propre conteneur Docker, sans conflit de ressources notable.

Pour maximiser le revenu passif de bande passante sur une seule IP datacenter, deux services supplémentaires sont stackables en parallèle :

- **TraffMonetizer** : accepte les IPs datacenter, 1-5 $/mois, même installation Docker. Stackable directement avec Repocket.
- **Earn.FM** : datacenter compatible selon pincto.com (janvier 2026), à vérifier pour les revenus spécifiques sur IP OVH.

En cumulant Repocket + TraffMonetizer + Earn.FM, le revenu passif de bande passante pourrait atteindre 5-14 $/mois pour la même maintenance de 5 min/mois.
