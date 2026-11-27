# Blockchain publique, registre permissionné ou base de données classique ? Le cas des paiements transfrontaliers

*Réalisé par Karroum Mouad, Master 2 Finance appliquée (option Fintech), Université Cadi Ayyad. TP3 Blockchain, novembre 2026.*

---

## 1. Le cas étudié et ses besoins

Envoyer de l'argent d'un pays à un autre reste lent, cher et peu transparent. Aujourd'hui, un paiement transfrontalier passe le plus souvent par une chaîne de banques correspondantes, chacune tenant son propre registre et vérifiant la conformité (lutte contre le blanchiment, sanctions). Cette architecture est coûteuse à cause de coûts fixes élevés, et elle convient mal aux petits montants.

Les autorités ont fixé des cibles chiffrées (feuille de route du G20, à atteindre fin 2027) :

| Dimension | Cible G20 |
|---|---|
| Coût (paiements de détail) | au plus 1 % en moyenne mondiale |
| Coût (transferts de migrants, ou remittances) | au plus 3 % |
| Vitesse | 75 % des paiements crédités en moins d'une heure, le reste sous un jour ouvrable |
| Transparence | coût total, délai prévu et suivi du statut communiqués au client |

**Où en est-on ?** Le rapport 2026 du Conseil de stabilité financière (FSB, 16 novembre 2026) indique que les paiements de détail transfrontaliers ont ralenti et que leur coût n'a pas baissé depuis 2023. La part des services créditant le bénéficiaire en un jour ouvrable est passée de 74 % (2023) à 67,3 % (2025), puis 59,8 % (2026). Le coût moyen d'un transfert de migrant tourne autour de 6,5 %, soit plus du double de la cible de 3 %. Les cibles 2027 sont jugées difficiles à atteindre.

**Les acteurs et la confiance.** Dans ce cas, plusieurs acteurs qui ne se font pas totalement confiance doivent partager un état commun des paiements : banques, opérateurs de transfert d'argent, banques centrales, régulateurs. C'est précisément le type de situation où l'on se demande si une blockchain apporte quelque chose.

**Question de recherche :** pour les paiements transfrontaliers, quelle architecture (blockchain publique, registre permissionné ou base de données classique) répond le mieux aux besoins, et dans quelles conditions ?

---

## 2. Les trois architectures

### A. Blockchain publique (sans permission)
N'importe qui peut participer et valider (exemples : Bitcoin, Ethereum). Pour les paiements, l'usage principal aujourd'hui passe par les **stablecoins**, des jetons adossés à une monnaie qui circulent sur ces chaînes. Un transfert type : convertir la monnaie locale en stablecoin, l'envoyer sur la chaîne, puis le convertir en monnaie du pays de destination. Environ 98 % des stablecoins adossés à une monnaie sont libellés en dollars américains.

### B. Registre distribué permissionné
Seuls des participants identifiés et autorisés lisent et écrivent sur le registre (technologies courantes : Hyperledger Fabric, Corda). Deux exemples institutionnels :
- **Project Agorá** (BIS, banques centrales et banques privées) : un prototype de plateforme partagée où des réserves de banque centrale et des dépôts bancaires sont « tokenisés ». Il permet un **règlement atomique** (la transaction se dénoue entièrement ou pas du tout) et conserve le système bancaire à deux niveaux. Le projet passe à des tests en valeur réelle, sans calendrier annoncé.
- **Project mBridge** : plateforme multi-monnaies de banque centrale numérique (CBDC) sur un registre dédié ; le BIS l'a transmise aux banques centrales partenaires en octobre 2024.

### C. Base de données classique
Un registre centralisé tenu par un opérateur ou un réseau de confiance (par exemple le modèle des banques correspondantes avec messagerie standardisée, ou la base d'un opérateur de transfert d'argent). Chaque acteur garde son propre enregistrement et on réconcilie les écarts.

---

## 3. Tableau comparatif

*Évaluation qualitative de l'auteur, fondée sur les sources de la section 6. Elle dépend du contexte et n'est pas une mesure.*

