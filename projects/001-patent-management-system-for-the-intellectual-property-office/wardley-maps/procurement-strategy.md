# Wardley Map: Patent Management System Procurement Strategy

**Map Type**: Procurement Strategy Map (Mode E)
**Project**: Patent Management System for the UK Intellectual Property Office
**Project ID**: 001
**Date**: 2025-10-15
**Author**: Dr. Emily Roberts (Enterprise Architect)
**Version**: 1.0

---

## Executive Summary

This Wardley Map provides strategic guidance for the £7M Patent Management System procurement, mapping all system components across the evolution axis (Genesis → Custom → Product → Commodity) to inform build vs buy decisions. The map reveals that **62% of functionality can be purchased or reused** (GOV.UK services, cloud infrastructure, commercial products via G-Cloud 14), while **38% requires custom development** (patent-specific workflows, ML classification, international integrations).

**Key Strategic Insights**:
- **Reuse GOV.UK Services** (£0.5M savings): Pay, Notify, Design System, Verify are mature commodities
- **Buy via G-Cloud 14** (£2.1M): OCR, chemical structure search, authentication, monitoring as products
- **Build Custom Components** (£4.4M): ML patent classification (0.35), semantic search (0.42), examination workflow (0.38), WIPO/EPO adapters (0.45)
- **Avoid Building Commodities**: AWS, PostgreSQL, Redis, Kafka are all >0.85 evolution, no business case for custom alternatives

This strategy aligns with **Technology Code of Practice Point 3 (Reuse)**, **Point 4 (Open Standards)**, and **Point 5 (Cloud First)**, supporting the 81% TCoP compliance score.

---

## 1. Wardley Map Visualization

### 1.1 OnlineWardleyMaps Code

```wardley
title Patent Management System Procurement Strategy (UK IPO)
anchor Patent Applicants [0.95, 0.85] // User need: External applicants filing patents
anchor Patent Examiners [0.95, 0.75] // User need: IPO examiners processing applications
anchor Public Users [0.95, 0.65] // User need: Public searching published patents

// Value Chain Layer 1: Core User-Facing Services
component Patent Filing Service [0.85, 0.52] // Custom digital service (Product)
component Patent Search Service [0.82, 0.48] // Custom semantic search (Custom-Product boundary)
component Examiner Dashboard [0.88, 0.38] // Custom examination interface (Custom)
component Public Portal [0.80, 0.68] // Product-level web application (Product)
component API Gateway [0.75, 0.82] // Commodity API management (Product-Commodity)

// Value Chain Layer 2: Business Capabilities
component Application Intake [0.72, 0.42] // Custom workflow (Custom)
component Patent Classification [0.68, 0.35] // ML-assisted classification (Custom-Genesis)
component Prior Art Search [0.70, 0.42] // Semantic search engine (Custom)
component Examination Workflow [0.75, 0.38] // Custom business process (Custom)
component Publication Engine [0.65, 0.58] // Product-level publishing (Product)
component Renewal Management [0.62, 0.55] // Product-level subscription management (Product)
component Notifications [0.70, 0.92] // REUSE: GOV.UK Notify (Commodity)
component Payments [0.68, 0.90] // REUSE: GOV.UK Pay (Commodity)

// Value Chain Layer 3: Supporting Services
component OCR Engine [0.58, 0.72] // BUY: Commercial OCR (Product)
component ML Classification Model [0.55, 0.35] // BUILD: Patent-specific ML (Custom)
component Semantic Search Engine [0.60, 0.42] // BUILD: Patent semantic search (Custom)
component Chemical Structure Search [0.52, 0.68] // BUY: Specialized product (Product)
component Document Storage [0.62, 0.88] // Commodity: S3-compatible (Commodity)
component Authentication [0.72, 0.68] // BUY: GOV.UK Verify or Auth0 (Product)
component Authorization (RBAC) [0.70, 0.62] // Product-level access control (Product)
component Audit Logging [0.65, 0.85] // Commodity: CloudWatch/ELK (Commodity)

// Value Chain Layer 4: Integration & Data
component WIPO Integration [0.50, 0.45] // BUILD: Custom ST.96 adapter (Custom)
component EPO Integration [0.52, 0.68] // BUY/BUILD: EPO OPS wrapper (Product)
component IP5 Data Exchange [0.48, 0.52] // BUILD: International exchange (Custom)
component Legacy PMS Integration [0.45, 0.35] // BUILD: Custom adapter (Custom-Genesis)
component Data Warehouse [0.58, 0.75] // Product: PostgreSQL analytics (Product)
component Event Streaming [0.60, 0.72] // Product: Kafka managed service (Product)

// Value Chain Layer 5: Platform & Infrastructure
component Application Runtime [0.55, 0.95] // Commodity: AWS EKS (Commodity)
component Database (PostgreSQL) [0.52, 0.92] // Commodity: AWS RDS (Commodity)
component Cache (Redis) [0.50, 0.90] // Commodity: AWS ElastiCache (Commodity)
component Search Index (OpenSearch) [0.55, 0.85] // Product-Commodity: AWS OpenSearch (Product)
component Object Storage [0.52, 0.95] // Commodity: AWS S3 (Commodity)
component CDN [0.50, 0.95] // Commodity: CloudFront (Commodity)
component Monitoring [0.58, 0.88] // Product: Prometheus/Grafana (Product-Commodity)
component IaC (Terraform) [0.55, 0.80] // Product: Infrastructure as Code (Product)

// GOV.UK Services (Reuse)
component GOV.UK Design System [0.72, 0.75] // REUSE: GDS frontend components (Product)
component GOV.UK Notify [0.70, 0.92] // REUSE: Government notification service (Commodity)
component GOV.UK Pay [0.68, 0.90] // REUSE: Government payment service (Commodity)
component GOV.UK Verify [0.72, 0.68] // REUSE: Identity assurance (Product)

// Evolution Markers
evolve Application Intake 0.55 label BUILD
evolve Patent Classification 0.42 label BUILD
evolve Prior Art Search 0.52 label BUILD
evolve Examination Workflow 0.45 label BUILD
evolve ML Classification Model 0.42 label BUILD
evolve Semantic Search Engine 0.52 label BUILD
evolve WIPO Integration 0.52 label BUILD
evolve Legacy PMS Integration 0.42 label BUILD

evolve OCR Engine 0.78 label BUY
evolve Chemical Structure Search 0.75 label BUY
evolve Authentication 0.75 label BUY
evolve EPO Integration 0.75 label BUY

// Dependencies
Patent Applicants->Patent Filing Service
Patent Examiners->Examiner Dashboard
Public Users->Public Portal
Public Users->Patent Search Service

Patent Filing Service->Application Intake
Patent Filing Service->Authentication
Patent Filing Service->GOV.UK Pay
Patent Filing Service->Notifications

Examiner Dashboard->Examination Workflow
Examiner Dashboard->Prior Art Search
Examiner Dashboard->Patent Classification
Examiner Dashboard->Authentication

Patent Search Service->Semantic Search Engine
Patent Search Service->Chemical Structure Search
Patent Search Service->Prior Art Search

Application Intake->OCR Engine
Application Intake->Document Storage
Application Intake->WIPO Integration
Application Intake->Event Streaming

Patent Classification->ML Classification Model
Patent Classification->WIPO Integration

Prior Art Search->Semantic Search Engine
Prior Art Search->Search Index (OpenSearch)
Prior Art Search->Chemical Structure Search

Examination Workflow->Authorization (RBAC)
Examination Workflow->Audit Logging
Examination Workflow->Event Streaming
Examination Workflow->EPO Integration

Publication Engine->Document Storage
Publication Engine->CDN
Publication Engine->WIPO Integration

Renewal Management->GOV.UK Pay
Renewal Management->GOV.UK Notify
Renewal Management->Database (PostgreSQL)

WIPO Integration->IP5 Data Exchange
WIPO Integration->Event Streaming
EPO Integration->Event Streaming

ML Classification Model->Application Runtime
ML Classification Model->Cache (Redis)
Semantic Search Engine->Search Index (OpenSearch)
Semantic Search Engine->Application Runtime

Document Storage->Object Storage
Event Streaming->Application Runtime
Search Index (OpenSearch)->Application Runtime
Data Warehouse->Database (PostgreSQL)

API Gateway->Authentication
API Gateway->Application Runtime

Monitoring->Application Runtime
Monitoring->Database (PostgreSQL)
IaC (Terraform)->Application Runtime

// Annotations
annotation 1 [[0.45, 0.25]] BUILD ZONE: Custom patent domain logic - no commercial alternatives
annotation 2 [[0.65, 0.90]] REUSE ZONE: GOV.UK services (£0.5M savings vs custom build)
annotation 3 [[0.58, 0.72]] BUY ZONE: G-Cloud 14 products (£2.1M procurement)
annotation 4 [[0.52, 0.95]] COMMODITY ZONE: AWS managed services (£0.9M cloud hosting)

note Legacy PMS Integration [Inertia: High - 40-year-old system, no APIs, batch-only]
note Patent Classification [Innovation: ML training on 10M patents, 95% accuracy target]
note WIPO Integration [Constraint: Must comply with ST.96 XML standard]
note GOV.UK Pay [Strategic: Reuse saves £200K vs custom payment processing]
```

### 1.2 Map Visualization Description

The map is organized into 5 vertical layers (value chain) from top to bottom:

1. **User Needs (0.95 visibility)**: Patent applicants, examiners, public users
2. **User-Facing Services (0.75-0.88 visibility)**: Filing service, search, examiner dashboard, public portal
3. **Business Capabilities (0.62-0.75 visibility)**: Application intake, classification, examination, publication, renewal
4. **Supporting Services (0.48-0.72 visibility)**: ML models, OCR, authentication, integrations (WIPO/EPO), data services
5. **Platform & Infrastructure (0.50-0.60 visibility)**: AWS services, databases, Kubernetes, monitoring

Horizontally (evolution axis):
- **Genesis (0.00-0.25)**: None - all components have some precedent
- **Custom (0.25-0.50)**: Patent classification (0.35), examination workflow (0.38), semantic search (0.42), WIPO integration (0.45), legacy integration (0.35) - **BUILD**
- **Product (0.50-0.75)**: OCR (0.72), chemical search (0.68), GOV.UK Verify (0.68), EPO integration (0.68), GOV.UK Design System (0.75) - **BUY**
- **Commodity (0.75-1.00)**: GOV.UK Pay (0.90), GOV.UK Notify (0.92), AWS services (0.90-0.95) - **REUSE/COMMODITY**

**Color Coding** (if rendered visually):
- 🟢 Green: REUSE (GOV.UK services) - £0.5M savings
- 🔵 Blue: BUY (G-Cloud 14) - £2.1M procurement
- 🟡 Yellow: BUILD (Custom) - £4.4M development
- ⚫ Grey: COMMODITY (AWS) - £0.9M hosting

---

## 2. Evolution Stages Reference

### Genesis (0.00-0.25): Uncharted

**Characteristics**: Uncertain, poorly understood, rapidly changing, rare, high failure rate, high cost

**Patent Management System Components**: None

**Rationale**: Even the most innovative components (ML patent classification, semantic search) have precedents in other domains (general ML classification, semantic search in other industries). No truly novel, uncharted technology required.

### Custom-Built (0.25-0.50): Differentiation

**Characteristics**: Unique to organization, competitive advantage, requires in-house expertise, rapidly evolving

**Patent Management System Components** (BUILD):

| Component | Evolution | Rationale | Build Justification |
|-----------|-----------|-----------|---------------------|
| **Patent Classification (ML)** | 0.35 | Patent-specific ML model trained on 10M CPC/IPC classifications; no commercial alternative with 95% accuracy on patent data | Competitive advantage for IPO examination speed; domain-specific training data |
| **Legacy PMS Integration** | 0.35 | 40-year-old bespoke system with no APIs; batch-only interfaces; undocumented proprietary formats | No vendor has expertise in legacy IPO systems; must build custom adapters |
| **Examination Workflow** | 0.38 | IPO-specific examination rules (UK Patent Act 1977, PCT requirements); unique business process | UK patent law nuances not supported by off-the-shelf workflow tools |
| **Semantic Prior Art Search** | 0.42 | Patent-specific semantic search trained on patent language, claims, technical descriptions | Commercial search engines lack patent domain fine-tuning; critical for examination quality |
| **WIPO Integration (ST.96)** | 0.45 | Custom adapter for WIPO ST.96 XML exchange; IPO-specific data mappings | WIPO ST.96 is evolving standard; requires ongoing customization for UK requirements |
| **Application Intake** | 0.42 | IPO-specific form validation, fee calculation, filing date rules | UK Patent Rules 2007 nuances require custom logic |
| **IP5 Data Exchange** | 0.52 | International patent data exchange with USPTO, EPO, JPO, KIPO, CNIPA | Near product stage but still custom integration for each office |

**BUILD Investment**: £4.4M (63% of development budget)

### Product (0.50-0.75): Rental

**Characteristics**: Off-the-shelf with customization, multiple vendors, defined features, declining cost, established best practices

**Patent Management System Components** (BUY via G-Cloud 14):

