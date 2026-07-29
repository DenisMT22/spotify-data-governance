# 1. Data Maturity Assessment & Challenge Identification

> *Évaluation de la maturité data et identification des défis de gouvernance.*

[← Retour au README](../README.md) · **1. Maturité & défis** · [2. Cadre de gouvernance →](02-governance-framework.md) · [3. Plan d'implémentation →](03-implementation-plan.md)

---

## 1.1 Spotify Data Landscape : maturité actuelle

Spotify, leader du streaming, traite chaque jour des **volumes massifs de données** : écoutes, abonnements, publicités, métadonnées de catalogue. Ses algorithmes de recommandation et son infrastructure cloud lui donnent une avance concurrentielle nette sur le marché.

Mais malgré cette puissance technologique, Spotify n'opère qu'au **niveau « proactif »** de maturité data — faute de **standardisation** et d'**optimisation** de ses processus de gestion à l'échelle de l'organisation. Autrement dit : les bonnes pratiques existent, portées par des équipes compétentes, mais elles restent locales, hétérogènes et non consolidées en un cadre d'entreprise.

### Positionnement sur l'échelle de maturité

| Niveau | Caractéristiques | Statut Spotify |
|:-------|:-----------------|:---------------|
| 1 — Initial | Gestion ad hoc, aucune règle formalisée | ✅ Dépassé |
| 2 — Réactif | Réponse aux incidents, pas d'anticipation | ✅ Dépassé |
| 3 — **Proactif** | **Bonnes pratiques identifiées, anticipation partielle, périmètres non harmonisés** | 🎯 **Niveau actuel** |
| 4 — Géré / Standardisé | Processus normalisés, mesurés et pilotés à l'échelle | ⬜ Cible du cadre proposé |
| 5 — Optimisé | Amélioration continue, gouvernance augmentée par la donnée elle-même | ⬜ Horizon |

### Forces et faiblesses

| ✅ Forces | ⚠️ Faiblesses |
|:----------|:--------------|
| **Infrastructure robuste** — capacité cloud éprouvée à absorber des volumes massifs en temps réel | **Gouvernance fragmentée** — pas de cadre unifié à l'échelle de l'organisation |
| **Forte culture data** — la décision par la donnée est ancrée dans les équipes produit et tech | **Pratiques non standardisées** — chaque équipe définit ses propres règles et conventions |
| **Personnalisation avancée** — moteur de recommandation reconnu comme un différenciateur produit | **Conformité variable** — application inégale des exigences réglementaires selon les régions |

**Lecture du diagnostic.** Les forces sont majoritairement **techniques**, les faiblesses majoritairement **organisationnelles**. C'est un signal clair : le levier de progression n'est pas un investissement supplémentaire en infrastructure, mais la mise en place d'un **cadre de gouvernance transverse** — rôles, standards, processus et outils partagés.

---

## 1.2 Key challenges in Data Governance

La croissance fulgurante de Spotify a fait de la donnée son **actif le plus précieux**. Mais cette croissance cache des failles structurelles : silos fragmentés, qualité inégale, contraintes réglementaires multiples et préoccupations grandissantes en matière de vie privée. Cinq défis majeurs se dégagent.

### Vue d'ensemble

| # | Défi | Nature dominante | Criticité |
|:--|:-----|:-----------------|:----------|
| 1 | Data Silos & Fragmentation | Organisationnelle | 🔴 Élevée |
| 2 | Regulatory Compliance (RGPD, CCPA) | Juridique | 🔴 Élevée |
| 3 | Data Quality Issues | Technique | 🟠 Moyenne à élevée |
| 4 | User Privacy Concerns | Réputationnelle | 🔴 Élevée |
| 5 | Data Accessibility & Integration | Technique & organisationnelle | 🟠 Moyenne |

---

### Défi 1 — Data Silos & Fragmentation

**Description.** La croissance rapide et l'expansion mondiale de Spotify ont fait émerger des silos de données au sein de l'organisation. Les départements **Marketing**, **Développement produit**, **Curation de contenu** et **Engineering** gèrent chacun leurs propres jeux de données de manière indépendante, avec leurs outils, conventions de nommage et référentiels. Aucune source de vérité unique ne permet de réconcilier ces périmètres : le Marketing dispose par exemple d'une vision fine de l'engagement sur les contenus financés par la publicité, tandis que le Développement produit se concentre sur les interactions avec les fonctionnalités premium.

**Risques et conséquences.**

- **Vision utilisateur incomplète** — aucun département ne dispose d'une image consolidée du parcours client, de la découverte de contenu à la conversion en abonnement.
- **Duplication des efforts** — les mêmes indicateurs sont recalculés plusieurs fois, avec des résultats divergents.
- **Décisions biaisées** — les arbitrages stratégiques reposent sur des vues partielles, parfois contradictoires, créant des angles morts dans la décision.
- **Opportunités manquées** — la collaboration inter-départements est freinée faute de données partagées.

---

### Défi 2 — Regulatory Compliance (RGPD, CCPA)

**Description.** La présence de Spotify dans **plus de 180 pays** engendre une complexité juridique considérable : chaque juridiction impose ses propres exigences en matière de collecte, de conservation, de transfert et de suppression des données personnelles. Le RGPD (Europe) et le CCPA (Californie) constituent les deux régimes les plus structurants, mais ils ne sont pas les seuls.

**Risques et conséquences.**

- **Amendes lourdes** — jusqu'à **20 M€ ou 4 % du chiffre d'affaires mondial** au titre du RGPD, le montant le plus élevé étant retenu.
- **Atteinte à la réputation** — une sanction publique pèse durablement sur la confiance des utilisateurs et des partenaires.
- **Coût de mise en conformité rétroactive** — corriger après coup est systématiquement plus coûteux qu'une conformité *by design*.

---

### Défi 3 — Data Quality Issues

**Description.** Erreurs de saisie, doublons d'entités, métadonnées de catalogue incomplètes et données obsolètes dégradent silencieusement la chaîne de valeur. Or, chez Spotify, la qualité des données alimente directement la qualité des **recommandations**.

**Risques et conséquences.**

- **Recommandations dégradées** — un moteur alimenté par des données bruitées produit des suggestions hors sujet.
- **Impact direct sur la satisfaction** — la pertinence perçue du produit chute.
- **Impact sur la fidélisation** — la dégradation de l'expérience se traduit mécaniquement en attrition (*churn*).

---

### Défi 4 — User Privacy Concerns

**Description.** Les utilisateurs exigent désormais **transparence et contrôle** sur leurs données : savoir ce qui est collecté, pouvoir refuser certains traitements (*opt-out*), obtenir la suppression de leur historique. Cette attente n'est plus seulement réglementaire, elle est devenue un critère de choix produit.

**Risques et conséquences.**

- **Perte de confiance** — un manque de transparence perçu érode le capital relationnel avec l'utilisateur.
- **Bad buzz** — une controverse sur l'usage des données se propage rapidement et durablement.
- **Attrition** — les utilisateurs les plus sensibles à la vie privée migrent vers des alternatives.

---

### Défi 5 — Data Accessibility & Integration

**Description.** Partager et intégrer les données entre départements reste difficile : formats hétérogènes, absence de catalogue commun, procédures d'accès manuelles et lentes. Les équipes qui ont besoin d'une donnée ne savent souvent ni qu'elle existe, ni à qui la demander.

**Risques et conséquences.**

- **Innovation ralentie** — les équipes produit passent plus de temps à chercher la donnée qu'à l'exploiter.
- **Lancements retardés** — les délais d'accès aux données deviennent un chemin critique des projets.
- **Sous-exploitation du patrimoine data** — des jeux de données à forte valeur restent inutilisés faute de visibilité.

---

## Conclusion

Les cinq défis identifiés ne sont pas indépendants : la fragmentation nourrit les problèmes de qualité, qui dégradent l'expérience utilisateur, qui amplifient les préoccupations de vie privée, elles-mêmes sanctionnables sur le plan réglementaire. Les traiter isolément ne produirait que des correctifs locaux.

> **Spotify doit transformer son chaos de données en un écosystème gouverné, conforme et centré utilisateur.**

C'est précisément l'objet du cadre proposé dans le livrable suivant.

---

**[→ 2. Design of the Data Governance Framework](02-governance-framework.md)**
