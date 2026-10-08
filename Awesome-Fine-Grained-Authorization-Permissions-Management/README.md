# Awesome Fine-Grained Authorization & Permissions Management 🔐 🛡️

<p align="center">
  <img src="assets/banner.svg" alt="Awesome Fine-Grained Authorization & Permissions Management Banner" width="100%">
</p>

<p align="center">
  <a href="https://github.com/ishandutta2007/Awesome-Awesome-Awesome"><img src="https://img.shields.io/badge/Awesome-%E2%9C%94-blueviolet?style=flat-square&logo=github" alt="Awesome"/></a>
  <a href="https://discord.gg/jc4xtF58Ve"><img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord" /></a>
  <a href="https://github.com/ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management"><img src="https://img.shields.io/github/stars/ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management?style=social" alt="GitHub Stars"/></a>
  <a href="https://github.com/ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management/fork"><img src="https://img.shields.io/github/forks/ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management?style=social" alt="GitHub Forks"/></a>
  <a href="https://github.com/ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management/blob/main/LICENSE"><img src="https://img.shields.io/github/license/ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management?color=blue" alt="License"/></a>
  <a href="https://github.com/ishandutta2007"><img alt="GitHub followers" src="https://img.shields.io/github/followers/ishandutta2007?label=Follow" /></a>
</p>

---

## 🌟 Top Fine-Grained Authorization, ReBAC & Permissions Management Ecosystem 🔑

**Curated Directory of Enterprise SaaS Authorization Platforms & Open-Source Policy Engines** 🛡️  
*Focused on Relationship-Based Access Control (ReBAC), Attribute-Based Access Control (ABAC), Policy-as-Code (OPA/Cedar/Rego), Google Zanzibar Implementations, PDP/PEP Architecture & Self-Hosted Decision Engines.*

**Last updated: October 2026** 📅

---

### 📌 Overview & Architecture Summary 🏛️

Welcome to the definitive developer and security reference for **fine-grained authorization (FGA)**, **open-source policy engines**, and **ReBAC/ABAC access control architecture**. Modern cloud-native applications require decoupling authorization logic from application code. Whether you need enterprise managed platforms (*Auth0 FGA*, *Permit.io*, *Styra DAS*, *PlainID*, *Oso Cloud*) or self-hosted open-source authorization engines (*Casbin*, *OPA*, *SpiceDB*, *OpenFGA*, *OPAL*, *Cerbos*), this guide maps out key commercial and open-source capabilities.

#### Key Architectural Trade-offs & Market Context 💡:
- **Google Zanzibar (ReBAC Graph Model):** Inspired by Google's 2019 whitepaper, **SpiceDB**, **OpenFGA**, and **Permify** store relationships as tuples in centralized graph stores. Optimized for reverse lookup (`ListObjects` / "Which resources can user X view?") with **sub-10ms p99 response times**. ⚡
- **Stateless Policy Decision Points (PDPs):** **Cerbos**, **OPA**, and **Cedar** act as stateless sidecars evaluating declarative policies (YAML, Rego, Cedar). Extremely fast (`< 1ms` latency) for direct check operations, but require external data provisioning or workarounds for list filtering. 📜
- **Hybrid Architectures:** **Topaz (Aserto)** and **OPAL (Permit.io)** bridge the gap by combining relationship directories with policy-as-code decision engines and real-time state synchronization. 🔄

---

## 📑 Table of Contents 📖