| Critère | A. Blockchain publique | B. Registre permissionné | C. Base de données classique |
|---|---|---|---|
| **Gouvernance** | Aucune autorité centrale ; décisions par consensus de la communauté | Consortium de membres connus ; règles négociées entre eux | Un opérateur ou un réseau ; décisions rapides mais pouvoir concentré |
| **Confiance requise** | Dans le code et le protocole, mais aussi dans les intermédiaires d'entrée et de sortie (échanges, banques) | Dans les membres du consortium et leur gouvernance | Dans l'opérateur central |
| **Confidentialité** | Faible par défaut (transactions visibles) ; protection plus difficile | Bonne : visibilité limitée aux parties concernées | Bonne, contrôlée par l'opérateur |
| **Performance** | Limites de capacité connues (problème d'échelle) | Élevée, ajustable ; règlement de l'ordre de quelques secondes en prototype | Très élevée, technologie mature |
| **Coût** | Frais de réseau faibles, mais coûts de conversion, de liquidité et d'accès aux monnaies locales | Coût d'investissement et de coordination élevé au départ | Coût maîtrisé, déjà amorti pour les systèmes existants |
| **Immuabilité et audit** | Très forte ; historique public vérifiable | Forte entre membres | Modifiable par l'administrateur ; audit à organiser |
| **Conformité (AML, sanctions)** | Difficile : adresses pseudonymes, cadres de contrôle pensés pour le monde bancaire | Intégrable dans le protocole (contrôles en parallèle plutôt qu'en séquence, selon le BIS) | Maîtrisée, mais lente et lourde en réconciliation |
| **Interopérabilité** | Bonne entre applications de la même chaîne, faible avec la finance traditionnelle | À construire entre consortiums | Dépend des standards (par exemple ISO 20022) |
| **Maturité réglementaire** | Encore en construction, risques de stabilité financière soulevés | Cadre plus lisible car acteurs régulés | Cadre établi |

---

## 4. Ce que disent les sources

- **Les stablecoins ne sont pas une solution miracle.** Un document de travail du BIS (n° 1385, octobre 2026) compare banques, opérateurs fintech de transfert d'argent et stablecoins. Il conclut que les fintechs ont déjà beaucoup réduit les coûts, et que la compétitivité des stablecoins dépend aussi de la liquidité du marché, de l'accès aux monnaies locales, de la conformité et de la confiance dans les intermédiaires, pas seulement de la technologie.
- **La technologie permissionnée améliore surtout le règlement entre grandes institutions.** Le BIS présente Agorá comme une réponse aux inefficacités du paiement de gros (wholesale) transfrontalier : règlement atomique, état partagé des paiements, contrôles de conformité menés en parallèle. Mais c'est un prototype ; aucun calendrier de mise en production n'est communiqué.
- **Les chaînes publiques posent des limites structurelles.** Le BIS (rapport annuel, juin 2026) souligne leurs difficultés d'échelle et le besoin de règles différentes pour garantir l'intégrité financière.
- **Remarque sur les sources :** les presses spécialisées donnent des chiffres différents pour le nombre de participants d'Agorá (banques centrales et banques). Je m'en tiens donc à la page officielle du BIS et je ne cite pas ces chiffres.

---

## 5. Recommandation argumentée

La bonne architecture dépend du **segment de paiement**. Il n'y a pas de réponse unique.

1. **Paiements de gros entre banques et banques centrales : registre permissionné.** Les acteurs sont connus et régulés, la confidentialité est indispensable et le règlement atomique réduit le risque de crédit. C'est l'axe suivi par les institutions (Agorá, mBridge).
2. **Petits transferts de migrants : aujourd'hui, la base de données d'un opérateur fintech reste très compétitive.** D'après le BIS, ces opérateurs ont déjà fortement comprimé les coûts. Les stablecoins sur chaîne publique peuvent aider sur certains corridors, mais seulement si l'entrée et la sortie vers la monnaie locale sont bon marché et fiables.
3. **Une blockchain publique est justifiée quand l'ouverture et l'absence d'intermédiaire comptent plus que la confidentialité**, par exemple pour des paiements entre acteurs sans relation bancaire commune, en acceptant les risques de conformité et de dépendance au dollar.
4. **Une simple base de données suffit si un acteur de confiance existe déjà** et que personne ne conteste ses enregistrements. Ajouter une blockchain n'a alors pas de valeur.

**Test rapide avant d'adopter une blockchain :** plusieurs parties écrivent-elles dans le registre ? Se font-elles imparfaitement confiance ? Veulent-elles éviter un intermédiaire central ? Si une de ces réponses est non, une base de données classique est probablement plus simple et moins chère.

---

## 6. Limites

- Le tableau est qualitatif : je n'ai pas mesuré moi-même les coûts ou les délais.
- Les données de coût et de vitesse sont des moyennes mondiales ; elles varient beaucoup selon le corridor (par exemple entre deux pays précis).
- Agorá et mBridge sont des projets pilotes ; leurs résultats ne garantissent pas un déploiement.
- Plusieurs sources sont récentes (2026) et les chiffres peuvent être révisés.

---

## 7. Sources

- FSB, *G20 Roadmap for Enhancing Cross-border Payments: Consolidated progress report for 2026*, 16 novembre 2026 : https://www.fsb.org/2026/11/g20-roadmap-for-enhancing-cross-border-payments-consolidated-progress-report-for-2026/
- Payment Expert, *FSB finds retail cross-border payments slow down ahead of G20 deadline*, 17 novembre 2026 (chiffres de vitesse 2023, 2025, 2026) : https://paymentexpert.com/2026/11/17/fsb-cross-border-payments-report-2026/
- The Paypers, *Understanding the G20 cross-border payments targets*, mars 2026 (cibles de vitesse et de coût) : https://thepaypers.com/payments/explainers/understanding-the-g20-cross-border-payments-targets
- Atlanta Fed, *Cutting through complexities of cross-border payments*, 2024 (cibles de coût et de transparence) : https://atlantafed.org/blogs/take-on-payments/2024/11/04/cutting-through-complexities-of-cross-border-payments
- Du, Huang et Scharfstein, *Competing rails for cross-border payments: banks, fintechs, and stablecoins*, BIS Working Paper 1385, octobre 2026 : https://www.bis.org/publications/working-paper-1385-competing-rails-crossborder-payments-banks-fintechs-and-stablecoins
- T. Adrian (FMI), discussion du papier ci-dessus, juin 2026 (coût moyen des transferts de migrants d'environ 6,5 %) : https://www.bis.org/events/20260626/25th-bis-annual-conference/25th-annual-conference-adrian.pdf
- BIS, *Project Agorá* : https://www.bis.org/project/agora
- BIS, *Project mBridge* : https://www.bis.org/project/mbridge
- BIS, rapport économique annuel 2026, chapitre III, *Anchoring trust in money: innovation beyond stablecoins*, 28 juin 2026 : https://www.bis.org/publications/iii-anchoring-trust-money-innovation-beyond-stablecoins
- RUSI, *Could stablecoins be the future of payments and financial integrity?*, 30 septembre 2026 (part du dollar dans les stablecoins) : https://www.rusi.org/explore-our-research/publications/commentary/could-stablecoins-be-future-payments-and-financial-integrity
