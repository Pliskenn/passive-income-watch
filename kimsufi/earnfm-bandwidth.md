---
name: Earn.FM - Partage de Bande Passante (Datacenter)
category: kimsufi
setup_complexity: low
time_investment: "20min setup + 0 min/mois (100% passif)"
estimated_income_monthly: "1-5 $/mois (IP datacenter OVH)"
hourly_rate: "> 60 $/h (maintenance = 0, setup amorti sur 12 mois)"
risks: low
legal_status: clear
sources:
  - https://earn.fm
  - https://www.pincto.com/2026/01/4-paying-bandwidth-sharing-apps-allowed.html
  - https://www.pincto.com/2026/04/the-ultimate-cash-paying-bandwidth.html
  - https://hub.docker.com/r/earnfm/earnfm-client
  - https://www.trustpilot.com/review/earn.fm
  - https://eagleearner.com/earnfm-review/
last_updated: 2026-04-19
added: 2026-04-19
---

## Résumé

Earn.FM revend l'accès à la bande passante de votre connexion à des entreprises (vérification publicitaire, SEO, data scraping). Taux de base : 0,20 $/Go. Compatible IPs datacenter et VPS selon confirmation pincto.com (janvier et avril 2026). S'installe en 20 minutes via Docker. Stackable avec Repocket sur le même Kimsufi, les deux partageant la même IP et le même pool de bande passante disponible.

## Prérequis

- Serveur avec accès root (Kimsufi : rempli)
- Docker installé
- Connexion Internet stable avec bande passante disponible (100 Mbps Kimsufi : rempli)
- IP fixe (Kimsufi : rempli)
- Compte Earn.FM créé (inscription gratuite sur earn.fm)

## Mise en place

1. Créer un compte sur earn.fm. Récupérer la clé API dans le tableau de bord.
2. Sur le Kimsufi, lancer le conteneur Docker :
   ```bash
   docker run -d \
     --name earnfm \
     --restart always \
     earnfm/earnfm-client \
     --key VOTRE_API_KEY
   ```
3. Vérifier dans le dashboard earn.fm que le nœud apparaît avec le statut actif (point vert).
4. Optionnel : activer les mises à jour automatiques du conteneur via Watchtower.
5. Configuration terminée.

## Rendement réaliste

- Taux : 0,20 $/Go de bande passante partagée (identique à Repocket)
- IP datacenter (OVH) : demande plus faible que les IPs résidentielles ; trafic alloué estimé à 5-25 Go/mois
- **Fourchette basse : 1 $/mois** (faible demande, IP OVH peu sollicitée)
- **Fourchette médiane : 2-3 $/mois**
- **Fourchette haute : 5 $/mois** (pic de demande, période favorable)

**Impact du cumul avec Repocket :**
Repocket et Earn.FM partagent la même IP et la même bande passante disponible. Le cumul n'est pas additif. Estimation de la combinaison sur le Kimsufi : 3-8 $/mois (vs 2-6 $ pour Repocket seul), soit un gain marginal de 1-2 $/mois lié aux périodes où l'un des services ne consomme pas de bande passante.

- Seuil de retrait minimum : 15 $ (atteint en 3-15 mois selon la demande)
- Paiements : PayPal, crypto ; paiement dans les 24h après demande de retrait

## Ratio temps / revenu

- Setup initial : 20 min
- Maintenance mensuelle : 0 min (daemon auto-restart)
- Revenu mensuel fourchette basse : 1 $/mois

Calcul amorti sur 12 mois : 20 min / 12 = 1,7 min/mois de temps imputé.
**Ratio : 1 $ / (1,7 min / 60) = 35 $/h** (fourchette basse)
**Ratio médiane : 2,5 $ / 0,028 h = 89 $/h**

L'objectif 50 $/h est atteint en médiane. La contrainte de ce poste est le revenu absolu (1-5 $/mois), non le ratio.

## Risques

- **Revenu absolu très faible** : 1-5 $/mois, contribution marginale. La valeur de cette fiche est dans la complémentarité avec Repocket, pas dans un revenu autonome significatif.
- **Bande passante partagée avec Repocket** : les gains combinés ne s'additionnent pas. Lancer les deux sur le même serveur sans supervision peut créer une concurrence entre les deux daemons pour la même ressource.
- **Minimum de retrait à 15 $** : délai de 3-15 mois avant le premier paiement.
- **Demande variable** : la plateforme vend la bande passante par cycles. Periodes creuses possibles (trafic nul pendant plusieurs jours).
- **Ancienneté limitée** : Earn.FM a été lancée en 2022. Track record de 3-4 ans, plus court que des acteurs établis. Paiements confirmés via Trustpilot et forums, mais sans garantie de continuité à long terme.
- **Changement de politique ToS** : une révision de la ToS bloquant les IPs datacenter supprimerait le revenu du jour au lendemain, comme cela a déjà été observé chez Honeygain et EarnApp.

## Sources

- https://www.pincto.com/2026/01/4-paying-bandwidth-sharing-apps-allowed.html (compatibilité datacenter confirmée, janvier 2026)
- https://www.pincto.com/2026/04/the-ultimate-cash-paying-bandwidth.html (synthèse bande passante datacenter, avril 2026)
- https://hub.docker.com/r/earnfm/earnfm-client (image Docker officielle Earn.FM, accès avril 2026)
- https://www.trustpilot.com/review/earn.fm (avis utilisateurs, accès avril 2026)
- https://eagleearner.com/earnfm-review/ (taux 0,20 $/Go confirmé, accès avril 2026)