- [📊 Market Overview & Sector Structure](#-market-overview--sector-structure-)
- [🏢 SaaS & Commercial Authorization Platforms](#-saas--commercial-authorization-platforms-)
- [🔓 Open-Source Authorization Engines & Repositories](#-open-source-authorization-engines--repositories-)
- [🛠️ How to Contribute](#%EF%B8%8F-how-to-contribute-)
- [🤝 Support & Sponsorship](#-support--sponsorship-)
- [📊 Star History](#-star-history-)
- [⚠️ Architecture & Deployment Disclaimer](#%EF%B8%8F-architecture--deployment-disclaimer-)

---

## 📊 Market Overview & Sector Structure 💼

> 💡 **Market Size & Industry Dynamics:** The global Identity and Fine-Grained Authorization (FGA) market is estimated at **$3.5 Billion in 2026** (projected to reach $8.2 Billion by 2030 at an 18.5% CAGR). The sector is **highly fragmented**, spanning distinct architectural paradigms—ranging from Google Zanzibar relationship graphs (ReBAC) to stateless decision engines (ABAC/PBAC) and embedded libraries—with no single winner-take-all enterprise vendor.

---

## 🏢 SaaS & Commercial Authorization Platforms 🌐

*Sorted by Company Valuation / Total Funding (Descending)* 📈

| SaaS / Commercial Platform | Company / Owner | Valuation / Total Funding | Standard Edition Starting Price | Free Tier / Free Trial Limits | Key Features & Architecture Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[Auth0 FGA](https://auth0.com/fine-grained-authorization)** 🔷 | Okta (Acquired Auth0) | ~$15 Billion (Okta Market Cap) | **$0.00005 per check** (Pay-as-you-go; base Auth0 from $23/mo) | **Free Forever**: 100,000 checks/month & 100,000 relationship tuples | **Managed Zanzibar ReBAC** — Built on OpenFGA OSS core. Native CIAM integration with Okta Identity Cloud for enterprise tenant & multi-tenant relationship authorization. |
| **[PlainID](https://www.plainid.com/)** 🔴 | PlainID | ~$100 Million Funding (Series C) | **$2,500/month** ($30,000/year base tier) | **30-Day Enterprise Trial**: Sandbox environment for up to 5 application integrations | **Enterprise PBAC Orchestration** — Policy-based access control engine for estate-wide IT governance, API access control, and enterprise data security. |
| **[Styra DAS](https://www.styra.com/)** 🟡 | Styra | ~$54 Million Funding (Series B) | **$950/month** (Team Tier) | **14-Day Free Trial**: Up to 20 systems & 1,000 OPA decision checks/mo | **Enterprise OPA Management** — Declarative Authorization Service for managing Open Policy Agent (OPA) deployments, policy lifecycles, and compliance auditing. |
| **[Oso Cloud](https://www.osohq.com/)** 🟣 | Oso | ~$23 Million Funding (Series A) | **$500/month** (Growth Tier) | **Free Forever**: Up to 10,000 monthly active users & 1,000,000 checks/month | **Managed Authorization Service** — Powered by the Polar declarative language with centralized authorization logic, local dev server, and multi-language SDKs. |
| **[Permit.io](https://www.permit.io/)** 🟢 | Permit.io | ~$14 Million Funding (Series A) | **$249/month** (Pro Plan) | **Free Forever**: Up to 1,000 Monthly Active Users & 1,000 resource instances | **Full-Stack Authorization Platform** — Supports RBAC, ABAC, and ReBAC with no-code visual policy editor, audit trail logs, and OPA/Cedar engine backends. |
| **[Aserto](https://www.aserto.com/)** 🔵 | Aserto | ~$5.1 Million Funding (Seed/Series A) | **$100/month** (Developer Tier) | **Free Forever**: Up to 1,000 Monthly Active Users & 100,000 directory objects | **Hybrid ReBAC + OPA SaaS** — Cloud-hosted control plane powered by open-source Topaz engine combining relationship graphs with Rego policy evaluation. |

---

## 🔓 Open-Source Authorization Engines & Repositories 🚀

*Sorted by GitHub Star Count (Descending)* 🌟

- **[Casbin](https://github.com/casbin/casbin)** [![Stars](https://img.shields.io/github/stars/casbin/casbin?style=social&color=white)](https://github.com/casbin/casbin/stargazers)  
  **An authorization library supporting ACL, RBAC, ABAC**, Apache-2.0 licensed. **20,435 GitHub stars** — **the most widely deployed embedded authorization library**. Multi-language support across Go, Java, Node.js, Python, Rust, C++, PHP, and .NET. 🔧

- **[Open Policy Agent (OPA)](https://github.com/open-policy-agent/opa)** [![Stars](https://img.shields.io/github/stars/open-policy-agent/opa?style=social&color=white)](https://github.com/open-policy-agent/opa/stargazers)  
  **General-purpose policy engine for cloud-native environments**, Apache-2.0 licensed. **12,331 GitHub stars** — **CNCF Graduated project**. Decouples policy decisions using the Rego declarative policy language across Kubernetes, microservices, APIs, and CI/CD pipelines. ☸️

- **[SpiceDB](https://github.com/authzed/spicedb)** [![Stars](https://img.shields.io/github/stars/authzed/spicedb?style=social&color=white)](https://github.com/authzed/spicedb/stargazers)  
  **Google Zanzibar-inspired permissions database**, Apache-2.0 licensed. **7,124 GitHub stars** — **the leading mature open-source ReBAC database**. Scalably stores and queries fine-grained authorization relationships with `LookupResources` API and p99 `< 10ms` latency target. 🛡️

- **[CASL](https://github.com/stalniy/casl)** [![Stars](https://img.shields.io/github/stars/stalniy/casl?style=social&color=white)](https://github.com/stalniy/casl/stargazers)  
  **Isomorphic JavaScript authorization library**, MIT licensed. **7,095 GitHub stars** — **the standard frontend & backend JS/TS permission utility**. Restricts resource access across React, Vue, Angular, Node.js, and React Native. 🟨

- **[Permify](https://github.com/Permify/permify)** [![Stars](https://img.shields.io/github/stars/Permify/permify?style=social&color=white)](https://github.com/Permify/permify/stargazers)  
  **Open-source authorization-as-a-service**, AGPL-3.0 licensed. **5,961 GitHub stars** — **Zanzibar-inspired fine-grained permissions engine**. Easily define DSL schemas and manage complex multi-tenant application authorization (now part of FusionAuth). 📦

- **[OpenFGA](https://github.com/openfga/openfga)** [![Stars](https://img.shields.io/github/stars/openfga/openfga?style=social&color=white)](https://github.com/openfga/openfga/stargazers)  
  **High-performance relationship-based authorization engine**, Apache-2.0 licensed. **5,934 GitHub stars** — **CNCF Incubating project** (created by Auth0/Okta). Flexible JSON/DSL schema modeling with `ListObjects` API, contextual ABAC conditions, and SDKs for Go, Node, Python, Java, .NET, and Ruby. 🎯

- **[OPAL (Open Policy Administration Layer)](https://github.com/permitio/opal)** [![Stars](https://img.shields.io/github/stars/permitio/opal?style=social&color=white)](https://github.com/permitio/opal/stargazers)  
  **Real-time policy and data administration layer**, Apache-2.0 licensed. **5,514 GitHub stars** — Created by Permit.io. Keeps policy agents (OPA, Cedar) in sync with real-time application state changes via WebSockets and pub/sub data updates. 🔄

- **[Ory Keto](https://github.com/ory/keto)** [![Stars](https://img.shields.io/github/stars/ory/keto?style=social&color=white)](https://github.com/ory/keto/stargazers)  
  **Open-source permission server based on Google Zanzibar**, Apache-2.0 licensed. **5,408 GitHub stars** — The authorization core of the Ory ecosystem (Hydra OAuth2, Kratos Identity). High-performance gRPC/REST APIs for fine-grained ACLs and relationship checks. 🐉

- **[Cerbos](https://github.com/cerbos/cerbos)** [![Stars](https://img.shields.io/github/stars/cerbos/cerbos?style=social&color=white)](https://github.com/cerbos/cerbos/stargazers)  
  **Open-core stateless authorization PDP engine**, Apache-2.0 licensed. **4,616 GitHub stars** — **Developer-loved stateless PDP**. Declarative YAML policies, GitOps-native workflows, and sub-millisecond local policy evaluation without storing relationship tuples. ⚡

- **[Oso](https://github.com/osohq/oso)** [![Stars](https://img.shields.io/github/stars/osohq/oso?style=social&color=white)](https://github.com/osohq/oso/stargazers)  
  **Declarative authorization language and embedded library**, Apache-2.0 licensed. **3,490 GitHub stars** — Uses the Polar policy language to express fine-grained permissions inside application code across Python, Node.js, Go, Rust, Ruby, and Java. 🟣

- **[Cedar Policy](https://github.com/cedar-policy/cedar)** [![Stars](https://img.shields.io/github/stars/cedar-policy/cedar?style=social&color=white)](https://github.com/cedar-policy/cedar/stargazers)  
  **Expressive and fast policy language & SDK**, Apache-2.0 licensed. **1,769 GitHub stars** — Developed by AWS. Supports fine-grained access control with formal verification proving policy correctness and deterministic evaluation speed. 🌲

- **[Topaz (Aserto)](https://github.com/aserto-dev/topaz)** [![Stars](https://img.shields.io/github/stars/aserto-dev/topaz?style=social&color=white)](https://github.com/aserto-dev/topaz/stargazers)  
  **Cloud-native hybrid authorization engine**, Apache-2.0 licensed. **1,363 GitHub stars** — Combines Google Zanzibar relationship graph directory with OPA Rego policy decision logic in a single sidecar deployment. 🔗

- **[Warrant](https://github.com/warrant-dev/warrant)** [![Stars](https://img.shields.io/github/stars/warrant-dev/warrant?style=social&color=white)](https://github.com/warrant-dev/warrant/stargazers)  
  **Centralized Zanzibar-based authorization engine**, Apache-2.0 licensed. **1,338 GitHub stars** — Defines, enforces, and audits fine-grained application access control (acquired by Okta and integrated into OpenFGA). 🏛️

- **[SpiceDB Operator](https://github.com/authzed/spicedb-operator)** [![Stars](https://img.shields.io/github/stars/authzed/spicedb-operator?style=social&color=white)](https://github.com/authzed/spicedb-operator/stargazers)  
  **Kubernetes Operator for SpiceDB**, Apache-2.0 licensed. **107 GitHub stars** — Automates SpiceDB deployment, datastore migrations, scaling, and lifecycle management on Kubernetes clusters. ☸️

- **[Keycloak OpenFGA Event Publisher](https://github.com/embesozzi/keycloak-openfga-event-publisher)** [![Stars](https://img.shields.io/github/stars/embesozzi/keycloak-openfga-event-publisher?style=social&color=white)](https://github.com/embesozzi/keycloak-openfga-event-publisher/stargazers)  
  **Keycloak to OpenFGA event bridge**, Apache-2.0 licensed. **61 GitHub stars** — Real-time event synchronization publishing Keycloak identity and group changes directly into OpenFGA tuple relationships. 🌉

- **[Permify CLI](https://github.com/Permify/permify-cli)** [![Stars](https://img.shields.io/github/stars/Permify/permify-cli?style=social&color=white)](https://github.com/Permify/permify-cli/stargazers)  
  **CLI management tool for Permify**, Apache-2.0 licensed. **7 GitHub stars** — Terminal interface for managing Permify schemas, running policy validations, and testing authorization tuple stores. 🖥️

---

## 🛠️ How to Contribute 🤝

Contributions to this directory are actively encouraged! Follow these steps to submit a new fine-grained authorization platform or open-source engine:

1. 🍴 **Fork** the repository.
2. 📝 **Add or edit** entries in `README.md` following the exact table/list schema and sorting order.
3. 🔗 Ensure project title, official website/repo link, star count badge, license, starting pricing, and clear technical descriptions are provided.
4. 🚀 Submit a **Pull Request** with a descriptive title detailing your additions.

---

## 🤝 Support & Sponsorship ☕

If you find this fine-grained authorization directory useful, please consider supporting the project:

- ⭐ **Star** this repository on GitHub to increase visibility!
- 🔀 **Fork** and share with fellow security engineers, platform teams, and open-source advocates.
- ☕ **Sponsor & Buy Me a Coffee**: Support ongoing open-source security research via the [GitHub Sponsor Dashboard](https://github.com/sponsors/ishandutta2007).

---

## 📊 Star History

[![Star History Chart](https://star-history.dera.page/svg?repos=ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management&type=date&legend=top-left)](https://star-history.dera.page/#ishandutta2007/Awesome-Fine-Grained-Authorization-Permissions-Management&type=date&legend=top-left)

---

## ⚠️ Architecture & Deployment Disclaimer 🔒

- **Community Curated Reference:** This list represents independent research for security engineers and software architects — not an official endorsement. ℹ️
- **ReBAC (Zanzibar) vs. ABAC (Stateless PDP):** Choosing between graph-based relationship stores (*SpiceDB*, *OpenFGA*) vs. stateless policy sidecars (*Cerbos*, *OPA*) is an architectural decision. ReBAC excels at deep relationship trees and reverse queries (`ListObjects`), whereas stateless PDPs excel at rapid local evaluation (`< 1ms Check`). ⚖️
- **Data Stores & Operational Requirements:** Open-source permissions engines require datastores (e.g. PostgreSQL or CockroachDB for SpiceDB; PostgreSQL or MySQL for OpenFGA) and active data sync pipelines. Always benchmark latency and consistency models before deploying to production environments. 🔐

---

<p align="center">
  <b>Made with ❤️ for security engineers, platform architects, and open-source authorization advocates.</b>
</p>