| Component | Evolution | Vendor Options (G-Cloud 14) | Buy Justification |
|-----------|-----------|------------------------------|-------------------|
| **OCR Engine** | 0.72 | ABBYY FineReader, Amazon Textract, Google Document AI | Mature technology; no competitive advantage from custom OCR; 98% accuracy requirement met by products |
| **GOV.UK Verify** | 0.68 | Government Digital Service (GDS) | Mandated identity assurance for government services; free to reuse |
| **Chemical Structure Search** | 0.68 | PerkinElmer ChemDraw, InfoChem ICM, NextMove LeadMine | Specialized chemistry IP; domain expertise outside IPO core competency |
| **EPO OPS Integration** | 0.68 | EPO provides REST API; commercial wrappers available (Darts-ip, Minesoft) | EPO OPS is product-stage API; wrapper libraries mature |
| **Authentication (MFA)** | 0.68 | Auth0 (GDS-approved), Okta, Azure AD B2C | Mature identity management; security risks too high for custom build |
| **GOV.UK Design System** | 0.75 | Government Digital Service (GDS) | Mandated for public services; WCAG 2.2 AA compliant; free to reuse |
| **Publication Engine** | 0.58 | Commercial document publishing (Docmosis, Windward, Aspose) | Standard document generation; no IPO-specific advantage |
| **Renewal Management** | 0.55 | Subscription management products (Chargebee, Recurly, Zuora) | Standard recurring billing; integrates with GOV.UK Pay |
| **Authorization (RBAC)** | 0.62 | Casbin, Open Policy Agent (OPA), AWS IAM | Mature access control patterns; open-source options |
| **Data Warehouse** | 0.75 | PostgreSQL (AWS RDS), Amazon Redshift | Mature analytics databases; no custom advantage |
| **Event Streaming** | 0.72 | Apache Kafka (AWS MSK, Confluent Cloud) | Industry-standard event streaming; mature ecosystem |

**BUY Investment**: £2.1M (30% of development budget)

### Commodity (+Utility) (0.75-1.00): Standardized

**Characteristics**: Widespread, well-understood, stable, pay-per-use, low cost, high automation

**Patent Management System Components** (REUSE/COMMODITY):

| Component | Evolution | Provider | Commodity Justification |
|-----------|-----------|----------|-------------------------|
| **GOV.UK Pay** | 0.90 | Government Digital Service (GDS) | Free to reuse; handles £3.5B government payments; PCI DSS compliant; no business case for custom payment processing (£200K savings) |
| **GOV.UK Notify** | 0.92 | Government Digital Service (GDS) | Free to reuse; 10M+ messages/day across government; email/SMS/letters; no business case for custom notification service (£150K savings) |
| **AWS EC2/EKS** | 0.95 | Amazon Web Services (AWS GovCloud UK) | Utility computing; TCoP Point 5 (Cloud First); no capital expenditure required |
| **PostgreSQL (RDS)** | 0.92 | AWS RDS (managed service) | Mature open-source RDBMS; fully managed; automatic backups/patches |
| **Redis (ElastiCache)** | 0.90 | AWS ElastiCache (managed service) | Standard caching; fully managed; no operational overhead |
| **S3 Object Storage** | 0.95 | AWS S3 (GovCloud UK) | Industry standard; 99.999999999% durability; UK data residency |
| **CloudFront CDN** | 0.95 | AWS CloudFront | Commodity content delivery; global edge network |
| **CloudWatch Monitoring** | 0.88 | AWS CloudWatch | Integrated AWS monitoring; commodity observability |
| **OpenSearch** | 0.85 | AWS OpenSearch Service | Managed Elasticsearch fork; mature full-text search |
| **Terraform IaC** | 0.80 | HashiCorp Terraform (open-source) | Industry-standard infrastructure as code; HCL widely adopted |

**COMMODITY Investment**: £0.9M (7% of budget for cloud hosting over 18 months)

---

## 3. Component Inventory

### 3.1 Complete Component Catalog

| Component ID | Name | Evolution | Visibility | Build/Buy/Reuse | Estimated Cost | Rationale |
|--------------|------|-----------|------------|-----------------|----------------|-----------|
| **UC-001** | Patent Applicants (User) | 0.85 | 0.95 | N/A | - | External users filing patents |
| **UC-002** | Patent Examiners (User) | 0.75 | 0.95 | N/A | - | IPO staff processing applications |
| **UC-003** | Public Users (User) | 0.65 | 0.95 | N/A | - | Citizens searching published patents |
| **C-001** | Patent Filing Service | 0.52 | 0.85 | BUILD (Custom) | £650K | IPO-specific filing rules (UK Patent Rules 2007) |
| **C-002** | Patent Search Service | 0.48 | 0.82 | BUILD (Custom) | £580K | Patent semantic search tuning required |
| **C-003** | Examiner Dashboard | 0.38 | 0.88 | BUILD (Custom) | £420K | IPO examination workflow UI |
| **C-004** | Public Portal | 0.68 | 0.80 | BUY (Product) | £280K | Standard web portal with GOV.UK Design System |
| **C-005** | API Gateway | 0.82 | 0.75 | BUY (Product) | £120K | AWS API Gateway (managed service) |
| **C-006** | Application Intake | 0.42 | 0.72 | BUILD (Custom) | £520K | IPO-specific validation, fee calculation |
| **C-007** | Patent Classification (ML) | 0.35 | 0.68 | BUILD (Custom) | £980K | ML model training on 10M patents (CPC/IPC) |
| **C-008** | Prior Art Search | 0.42 | 0.70 | BUILD (Custom) | £720K | Patent-specific semantic search engine |
| **C-009** | Examination Workflow | 0.38 | 0.75 | BUILD (Custom) | £620K | UK Patent Act 1977 compliance |
| **C-010** | Publication Engine | 0.58 | 0.65 | BUY (Product) | £180K | Commercial document publishing (Docmosis) |
| **C-011** | Renewal Management | 0.55 | 0.62 | BUY (Product) | £150K | Subscription management (Chargebee + GOV.UK Pay) |
| **C-012** | OCR Engine | 0.72 | 0.58 | BUY (Product) | £240K | ABBYY FineReader Server (G-Cloud 14) |
| **C-013** | ML Classification Model | 0.35 | 0.55 | BUILD (Custom) | £850K | Patent-specific ML training data and models |
| **C-014** | Semantic Search Engine | 0.42 | 0.60 | BUILD (Custom) | £680K | Patent language fine-tuning (BERT/GPT) |
| **C-015** | Chemical Structure Search | 0.68 | 0.52 | BUY (Product) | £320K | PerkinElmer ChemDraw (specialized chemistry IP) |
| **C-016** | Document Storage | 0.88 | 0.62 | COMMODITY | £120K | AWS S3 (utility storage) |
| **C-017** | Authentication | 0.68 | 0.72 | BUY (Product) | £180K | Auth0 (GDS-approved) or GOV.UK Verify (free) |
| **C-018** | Authorization (RBAC) | 0.62 | 0.70 | BUY (Product) | £90K | Open Policy Agent (OPA) - open-source |
| **C-019** | Audit Logging | 0.85 | 0.65 | COMMODITY | £80K | AWS CloudWatch Logs |
| **C-020** | WIPO Integration (ST.96) | 0.45 | 0.50 | BUILD (Custom) | £420K | Custom adapter for WIPO XML exchange |
| **C-021** | EPO Integration (OPS API) | 0.68 | 0.52 | BUY (Product) | £150K | EPO OPS REST API wrapper (Darts-ip) |
| **C-022** | IP5 Data Exchange | 0.52 | 0.48 | BUILD (Custom) | £380K | International office integrations (USPTO, JPO, KIPO, CNIPA) |
| **C-023** | Legacy PMS Integration | 0.35 | 0.45 | BUILD (Custom) | £620K | Custom adapter for 40-year-old system |
| **C-024** | Data Warehouse | 0.75 | 0.58 | BUY (Product) | £140K | PostgreSQL (AWS RDS analytics instance) |
| **C-025** | Event Streaming | 0.72 | 0.60 | BUY (Product) | £220K | Apache Kafka (AWS MSK managed service) |
| **C-026** | Application Runtime (EKS) | 0.95 | 0.55 | COMMODITY | £280K | AWS Elastic Kubernetes Service (18 months) |
| **C-027** | Database (PostgreSQL RDS) | 0.92 | 0.52 | COMMODITY | £180K | AWS RDS PostgreSQL (managed, 18 months) |
| **C-028** | Cache (Redis) | 0.90 | 0.50 | COMMODITY | £60K | AWS ElastiCache Redis (18 months) |
| **C-029** | Search Index (OpenSearch) | 0.85 | 0.55 | COMMODITY | £140K | AWS OpenSearch Service (18 months) |
| **C-030** | Object Storage (S3) | 0.95 | 0.52 | COMMODITY | £80K | AWS S3 (18 months, patent documents) |
| **C-031** | CDN (CloudFront) | 0.95 | 0.50 | COMMODITY | £40K | AWS CloudFront (public portal) |
| **C-032** | Monitoring | 0.88 | 0.58 | COMMODITY | £100K | Prometheus/Grafana + CloudWatch |
| **C-033** | IaC (Terraform) | 0.80 | 0.55 | COMMODITY | £60K | HashiCorp Terraform (open-source) |
| **C-034** | GOV.UK Design System | 0.75 | 0.72 | REUSE (Free) | £0 | GDS frontend components (WCAG 2.2 AA) |
| **C-035** | GOV.UK Notify | 0.92 | 0.70 | REUSE (Free) | £0 | GDS notification service (saves £150K) |
| **C-036** | GOV.UK Pay | 0.90 | 0.68 | REUSE (Free) | £0 | GDS payment service (saves £200K) |
| **C-037** | GOV.UK Verify | 0.68 | 0.72 | REUSE (Free) | £0 | GDS identity assurance (optional, if used) |

**Total Estimated Cost**: £9.68M (includes contingency; £7M baseline budget + £2.68M contingency/optimism bias)

### 3.2 Cost Breakdown by Strategy

| Strategy | Components | Total Cost | % of Budget | Savings vs Custom Build All |
|----------|------------|------------|-------------|------------------------------|
| **BUILD (Custom)** | 12 components | £6.44M | 66% | - |
| **BUY (G-Cloud 14)** | 11 components | £2.06M | 21% | £1.2M savings (if built custom) |
| **REUSE (GOV.UK)** | 4 components | £0K | 0% | £350K savings (vs custom) |
| **COMMODITY (AWS)** | 10 components | £1.12M | 12% | £2.8M savings (vs on-premise) |
| **TOTAL** | 37 components | £9.62M | 100% | £4.35M total savings vs all-custom build |

**Budget Allocation** (£7M RFP budget):
- Development (BUILD + BUY): £6.1M (87%)
- Infrastructure (COMMODITY): £0.9M (13%)
- GOV.UK Services (REUSE): £0M (free, £0.35M opportunity cost avoided)

**Optimism Bias Adjustment**: HM Treasury Green Book recommends 40% optimism bias for IT projects. £7M baseline budget accommodates contingency within £9.62M upper bound.

---

## 4. Build vs Buy Analysis

### 4.1 Decision Framework

**Decision Criteria** (aligned with Architecture Principles):

| Criterion | Weight | BUILD Indicator | BUY Indicator |
|-----------|--------|-----------------|---------------|
| **Evolution Stage** | 30% | Genesis/Custom (0.0-0.5) | Product/Commodity (0.5-1.0) |
| **Competitive Advantage** | 25% | Unique to IPO patent examination | Common across industries |
| **Domain Specificity** | 20% | Patent/UK law specific | Generic business function |
| **Vendor Availability** | 15% | No suitable G-Cloud vendors | Multiple G-Cloud options |
| **Total Cost of Ownership** | 10% | Custom build cheaper long-term | Product cheaper (licensing < dev) |

**Scoring**: Each component scored 0-100 on each criterion. Weighted score >60 = BUILD, <40 = BUY, 40-60 = BUY with customization.

### 4.2 BUILD Decisions (Custom Development)

| Component | Evolution | BUILD Score | Key Justification | Risks if BOUGHT |
|-----------|-----------|-------------|-------------------|-----------------|
| **Patent Classification (ML)** | 0.35 | 88 | Patent-specific training data (10M CPC/IPC classifications); 95% accuracy target unmet by commercial ML; competitive advantage for IPO examination speed | Commercial ML tools lack patent domain accuracy; vendor lock-in to inferior models; ongoing licensing costs (£200K/year) |
| **Legacy PMS Integration** | 0.35 | 92 | 40-year-old bespoke IPO system; no APIs; proprietary batch formats; no vendor has IPO legacy expertise | No vendors can integrate; critical path blocker if outsourced; IPO retains legacy system knowledge |
| **Examination Workflow** | 0.38 | 85 | UK Patent Act 1977 compliance; IPO-specific business rules; examiner productivity critical to BR-001 (18→12 months) | Off-the-shelf workflow tools don't support UK patent law nuances; customization costs exceed custom build |
| **Semantic Prior Art Search** | 0.42 | 82 | Patent language fine-tuning (claims, technical descriptions); semantic similarity for patent documents; quality differentiator for IPO | Commercial search lacks patent semantic accuracy; examiner effectiveness depends on search quality; vendor lock-in risk |
| **WIPO Integration (ST.96)** | 0.45 | 78 | WIPO ST.96 XML standard evolving; IPO-specific mappings for UK patent data; international obligations (PCT) | WIPO ST.96 wrappers immature; IPO must control international data exchange for sovereignty |
| **Application Intake** | 0.42 | 80 | UK Patent Rules 2007 validation; IPO fee structure; filing date determination (critical legal function) | Commercial intake forms don't support UK Patent Rules; legal risk if validation errors |
| **IP5 Data Exchange** | 0.52 | 72 | Bilateral integrations with 5 international patent offices (USPTO, EPO, JPO, KIPO, CNIPA); each office has unique APIs/formats | No single vendor integrates all IP5 offices; IPO must own international relationships |
| **Examiner Dashboard** | 0.38 | 83 | IPO examiner workflows (search, classification, objections, correspondence); GDS Service Standard UI/UX for internal users | Off-the-shelf dashboards don't match IPO examination process; examiner productivity critical (BR-001) |
| **Patent Filing Service** | 0.52 | 75 | IPO-specific filing rules (UK Patent Rules 2007, PCT national phase); integration with legacy PMS; GOV.UK Design System styling | Near product stage but UK-specific validation requires custom logic; cost effective to build on GOV.UK patterns |
| **Patent Search Service** | 0.48 | 78 | Public search interface for 3M published patents; semantic search integration; performance critical for public satisfaction (BR-004) | Commercial patent search UIs expensive (£300K+ licensing); IPO controls user experience |
| **Prior Art Search** | 0.42 | 80 | Patent examiner search combining semantic, keyword, classification, chemical structure; ML ranking of results by relevance | Commercial prior art tools (Orbit, PatBase) expensive (£500K/year); IPO retains search IP |
| **ML Classification Model** | 0.35 | 90 | Training on 10M IPO historical classifications (CPC/IPC); transfer learning from USPTO/EPO; domain-specific accuracy | Commercial ML platforms lack patent training data access; model IP valuable to IPO |

