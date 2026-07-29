<p align="center">
  <img src="assets/alexander-shatov-JlO3-oY5ZlQ.jpg" alt="Illustration streaming musical" width="100%">
</p>

<p align="center"><sub>Photo : <a href="https://unsplash.com/@alexbemore">Alexander Shatov</a> — Unsplash</sub></p>

# Spotify Data Governance Framework

> Conception et pilotage d'un cadre de gouvernance de données conforme, centré utilisateur et scalable.

![Projet](https://img.shields.io/badge/Projet-Data%20Governance-0E7C86?style=flat-square)
![Jedha](https://img.shields.io/badge/Jedha-Lead%20Data%20Science%20%26%20Engineering-1DB954?style=flat-square)
![Bloc](https://img.shields.io/badge/Bloc%201-Architecte%20IA%20·%20RNCP%207-11734A?style=flat-square)

![RGPD](https://img.shields.io/badge/Conformité-RGPD-0E7C86?style=flat-square)
![CCPA](https://img.shields.io/badge/Conformité-CCPA-12836C?style=flat-square)

![DataHub](https://img.shields.io/badge/Catalogue-DataHub-2E8B57?style=flat-square)
![Great Expectations](https://img.shields.io/badge/Qualité-Great%20Expectations-2E8B57?style=flat-square)
![Apache Ranger](https://img.shields.io/badge/Sécurité-Apache%20Ranger-2E8B57?style=flat-square)
![Airflow](https://img.shields.io/badge/Orchestration-Airflow-2E8B57?style=flat-square)

![Markdown](https://img.shields.io/badge/Made%20with-Markdown-1F6F78?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-3D9970?style=flat-square)

[![Certification Jedha](https://img.shields.io/badge/🎓_Certification-Jedha_RNCP_38777-0E7C86?style=for-the-badge)](https://app.jedha.co/certifications/rncp38777bc01)
[![Présentation](https://img.shields.io/badge/📊_Présentation-Google_Drive-1DB954?style=for-the-badge)](https://drive.google.com/drive/folders/1adNCnlx-g_hUXuZ5t3RDlm3Htatq779w?usp=sharing)

---

## Contexte du projet

Projet réalisé dans le cadre de la formation **Jedha — Lead Data Science & Engineering** (Bloc 1 — Architecte en Intelligence Artificielle, RNCP niveau 7).

**Rôle :** Data Governance Specialist pour Spotify.

**Objectif :** concevoir et piloter un cadre de gouvernance de données garantissant la conformité **RGPD**, **CCPA** et **PCI-DSS**, tout en améliorant la qualité des données et l'efficacité opérationnelle à l'échelle des opérations mondiales de Spotify.

**Projet hands-on**, structuré autour de quatre livrables :

| # | Livrable |
|:--|:---------|
| 1 | Politique de gouvernance des données |
| 2 | Rôles & responsabilités organisationnels |
| 3 | Plan d'implémentation |
| 4 | Présentation finale aux parties prenantes |

---

## Résumé exécutif

Spotify est un leader technologique dont les algorithmes de recommandation et l'infrastructure cloud constituent un avantage concurrentiel réel. Pourtant, en matière de gouvernance de données, l'organisation n'opère qu'au niveau **« proactif »** : les bonnes pratiques existent, mais elles ne sont ni standardisées ni optimisées à l'échelle de l'entreprise. Il en résulte une gouvernance **fragmentée** — silos entre Marketing, Finance, Ops et Sales, qualité inégale, conformité variable d'un pays à l'autre — alors même que la plateforme sert plus de 450 millions d'utilisateurs répartis dans plus de 180 juridictions.

Ce livrable propose un **cadre de gouvernance conforme, centré utilisateur et scalable**, structuré autour de six principes directeurs, d'une conformité RGPD/CCPA *by design*, d'une chaîne de qualité outillée (catalogue, tests, monitoring) et d'un **modèle organisationnel en Centre d'Excellence (CoE)** — équipe centrale d'experts épaulée par des champions métiers dans chaque département. Sa mise en œuvre est déclinée en un **pilote en trois phases**, assorti de KPIs de succès, d'une gestion des risques et de critères de validation explicites avant généralisation.

<p align="center">
  <img src="assets/andrik-langfield-uPfyxkwA3RM.jpg" alt="Utilisateur à l'écoute au casque" width="100%">
</p>

<p align="center"><em>Une gouvernance centrée utilisateur : transparence, contrôle et confiance.</em><br>
<sub>Photo : <a href="https://unsplash.com/@andriklangfield">Andrik Langfield</a> — Unsplash</sub></p>

---

## Table des matières

| # | Livrable | Contenu |
|:--|:---------|:--------|
| 1 | **[Data Maturity Assessment & Challenge Identification](docs/01-maturity-assessment.md)** | Maturité actuelle · Forces / Faiblesses · 5 défis clés de gouvernance |
| 2 | **[Design of the Data Governance Framework](docs/02-governance-framework.md)** | 6 principes · Cadre RGPD / CCPA · Qualité des données · 7 rôles |
| 3 | **[Implementation Plan Development](docs/03-implementation-plan.md)** | 3 modèles organisationnels → CoE · Stack technologique · Pilote & KPIs |

### Parcours de lecture rapide

- **Vous découvrez le sujet** → [1. Maturité & défis](docs/01-maturity-assessment.md) puis [2. Cadre](docs/02-governance-framework.md)
- **Vous cherchez le volet conformité** → [2.2 Cadre de conformité RGPD / CCPA](docs/02-governance-framework.md#22-cadre-de-conformité-rgpd--ccpa)
- **Vous cherchez le volet outillage** → [3.2 Stack technologique](docs/03-implementation-plan.md#32-stack-technologique)
- **Vous cherchez la recommandation finale** → [3.1 Modèle organisationnel](docs/03-implementation-plan.md#31-modèle-organisationnel)

---

## Stack technologique de référence

| Catégorie | Outils référencés | Rôle dans le cadre |
|:----------|:------------------|:-------------------|
| 🗂️ **Catalogue des données** | Apache Atlas · **DataHub** · Collibra · Amundsen | Découverte des schémas, lignage, métadonnées |
| ✅ **Qualité des données** | **Great Expectations** · Deequ · Monte Carlo · Databand | Profiling, tests CI/CD, alertes temps réel |
| 🔒 **Confidentialité & sécurité** | **Apache Ranger** · BigID · OneTrust · Privacera | Masquage, tokenisation PII, audit trail, consentements |
| ⚙️ **Orchestration & pipeline** | **Apache Airflow** · Prefect · Luigi · Dagster | Workflows, retry, monitoring d'exécution |

> Outils **en gras** = socle retenu pour la phase 1 de l'architecture recommandée. Détail en [3.2](docs/03-implementation-plan.md#32-stack-technologique).

---

## Ressources

- 🎓 **Certification Jedha** — [Lead Data Science & Engineering · RNCP 38777 (Bloc 1)](https://app.jedha.co/certifications/rncp38777bc01)
- 📊 **Présentation du projet** — [Dossier Google Drive](https://drive.google.com/drive/folders/1adNCnlx-g_hUXuZ5t3RDlm3Htatq779w?usp=sharing)
- 📄 **Présentation complète (PDF)** — [`assets/Spotify-Data-Governance.pdf`](assets/Spotify-Data-Governance.pdf)

---

## Structure du dépôt

```text
spotify-data-governance/
├── README.md                          # Vous êtes ici
├── LICENSE                            # MIT
├── docs/
│   ├── 01-maturity-assessment.md      # Maturité & défis
│   ├── 02-governance-framework.md     # Cadre de gouvernance
│   └── 03-implementation-plan.md      # Plan d'implémentation
└── assets/
    ├── Spotify-Data-Governance.pdf    # Présentation complète
    └── *.jpg                          # Visuels (crédits Unsplash)
```

---

## Auteur

**Denis Mutombo Tshituka** — ML Engineer | Architecte en Intelligence Artificielle (RNCP 7) | Data Science & Engineering • MLOps

- LinkedIn : https://www.linkedin.com/in/denis-mutombo-tshituka-66a5183a0/
- GitHub : https://github.com/DenisMT22

---

## Licence

Distribué sous licence **MIT** — voir [LICENSE](LICENSE).
