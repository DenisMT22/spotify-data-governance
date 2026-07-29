# 2. Design of the Data Governance Framework

> *Conception du cadre de gouvernance : principes, conformité, qualité et organisation.*

[← Retour au README](../README.md) · [1. Maturité & défis](01-maturity-assessment.md) · **2. Cadre de gouvernance** · [3. Plan d'implémentation →](03-implementation-plan.md)

---

## 2.1 Principes de gouvernance de données

Le cadre repose sur **six principes directeurs**. Ils constituent la grille de référence à laquelle tout nouveau traitement, produit ou pipeline doit pouvoir être confronté.

### 1. Qualité des données

Garantir l'**exactitude**, la **cohérence** et la **fiabilité** des données sur l'ensemble de leur cycle de vie. Ce principe s'appuie sur une **validation automatisée** dès l'ingestion et un **monitoring continu** en production, plutôt que sur des contrôles manuels ponctuels.

### 2. Sécurité & Confidentialité

Protéger les données par un **chiffrement end-to-end**, des **contrôles d'accès granulaires** (au niveau colonne et ligne), l'**anonymisation des données sensibles** et le respect des exigences de **conformité internationale**. La sécurité est un prérequis d'architecture, pas une couche ajoutée après coup.

### 3. Accessibilité & Intégration

**Éliminer les silos** au profit d'une **plateforme unifiée**, offrant à chaque équipe un **accès sécurisé au bon moment** et au bon niveau de granularité. L'objectif est de rendre la donnée trouvable et exploitable sans multiplier les copies.

### 4. Conformité Réglementaire

Respecter le **RGPD**, le **CCPA** et les **lois locales** applicables dans chaque juridiction, en s'appuyant sur des **processus automatisés** pour traiter les demandes d'**accès**, de **rectification** et de **suppression** dans les délais légaux.

### 5. Responsabilité partagée

Définir des **rôles et responsabilités clairs**, où **chaque employé est responsable** de la qualité et de la sécurité des données qu'il manipule, soutenu par des **formations adaptées** à son métier. La gouvernance n'est pas déléguée à une équipe : elle est distribuée et outillée.

### 6. Innovation responsable

Promouvoir un **usage éthique des données** et maintenir un **équilibre entre personnalisation et protection de la vie privée**. La valeur produit ne doit jamais être obtenue au détriment de la confiance de l'utilisateur.

> 📌 **Note d'échelle.** Ce cadre est dimensionné pour **plus de 450 millions d'utilisateurs** répartis dans **plus de 180 pays**. Chaque principe doit donc être applicable de manière automatisée et multilingue — un contrôle manuel ne passe pas l'échelle.

---

## 2.2 Cadre de conformité (RGPD / CCPA)

Les deux régimes réglementaires les plus structurants pour Spotify sont le RGPD (Union européenne) et le CCPA (Californie). Ils partagent une philosophie commune — redonner le contrôle à la personne concernée — mais diffèrent dans leurs mécanismes et leurs délais.

| 🇪🇺 **RGPD — Europe** | 🇺🇸 **CCPA — Californie (USA)** |
|:----------------------|:--------------------------------|
| **Consentement explicite** — obtention et révocation traçables, granulaires par finalité | **Transparence** sur la collecte et l'utilisation des données personnelles |
| **Droit à l'oubli** — suppression automatisée sous **30 jours** | **Droit de suppression** — sur demande vérifiée du consommateur |
| **Notification de violation** aux autorités sous **72 heures** | **Opt-out sur la vente des données** — mécanisme accessible et sans friction |
| **Portabilité** — export des données au format **JSON / XML** | **Non-discrimination** — services équivalents même en cas d'opt-out |
| **Privacy by design** — protection intégrée dès la conception des traitements | **Vérification d'identité** avant toute action sur les données |
| **Registre des traitements** — documentation exhaustive et tenue à jour | **Délais de réponse sous 45 jours** |

### Stratégie de conformité globale

Quatre leviers transverses assurent l'application homogène de ces exigences sur l'ensemble des juridictions :

| Levier | Mise en œuvre |
|:-------|:--------------|
| 🔍 **Audit trimestriel** | Revue périodique des traitements, des accès et des registres |
| 🎓 **Formation obligatoire** | Parcours de formation du personnel, adapté par métier et renouvelé |
| 🤖 **Outils automatisés** | **Dashboard de monitoring en temps réel** de la conformité |
| 🌍 **Support multilingue** | Interfaces de droits utilisateurs disponibles en **plus de 25 langues** |

### Enjeu

| Indicateur | Valeur |
|:-----------|:-------|
| Amende maximale évitée (RGPD) | **20 M€ ou 4 % du chiffre d'affaires mondial** |
| Périmètre de couverture | **Plus de 180 pays** |
| Délai maximal de réponse (RGPD / CCPA) | 30 jours / 45 jours |
| Délai de notification de violation | 72 heures |

---

## 2.3 Amélioration de la qualité des données

La qualité n'est pas un projet ponctuel de nettoyage : c'est un **processus continu**, outillé et mesuré.

### Processus de validation

**Contrôles à l'ingestion**

- Contrôles automatiques appliqués à chaque flux entrant
- **Détection d'anomalies par machine learning** sur les distributions et volumétries
- Validation des **formats et des types** de données
- **Alertes proactives** déclenchées avant propagation en aval

**Nettoyage & standardisation**

- **Déduplication** des entités (utilisateurs, artistes, titres, albums)
- **Normalisation des métadonnées** du catalogue
- **Enrichissement** à partir de référentiels de confiance
- **Harmonisation des taxonomies** (genres, humeurs, langues, marchés)

### Monitoring & KPIs

| Dimension | Objectif |
|:----------|:---------|
| **Précision** | Élevée — les valeurs reflètent fidèlement la réalité métier |
| **Complétude** | Maximale — les champs critiques sont systématiquement renseignés |
| **Cohérence** | Globale — une même entité est représentée à l'identique dans tous les systèmes |
| **Actualité** | Continue — la fraîcheur des données est adaptée à leur usage |

### Outils

| Outil | Rôle |
|:------|:-----|
| **Apache Kafka** | Streaming temps réel des flux de données |
| **Great Expectations** | Tests de qualité déclaratifs et versionnés |
| **Apache Airflow** | Orchestration des traitements et des contrôles |
| **Grafana** | Monitoring visuel et alerting |

### Objectifs UX

L'amélioration de la qualité n'est pas une fin en soi ; elle est évaluée à l'aune de son effet sur l'expérience utilisateur :

- **Optimiser la précision des recommandations**
- **Réduire le temps de traitement** des données de bout en bout
- **Améliorer la satisfaction utilisateur** mesurée sur le produit

---

## 2.4 Structure organisationnelle

Sept rôles portent la gouvernance, du niveau stratégique au niveau opérationnel quotidien.

| Rôle | Périmètre de responsabilité |
|:-----|:----------------------------|
| **1. Chief Data Officer (CDO)** | Stratégie globale des données · Supervision de la gouvernance · Diffusion d'une culture data-driven |
| **2. Data Protection Officer (DPO)** | Conformité RGPD / CCPA · Gestion des violations de données · Formation à la confidentialité |
| **3. Head of Engineering** | Infrastructure technique · Sécurité des systèmes · Architecture des données |
| **4. Legal Team** | Conseil juridique · Conformité réglementaire · Gestion des risques légaux |
| **5. Marketing Director** | Utilisation éthique des données marketing · Segmentation conforme |
| **6. Product Managers** | Mobilisation de données fiables au service de l'innovation produit |
| **7. Data Stewards** | Qualité au quotidien · Catalogage · Documentation des données |

### Articulation des rôles

- **Niveau stratégique** — CDO, DPO, Head of Engineering, Legal Team : définissent le cadre, arbitrent et engagent l'organisation.
- **Niveau métier** — Marketing Director, Product Managers : appliquent le cadre dans leurs domaines et remontent les besoins.
- **Niveau opérationnel** — Data Stewards : garants de la qualité et de la documentation au plus près des jeux de données.

> Ce découpage prend tout son sens dans le **modèle en Centre d'Excellence** recommandé au livrable suivant : les rôles stratégiques constituent le noyau central, les rôles métiers fournissent les **champions** déployés dans chaque département.

---

**[← 1. Data Maturity Assessment](01-maturity-assessment.md)** · **[→ 3. Implementation Plan Development](03-implementation-plan.md)**