**Total BUILD Cost**: £6.44M (12 components)

**BUILD Strategy Risks**:
- **Delivery Risk**: Custom components on critical path; 18-month timeline tight for ML training + integration
- **Mitigation**: Agile sprints with MVP; ML model training in parallel with infrastructure setup; dedicated ML team (3 FTE)

### 4.3 BUY Decisions (G-Cloud 14 Procurement)

| Component | Evolution | BUY Score | G-Cloud Vendor Options | Cost Justification | Risks if BUILT |
|-----------|-----------|-----------|------------------------|--------------------|--------------------|
| **OCR Engine** | 0.72 | 22 | ABBYY FineReader (£180K), Amazon Textract (£60K) | 98% accuracy requirement met by products; no competitive advantage from custom OCR; saves £400K+ vs building | Reinventing commodity; OCR R&D outside IPO expertise; 2+ year development time |
| **Chemical Structure Search** | 0.68 | 18 | PerkinElmer ChemDraw (£320K), InfoChem ICM | Specialized chemistry IP; pharmaceutical/chemistry patents require structure search; domain expertise outside IPO | Chemistry algorithms complex; patent pending structure search methods; 3+ year development |
| **Authentication (MFA)** | 0.68 | 15 | Auth0 (£180K), Okta, GOV.UK Verify (£0) | Security risks too high for custom build; Cyber Essentials Plus requires MFA; mature product ecosystem | Security vulnerabilities in custom auth; penetration testing failures; BPSS clearance for developers |
| **EPO OPS Integration** | 0.68 | 28 | Darts-ip (£150K), Minesoft | EPO provides REST API; commercial wrappers mature; vendor maintains EPO API changes | EPO API changes require ongoing maintenance; wrapper libraries save £200K development |
| **Publication Engine** | 0.58 | 32 | Docmosis (£120K), Windward, Aspose | Standard document generation (PDF, HTML); patent publication templates; WIPO ST.36/ST.96 XML output | Document rendering complex (formulas, chemical structures); template engines mature |
| **Renewal Management** | 0.55 | 35 | Chargebee (£90K), Recurly + GOV.UK Pay | Recurring billing (annual patent renewals); integrates with GOV.UK Pay; PCI DSS compliant | Subscription management has legal/financial risk; payment reconciliation complex |
| **Authorization (RBAC)** | 0.62 | 30 | Open Policy Agent (£0 OSS), Casbin | Role-based access control patterns mature; open-source options; policy-as-code (Rego language) | RBAC logic complex (examiner roles, manager approval, BPSS clearance levels); security risk if bugs |
| **Data Warehouse** | 0.75 | 12 | AWS RDS PostgreSQL (£140K) | Mature RDBMS; analytics queries; patent statistics for IPO management reporting | Database optimization complex; PostgreSQL ecosystem mature (no competitive advantage from fork) |
| **Event Streaming** | 0.72 | 20 | AWS MSK (£220K), Confluent Cloud | Industry-standard event streaming; microservices integration; patent application state changes | Kafka operational complexity; managed service saves £300K+ ops cost; no competitive advantage |
| **API Gateway** | 0.82 | 10 | AWS API Gateway (£120K) | Commodity API management; rate limiting, authentication, logging; integrates with AWS services | API gateway is solved problem; reinventing wheel; AWS integration simpler |
| **Public Portal** | 0.68 | 25 | Custom build on GOV.UK Design System (£280K) | Borderline BUY/BUILD; GOV.UK Design System provides components; custom assembly for patent search UI | Could use commercial CMS (Drupal) but GOV.UK patterns require custom integration anyway; cost-neutral |

**Total BUY Cost**: £2.06M (11 components via G-Cloud 14 + OSS)

**BUY Strategy Risks**:
- **Vendor Lock-In**: ABBYY FineReader, ChemDraw have proprietary formats; mitigated by open API wrappers
- **License Escalation**: Usage-based pricing (OCR pages, API calls); mitigated by volume negotiation in G-Cloud call-off
- **Vendor Failure**: G-Cloud vendor goes out of business; mitigated by escrow agreements for critical components (OCR, chemical search)

### 4.4 REUSE Decisions (GOV.UK Services)

| Component | Evolution | REUSE Rationale | Savings vs BUILD | Mandatory? |
|-----------|-----------|-----------------|-------------------|------------|
| **GOV.UK Pay** | 0.90 | Free government payment service; handles £3.5B/year across government; PCI DSS compliant; patent renewal fees (£50-£600/year) | £200K custom payment gateway + £80K/year PCI compliance | Yes (TCoP Point 3: Reuse) |
| **GOV.UK Notify** | 0.92 | Free notification service; 10M+ messages/day; email/SMS; patent filing confirmations, examination updates, renewal reminders | £150K custom notification service + £40K/year email/SMS costs | Yes (TCoP Point 3: Reuse) |
| **GOV.UK Design System** | 0.75 | Mandated frontend components; WCAG 2.2 AA compliant; responsive design; GDS Service Assessment requirement | £120K custom design system (but would fail GDS assessment) | Yes (GDS Service Standard Point 13) |
| **GOV.UK Verify** | 0.68 | Identity assurance for citizens; optional (can use Auth0 instead); declining usage (being replaced by GOV.UK One Login 2024) | £100K custom identity verification | No (but recommended if available) |

**Total REUSE Savings**: £570K capital + £120K/year operational vs custom build

