# Blockchain, registre permissionné ou base de données ? Le cas des paiements transfrontaliers

Projet individuel du **TP3 « GitHub et projets blockchain »**, Master Fintech / Blockchain (Université Cadi Ayyad).

**Auteur :** Karroum Mouad
**Compte GitHub :** [mkarroum2368-ux](https://github.com/mkarroum2368-ux)

## Question traitée

Pour les paiements transfrontaliers, quelle architecture répond le mieux aux besoins : une **blockchain publique**, un **registre distribué permissionné** ou une **base de données classique** ?

1. Présentation du cas : les limites actuelles des paiements transfrontaliers (coût, vitesse, transparence) et les cibles du G20.
2. Description des trois architectures, avec des exemples (stablecoins sur chaîne publique, Project Agorá et mBridge pour le permissionné, banques correspondantes pour la base de données classique).
3. Tableau comparatif sur huit critères : gouvernance, confiance, confidentialité, performance, coût, immuabilité, conformité, maturité réglementaire.
4. Recommandation argumentée selon le segment de paiement, puis limites.
## Démarche

1. Présentation du cas : les limites actuelles des paiements transfrontaliers (coût, vitesse, transparence) et les cibles du G20.
2. Description des trois architectures, avec des exemples (stablecoins sur chaîne publique, Project Agorá et mBridge pour le permissionné, banques correspondantes pour la base de données classique).
3. Tableau comparatif sur huit critères : gouvernance, confiance, confidentialité, performance, coût, immuabilité, conformité, maturité réglementaire.
4. Recommandation argumentée selon le segment de paiement, puis limites.
## Résultat obtenu

Il n'existe pas d'architecture unique. En résumé :
- **paiements de gros entre institutions** : le registre permissionné est le plus adapté ;
- **petits transferts de migrants** : les opérateurs fintech sur base de données classique restent très compétitifs, et les stablecoins ne sont utiles que si l'entrée et la sortie vers les monnaies locales sont fiables et peu chères ;
- **chaîne publique** : justifiée quand l'ouverture prime sur la confidentialité et que l'on accepte les risques de conformité ;
- **base de données classique** : suffisante quand un acteur de confiance existe déjà.

Le détail est dans [`comparatif-paiements-transfrontaliers.md`](comparatif-paiements-transfrontaliers.md).

## Contenu du dépôt

| Fichier | Description |
|---|---|
| `README.md` | Présentation du projet |
| `comparatif-paiements-transfrontaliers.md` | Analyse complète, tableau comparatif et sources |

## Sources principales

Rapport 2026 du FSB sur la feuille de route du G20 pour les paiements transfrontaliers ; BIS Working Paper 1385 (banques, fintechs et stablecoins) ; pages BIS sur Project Agorá et Project mBridge ; rapport économique annuel 2026 du BIS. La liste complète avec les liens est à la fin du fichier d'analyse.

## Outils utilisés

- **GitHub Desktop** pour les commits et la synchronisation du dépôt.
- **Assistant d'IA (Claude, Anthropic)** : aide à la recherche de sources, à la structuration du comparatif et à la rédaction d'une première version en français. Le contenu a été relu, et je suis en mesure de l'expliquer.

## Précautions

Aucun achat ni transfert de cryptomonnaie réelle n'a été effectué. Ce dépôt ne contient ni clé privée, ni phrase de récupération, ni mot de passe, ni jeton d'accès.
