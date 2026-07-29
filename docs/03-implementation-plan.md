# 3. Implementation Plan Development

> *Modèle organisationnel, stack technologique et déploiement pilote.*

[← Retour au README](../README.md) · [1. Maturité & défis](01-maturity-assessment.md) · [2. Cadre de gouvernance](02-governance-framework.md) · **3. Plan d'implémentation**

---

## 3.1 Modèle organisationnel

Trois modèles d'organisation de la gouvernance sont envisageables. Chacun arbitre différemment entre **cohérence** et **agilité**.

### Comparaison des trois modèles

| Critère | 🏛️ Centralisé | 🌟 Centre d'Excellence (CoE) | 🔗 Intégré |
|:--------|:--------------|:-----------------------------|:-----------|
| **Principe** | Contrôle unifié par une équipe centrale | Équipe centrale d'experts + champions métiers dans chaque département | Gouvernance intégrée dans les processus métier, infrastructure partagée |
| **Cohérence des standards** | Très forte | Forte | Faible |
| **Agilité métier** | Faible | Bonne | Très forte |
| **Scalabilité** | Limitée | Optimale | Variable |
| **Coût de mise en place** | Modéré | Élevé | Faible |

### Détail des avantages et limites

#### 🏛️ Modèle centralisé

*Contrôle unifié par une équipe centrale.*

| ✅ Avantages | ❌ Limites |
|:-------------|:-----------|
| Cohérence globale | Moins d'agilité |
| Standards uniformes | Éloignement du métier |
| Contrôle qualité strict | Goulots d'étranglement |
| Conformité centralisée | Résistance au changement |

#### 🌟 Modèle Centre d'Excellence — **RECOMMANDÉ**

*Équipe centrale d'experts appuyée par des champions métiers dans chaque département.*

| ✅ Avantages | ❌ Limites |
|:-------------|:-----------|
| Standards partagés | Coordination complexe |
| Expertise métier préservée | Formation intensive requise |
| Collaboration renforcée | Coût initial élevé |
| Scalabilité optimale | Temps de mise en place |

#### 🔗 Modèle intégré

*Gouvernance intégrée dans les processus métier, sur une infrastructure partagée.*

| ✅ Avantages | ❌ Limites |
|:-------------|:-----------|
| Équipes agiles | Absence de source de vérité unique |
| Donnée directement liée au métier | Risque de nouveaux silos |
| Équipes plus spécialisées | Difficile sans expertise technique interne |

### Recommandation

> **Le modèle Centre d'Excellence (CoE) est retenu pour Spotify.**

Le modèle **centralisé** recréerait les goulots d'étranglement que le diagnostic cherche précisément à supprimer, dans une organisation dont la culture produit repose sur l'autonomie des équipes. Le modèle **intégré**, à l'inverse, reproduirait à terme la fragmentation constatée au [défi 1](01-maturity-assessment.md#défi-1--data-silos--fragmentation), faute de source de vérité unique.

Le **CoE** est le seul des trois à répondre simultanément aux deux faiblesses structurelles identifiées : il apporte les **standards partagés** qui manquent aujourd'hui, tout en préservant l'**expertise métier** et l'agilité des équipes. Ses limites — coordination, formation, coût initial — sont réelles mais **maîtrisables dans le temps**, là où les limites des deux autres modèles sont structurelles.

---

## 3.2 Stack technologique

### Les quatre catégories d'outillage

#### 🗂️ Catalogue des données

**Outils :** Apache Atlas · DataHub · Collibra · Amundsen

- Auto-découverte des schémas
- Lignage (*data lineage*) de bout en bout
- Métadonnées enrichies
- Recherche intelligente

#### ✅ Qualité des données

**Outils :** Great Expectations · Deequ · Monte Carlo · Databand

- Profiling automatique des jeux de données
- Tests de qualité intégrés en CI/CD
- Alertes temps réel
- Tableau de bord qualité

#### 🔒 Confidentialité & sécurité

**Outils :** Apache Ranger · BigID · OneTrust · Privacera

- Masquage dynamique des données
- Tokenisation des PII
- *Audit trail* complet
- Gestion des consentements

#### ⚙️ Orchestration & Pipeline

**Outils :** Apache Airflow · Prefect · Luigi · Dagster