**REUSE Strategy Risks**:
- **GOV.UK Service Downtime**: Notify/Pay outages impact IPO services; mitigated by retry logic and status page monitoring
- **Feature Limitations**: GOV.UK services may not support all IPO requirements (e.g., Pay doesn't support partial refunds); mitigated by G-Cloud fallback (Stripe/PayPal)

### 4.5 COMMODITY Decisions (AWS Managed Services)

| Component | Evolution | COMMODITY Rationale | Savings vs On-Premise | Migration Risk |
|-----------|-----------|---------------------|-----------------------|----------------|
| **AWS EKS (Kubernetes)** | 0.95 | TCoP Point 5 (Cloud First); managed Kubernetes; auto-scaling; IPO has no data center | £500K capital (servers) + £200K/year ops | Low (IPO already AWS) |
| **PostgreSQL (RDS)** | 0.92 | Managed database; automatic backups; multi-AZ HA; patent data (3M records) | £120K capital (DB servers) + £80K/year DBA | Low (PostgreSQL standard) |
| **Redis (ElastiCache)** | 0.90 | Managed caching; session storage; examination workflow state | £40K capital + £30K/year ops | Low (Redis standard) |
| **OpenSearch** | 0.85 | Managed search; full-text patent search; 3M published patents indexed | £80K capital (search cluster) + £50K/year ops | Medium (Elasticsearch fork; API compatible) |
| **S3 Object Storage** | 0.95 | Patent document storage (PDFs, images); 99.999999999% durability; UK data residency | £200K capital (SAN storage) + £100K/year ops | Low (standard S3 API) |
| **CloudFront CDN** | 0.95 | Public portal content delivery; global edge network; DDoS protection | £60K capital (CDN servers) + £40K/year bandwidth | Low (standard CDN) |
| **CloudWatch** | 0.88 | Integrated AWS monitoring; logs, metrics, traces; alerts for SLA breaches | £50K capital (monitoring tools) + £40K/year ops | Low (CloudWatch native) |
| **Terraform IaC** | 0.80 | Infrastructure as code; version-controlled infrastructure; AWS provider mature | £80K custom provisioning scripts + £60K/year ops | Low (HCL standard) |

**Total COMMODITY Savings**: £1.13M capital + £600K/year operational vs on-premise over 5 years = £4.13M NPV

**COMMODITY Strategy Risks**:
- **AWS Vendor Lock-In**: Difficult to migrate from AWS to Azure/GCP; mitigated by Terraform (multi-cloud IaC) and Kubernetes (container portability)
- **AWS UK Region Outages**: eu-west-2 (London) regional failures; mitigated by multi-AZ architecture and RTO/RPO alignment (4-hour RTO acceptable per NFR-001)

---

## 5. Inertia and Barriers to Movement

### 5.1 Inertia Analysis

**Inertia** = Resistance to moving a component along the evolution axis (e.g., modernizing legacy systems, adopting new technology)

| Component | Current Evolution | Desired Evolution | Inertia Level | Inertia Source | Impact on Project |
|-----------|-------------------|-------------------|---------------|----------------|-------------------|
| **Legacy PMS** | 0.35 | 0.50 (modernize) | **Very High** | 40-year-old system; no APIs; batch-only; tribal knowledge; fear of data loss; examiner workflow dependency | **CRITICAL PATH RISK**: Legacy integration blocker (C-023, £620K); 6-month integration window; requires dedicated legacy team (2 FTE) |
| **Examiner Workflows** | 0.38 | 0.55 (standardize) | **High** | Examiner resistance to workflow changes; "we've always done it this way"; manual process comfort; training burden | **CHANGE MANAGEMENT**: 200 examiners need training; phased rollout required (alpha/beta per GDS); 3-month parallel running |
| **On-Premise Infrastructure** | 0.60 | 0.95 (cloud) | **Medium** | Existing data center; capital sunk cost; IT operations team skillset (on-prem); OFFICIAL-SENSITIVE data sovereignty concerns | **PROCUREMENT DELAY**: Cloud security accreditation (2 months); BPSS clearance for AWS admins; data migration (3 months) |
| **Manual Patent Classification** | 0.30 | 0.60 (ML-assisted) | **High** | Examiner expertise ("ML can't understand patents"); CPC/IPC classification complexity; quality concerns; job security fears | **ADOPTION RISK**: Examiners may ignore ML suggestions; requires 95% accuracy to gain trust; 6-month pilot needed |
| **Paper-Based Processes** | 0.25 | 0.70 (digital) | **Medium** | 20% of applications still paper; scanning backlog (50K documents); legal signatures; original documents required by law | **SCOPE CREEP**: Paper digitization not in scope but impacts intake (C-006); OCR quality issues for handwritten notes |
| **WIPO ST.96 Adoption** | 0.45 | 0.65 (product) | **High** | WIPO ST.96 XML replacing ST.36; international patent offices at different adoption stages; UK must align with EPO timeline | **EXTERNAL DEPENDENCY**: EPO mandates ST.96 by 2026; IPO must comply; integration testing with WIPO delayed by pandemic |
| **Procurement Bureaucracy** | 0.50 | 0.80 (streamlined) | **High** | G-Cloud 14 call-off process; Central Digital and Data Office (CDDO) approval gates; HMT Green Book business case; 6-month procurement cycle | **TIMELINE RISK**: 18-month delivery assumes vendor onboarded by Month 2; procurement delays push delivery to Month 20+ |

**Total Inertia Score**: 42/70 (60%) = **HIGH INERTIA ENVIRONMENT**

**Inertia Mitigation Strategies**:
1. **Legacy PMS Integration**: Dedicate 2 FTE legacy specialists; 6-month parallel running; phased data migration (non-critical data first)
2. **Examiner Change Management**: GDS-style alpha/beta with 10 examiners; 3-month private beta with 50 examiners; training program (2 days per examiner)
3. **Cloud Security Accreditation**: Start ITHC (penetration testing) in Month 3; AWS GovCloud UK pre-accredited for OFFICIAL; expedite BPSS clearance
4. **ML Classification Trust**: 95% accuracy target (exceeds examiner average 92%); explainable AI (show similar patents); 6-month pilot with opt-out
5. **WIPO ST.96 Migration**: Implement ST.96 in parallel with ST.36; dual XML export; EPO integration testing in Month 9 (before EPO mandate)
6. **Procurement Acceleration**: Use G-Cloud 14 Direct Award (no competition needed if <£100K per component); aggregate procurement for oversight

### 5.2 Barriers to Evolution

| Barrier Type | Description | Affected Components | Mitigation |
|--------------|-------------|---------------------|------------|
| **Regulatory** | UK Patent Rules 2007 mandate paper filing option; legal signatures required for some documents | C-006 (Application Intake), C-001 (Patent Filing Service) | Hybrid digital/paper process; DocuSign for legal signatures (GDS-approved) |
| **Skills Gap** | IPO IT team lacks ML/AI expertise; limited Kubernetes experience; legacy COBOL knowledge concentrated in 3 staff near retirement | C-007 (ML Classification), C-026 (EKS), C-023 (Legacy Integration) | Training program (AWS certification); hire ML engineer (1 FTE); knowledge transfer from legacy team (12 months) |
| **Budget Constraints** | £7M budget fixed; HMT requires business case approval for >10% variance; contingency only 15% (£1.05M) | All components | Prioritize MVP features; descope "nice-to-have" (e.g., mobile app); reuse GOV.UK services to save £570K |
| **Security Clearance** | All personnel need BPSS minimum; OFFICIAL-SENSITIVE access needs SC clearance; vendor staff clearance takes 3-6 months | All components | Vendor must commit to clearance in proposal (MQ-20, MQ-21); start clearance process in Month 1; use pre-cleared staff |
| **International Dependencies** | WIPO ST.96 timeline; EPO OPS API changes; IP5 offices vary in API maturity | C-020 (WIPO Integration), C-021 (EPO Integration), C-022 (IP5 Data Exchange) | Bilateral agreements with each office; fallback to email/FTP if APIs unavailable; WIPO liaison officer |
| **GDS Service Assessment** | Public beta requires GDS Service Assessment (16 criteria); failure blocks go-live | C-001 (Filing Service), C-004 (Public Portal), C-002 (Search Service) | GDS assessment in Month 15; address feedback in Month 16-17; use GOV.UK Design System to de-risk |
| **Data Migration** | 3M published patents; 500K unpublished applications; 40 years of examination history; data quality issues (duplicates, encoding errors) | C-023 (Legacy Integration), C-027 (Database), C-016 (Document Storage) | 6-month data migration; cleanse data in legacy system first; phased cutover (published patents first) |

---

## 6. Movement Predictions (3-Year Horizon)

### 6.1 Components Likely to Evolve (0.1+ movement in 3 years)

| Component | Current (2025) | Predicted (2028) | Movement | Evolution Driver | Strategic Implication |
|-----------|----------------|------------------|----------|------------------|------------------------|
| **ML Patent Classification** | 0.35 | 0.60 | +0.25 | USPTO/EPO/IPO share ML models; WIPO standardizes ML classification datasets; commercial vendors (Clarivate, PatSnap) productize patent ML | **RISK**: IPO custom ML (£980K investment) commoditized by vendors; **MITIGATION**: IPO trains on UK-specific data; maintains competitive advantage for 3 years; plan to BUY commercial ML by 2028 |
| **Semantic Prior Art Search** | 0.42 | 0.65 | +0.23 | Google Patents, Microsoft Academic, Semantic Scholar apply transformer models (BERT/GPT) to patent search; patent offices share search APIs | **RISK**: Custom semantic search (£680K) becomes product; **MITIGATION**: IPO builds MVP; migrate to commercial by 2028; saves £400K+ ongoing maintenance |
| **WIPO ST.96 Integration** | 0.45 | 0.72 | +0.27 | WIPO mandates ST.96 globally by 2026; all IP5 offices adopt; commercial vendors (CPA Global) provide ST.96 adapters | **OPPORTUNITY**: IPO custom adapter (£420K) becomes product; license to other patent offices (revenue); migrate to commercial adapter by 2028 |
| **GOV.UK Verify → GOV.UK One Login** | 0.68 | 0.85 | +0.17 | GDS launches GOV.UK One Login (2024-2025); replaces GOV.UK Verify; single sign-on for all government services | **ACTION REQUIRED**: IPO must migrate from GOV.UK Verify to One Login by 2026; factor into roadmap (£50K migration cost) |
| **Chemical Structure Search** | 0.68 | 0.80 | +0.12 | PerkinElmer, InfoChem mature; open-source alternatives (RDKit, CDK) improve; NIH PubChem provides free APIs | **OPPORTUNITY**: Switch from commercial (£320K) to open-source by 2028; saves £100K+/year licensing |
| **EPO OPS Integration** | 0.68 | 0.85 | +0.17 | EPO improves OPS API; adds bulk data access, webhooks; GraphQL interface; commercial wrappers (Darts-ip) mature | **LOW RISK**: Commercial wrapper (£150K) remains cost-effective; EPO API stability improves; no action needed |
| **Kubernetes (EKS)** | 0.95 | 0.98 | +0.03 | Kubernetes fully commoditized; serverless (AWS Lambda, Fargate) replaces containers for some workloads | **FUTURE OPTIMIZATION**: Consider serverless for stateless APIs by 2028; reduces infrastructure cost 20% (£50K/year savings) |

### 6.2 Components Unlikely to Evolve (Stable <0.05 movement)

| Component | Current (2025) | Predicted (2028) | Movement | Stability Reason | Strategic Implication |
|-----------|----------------|------------------|----------|------------------|------------------------|
| **Examination Workflow** | 0.38 | 0.42 | +0.04 | UK patent law stable; IPO-specific business rules; no commercial vendors target patent examination workflows | **LONG-TERM INVESTMENT**: IPO owns examination workflow IP indefinitely; justify £620K custom build; no commoditization risk |
| **Legacy PMS Integration** | 0.35 | 0.30 | -0.05 | Legacy PMS being decommissioned by 2027; integration becomes obsolete; no evolution driver | **TECHNICAL DEBT**: Legacy adapter (£620K) has 3-year lifespan; amortize cost over short period; plan decommissioning |
| **Application Intake** | 0.42 | 0.46 | +0.04 | UK Patent Rules 2007 stable; IPO-specific fee structure; filing date rules unique | **STABLE INVESTMENT**: Custom intake (£520K) justified long-term; no commercial alternatives; low obsolescence risk |
| **AWS S3** | 0.95 | 0.96 | +0.01 | Object storage fully commoditized; S3 de facto standard; minimal innovation left | **NO ACTION**: Continue using S3; lowest cost utility storage; no alternative evaluation needed |
| **PostgreSQL** | 0.92 | 0.93 | +0.01 | RDBMS mature; PostgreSQL dominant open-source DB; AWS RDS fully managed | **NO ACTION**: PostgreSQL safe long-term choice; no migration risk; continue with RDS |

### 6.3 Disruptive Threats (New Components Emerging)

| Emerging Component | Current Adoption | Threat to Existing Component | Timeframe | Strategic Response |
|--------------------|------------------|------------------------------|-----------|---------------------|
| **Large Language Models (GPT-4, Claude)** | 0.35 (Custom) | Threatens ML Classification (0.35), Semantic Search (0.42); LLMs can classify patents, summarize claims, generate prior art search queries | **2-3 years** | **MONITOR**: Evaluate GPT-4 for patent classification in 2026; pilot LLM-generated search queries; potential to replace custom ML (£980K) with API calls (£50K/year) |
| **Blockchain for Patent Provenance** | 0.20 (Genesis) | Threatens centralized patent databases; distributed ledger for patent applications, timestamps, international filing dates | **5+ years** | **WATCH**: WIPO exploring blockchain; not mature enough for 2025 implementation; revisit in 2028 |
| **Quantum Computing for Prior Art Search** | 0.10 (Genesis) | Threatens classical semantic search (0.42); quantum algorithms for combinatorial patent search across 100M+ patents | **10+ years** | **IGNORE**: Too early; quantum hardware not accessible; focus on classical ML/transformers |
| **GOV.UK One Login** | 0.60 (Product) | Replaces GOV.UK Verify (0.68); mandatory single sign-on for all government services by 2026 | **1-2 years** | **ACTION REQUIRED**: Plan migration to GOV.UK One Login in roadmap (2026-2027); £50K integration cost; GDS mandates adoption |
| **No-Code/Low-Code Platforms** | 0.55 (Product) | Threatens custom workflow development (0.38); OutSystems, Mendix, Microsoft Power Apps enable citizen developers | **3-5 years** | **EVALUATE**: Consider low-code for future enhancements (2027+); not suitable for 2025 initial build (complexity, security) |

---

## 7. UK Government Context (GDS & TCoP Alignment)

### 7.1 Technology Code of Practice (TCoP) Mapping

**TCoP Compliance**: 81% (105/130 points) - See TCoP Assessment Document

| TCoP Point | Wardley Map Strategic Alignment | Components Supporting TCoP | Evidence |
|------------|----------------------------------|----------------------------|----------|
| **1. Define user needs** | User needs at top of map (0.95 visibility): Patent Applicants, Examiners, Public Users | C-001 (Filing Service), C-003 (Examiner Dashboard), C-004 (Public Portal) | User research with 50 examiners, 100 applicants; GDS Service Standard assessment planned |
| **2. Make things accessible** | WCAG 2.2 AA mandatory; GOV.UK Design System (0.75) reused | C-034 (GOV.UK Design System), C-004 (Public Portal), C-001 (Filing Service) | Accessibility audits (DAC, AbilityNet); IAAP-certified accessibility specialists on team (MQ-12) |
| **3. Be open and use open standards** | WIPO ST.96 XML (0.45), EPO OPS REST (0.68), OpenAPI 3.0 for APIs | C-020 (WIPO Integration), C-021 (EPO Integration), C-005 (API Gateway) | WIPO ST.96 compliance; open API documentation; Swagger/OpenAPI specs |
| **4. Make use of open source** | PostgreSQL (0.92), Redis (0.90), Kafka (0.72), Terraform (0.80), OPA (0.62) | C-027 (PostgreSQL), C-028 (Redis), C-025 (Kafka), C-033 (Terraform), C-018 (OPA) | Open-source components >40% of stack; contribute back to OSS communities |
| **5. Use cloud first** | AWS GovCloud UK (0.95); 100% cloud deployment; no on-premise infrastructure | C-026 (EKS), C-027 (RDS), C-028 (ElastiCache), C-029 (OpenSearch), C-030 (S3) | TCoP Point 5 full compliance; £4.13M NPV savings vs on-premise |
| **6. Make things secure** | OFFICIAL-SENSITIVE controls; Cyber Essentials Plus (MQ-5); ISO 27001 (MQ-6); STRIDE threat model | C-017 (Authentication), C-018 (Authorization), C-019 (Audit Logging), ITHC penetration testing | Security architecture reviewed by CISO; BPSS/SC clearance for personnel (MQ-20, MQ-21) |
| **7. Make privacy integral** | GDPR compliance; Data Protection Officer oversight; privacy by design; UK data residency | C-027 (Database UK region), C-030 (S3 UK region), Data Protection Impact Assessment (DPIA) | DPIA completed; DPO approval (Laura Davies); AWS UK region enforced by IaC |
| **8. Share, reuse and collaborate** | GOV.UK Pay (0.90), Notify (0.92), Design System (0.75), Verify (0.68) reused; £570K savings | C-034 (Design System), C-035 (Notify), C-036 (Pay), C-037 (Verify) | **KEY STRATEGIC DECISION**: Reuse GOV.UK services rather than build custom; TCoP Point 8 compliance drives £570K savings |
| **9. Integrate and adapt technology** | API-first architecture; OpenAPI 3.0; WIPO ST.96 XML; EPO OPS REST; microservices on Kubernetes | C-005 (API Gateway), C-020 (WIPO), C-021 (EPO), C-026 (EKS) | RESTful APIs for all services; event-driven architecture (Kafka); loosely coupled microservices |
| **10. Make better use of data** | Open data portal (3M published patents); patent analytics; ML training data (10M classifications) | C-004 (Public Portal), C-024 (Data Warehouse), C-007 (ML Classification) | Open data API (non-OFFICIAL patents); analytics dashboard for IPO management; ML improves with data |
| **11. Define your purchasing strategy** | **THIS WARDLEY MAP**: Build vs Buy analysis; G-Cloud 14 procurement; 62% buy/reuse, 38% build | All 37 components mapped by evolution stage | Build (38%, £6.44M), Buy (21%, £2.06M), Reuse (0%, £0), Commodity (12%, £1.12M) |
| **12. Meet the Digital Service Standard** | GDS Service Assessment planned (Month 15); public beta; alpha with 10 users; GOV.UK Design System | C-001 (Filing Service), C-002 (Search Service), C-004 (Public Portal) | Private alpha (Month 6), private beta (Month 12), public beta (Month 15), GDS assessment, live (Month 18) |
| **13. Use common technology platforms** | GOV.UK platforms (Pay, Notify, Design System, Verify/One Login); GDS standards; government cloud (AWS GovCloud) | C-034 (Design System), C-035 (Notify), C-036 (Pay), C-037 (Verify), C-026 (AWS) | **KEY STRATEGIC DECISION**: Leverage GDS platforms to avoid reinventing wheel; aligns with TCoP Point 13 |

**Wardley Map Strategic Insight**: TCoP Point 8 (Reuse) and Point 11 (Purchasing Strategy) are directly addressed by this Wardley Map. By classifying components by evolution stage, IPO identifies:
- **What to reuse** (GOV.UK services at 0.85+ evolution)
- **What to buy** (Products at 0.50-0.75 via G-Cloud 14)
- **What to build** (Custom at 0.25-0.50 for competitive advantage)

This strategic alignment delivers **£4.92M total savings** (£570K reuse + £1.2M buy vs build + £3.15M commodity cloud) versus an all-custom build approach.

### 7.2 GDS Service Standard Mapping

| GDS Point | Wardley Map Component | Evolution Stage | Strategic Decision |
|-----------|----------------------|-----------------|-------------------|
| **1. Understand users and their needs** | Patent Applicants (0.85), Patent Examiners (0.75), Public Users (0.65) | User needs (high visibility) | User research informs Filing Service (0.52), Examiner Dashboard (0.38), Public Portal (0.68) |
| **2. Solve a whole problem for users** | End-to-end patent journey: Filing (0.52) → Classification (0.35) → Examination (0.38) → Publication (0.58) → Renewal (0.55) | Full value chain | Wardley Map shows complete user journey; no gaps in service delivery |
| **3. Provide a joined up experience** | API Gateway (0.82) integrates all services; GOV.UK Design System (0.75) for consistent UI | Product-stage integration | Microservices with unified API; consistent GOV.UK styling; single sign-on (GOV.UK Verify/One Login) |
| **4. Make the service simple to use** | GOV.UK Design System (0.75); Public Portal (0.68); WCAG 2.2 AA accessibility | Product-stage UI | Reuse mature GOV.UK patterns; avoid custom UI frameworks; accessibility built-in |
| **5. Make sure everyone can use the service** | WCAG 2.2 AA compliance; manual accessibility testing; IAAP-certified specialists | Accessibility mandatory | C-034 (Design System) ensures Level AA; C-004 (Public Portal) audited by DAC |
| **6. Have a multidisciplinary team** | Evaluation team: Enterprise Architect, CISO, Product Owner, Accessibility Specialist, Domain Architect | Team composition | Team scoring in evaluation criteria (15 points); 10 key roles defined (MQ-27) |
| **7. Use agile ways of working** | Agile delivery methodology scored (10 points); sprints, retrospectives, continuous deployment | Delivery methodology | DevSecOps pipeline; CI/CD with GitHub Actions/GitLab; 2-week sprints |
| **8. Iterate and improve frequently** | Alpha (Month 6), Private Beta (Month 12), Public Beta (Month 15), Live (Month 18) | GDS phases | Wardley Map will be updated after each phase; components will evolve |
| **9. Create a secure service** | Authentication (0.68), Authorization (0.62), Audit Logging (0.85), STRIDE threat model | Security by design | OFFICIAL-SENSITIVE controls; Cyber Essentials Plus; ITHC penetration testing |
| **10. Define success metrics** | BR-001 (18→12 months), BR-002 (£2M savings), BR-003 (95% satisfaction), BR-004 (99.5% uptime) | Business requirements | Metrics tracked in monitoring (C-032); dashboards for SRO/Product Owner |
| **11. Choose the right tools and technology** | **THIS WARDLEY MAP**: Evolution-based tool selection; buy products, reuse GOV.UK services, build custom only when necessary | Strategic procurement | Build (38%), Buy (21%), Reuse (41% by component count) balances innovation and reuse |
| **12. Make new source code open** | Open-source by default; IPO GitHub organization; MIT/Apache 2.0 licenses | Open source | ML classification model (0.35), semantic search (0.42), WIPO adapters (0.45) published on GitHub |
| **13. Use common platforms** | GOV.UK Pay (0.90), Notify (0.92), Design System (0.75), Verify/One Login (0.68) | GDS platforms | **KEY STRATEGIC DECISION**: Reuse all available GDS platforms; only build when GDS has no solution |
| **14. Operate a reliable service** | Monitoring (0.88), Audit Logging (0.85), Multi-AZ AWS (0.95), RTO 4h, RPO 1h | Reliability engineering | SRE practices; 99.5% uptime SLA (NFR-001); incident response playbooks |
| **15. Support a culture of learning** | Alpha/beta feedback loops; retrospectives; blameless post-mortems | Continuous improvement | Lessons learned after each GDS phase; Wardley Map updated with new insights |
| **16. Make your service supportable** | Documentation, runbooks, training materials for IPO operations team | Operational readiness | Handover to IPO Ops (Month 18); 2-day training for 10 staff; on-call rotation |
| **17. Explain what data is collected** | Privacy policy, DPIA, Data Protection Officer oversight, GDPR compliance | Privacy by design | Public-facing privacy notice; data retention policy (7 years for applications) |
| **18. Make your service work with any device** | Responsive design (GOV.UK Design System); mobile-first; supports assistive technologies | Cross-device compatibility | Public Portal (0.68) tested on iOS, Android, Windows, macOS; screen readers |

**Wardley Map Strategic Insight**: GDS Point 13 ("Use common platforms") drives the REUSE strategy. By mapping GOV.UK services at 0.75-0.92 evolution (Product-Commodity), IPO justifies reusing Pay, Notify, Design System rather than building custom alternatives. This delivers £570K savings and accelerates delivery by 3-6 months (no custom development needed for payments/notifications).

### 7.3 Digital Marketplace (G-Cloud 14) Procurement Strategy

**G-Cloud 14 Context**: UK Government's framework for cloud services procurement; mandatory for central government departments (IPO is part of Department for Business and Trade)

**Wardley Map Procurement Guidance**:

| Evolution Stage | G-Cloud Procurement Approach | Wardley Map Components | Total Budget |
|-----------------|------------------------------|------------------------|--------------|
| **Genesis (0.00-0.25)** | DO NOT PROCURE via G-Cloud; build in-house R&D; no vendors available | None in this project | £0 |
| **Custom (0.25-0.50)** | BUILD in-house; no suitable G-Cloud vendors; IPO-specific requirements | Patent Classification (0.35), Legacy Integration (0.35), Examination Workflow (0.38), Semantic Search (0.42), WIPO Integration (0.45) | £6.44M (38% of budget) |
| **Product (0.50-0.75)** | BUY via G-Cloud 14 Direct Award (<£100K per service) or Further Competition (>£100K); multiple vendors available | OCR (0.72), Chemical Search (0.68), EPO Integration (0.68), Authentication (0.68), Publication (0.58), Renewal (0.55), RBAC (0.62), Data Warehouse (0.75), Event Streaming (0.72), API Gateway (0.82) | £2.06M (21% of budget) |
| **Commodity (0.75-1.00)** | USE AWS GovCloud UK (pre-approved); reuse GOV.UK services (free); commodity procurement | AWS services (0.85-0.95), GOV.UK Pay (0.90), GOV.UK Notify (0.92), GOV.UK Design System (0.75) | £1.12M (12% of budget) |

**G-Cloud 14 Direct Award Strategy** (for Product-stage components 0.50-0.75):

1. **OCR Engine (0.72, £240K)**: ABBYY FineReader Server listed on G-Cloud 14; Direct Award (no competition); negotiate volume pricing (50K applications/year)
2. **Chemical Structure Search (0.68, £320K)**: PerkinElmer ChemDraw or InfoChem ICM on G-Cloud 14; Further Competition (>£100K); technical evaluation (pattern matching accuracy, USPTO/EPO database integration)
3. **Authentication (0.68, £180K)**: Auth0 on G-Cloud 14; Direct Award; OR use free GOV.UK Verify/One Login (decision based on MFA requirements)
4. **EPO Integration (0.68, £150K)**: Darts-ip or Minesoft wrappers on G-Cloud 14; Direct Award; evaluate EPO OPS API coverage
5. **Publication Engine (0.58, £180K)**: Docmosis, Windward on G-Cloud 14; Direct Award; template design services bundled
6. **Renewal Management (0.55, £150K)**: Chargebee on G-Cloud 14; Direct Award; integrate with GOV.UK Pay
7. **Event Streaming (0.72, £220K)**: AWS MSK (Managed Kafka) on G-Cloud 14; Direct Award; AWS GovCloud UK eligible
8. **Data Warehouse (0.75, £140K)**: AWS RDS PostgreSQL on G-Cloud 14; Direct Award; analytics instance sizing
9. **API Gateway (0.82, £120K)**: AWS API Gateway on G-Cloud 14; Direct Award; integrated with AWS services
10. **Authorization (0.62, £90K)**: Open Policy Agent (open-source, free); OR Casbin on G-Cloud 14; prefer OSS

**Total G-Cloud 14 Procurement**: £2.06M across 11 product-stage components

**Wardley Map Procurement Insight**: By classifying components at 0.50-0.75 evolution, IPO identifies which services have mature G-Cloud vendors. Custom components (0.25-0.50) are too unique for G-Cloud procurement; commodity components (0.75+) are utility services (AWS, GOV.UK). This strategic map guides procurement team on which RFPs to issue vs which services to direct-award.

---

## 8. Dependencies and Value Chain

### 8.1 Dependency Map

**Value Chain Flow** (top to bottom):

```
Patent Applicants (User Need 0.95 visibility)
  ↓
Patent Filing Service (0.52)
  ↓
Application Intake (0.42) + GOV.UK Pay (0.90) + GOV.UK Notify (0.92)
  ↓
OCR Engine (0.72) + Document Storage (0.88) + WIPO Integration (0.45)
  ↓
Patent Classification (ML) (0.35) + Legacy PMS Integration (0.35)
  ↓
Patent Examiners (User Need 0.95 visibility)
  ↓
Examiner Dashboard (0.38)
  ↓
Prior Art Search (0.42) + Examination Workflow (0.38)
  ↓
Semantic Search Engine (0.42) + Chemical Structure Search (0.68) + EPO Integration (0.68)
  ↓
Publication Engine (0.58) + WIPO Integration (0.45)
  ↓
Public Users (User Need 0.95 visibility)
  ↓
Public Portal (0.68) + Patent Search Service (0.48)
  ↓
API Gateway (0.82) + Authentication (0.68) + CDN (0.95)
  ↓
Application Runtime (EKS 0.95) + Database (PostgreSQL 0.92) + Search Index (OpenSearch 0.85)
```

### 8.2 Critical Path Analysis

**Critical Dependencies** (blockers if delayed):

| Dependency | Dependent Component | Blocker Component | Impact if Blocker Delayed | Mitigation |
|------------|---------------------|-------------------|---------------------------|------------|
| **Legacy Integration Required First** | Application Intake (0.42) | Legacy PMS Integration (0.35) | Filing service cannot save applications to legacy system; examiners have no access to new applications | **CRITICAL PATH**: Start legacy integration in Month 1; 6-month integration window; parallel running in Month 6-12 |
| **ML Model Training Before Classification** | Patent Classification (0.35) | ML Classification Model (0.35) | Classification service non-functional without trained model; examiners cannot use ML suggestions | **PARALLEL WORK**: Train ML model (Month 1-6) while building classification service (Month 3-9); model ready by service launch |
| **GOV.UK Pay for Payments** | Patent Filing Service (0.52), Renewal Management (0.55) | GOV.UK Pay (0.90) | Cannot accept filing fees/renewal payments; revenue loss; applications rejected | **LOW RISK**: GOV.UK Pay is free, mature service; integration 2-week effort; backup: Stripe on G-Cloud 14 |
| **Authentication Before Any Service** | All user-facing services (Filing 0.52, Dashboard 0.38, Portal 0.68) | Authentication (0.68) | No user login; security failure; cannot launch any service | **EARLY PRIORITY**: Implement Auth0/GOV.UK Verify in Month 2; all services depend on auth; 4-week integration |
| **AWS Infrastructure Before Apps** | All application services | AWS EKS (0.95), RDS (0.92), S3 (0.95) | No infrastructure to deploy applications; development blocked | **MONTH 1 PRIORITY**: Terraform IaC for AWS in Month 1; infrastructure ready by Month 2; CI/CD pipeline depends on this |
| **WIPO Integration for International Filing** | Application Intake (0.42), Patent Classification (0.35), Publication Engine (0.58) | WIPO Integration (0.45) | Cannot receive PCT applications; cannot export patents to WIPO; international obligations unmet | **MONTH 6 TARGET**: WIPO ST.96 integration by Month 6; PCT applications 30% of intake; critical for BR-003 (international integration) |
| **GOV.UK Design System for UI** | Public Portal (0.68), Patent Filing Service (0.52) | GOV.UK Design System (0.75) | UI doesn't meet GDS standards; fails accessibility; GDS Service Assessment failure | **NO RISK**: Design System is free, reusable; frontend developers trained on GDS patterns; 1-week integration |

**Critical Path Timeline** (18-month delivery):

```
Month 1: AWS infrastructure (Terraform IaC) + Legacy PMS integration starts
  ↓
Month 2: Authentication (Auth0/GOV.UK Verify) + Application runtime (EKS) ready
  ↓
Month 3: Application Intake development + ML model training (parallel)
  ↓
Month 4: OCR integration + Document storage (S3)
  ↓
Month 5: Patent Classification service (depends on ML model Month 6)
  ↓
Month 6: WIPO Integration (ST.96) + ML model trained + Legacy integration complete + ALPHA LAUNCH
  ↓
Month 7: Examiner Dashboard development
  ↓
Month 8: Prior Art Search + Semantic Search Engine
  ↓
Month 9: EPO Integration (OPS API) + Chemical Structure Search (PerkinElmer)
  ↓
Month 10: Examination Workflow + Publication Engine
  ↓
Month 11: Renewal Management + GOV.UK Pay integration
  ↓
Month 12: PRIVATE BETA LAUNCH (50 examiners)
  ↓
Month 13: Public Portal development + Patent Search Service
  ↓
Month 14: API Gateway + CDN (CloudFront) for public access
  ↓
Month 15: PUBLIC BETA LAUNCH + GDS Service Assessment
  ↓
Month 16: GDS feedback addressed
  ↓
Month 17: Load testing, security ITHC, final bug fixes
  ↓
Month 18: LIVE LAUNCH + Legacy PMS decommissioning plan
```

**Critical Path Risks**:
- **Legacy Integration Overruns**: 40% of IT projects with legacy integration exceed timeline; mitigated by dedicated team (2 FTE) and 6-month buffer
- **ML Model Accuracy <95%**: ML training may not hit 95% accuracy target; mitigated by transfer learning from USPTO/EPO models and manual fallback
- **WIPO ST.96 Delays**: International standards coordination delays; mitigated by dual ST.36/ST.96 support and EPO liaison
- **GDS Service Assessment Failure**: Service may not pass GDS assessment; mitigated by using GOV.UK Design System and early accessibility audits

### 8.3 Synergies and Co-Dependencies

**Synergistic Component Groupings** (buy together, deploy together):

| Synergy Group | Components | Evolution Spread | Procurement Strategy | Benefits |
|---------------|------------|------------------|----------------------|----------|
| **GOV.UK Services Bundle** | GOV.UK Pay (0.90), GOV.UK Notify (0.92), GOV.UK Design System (0.75), GOV.UK Verify (0.68) | 0.68-0.92 | FREE REUSE | £570K savings vs custom build; consistent UX; automatic updates from GDS; single sign-on |
| **AWS Managed Services Bundle** | EKS (0.95), RDS (0.92), ElastiCache (0.90), OpenSearch (0.85), S3 (0.95), CloudFront (0.95), CloudWatch (0.88) | 0.85-0.95 | AWS ENTERPRISE DISCOUNT | 15% volume discount on AWS services (£120K savings); integrated monitoring; single vendor relationship |
| **Patent ML/AI Bundle** | ML Classification Model (0.35), Semantic Search Engine (0.42), Patent Classification (0.35), Prior Art Search (0.42) | 0.35-0.42 | BUILD (Single ML Team) | Shared ML infrastructure (GPU training, model registry); team expertise (3 ML engineers); transfer learning across models |
| **International Integration Bundle** | WIPO Integration (0.45), EPO Integration (0.68), IP5 Data Exchange (0.52) | 0.45-0.68 | BUILD + BUY (EPO wrapper) | Single integration team (2 FTE international architects); shared XML parsers; consistent error handling |
| **Security & Compliance Bundle** | Authentication (0.68), Authorization (0.62), Audit Logging (0.85), STRIDE threat model | 0.62-0.85 | BUY (Auth0) + BUILD (RBAC) | Single security architecture; centralized audit logs; CISO oversight; Cyber Essentials Plus compliance |

**Wardley Map Strategic Insight**: Synergies reduce total cost by 18% (£1.8M savings) vs procuring components independently:
- GOV.UK bundle: £570K savings
- AWS volume discount: £120K savings
- Shared ML team: £400K savings (vs separate teams per model)
- Shared international team: £200K savings
- Security bundle: £180K savings (Auth0 SSO vs multiple auth systems)

---

## 9. Strategic Gameplay (Competitive Moves)

### 9.1 Offensive Strategies (Competitive Advantage for IPO)

| Strategy | Wardley Map Justification | Target Components | Expected Outcome | Investment | ROI |
|----------|---------------------------|-------------------|------------------|------------|-----|
| **Build World-Class Patent ML** | ML Classification (0.35 Custom) gives IPO competitive advantage over other patent offices; USPTO/EPO have <90% accuracy; IPO targets 95% | C-007 (Patent Classification), C-013 (ML Model) | IPO becomes global leader in ML-assisted patent examination; license model to other patent offices (£500K/year revenue); faster examination (18→12 months) attracts more applicants | £980K (ML model training) | 3-year payback; £2M+ revenue over 5 years |
| **Open-Source Patent Tools** | WIPO Integration (0.45), Semantic Search (0.42) built custom; open-source on GitHub to accelerate evolution to Product stage (0.65+); other patent offices adopt IPO code | C-020 (WIPO Integration), C-014 (Semantic Search) | IPO builds reputation as innovation leader; reduces maintenance cost (community contributions); potential to productize (licensing revenue); aligns with TCoP Point 4 (Open Source) | £0 (already building custom) | Brand value; government innovation awards; GDS case study |
| **GOV.UK Patent Platform** | IPO creates reusable "patent platform" (classification + search + workflow) for other UK IP rights (trademarks, designs); leverages Custom components (0.35-0.42) | C-007 (Classification), C-009 (Workflow), C-014 (Search) | IPO amortizes development cost across multiple IP rights; £3M+ savings for trademarks/designs projects; platform becomes Product stage (0.60+) | £6.44M (already budgeted) | 50% cost recovery from other IP rights (£3.2M) |
| **Patent API Marketplace** | Publish open patent data API (3M published patents); build developer ecosystem; monetize via premium API tiers (bulk data, real-time updates) | C-004 (Public Portal), C-005 (API Gateway), C-030 (S3 data) | IPO generates revenue from patent data (£200K/year); UK tech companies build patent analytics tools; supports BR-005 (Open Data) | £180K (API Gateway + CDN) | 2-year payback; £1M+ revenue over 5 years |

### 9.2 Defensive Strategies (Risk Mitigation)

| Strategy | Wardley Map Justification | Target Components | Threat Mitigated | Investment | Risk Reduction |
|----------|---------------------------|-------------------|------------------|------------|----------------|
| **Avoid Vendor Lock-In** | BUY components (0.50-0.75) have lock-in risk; use open APIs, avoid proprietary formats; multi-cloud strategy (Terraform) | C-012 (OCR), C-015 (Chemical Search), C-017 (Authentication), C-021 (EPO Integration) | Vendor price increases, vendor bankruptcy, vendor feature stagnation; can switch to alternative G-Cloud vendor within 6 months | £60K (Terraform multi-cloud IaC) | Eliminates £500K+ migration cost if locked in |
| **Containerize All Apps** | Kubernetes (0.95 Commodity) enables portability; avoid AWS-specific services where possible (Lambda, DynamoDB); use PostgreSQL (0.92) not Aurora | C-026 (EKS), C-027 (PostgreSQL), containerized microservices | AWS vendor lock-in; can migrate to Azure/GCP within 12 months if AWS prices increase 30%+ | £0 (Kubernetes standard) | Maintains competitive cloud pricing; avoids 3-year AWS commitments |
| **Dual GOV.UK Services** | GOV.UK Pay (0.90) and Notify (0.92) are free but have SLA risk; implement failover to commercial alternatives (Stripe, Twilio) | C-036 (GOV.UK Pay), C-035 (GOV.UK Notify) | GOV.UK service outages (SLA 99.5%); payment failures block patent renewals (£50M/year revenue risk); notification failures breach legal deadlines | £50K (Stripe/Twilio integration as backup) | Eliminates £50M revenue risk; maintains 99.9% uptime |
| **Legacy PMS Decommissioning** | Legacy Integration (0.35 Custom) is technical debt; plan decommissioning by 2027 to avoid ongoing maintenance (£200K/year) | C-023 (Legacy Integration) | Legacy system becomes unsupportable (COBOL developers retire); integration breaks; data loss; IPO cannot process applications | £620K (integration) + £300K (decommissioning 2027) | Eliminates £200K/year maintenance; reduces security vulnerabilities (legacy system unpatched) |
| **ML Model Bias Audits** | ML Classification (0.35) may have bias (gender, race in inventor names; country of origin); legal risk if biased classifications delay certain applications | C-007 (Patent Classification), C-013 (ML Model) | Discrimination lawsuits; judicial review challenges; IPO reputation damage; regulatory investigation (Equality and Human Rights Commission) | £80K (bias audits by external AI ethics firm) | Eliminates £5M+ legal liability; maintains IPO impartiality |

### 9.3 Market Creation (Ecosystem Development)

| Strategy | Wardley Map Justification | Target Components | Ecosystem Goal | Investment | Market Impact |
|----------|---------------------------|-------------------|----------------|------------|---------------|
| **Patent API Developer Portal** | Public API (0.82 Product) creates developer ecosystem; encourage UK startups to build patent analytics, IP management tools | C-005 (API Gateway), C-004 (Public Portal), API documentation | 100+ developers, 20+ patent tech startups, £10M+ private investment in UK patent tech sector | £120K (API Gateway + developer portal + documentation) | New market for patent technology; UK becomes global patent tech hub; supports HMG innovation agenda |
| **ML Model Marketplace** | IPO-trained ML models (Classification 0.35, Semantic Search 0.42) licensed to other patent offices, law firms, IP consultancies | C-013 (ML Model), C-014 (Semantic Search), licensing agreements | £500K/year licensing revenue; 10+ international patent offices adopt IPO models; IPO becomes ML training hub | £980K (ML development, already budgeted) | IPO recoups ML investment via licensing; UK becomes global IP AI leader |
| **WIPO ST.96 Reference Implementation** | IPO open-sources WIPO Integration (0.45) as reference implementation; other patent offices adopt; IPO influences WIPO standard evolution | C-020 (WIPO Integration), open-source on GitHub | 50+ patent offices adopt IPO code; IPO engineers invited to WIPO technical committees; UK shapes international IP standards | £420K (WIPO integration, already budgeted) | UK influence in international IP governance; IPO thought leadership; accelerates ST.96 global adoption |

---

## 10. Risk Analysis

### 10.1 Technical Risks

| Risk ID | Risk Description | Probability | Impact | Wardley Map Components Affected | Mitigation Strategy | Residual Risk |
|---------|------------------|-------------|--------|---------------------------------|---------------------|---------------|
| **TR-001** | Legacy PMS integration fails; 40-year-old system has undocumented interfaces, batch-only, COBOL codebase | **HIGH (60%)** | **CRITICAL** | C-023 (Legacy Integration 0.35), C-006 (Application Intake 0.42) | Dedicated legacy team (2 FTE); 6-month integration window; parallel running; fallback to manual data entry | **MEDIUM** (30% residual risk; mitigated by dedicated team) |
| **TR-002** | ML classification accuracy <95%; model doesn't understand patent language nuances, technical terminology | **MEDIUM (40%)** | **HIGH** | C-007 (Patent Classification 0.35), C-013 (ML Model 0.35) | Transfer learning from USPTO/EPO; train on 10M+ IPO historical classifications; 6-month pilot with examiners; manual fallback | **LOW** (15% residual risk; pilot validates accuracy) |
| **TR-003** | WIPO ST.96 integration delays; WIPO standard evolving, IPO-to-WIPO mappings complex, international coordination slow | **MEDIUM (50%)** | **MEDIUM** | C-020 (WIPO Integration 0.45), C-006 (Application Intake 0.42) | Dual ST.36/ST.96 support; WIPO liaison officer; EPO integration testing; fallback to email/FTP exchange | **LOW** (20% residual risk; dual format support) |
| **TR-004** | Semantic search doesn't understand patent claims; search results irrelevant; examiners lose trust; revert to keyword search | **MEDIUM (35%)** | **MEDIUM** | C-014 (Semantic Search 0.42), C-008 (Prior Art Search 0.42) | Fine-tune on patent corpus (not Wikipedia); A/B test with examiners; hybrid semantic + keyword search; explainable AI (show similar patents) | **MEDIUM** (25% residual risk; hybrid approach hedges) |
| **TR-005** | AWS GovCloud UK outage; eu-west-2 region failure; patent services unavailable for >4 hours (breaches NFR-001 RTO) | **LOW (10%)** | **HIGH** | C-026 (EKS 0.95), C-027 (RDS 0.92), C-030 (S3 0.95), all services depend on AWS | Multi-AZ architecture; RDS cross-region read replica (eu-west-1); S3 cross-region replication; 4-hour RTO aligns with AWS SLA | **LOW** (5% residual risk; multi-AZ sufficient for RTO) |
| **TR-006** | Chemical structure search (PerkinElmer ChemDraw) doesn't integrate with patent database; proprietary formats | **LOW (20%)** | **MEDIUM** | C-015 (Chemical Structure Search 0.68), C-008 (Prior Art Search 0.42) | Evaluate multiple vendors (PerkinElmer, InfoChem); require REST API in RFP; fallback to manual chemical search by examiners | **LOW** (10% residual risk; multiple vendor options) |
| **TR-007** | OCR accuracy <98%; handwritten patent applications, poor scan quality, chemical formulas unrecognized | **MEDIUM (40%)** | **LOW** | C-012 (OCR Engine 0.72), C-006 (Application Intake 0.42) | ABBYY FineReader has 99%+ accuracy on printed text; train on patent documents; manual review for low-confidence OCR; 80% of applications are digital anyway | **LOW** (15% residual risk; mostly digital applications) |

### 10.2 Strategic Risks

| Risk ID | Risk Description | Probability | Impact | Wardley Map Components Affected | Mitigation Strategy | Residual Risk |
|---------|------------------|-------------|--------|---------------------------------|---------------------|---------------|
| **SR-001** | ML classification (0.35 Custom) commoditized by vendors (Clarivate, PatSnap) within 3 years; IPO £980K investment obsolete | **HIGH (70%)** | **MEDIUM** | C-007 (Patent Classification 0.35), C-013 (ML Model 0.35) | IPO trains on UK-specific data (competitive advantage for 3 years); plan to license or sell ML model to recoup investment; monitor vendor ML products | **MEDIUM** (50% residual risk; commoditization inevitable) |
| **SR-002** | Semantic search (0.42 Custom) becomes Product stage (0.65); Google Patents, Microsoft Academic provide free patent semantic search | **MEDIUM (60%)** | **MEDIUM** | C-014 (Semantic Search 0.42), C-008 (Prior Art Search 0.42) | Build MVP only (£680K); plan to migrate to commercial by 2028 (£400K+ ongoing maintenance savings); IPO search fine-tuned for UK examiners (temporary advantage) | **MEDIUM** (45% residual risk; plan migration by 2028) |
| **SR-003** | GOV.UK Verify (0.68) decommissioned by GDS; replaced by GOV.UK One Login; IPO must migrate authentication | **CERTAINTY (100%)** | **LOW** | C-017 (Authentication 0.68), C-037 (GOV.UK Verify 0.68) | Plan migration to GOV.UK One Login in roadmap (2026-2027); £50K integration cost budgeted; GDS provides migration support | **LOW** (migration planned; GDS timeline known) |
| **SR-004** | G-Cloud 14 vendors increase prices post-contract (lock-in); OCR, chemical search licensing costs double | **MEDIUM (40%)** | **MEDIUM** | C-012 (OCR 0.72), C-015 (Chemical Search 0.68) | G-Cloud contracts have price caps; negotiate 3-year fixed pricing; maintain vendor switching capability (open APIs); evaluate OSS alternatives (RDKit for chemistry) | **LOW** (20% residual risk; G-Cloud price protections) |
| **SR-005** | UK Government budget cuts; IPO £7M project reduced to £5M; scope cut required; technical debt incurred | **LOW (15%)** | **HIGH** | All components (BUILD components most at risk) | MVP prioritization; descope "nice-to-have" features (e.g., mobile app, advanced analytics); GOV.UK reuse saves £570K (buffer); phase 2 funding for enhancements | **MEDIUM** (25% residual risk; government funding volatile) |
| **SR-006** | Patent examination automation (AI) eliminates examiner jobs; industrial action; project blocked by unions | **MEDIUM (30%)** | **HIGH** | C-007 (Patent Classification 0.35), C-009 (Examination Workflow 0.38), C-003 (Examiner Dashboard 0.38) | ML is "assistive" not "autonomous"; examiners retain final decision authority; frame as productivity tool (12-month target) not job replacement; union consultation | **LOW** (10% residual risk; assistive framing) |

### 10.3 Procurement Risks

| Risk ID | Risk Description | Probability | Impact | Wardley Map Components Affected | Mitigation Strategy | Residual Risk |
|---------|------------------|-------------|--------|---------------------------------|---------------------|---------------|
| **PR-001** | Vendor proposals don't meet mandatory qualifications (MQ-1 to MQ-28); <3 qualified vendors; insufficient competition | **MEDIUM (35%)** | **MEDIUM** | All BUY components (C-012, C-015, C-017, C-021, etc.) | Pre-market engagement with G-Cloud 14 vendors; clarify requirements before RFP; lower barrier (e.g., accept BPSS commitment not actual clearance); fallback to BUILD if no vendors | **LOW** (15% residual risk; G-Cloud has deep vendor pool) |
| **PR-002** | Vendor fails security clearance (BPSS, SC); cannot access OFFICIAL-SENSITIVE patent data; project delayed 3-6 months | **MEDIUM (40%)** | **HIGH** | All components requiring OFFICIAL-SENSITIVE access (C-007, C-009, C-023) | Mandatory qualification MQ-20 (BPSS commitment), MQ-21 (SC commitment); start clearance in Month 1; vendor must have pre-cleared staff; IPO sponsors clearance | **MEDIUM** (30% residual risk; clearance delays common) |
| **PR-003** | Vendor goes bankrupt mid-project; code/IP lost; re-procurement required; 6-month delay | **LOW (10%)** | **HIGH** | All BUILD components outsourced (if vendor builds custom components) | Vendor financial stability check (MQ-15, MQ-16); escrow agreements for source code; payment milestones (not upfront); prefer large vendors or consortia | **LOW** (5% residual risk; financial checks + escrow) |
| **PR-004** | Procurement timeline overruns; G-Cloud 14 call-off takes 6 months instead of 2 months; vendor onboarding delayed | **MEDIUM (50%)** | **MEDIUM** | Timeline depends on vendor onboarding Month 1-2; delays push delivery to Month 20+ | Expedite procurement (Direct Award where possible); CDDO pre-approval; HMT business case approved before RFP; vendor shortlist pre-identified | **MEDIUM** (35% residual risk; government procurement slow) |
| **PR-005** | Vendor proposal costs exceed £7M budget; lowest bidder is £9M; budget overrun or scope cut required | **LOW (20%)** | **HIGH** | All components; budget overrun forces scope cuts | Detailed cost estimates in SOW; vendor budget guidance (£7M); value engineering (descope non-MVP); phased delivery (Phase 1: £5M core, Phase 2: £2M enhancements) | **LOW** (10% residual risk; budget guidance in RFP) |

---

## 11. Requirements Traceability

### 11.1 Business Requirements to Wardley Map Components

| BR ID | Business Requirement | Wardley Map Components | Evolution Stage | Build/Buy/Reuse | Strategic Rationale |
|-------|----------------------|------------------------|-----------------|-----------------|---------------------|
| **BR-001** | Reduce patent examination time from 18 to 12 months (33% improvement) | C-007 (Patent Classification 0.35), C-008 (Prior Art Search 0.42), C-009 (Examination Workflow 0.38), C-003 (Examiner Dashboard 0.38) | Custom (0.35-0.42) | BUILD | ML-assisted classification and semantic search are custom innovations (no commercial alternatives with 95% accuracy); competitive advantage for IPO examination speed |
| **BR-002** | Achieve £2M annual cost savings through cloud modernization and automation | C-026 (EKS 0.95), C-027 (RDS 0.92), C-030 (S3 0.95), GOV.UK services (0.85-0.92) | Commodity (0.85-0.95) | COMMODITY + REUSE | Cloud (AWS) saves £3.15M vs on-premise over 5 years; GOV.UK reuse saves £570K vs custom build; automation (ML classification, workflow) reduces manual effort |
| **BR-003** | 95% user satisfaction (examiners, applicants, public) | C-034 (GOV.UK Design System 0.75), C-003 (Examiner Dashboard 0.38), C-004 (Public Portal 0.68), C-001 (Filing Service 0.52) | Product-Custom (0.38-0.75) | REUSE (Design System) + BUILD (Dashboard) | GOV.UK Design System ensures WCAG 2.2 AA accessibility and consistent UX (drives satisfaction); custom examiner dashboard optimized for IPO workflows |
| **BR-004** | 99.5% system uptime (3M published patents, 50K applications/year, public access) | C-026 (EKS 0.95), C-027 (RDS 0.92), C-032 (Monitoring 0.88), Multi-AZ AWS | Commodity (0.88-0.95) | COMMODITY | AWS multi-AZ achieves 99.99% uptime SLA; exceeds 99.5% requirement; monitoring (Prometheus/Grafana) tracks SLA compliance |
| **BR-005** | Open data: Publish 3M patents via public API (non-OFFICIAL data only) | C-004 (Public Portal 0.68), C-005 (API Gateway 0.82), C-030 (S3 0.95), C-031 (CDN 0.95) | Commodity-Product (0.68-0.95) | BUY (API Gateway) + COMMODITY (S3, CDN) | API Gateway (0.82 Product) is mature technology; AWS S3/CloudFront (0.95 Commodity) are lowest-cost solution for public data delivery |
| **BR-006** | International integration: WIPO (PCT), EPO (patent data exchange), IP5 (bilateral data sharing) | C-020 (WIPO Integration 0.45), C-021 (EPO Integration 0.68), C-022 (IP5 Data Exchange 0.52) | Custom-Product (0.45-0.68) | BUILD (WIPO, IP5) + BUY (EPO wrapper) | WIPO ST.96 (0.45 Custom) requires custom adapter; EPO OPS (0.68 Product) has commercial wrappers; IP5 (0.52 Custom-Product boundary) requires bilateral custom integrations |

### 11.2 Functional Requirements to Wardley Map Components

| FR ID | Functional Requirement | Wardley Map Components | Evolution Stage | Build/Buy/Reuse | Strategic Rationale |
|-------|------------------------|------------------------|-----------------|-----------------|---------------------|
| **FR-001** | Patent application intake: digital forms, PDF upload, fee payment, filing date determination | C-001 (Filing Service 0.52), C-006 (Application Intake 0.42), C-036 (GOV.UK Pay 0.90), C-012 (OCR 0.72) | Custom-Commodity (0.42-0.90) | BUILD (Intake, Filing) + REUSE (GOV.UK Pay) + BUY (OCR) | UK Patent Rules 2007 validation requires custom logic (0.42 Custom); GOV.UK Pay (0.90 Commodity) is free; OCR (0.72 Product) is mature commercial technology |
| **FR-002** | Automatic patent classification using ML (CPC/IPC codes; 10,000 classes; 95% accuracy target) | C-007 (Patent Classification 0.35), C-013 (ML Model 0.35) | Custom (0.35) | BUILD | No commercial ML achieves 95% on patent data; IPO-specific training data (10M classifications); competitive advantage; justify £980K investment |
| **FR-003** | Semantic prior art search across 3M published patents (keyword, classification, semantic similarity) | C-008 (Prior Art Search 0.42), C-014 (Semantic Search 0.42), C-029 (OpenSearch 0.85) | Custom-Commodity (0.42-0.85) | BUILD (Semantic Search) + COMMODITY (OpenSearch) | Patent semantic search (0.42 Custom) requires fine-tuning on patent language; OpenSearch (0.85 Product-Commodity) is managed AWS service for indexing |
| **FR-004** | Examiner workflow: assign applications, conduct prior art search, write examination reports, issue objections, approve/reject | C-009 (Examination Workflow 0.38), C-003 (Examiner Dashboard 0.38), C-018 (Authorization 0.62) | Custom-Product (0.38-0.62) | BUILD (Workflow, Dashboard) + BUY (RBAC) | UK Patent Act 1977 compliance requires custom workflow logic (0.38 Custom); RBAC (0.62 Product) uses Open Policy Agent |
| **FR-005** | Patent publication: generate PDF/HTML, publish to public portal, notify applicants, export to WIPO/EPO | C-010 (Publication Engine 0.58), C-035 (GOV.UK Notify 0.92), C-020 (WIPO Integration 0.45), C-031 (CDN 0.95) | Custom-Commodity (0.45-0.95) | BUY (Publication) + REUSE (Notify, CDN) + BUILD (WIPO) | Publication engine (0.58 Product) uses Docmosis; GOV.UK Notify (0.92 Commodity) is free; WIPO export (0.45 Custom) requires ST.96 XML |
| **FR-006** | Renewal management: calculate renewal fees, send reminders, process payments, update patent status | C-011 (Renewal Management 0.55), C-036 (GOV.UK Pay 0.90), C-035 (GOV.UK Notify 0.92), C-027 (PostgreSQL 0.92) | Product-Commodity (0.55-0.92) | BUY (Renewal via Chargebee) + REUSE (Pay, Notify) | Renewal management (0.55 Product) uses Chargebee subscription billing; integrates with GOV.UK Pay (0.90 Commodity) |
| **FR-007** | Chemical structure search for pharmaceutical/chemistry patents (substructure, similarity search) | C-015 (Chemical Structure Search 0.68), C-008 (Prior Art Search 0.42) | Product (0.68) | BUY | Chemistry IP is specialized; PerkinElmer ChemDraw (0.68 Product) is mature; no business case for custom chemistry algorithms (3+ years development) |
| **FR-008** | Public patent search: keyword, classification, applicant, inventor, filing date; results ranked by relevance | C-002 (Patent Search Service 0.48), C-004 (Public Portal 0.68), C-005 (API Gateway 0.82), C-029 (OpenSearch 0.85) | Product-Custom (0.48-0.85) | BUILD (Search Service) + BUY (Portal, API Gateway) + COMMODITY (OpenSearch) | Public search service (0.48 Custom-Product) fine-tuned for patent search UX; portal (0.68 Product) uses GOV.UK Design System; OpenSearch (0.85 Commodity) for indexing |
| **FR-009** | API for patent data: RESTful API, OpenAPI 3.0, rate limiting, authentication, bulk data download | C-005 (API Gateway 0.82), C-017 (Authentication 0.68), C-016 (Document Storage 0.88), C-031 (CDN 0.95) | Product-Commodity (0.68-0.95) | BUY (API Gateway, Auth) + COMMODITY (S3, CDN) | API Gateway (0.82 Product) is mature AWS service; Auth0 (0.68 Product) for OAuth 2.0; S3/CloudFront (0.95 Commodity) for bulk data |
| **FR-010** | Legacy PMS integration: batch data sync, bi-directional updates, data migration, parallel running (6 months) | C-023 (Legacy PMS Integration 0.35), C-027 (PostgreSQL 0.92), C-025 (Event Streaming 0.72) | Custom-Commodity (0.35-0.92) | BUILD (Legacy adapter) + COMMODITY (PostgreSQL, Kafka) | 40-year-old legacy system (0.35 Genesis-Custom) has no APIs; custom adapter required; no vendor has IPO legacy expertise; Kafka (0.72 Product) for event streaming |

### 11.3 Non-Functional Requirements to Wardley Map Components

| NFR ID | Non-Functional Requirement | Wardley Map Components | Evolution Stage | Build/Buy/Reuse | Strategic Rationale |
|--------|----------------------------|------------------------|-----------------|-----------------|---------------------|
| **NFR-001** | Performance: <3s page load, <500ms API response, 99.5% uptime, 4h RTO, 1h RPO | C-026 (EKS 0.95), C-027 (RDS 0.92), C-028 (Redis 0.90), C-031 (CDN 0.95), C-032 (Monitoring 0.88) | Commodity (0.88-0.95) | COMMODITY | AWS multi-AZ architecture achieves 99.99% SLA; Redis caching (0.90) for <500ms response; CloudFront CDN (0.95) for <3s load; monitoring (0.88) tracks SLA |
| **NFR-002** | Security: OFFICIAL-SENSITIVE controls, Cyber Essentials Plus, ISO 27001, STRIDE threat model, ITHC penetration testing | C-017 (Authentication 0.68), C-018 (Authorization 0.62), C-019 (Audit Logging 0.85), BPSS/SC clearance (MQ-20, MQ-21) | Product-Commodity (0.62-0.85) | BUY (Auth0 MFA) + BUY (OPA RBAC) + COMMODITY (CloudWatch Logs) | Authentication (0.68 Product) too risky to build custom; Auth0 meets Cyber Essentials Plus; audit logging (0.85 Commodity) via CloudWatch |
| **NFR-003** | Accessibility: WCAG 2.2 Level AA compliance, manual testing, IAAP-certified specialists, GOV.UK Design System | C-034 (GOV.UK Design System 0.75), C-004 (Public Portal 0.68), C-001 (Filing Service 0.52) | Product-Custom (0.52-0.75) | REUSE (Design System) + BUILD (accessible UI) | GOV.UK Design System (0.75 Product) is WCAG 2.2 AA compliant by default; reuse saves £120K vs custom accessible design; manual testing required regardless |
| **NFR-004** | Scalability: Support 50K applications/year, 200 concurrent examiners, 10K concurrent public users, 3M published patents | C-026 (EKS 0.95), C-027 (RDS 0.92), C-029 (OpenSearch 0.85), C-031 (CDN 0.95), auto-scaling | Commodity (0.85-0.95) | COMMODITY | Kubernetes (EKS 0.95) auto-scales pods; RDS (0.92) auto-scales storage; CloudFront CDN (0.95) handles 10K+ concurrent users; OpenSearch (0.85) indexes 3M patents |
| **NFR-005** | Data Sovereignty: All data stored in UK (AWS eu-west-2 London region); GDPR compliance; DPO oversight | C-027 (RDS uk-west-2), C-030 (S3 uk-west-2), C-026 (EKS uk-west-2), DPIA | Commodity (0.92-0.95) | COMMODITY | AWS GovCloud UK enforces UK data residency by default; Terraform IaC (0.80) enforces eu-west-2 region constraint; S3 cross-region replication disabled |
| **NFR-006** | Observability: Metrics (Prometheus), Logs (ELK/CloudWatch), Traces (OpenTelemetry), Dashboards (Grafana), Alerts | C-032 (Monitoring 0.88), C-019 (Audit Logging 0.85), CloudWatch (0.88) | Commodity (0.85-0.88) | COMMODITY | Monitoring (0.88 Product-Commodity) uses Prometheus/Grafana + CloudWatch; mature observability stack; no custom tooling needed; integrated with AWS services |

**Traceability Summary**: All 6 business requirements, 10 functional requirements, and 6 non-functional requirements map to specific Wardley Map components with evolution stages and build/buy/reuse decisions justified. This traceability ensures procurement strategy aligns with requirements and business outcomes.

---

## 12. Strategic Recommendations

### 12.1 Immediate Actions (Month 1-3)

| Action | Wardley Map Justification | Responsible | Deadline | Expected Outcome |
|--------|---------------------------|-------------|----------|------------------|
| **Start Legacy PMS Integration** | Legacy Integration (0.35 Custom) is critical path blocker; 6-month integration window required | Legacy Integration Team (2 FTE) | Month 1 | Unblock application intake (C-006) and examination workflow (C-009); mitigate TR-001 risk |
| **Deploy AWS Infrastructure (IaC)** | AWS (0.95 Commodity) is foundation for all services; Terraform IaC (0.80 Product) enables infrastructure-as-code | Cloud Architect | Month 1 | EKS, RDS, S3, CloudWatch ready by Month 2; CI/CD pipeline deployed; development environment available |
| **Integrate GOV.UK Pay & Notify** | GOV.UK services (0.90-0.92 Commodity) are free, mature; low integration effort (2 weeks each); £350K savings vs custom build | Frontend Developer | Month 2 | Payment processing (patent fees, renewals) and notifications (filing confirmations, examination updates) functional |
| **Implement Authentication (Auth0)** | Authentication (0.68 Product) is dependency for all user-facing services; security critical (OFFICIAL-SENSITIVE); 4-week integration | Security Engineer | Month 2 | User login (examiners, applicants, public); MFA enabled; Cyber Essentials Plus compliance; BPSS clearance gating |
| **Start ML Model Training** | ML Classification (0.35 Custom) requires 6-month training; must complete by Month 6 for alpha launch; train in parallel with service development | ML Engineer (3 FTE) | Month 1 | 10M historical classifications trained; 95% accuracy target; model ready for classification service (C-007) integration |
| **Procure OCR Engine (ABBYY)** | OCR (0.72 Product) required for application intake (C-006); G-Cloud 14 Direct Award (<£100K); 98% accuracy requirement | Procurement | Month 1 | ABBYY FineReader Server licensed; 50K applications/year volume pricing; OCR API integrated by Month 4 |
| **Engage WIPO Liaison Officer** | WIPO Integration (0.45 Custom) has international dependencies; ST.96 XML coordination required; mitigate TR-003 risk | International Architect | Month 1 | WIPO ST.96 requirements clarified; test data obtained; EPO integration timeline confirmed; bilateral agreements with IP5 offices |

### 12.2 Short-Term Actions (Month 4-9)

| Action | Wardley Map Justification | Responsible | Deadline | Expected Outcome |
|--------|---------------------------|-------------|----------|------------------|
| **Launch Alpha (10 examiners)** | GDS Service Standard requires alpha phase; validate ML classification (0.35), semantic search (0.42), examination workflow (0.38) with real users | Product Owner | Month 6 | User feedback on ML accuracy, search relevance, workflow usability; iterate based on feedback; mitigate SR-006 (examiner resistance) |
| **Complete WIPO ST.96 Integration** | WIPO Integration (0.45 Custom) unblocks PCT applications (30% of intake); BR-006 international integration requirement | International Architect | Month 6 | PCT applications received via WIPO; patent data exported to WIPO; ST.96 XML validated; dual ST.36/ST.96 support |
| **Procure Chemical Structure Search** | Chemical Structure Search (0.68 Product) required for pharmaceutical/chemistry patents; G-Cloud 14 Further Competition (>£100K); evaluate PerkinElmer vs InfoChem | Procurement | Month 7 | PerkinElmer ChemDraw licensed; chemical structure search integrated into prior art search (C-008); examiners can search by chemical formula |
| **Integrate EPO OPS API** | EPO Integration (0.68 Product) required for European patent data exchange; commercial wrapper (Darts-ip) reduces development effort | International Architect | Month 9 | EPO patent data synchronized; examiners can view EPO prior art; bilateral data exchange with EPO operational |
| **Launch Private Beta (50 examiners)** | GDS Service Standard requires private beta; scale from alpha (10 users) to beta (50 users); validate performance (NFR-001) and security (NFR-002) at scale | Product Owner | Month 12 | Beta feedback; performance validated (<3s load, <500ms API); security ITHC testing; prepare for public beta Month 15 |

### 12.3 Long-Term Actions (Month 10-18 & Beyond)

| Action | Wardley Map Justification | Responsible | Deadline | Expected Outcome |
|--------|---------------------------|-------------|----------|------------------|
| **Launch Public Beta + GDS Assessment** | GDS Service Standard Point 12 requires GDS Service Assessment before live; public beta with real users; GOV.UK Design System (0.75) de-risks assessment | Product Owner | Month 15 | GDS Service Assessment passed; public portal (C-004) live; patent search (C-002) available to public; BR-005 (open data) achieved |
| **Live Launch + Legacy Decommissioning** | New PMS replaces legacy system; legacy integration (0.35 Custom) decommissioned by 2027 to avoid £200K/year maintenance; parallel running ends | Enterprise Architect | Month 18 | Live service operational; BR-001 (12-month examination time) achieved; BR-002 (£2M savings) realized; legacy PMS decommissioning plan approved |
| **Evaluate ML Commoditization (2028)** | ML Classification (0.35 Custom) may be commoditized by commercial vendors (Clarivate, PatSnap) by 2028; monitor SR-001 risk; plan migration to product | Enterprise Architect | 2028 (Year 3) | Decision: Continue custom ML or migrate to commercial product; potential £400K/year maintenance savings; license IPO ML model to other patent offices (£500K/year revenue) |
| **Migrate to GOV.UK One Login** | GOV.UK Verify (0.68) replaced by GOV.UK One Login (0.85 Commodity) by 2026; GDS mandates migration; £50K integration cost | Security Engineer | 2026-2027 | Single sign-on across all government services; improved user experience; GDS compliance maintained |
| **Open-Source Patent Tools (GitHub)** | WIPO Integration (0.45), Semantic Search (0.42) open-sourced to accelerate evolution to Product stage (0.65+); TCoP Point 4 (Open Source) compliance | Enterprise Architect | 2026 | IPO GitHub repository with WIPO adapters, semantic search engine; other patent offices adopt IPO code; IPO becomes thought leader in patent technology |
| **Patent API Marketplace** | Public API (0.82 Product) monetized via premium tiers (bulk data, real-time updates); create developer ecosystem; £200K/year revenue | Product Owner | 2027 | 100+ developers registered; 20+ patent tech startups using IPO API; £10M+ private investment in UK patent technology sector |

### 12.4 Strategic Roadmap (3-Year Horizon)

```
YEAR 1 (2025-2026): BUILD + REUSE + PROCURE
|
├─ Q1 (Month 1-3): Foundation
│  ├─ AWS infrastructure (Terraform IaC)
│  ├─ GOV.UK services integration (Pay, Notify, Design System)
│  ├─ Legacy PMS integration start (critical path)
│  ├─ ML model training start (6-month runway)
│  └─ Authentication (Auth0/GOV.UK Verify)
|
├─ Q2 (Month 4-6): Alpha Launch
│  ├─ Application intake + OCR
│  ├─ WIPO ST.96 integration
│  ├─ ML classification service (model trained)
│  ├─ ALPHA: 10 examiners pilot
│  └─ User feedback iteration
|
├─ Q3 (Month 7-9): Examiner Workflow
│  ├─ Examiner dashboard
│  ├─ Prior art search + semantic search
│  ├─ EPO OPS integration
│  ├─ Chemical structure search (PerkinElmer)
│  └─ Examination workflow
|
└─ Q4 (Month 10-12): Private Beta
   ├─ Publication engine
   ├─ Renewal management
   ├─ PRIVATE BETA: 50 examiners
   └─ Performance + security testing (ITHC)

YEAR 2 (2026-2027): PUBLIC BETA + LIVE LAUNCH
|
├─ Q1 (Month 13-15): Public Portal
│  ├─ Public portal (patent search)
│  ├─ API gateway (open data)
│  ├─ CDN (CloudFront)
│  └─ PUBLIC BETA + GDS Service Assessment
|
├─ Q2 (Month 16-18): Live Launch
│  ├─ GDS feedback addressed
│  ├─ Load testing + final ITHC
│  ├─ LIVE LAUNCH (Month 18)
│  └─ Legacy PMS parallel running ends
|
├─ Q3 (Month 19-21): Optimization
│  ├─ Performance optimization (ML model tuning)
│  ├─ Examiner training program (200 staff)
│  ├─ User feedback incorporation
│  └─ BR-001 validation (18→12 month examination time)
|
└─ Q4 (Month 22-24): Stabilization
   ├─ Legacy PMS decommissioning plan
   ├─ IPO operations handover
   ├─ Runbooks + documentation
   └─ Post-live support (12 months)

YEAR 3 (2027-2028): EVOLUTION + REVENUE
|
├─ ML Commercialization: License ML model to other patent offices (£500K/year revenue)
├─ API Marketplace: Premium API tiers for patent data (£200K/year revenue)
├─ Open Source: Publish WIPO adapters, semantic search on GitHub (thought leadership)
├─ GOV.UK One Login: Migrate from GOV.UK Verify (£50K)
├─ Commoditization Evaluation: Monitor ML/semantic search vendor products; plan migration by 2028
└─ Platform Reuse: Extend patent platform to trademarks/designs (£3M+ savings)
```

---

## 13. Conclusion

### 13.1 Strategic Summary

This Wardley Map provides a **strategic procurement framework** for the UK IPO Patent Management System, classifying 37 components across the evolution axis (Genesis → Custom → Product → Commodity) to inform build vs buy vs reuse decisions:

- **BUILD (38%, £6.44M)**: 12 custom components (0.25-0.50 evolution) where IPO has competitive advantage: ML patent classification (0.35), semantic search (0.42), examination workflow (0.38), WIPO/EPO integrations (0.45-0.68)
- **BUY (21%, £2.06M)**: 11 product-stage components (0.50-0.75) via G-Cloud 14: OCR (0.72), chemical search (0.68), authentication (0.68), publication/renewal tools (0.55-0.58)
- **REUSE (0%, £0 / £570K savings)**: 4 GOV.UK services (0.75-0.92) that are free: GOV.UK Pay (0.90), Notify (0.92), Design System (0.75), Verify (0.68)
- **COMMODITY (12%, £1.12M)**: 10 AWS managed services (0.85-0.95): EKS, RDS, S3, Redis, OpenSearch, CloudWatch

**Total Savings vs All-Custom Build**: £4.92M (£570K reuse + £1.2M buy vs build + £3.15M commodity cloud vs on-premise)

**Strategic Alignment**:
- **Technology Code of Practice (TCoP)**: 81% compliance; Point 8 (Reuse) and Point 11 (Purchasing Strategy) directly addressed by this Wardley Map
- **GDS Service Standard**: Point 13 ("Use common platforms") drives reuse of GOV.UK Pay/Notify/Design System; Point 11 ("Choose right tools") informed by evolution-based classification
- **G-Cloud 14 Procurement**: Product-stage components (0.50-0.75) procured via G-Cloud Direct Award; custom components (0.25-0.50) built in-house; commodity (0.75+) via AWS utility services

### 13.2 Key Strategic Insights

1. **62% of functionality can be purchased or reused** (GOV.UK services, G-Cloud products, AWS managed services), focusing IPO's £6.44M custom build investment on truly differentiated patent-specific capabilities (ML classification, semantic search, examination workflow).

2. **GOV.UK services deliver £570K savings** by reusing mature government platforms (Pay, Notify, Design System) rather than building custom alternatives—a direct application of TCoP Point 8 (Reuse).

3. **ML patent classification (0.35 Custom) provides 3-year competitive advantage** before likely commoditization by vendors (Clarivate, PatSnap); IPO should plan to license/sell ML model to recoup £980K investment and generate £500K/year revenue.

4. **Legacy PMS integration (0.35 Custom) is critical path risk** requiring dedicated team (2 FTE), 6-month integration window, and parallel running; no vendor has expertise in 40-year-old IPO systems, justifying £620K custom build.

5. **Strategic evolution monitoring required**: ML classification (0.35) and semantic search (0.42) may evolve to Product stage (0.65+) by 2028, enabling migration to commercial products and £400K+/year maintenance savings.

### 13.3 Next Steps for Procurement

1. **Issue RFP with this Wardley Map**: Include procurement strategy map in Statement of Work (SOW) Section 4 to guide vendors on which components to bid for (BUY category only, not BUILD/REUSE)

2. **Evaluate vendor proposals against evolution stages**: Vendors proposing to build commodity components (e.g., custom payment gateway instead of GOV.UK Pay) should be questioned on strategic rationale and value for money

3. **Update Wardley Map quarterly**: Track component evolution during 18-month delivery; adjust build/buy decisions as technology matures; monitor vendor ML/semantic search products for commoditization

4. **Use map for change control**: If scope changes arise (e.g., new requirements), classify new components by evolution stage to determine build/buy/reuse strategy and cost impact

5. **Share with evaluation committee**: All evaluators (Enterprise Architect, CISO, Product Owner) should reference this Wardley Map when scoring vendor proposals to ensure strategic alignment

---

**Document Version**: 1.0
**Generated**: 2025-10-15 via ArcKit Wardley Mapping Tool
**Next Review**: 2026-01-15 (Post-Alpha Phase, update component evolution based on user feedback)
**Wardley Map Visualization**: [OnlineWardleyMaps.com](#) (paste code from Section 1.1)

---

**Appendices**:

- **Appendix A**: Component Evolution Calculation Methodology (how 0.35, 0.42, etc. scores were determined)
- **Appendix B**: Build vs Buy Scoring Matrix (60-point criteria for each component)
- **Appendix C**: G-Cloud 14 Vendor Mapping (which G-Cloud services align with Product-stage components)
- **Appendix D**: 3-Year Evolution Predictions (detailed rationale for 2028 movement forecasts)
- **Appendix E**: Wardley Map Glossary (Genesis, Custom, Product, Commodity definitions for stakeholders)

---

**Related Documents**:
- Requirements.md (BR-001 to BR-006, FR-001 to FR-010, NFR-001 to NFR-006)
- Statement of Work (SOW) (RFP-IPO-PMS-2025-001, £7M budget, 18-month delivery)
- Technology Code of Practice (TCoP) Assessment (81% compliance, 105/130 points)
- Vendor Evaluation Criteria (28 mandatory qualifications, 60% technical / 40% cost)
- Architecture Principles (21 principles including Cloud-First, API-First, Reuse GOV.UK Services)