- Workflows complexes
- Retry automatique
- Monitoring d'exécution
- Gestion des dépendances

### Architecture recommandée pour Spotify

| Phase | Intitulé | Composants | Objectif |
|:------|:---------|:-----------|:---------|
| **Phase 1** | **Foundation** | **DataHub** + **Great Expectations** + **Apache Ranger** | Poser le socle : catalogue, qualité et sécurité |
| **Phase 2** | **Scale** | **Airflow** + **Monte Carlo** + **Privacera** | Orchestration avancée et monitoring proactif |
| **Phase 3** | **Intelligence** | Gouvernance ML-powered + self-service | Autonomie des utilisateurs sur leurs données |

**Logique de séquencement.** La phase 1 rend la donnée **trouvable, fiable et protégée** — sans ce socle, toute automatisation ultérieure amplifierait simplement le désordre existant. La phase 2 industrialise et passe d'un contrôle réactif à une **détection proactive** des incidents. La phase 3 transfère la capacité d'action vers les équipes elles-mêmes, ce qui n'est soutenable qu'une fois les garde-fous des deux premières phases en place.

---

## 3.3 Plan pilote & déploiement

Le pilote se déroule en **trois phases successives**, chacune conditionnant la suivante.

### Timeline

#### Phase 1 — Préparation & Setup *(fondation)*

- Constitution de l'**équipe pilote**
- **Installation et configuration** de DataHub + Great Expectations
- **Inventaire des datasets utilisateurs prioritaires**
- **Définition des standards** de qualité et de métadonnées
- **Formation initiale** des participants

#### Phase 2 — Déploiement & Intégration *(implémentation)*

- **Catalogage automatique** des données utilisateurs
- **Contrôles qualité** appliqués aux pipelines critiques
- **Masques de données** pour la conformité RGPD / CCPA
- **Tableau de bord de gouvernance** en temps réel
- **Tests de performance** sur volumes de production

#### Phase 3 — Optimisation & Mesure *(validation)*

- **Monitoring et ajustement** des règles de qualité
- **Tests d'acceptation utilisateur**
- **Évaluation des KPIs** et mesure de l'impact business
- **Documentation des bonnes pratiques**
- **Préparation du plan de déploiement global**

### KPIs de succès

| KPI | Objectif visé |
|:----|:--------------|
| **Qualité** | Réduction des anomalies détectées sur les datasets pilotes |
| **Performance** | Amélioration des temps d'accès à la donnée |
| **Conformité** | Couverture RGPD complète sur le périmètre pilote |
| **Adoption** | Taux d'adoption élevé par les équipes utilisatrices |

### Gestion des risques

| Risque | Mesure de mitigation |
|:-------|:---------------------|
| **Résistance au changement** | Formation + champions métiers relais dans chaque département |
| **Performance des systèmes** | Tests de charge + déploiement progressif |
| **Complexité d'intégration** | APIs standardisées + documentation systématique |

### Critères de validation du pilote

Le passage au déploiement global est conditionné à la satisfaction des **quatre critères** suivants :

- [ ] **Catalogue complet** des datasets utilisateurs du périmètre pilote
- [ ] **Conformité RGPD opérationnelle** — droits utilisateurs traités de bout en bout
- [ ] **Amélioration mesurable de la qualité** des données
- [ ] **Adoption positive** confirmée par les équipes

> Ces quatre critères couvrent chacun une dimension distincte — technique, réglementaire, mesurable et humaine. Un pilote qui n'en valide que trois ne démontre pas la viabilité du cadre à l'échelle de l'organisation.

---

## Synthèse

Le cadre proposé articule trois décisions structurantes :

1. **Une organisation en Centre d'Excellence**, qui concilie standards partagés et autonomie métier.
2. **Une stack en trois phases**, séquencée pour poser le socle avant d'automatiser puis d'ouvrir en self-service.
3. **Un pilote borné et mesuré**, dont la généralisation dépend de critères de validation explicites.

Ensemble, ces décisions font passer Spotify du niveau **proactif** au niveau **géré et standardisé** de maturité data — objectif fixé au [livrable 1](01-maturity-assessment.md#positionnement-sur-léchelle-de-maturité).

---

**[← 2. Design of the Data Governance Framework](02-governance-framework.md)** · **[↑ Retour au README](../README.md)**
