# Statement of Work (SOW): Patent Management System for the UK Intellectual Property Office

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.sow`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-SOW-v2.0 |
| **Document Type** | Statement of Work / Request for Proposal (RFP) |
| **Project** | Patent Management System for the UK Intellectual Property Office (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | OPEN FOR TENDER |
| **Version** | 2.0 |
| **Created Date** | 2025-10-15 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | On-Demand |
| **Next Review Date** | 2026-02-28 |
| **Owner** | Tim Moss (Senior Responsible Owner) |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Procurement Team, Architecture Team, Digital Marketplace |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-15 | ArcKit AI | Initial creation from `/arckit.sow` command | [PENDING] | [PENDING] |
| 2.0 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 format; aligned with requirements.md v2.0 | [PENDING] | [PENDING] |

## Document Purpose

This Statement of Work (SOW) defines the requirements, deliverables, evaluation criteria, and contract terms for the procurement of a modern Patent Management System. It serves as the Request for Proposal (RFP) document for vendor procurement via G-Cloud 14 Framework.

---

## Procurement Details

| Field | Value |
|-------|-------|
| **Contracting Authority** | UK Intellectual Property Office (IPO) |
| **Procurement Framework** | G-Cloud 14 Framework |
| **Submission Deadline** | 2025-11-30 17:00 GMT |
| **Contract Award Date** | 2026-01-15 |
| **Contract Start Date** | 2026-02-01 |

---

## Executive Summary

### Project Overview

The UK Intellectual Property Office (IPO) seeks a qualified supplier to design, develop, and deliver a modern Patent Management System (PMS) that will transform how the UK manages patent applications from initial filing through to grant, maintenance, and eventual expiry.

The current patent infrastructure relies on legacy systems developed over 20+ years, resulting in fragmented workflows, processing delays, and limited integration with international patent offices. This modernization initiative will replace these systems with a cloud-native, API-first platform that delivers:

- **Operational Efficiency**: Reduce average time to first office action from 18 months to 12 months
- **Cost Savings**: Achieve £1.75M annual operational savings through cloud optimization and automation
- **International Integration**: Seamless data exchange with WIPO, EPO, and IP5 offices using WIPO ST.96 standards
- **Public Service Excellence**: 99.95% availability for public-facing services with WCAG 2.2 Level AA accessibility
- **Regulatory Compliance**: Full compliance with UK Government Technology Code of Practice, GDPR, and OFFICIAL-SENSITIVE security classification

### Business Context

The IPO is the official government body responsible for intellectual property rights in the United Kingdom, processing approximately 50,000 patent applications annually. The modernization directly supports the UK's commitment to innovation, economic growth, and international collaboration in intellectual property protection.

By improving processing efficiency, reducing examination backlogs from 15,000 to 5,000 applications, and enhancing public access to patent information, the IPO will better serve inventors, businesses, and the broader innovation ecosystem.

### Contract Value and Duration

- **Total Contract Value**: �7,000,000 (inclusive of all costs)
- **Contract Duration**: 18 months (from contract signature to go-live)
- **Implementation Timeline**: 14 months development + 4 months transition/stabilization
- **Warranty Period**: 90 days post-go-live (defect remediation at no additional cost)
- **Optional Support Period**: 24 months post-implementation support (priced separately)

### Budget Breakdown

| Category | Amount (�) |
|----------|-----------|
| Development & Implementation | 3,500,000 |
| Architecture & Design | 400,000 |
| User Research & Accessibility | 250,000 |
| Security & Compliance (ITHC, Cyber Essentials Plus) | 500,000 |
| Data Migration & Historical Digitization | 800,000 |
| Training & Knowledge Transfer | 350,000 |
| Project Management & Governance | 500,000 |
| Contingency (15%) | 700,000 |
| **Total** | **7,000,000** |

### Key Dates

| Milestone | Date |
|-----------|------|
| RFP Issued | 2025-10-15 |
| Clarification Questions Deadline | 2025-11-10 |
| Proposal Submission Deadline | 2025-11-30 |
| Supplier Presentations (Shortlist) | 2025-12-10 to 2025-12-15 |
| Contract Award Notification | 2026-01-15 |
| Contract Signature | 2026-02-01 |
| Requirements Review Gate | 2026-02-28 |
| High-Level Design (HLD) Review Gate | 2026-03-31 |
| Detailed Design (DLD) Review Gate | 2026-05-15 |
| Alpha Phase Complete | 2026-06-30 |
| Private Beta Launch | 2026-09-30 |
| Public Beta Launch | 2026-11-30 |
| Production Go-Live | 2027-03-15 |
| Warranty Period End | 2027-06-15 |

---

## 1. Scope of Work

### 1.1 Overview

The successful supplier will deliver a comprehensive Patent Management System covering the complete patent lifecycle from application filing through to grant, renewal, opposition, and expiry. The solution must integrate with international patent offices (WIPO, EPO, IP5), government digital services (GOV.UK Verify, GOV.UK Pay, GOV.UK Notify), and provide public-facing APIs for open data access.

### 1.2 In Scope

The supplier is responsible for delivering the following capabilities:

#### 1.2.1 Patent Application Intake
- Multi-channel filing (online portal, REST API, paper mail digitization)
- Support for all filing routes: direct UK filing, PCT national phase, priority claims, divisional applications
- Document upload and validation (specifications, claims, drawings, abstracts)
- Automated validation of application completeness
- Filing receipt generation and confirmation via email/SMS

#### 1.2.2 Patent Classification
- Automated CPC/IPC classification using machine learning models
- Classification suggestion with confidence scores
- Examiner review and approval workflow
- Historical classification correction and reclassification capability
- Integration with EPO and WIPO classification databases

#### 1.2.3 Prior Art Search Platform
- Semantic search across UK, EPO, USPTO, JPO, KIPO, CNIPA patent databases
- Non-patent literature search (academic journals, technical publications)
- Chemical structure search for pharmaceutical patents
- Image-based search for patent drawings similarity
- Patent family search (INPADOC integration)
- Search result ranking by technical relevance
- Export of search results in multiple formats (PDF, CSV, BibTeX)

#### 1.2.4 Examiner Workflow and Case Management
- Examiner dashboard with assigned applications, pending actions, and deadlines
- Case detail view with full application history and correspondence
- Office action creation and issuance
- Examiner notes and internal collaboration tools
- Productivity metrics and workload balancing
- Integration with prior art search and classification tools

#### 1.2.5 Applicant Prosecution and Self-Service Portal
- Secure applicant portal with GOV.UK Verify authentication
- Real-time application status tracking
- Response to office actions with document upload
- Amendment submission and version control
- Payment of filing fees and renewal fees via GOV.UK Pay
- Email/SMS notifications via GOV.UK Notify
- Bulk portfolio management for patent attorneys

#### 1.2.6 Publication System
- Automated 18-month publication scheduling
- A-publication generation (application publication)
- B-publication generation (grant publication)
- PDF generation with patent office formatting standards
- Publication to public website and bulk download
- Integration with WIPO and EPO publication systems

#### 1.2.7 Grant and Refusal Decision Processing
- Grant certificate generation
- Refusal decision letters
- Legal status updates and register maintenance
- Integration with patent register and public search

#### 1.2.8 Renewal Fee Management
- Automated renewal deadline tracking (annual fees for up to 20 years)
- Reminder notifications at 6, 3, 1 months, and 1 week before deadline
- Payment processing via GOV.UK Pay
- Grace period management with late fee calculation
- Automatic lapsing for non-payment
- Renewal certificate generation

#### 1.2.9 Opposition Proceedings Workflow
- Third-party opposition filing and case management
- Opposition hearing scheduling
- Decision recording and publication
- Integration with main patent case file

#### 1.2.10 Public Patent Search Portal
- Public-facing search interface with GOV.UK Design System
- Advanced search (text, classification, applicant, date ranges)
- Patent detail pages with full-text and drawings
- WCAG 2.2 Level AA accessibility compliance
- Mobile-responsive design
- High availability (99.95% uptime)

#### 1.2.11 Open Data APIs
- RESTful API with OpenAPI 3.0 specification
- Public API tier (rate-limited, no authentication)
- Registered API tier (higher limits with free API key)
- Commercial API tier (SLA-backed)
- Bulk data downloads (JSON, XML, CSV formats)
- Open Government Licence (OGL) applied to published data

#### 1.2.12 Integration with External Systems
- **WIPO**: PCT application intake via ePCT, WIPO ST.96 XML exchange
- **EPO**: Patent family data synchronization, EPO Open Patent Services integration
- **IP5 Offices**: Prior art data feeds from USPTO, JPO, KIPO, CNIPA
- **GOV.UK Verify**: User authentication (SAML 2.0)
- **GOV.UK Pay**: Payment processing (REST API)
- **GOV.UK Notify**: Email and SMS notifications (REST API)

#### 1.2.13 Historical Patent Digitization
- OCR processing of historical paper patents (estimated 500,000 documents)
- Image enhancement and cleanup
- Full-text extraction with >98% accuracy
- Metadata extraction (title, applicant, date, classification)
- Quality assurance workflow
- Integration into searchable patent database

#### 1.2.14 Data Migration
- Migration of existing patent applications from legacy systems
- Data cleansing and normalization
- Historical data reconciliation
- User account migration
- Zero data loss requirement

### 1.3 Out of Scope

The following are explicitly OUT OF SCOPE for this contract:

- Trade mark management systems (separate system)
- Design rights management systems (separate system)
- Copyright registration (not applicable in UK)
- Patent attorney licensing and regulation systems
- Fee payment infrastructure (will use GOV.UK Pay)
- Email/SMS infrastructure (will use GOV.UK Notify)
- Identity and authentication infrastructure (will use GOV.UK Verify)
- Ongoing operational support beyond warranty period (separate contract)

### 1.4 Deliverables

The supplier must deliver the following artifacts:

#### 1.4.1 Architecture and Design Deliverables
- **Requirements Review Document**: Confirmation of requirements understanding with gap analysis
- **High-Level Design (HLD)**: Solution architecture with C4 diagrams, technology selections, API specifications, threat model, security controls
- **Detailed Design (DLD)**: Component design, database schemas, API contracts, sequence diagrams, workflow orchestration design
- **Architecture Decision Records (ADRs)**: Documented rationale for all major technical decisions

#### 1.4.2 Development Deliverables
- **Source Code**: Complete application source code in Git repository (GitHub Government or GitLab self-hosted)
- **Infrastructure-as-Code**: Terraform scripts for AWS infrastructure provisioning
- **CI/CD Pipelines**: Automated build, test, security scan, and deployment pipelines (GitHub Actions or GitLab CI)
- **Database Migration Scripts**: Version-controlled database schema evolution
- **Configuration Management**: Environment-specific configuration templates

#### 1.4.3 Testing Deliverables
- **Unit Tests**: Minimum 80% code coverage with automated execution in CI/CD
- **Integration Tests**: Component interaction tests with databases, message queues, external APIs
- **Contract Tests**: API contract validation between microservices
- **End-to-End Tests**: Critical patent workflows (file � classify � search � examine � grant)
- **Performance Test Results**: Load testing reports for peak capacity (500 concurrent filers, 1000 searches/min)
- **Security Test Results**: SAST/DAST scan results, penetration test (ITHC) report
- **Accessibility Test Results**: WCAG 2.2 Level AA compliance report with manual audit
- **User Acceptance Test (UAT) Plan**: Test scenarios, scripts, and results

#### 1.4.4 Security and Compliance Deliverables
- **Threat Model**: STRIDE analysis with risk ratings and mitigations
- **Security Architecture Document**: Security controls for OFFICIAL-SENSITIVE classification
- **ITHC Report**: IT Health Check penetration testing by NCSC-approved provider
- **Cyber Essentials Plus Certificate**: Certification evidence
- **Data Protection Impact Assessment (DPIA)**: GDPR compliance assessment
- **Algorithmic Transparency Recording Standard (ATRS)**: For ML-based classification and search features
- **Technology Code of Practice (TCoP) Assessment**: Compliance scorecard with evidence

#### 1.4.5 Documentation Deliverables
- **System Architecture Documentation**: C4 model diagrams (context, container, component, deployment)
- **API Documentation**: OpenAPI 3.0 specifications with developer guides
- **Administrator Guides**: System administration, user management, configuration
- **User Manuals**: Applicant portal guide, examiner desktop guide, patent attorney guide
- **Operational Runbooks**: Incident response, disaster recovery, backup/restore procedures
- **Training Materials**: Slides, videos, hands-on exercises for examiners and administrators

#### 1.4.6 Training and Knowledge Transfer
- **Train-the-Trainer Sessions**: 5 days of training for IPO technical staff
- **Examiner Training**: 10 days of classroom training for patent examiners (3 cohorts of 20 examiners each)
- **Administrator Training**: 3 days for system administrators
- **Applicant Training Materials**: Self-service video tutorials and guides
- **Technical Handover**: Architecture walkthrough, code review, operational procedures

#### 1.4.7 Go-Live Support
- **Go-Live Runbook**: Detailed cutover plan with rollback procedures
- **Hypercare Support**: 90-day warranty period with on-site support (5 FTE)
- **Defect Resolution**: P1 (critical) within 4 hours, P2 (high) within 24 hours, P3 (medium) within 5 days, P4 (low) within 30 days
- **Performance Tuning**: Post-go-live optimization to meet SLAs

---

## 2. Technical Requirements

### 2.1 Mandatory Architecture Principles

The solution MUST comply with the IPO Enterprise Architecture Principles (see Appendix A - Architecture Principles reference). Key principles include:

#### 2.1.1 Cloud-First
- Deploy on UK Government-approved cloud platforms (AWS GovCloud UK, Azure Government UK, or Google Cloud for Government)
- Data residency within UK jurisdiction for OFFICIAL-SENSITIVE data
- Infrastructure-as-Code (Terraform preferred)
- Multi-AZ deployment for resilience
- Managed services preferred over self-hosted

#### 2.1.2 API-First Integration
- All services expose RESTful APIs with OpenAPI 3.0 specifications
- OAuth 2.0 / OpenID Connect for API authentication
- Rate limiting and quota management at API gateway
- Versioned APIs with backward compatibility
- Support for WIPO ST.96 XML standard for international patent data exchange

#### 2.1.3 Security by Design (OFFICIAL-SENSITIVE)
- Government Security Classification: OFFICIAL-SENSITIVE for unpublished patent applications
- Multi-factor authentication (MFA) for all examiner and administrator access
- Encryption at rest (AES-256) and in transit (TLS 1.3+)
- Secrets management via AWS Secrets Manager or HashiCorp Vault
- Annual ITHC penetration testing by NCSC-approved provider
- Cyber Essentials Plus certification
- Structured audit logging for all access to patent data
- 24/7 protective monitoring and incident response

#### 2.1.4 Accessibility (WCAG 2.2 Level AA)
- Full compliance with Public Sector Bodies Accessibility Regulations 2018
- Keyboard navigation and screen reader support
- Sufficient color contrast (4.5:1 for normal text, 3:1 for large text)
- Accessible forms with proper labels and error messages
- Alternative text for all images and patent drawings
- Support for 400% text zoom
- External accessibility audit by qualified specialists

#### 2.1.5 Observability and Operational Excellence
- Structured JSON logging to CloudWatch or equivalent
- Prometheus-compatible metrics (RED: Rate, Errors, Duration)
- Distributed tracing with AWS X-Ray or OpenTelemetry
- Business KPI dashboards (applications filed, processing times, backlog)
- SLO-based alerting with 24/7 on-call runbooks

### 2.2 Technology Stack Requirements

#### 2.2.1 Approved Technologies
Suppliers MUST select technologies from the IPO approved list:

**Programming Languages**:
- Backend: Java 17+ (Spring Boot), Python 3.11+, TypeScript/Node.js, Go
- Frontend: TypeScript/React with GOV.UK Frontend Design System (MANDATORY for public services)

**Databases**:
- Relational: PostgreSQL 14+ (AWS RDS or Aurora PostgreSQL)
- Document: MongoDB, AWS DocumentDB
- Search: OpenSearch/Elasticsearch
- Cache: Redis (cloud-managed)
- Graph: Neo4j (for patent citation networks)

**Messaging/Streaming**:
- Apache Kafka, Amazon SQS, Amazon SNS, Amazon EventBridge

**Container Orchestration**:
- Amazon EKS (Kubernetes), AWS Lambda (serverless)

**Infrastructure-as-Code**:
- Terraform (preferred), AWS CDK

Exceptions to the approved list require documented justification with Enterprise Architect approval.

#### 2.2.2 Patent-Specific Requirements
- **OCR Engine**: High-accuracy OCR for historical patent digitization (ABBYY FineReader or equivalent with >98% accuracy)
- **Chemical Structure Search**: ChemAxon, RDKit, or equivalent for pharmaceutical patent search
- **Machine Translation**: Neural machine translation for international patent applications (Amazon Translate or equivalent)
- **ML Classification**: Machine learning framework for automated CPC/IPC classification (PyTorch, TensorFlow, or AWS SageMaker)

### 2.3 Non-Functional Requirements (NFRs)

#### 2.3.1 Performance
- **Web Application Response Time**:
  - Public-facing pages: <2 seconds (p95)
  - Applicant portal: <3 seconds (p95)
  - Examiner desktop: <1 second for case switching
  - API responses: <200ms (p95)
- **Patent Search Performance**:
  - Keyword search: <2 seconds (p95)
  - Semantic search: <5 seconds (p95)
  - Concurrent searches: 1,000 searches/minute
- **Load Capacity**:
  - Peak concurrent users: 5,000 (public search)
  - Patent filing: 1,000 applications/day (peak)
  - Public searches: 100,000 searches/day

#### 2.3.2 Availability and Resilience
- **Uptime Targets**:
  - Public-facing services: 99.95% (21.6 minutes/month downtime)
  - Applicant portal: 99.9% (43.2 minutes/month)
  - Examiner desktop: 99.5% (3.6 hours/month)
- **Disaster Recovery**:
  - RPO (Recovery Point Objective): <1 hour
  - RTO (Recovery Time Objective): <4 hours for public services
  - Multi-AZ deployment with automatic failover (<5 minutes)
  - Cross-region backup within UK for manual failover (<2 hours)
  - Quarterly disaster recovery drills with documented results

#### 2.3.3 Scalability
- Horizontal auto-scaling for application tier
- Database scaling to handle 10TB data over 10 years
- Data archival strategy (hot/warm/cold storage tiers)
- Auto-scale triggers: CPU >70% or Memory >80% scale up, CPU <30% scale down

#### 2.3.4 Security
- **Authentication**: GOV.UK Verify or Government Gateway integration (SAML 2.0)
- **MFA**: TOTP authenticator app or hardware tokens (YubiKey) for administrators
- **Session Management**: 30-minute timeout for applicants, 2-hour timeout for examiners
- **Encryption**: TLS 1.3+ in transit, AES-256 at rest
- **Vulnerability Management**:
  - SAST (SonarQube) and dependency scanning (Snyk) in CI/CD
  - Fail build on CVSS e7.0 vulnerabilities
  - Remediation SLA: Critical (24 hours), High (7 days), Medium (30 days)

#### 2.3.5 Compliance
- **UK GDPR and Data Protection Act 2018**: DPIA completed, privacy by design, data subject rights implemented
- **Government Security Classifications**: OFFICIAL-SENSITIVE controls for unpublished patents
- **Audit Logging**: 7-year retention for security logs, 25-year retention for patent access logs (immutable WORM storage)
- **Accessibility**: WCAG 2.2 Level AA with automated and manual testing
- **GDS Service Standard**: Pass Service Assessment for Beta and Live phases

### 2.4 Integration Requirements

The solution MUST integrate with the following external systems:

#### 2.4.1 WIPO Integration
- **Purpose**: Receive PCT applications entering UK national phase
- **Integration Type**: SFTP file exchange + ePCT web services
- **Data Format**: WIPO ST.96 XML
- **Authentication**: SFTP SSH key, SAML 2.0 for ePCT
- **Frequency**: Daily batch for PCT applications

#### 2.4.2 EPO Integration
- **Purpose**: Exchange patent family data, retrieve prior art
- **Integration Type**: EPO Open Patent Services (OPS) REST API
- **Authentication**: OAuth 2.0 client credentials
- **SLA**: Latency <2 seconds, availability 99.5%, rate limit 1,000 requests/day

#### 2.4.3 GOV.UK Verify Integration
- **Purpose**: User authentication
- **Integration Type**: SAML 2.0 Single Sign-On
- **SLA**: Availability 99.9%, response time <3 seconds

#### 2.4.4 GOV.UK Pay Integration
- **Purpose**: Payment processing for filing and renewal fees
- **Integration Type**: REST API
- **SLA**: Availability 99.9%, payment confirmation <5 seconds
- **Transaction Fee**: 1.75% for UK cards

#### 2.4.5 GOV.UK Notify Integration
- **Purpose**: Email and SMS notifications
- **Integration Type**: REST API
- **Notification Types**: Filing confirmations, office actions, renewal reminders, payment receipts
- **SLA**: Availability 99.9%, delivery <1 minute for email

---

## 3. Project Governance and Methodology

### 3.1 Agile Delivery Methodology

The project MUST be delivered using Agile methodologies aligned with GDS Service Manual guidance:

- **Sprints**: 2-week sprints with sprint planning, daily standups, sprint reviews, and retrospectives
- **Phases**: Alpha (prove viability), Private Beta (test with limited users), Public Beta (wider testing), Live (full production)
- **User Stories**: All requirements captured as user stories with acceptance criteria
- **Continuous Delivery**: Working software delivered incrementally with CI/CD automation
- **User Research**: Ongoing research with patent examiners, applicants, and attorneys throughout delivery

### 3.2 Architecture Review Gates

The project will undergo formal architecture review at four gates:

#### Gate 1: Requirements Review (M1 - 2026-02-28)
- **Deliverables**: Requirements review document, user stories, service blueprint
- **Reviewers**: IPO Enterprise Architect, Patent Domain Architect, Product Owner
- **Approval Criteria**: Requirements aligned with architecture principles, patent workflow requirements documented, compliance obligations identified

#### Gate 2: High-Level Design (M2 - 2026-03-31)
- **Deliverables**: HLD document, C4 diagrams, technology selections, API specifications, threat model, security controls
- **Reviewers**: IPO Enterprise Architect, Security Architect, Patent Domain Architect, Data Architect
- **Approval Criteria**: Technology from approved list, security for OFFICIAL-SENSITIVE defined, API specifications complete, threat model with mitigations, data residency confirmed

#### Gate 3: Detailed Design (M3 - 2026-05-15)
- **Deliverables**: DLD document, database schemas, API contracts, sequence diagrams, event schemas
- **Reviewers**: Patent Domain Architect, Technical Leads, Senior Engineers
- **Approval Criteria**: Database design complete, API contracts with versioning, event schemas defined, resilience patterns documented

#### Gate 4: Pre-Production (M4 - 2027-02-15)
- **Deliverables**: Infrastructure-as-Code, CI/CD pipelines, monitoring dashboards, runbooks, disaster recovery plan, ITHC report
- **Reviewers**: Site Reliability Engineers, Security Operations, Patent Domain Architect
- **Approval Criteria**: IaC peer-reviewed, CI/CD with security gates operational, observability instrumented, security hardening complete, DR tested, ITHC passed, load testing complete, accessibility audit passed, GDS Service Assessment scheduled

Each gate requires **GO** approval before proceeding to the next phase. Outcomes can be:
- **GO**: Proceed to next phase
- **GO WITH CONDITIONS**: Minor issues, must address before next gate
- **NO-GO**: Major concerns, revise and resubmit

### 3.3 Project Governance Structure

#### 3.3.1 Governance Roles
- **Senior Responsible Owner (SRO)**: IPO Chief Executive - ultimate accountability
- **Project Board**: Meets monthly, steering decisions, risk escalation
- **Product Owner**: IPO Director of Patents - requirements authority, prioritization
- **Technical Architect**: IPO Enterprise Architect - architecture oversight
- **Security Architect**: IPO CISO - security review and approval
- **Supplier Project Manager**: Day-to-day delivery management
- **Supplier Technical Lead**: Technical delivery and architecture

#### 3.3.2 Governance Meetings
- **Project Board**: Monthly, strategic decisions, budget, risks
- **Steering Committee**: Bi-weekly, tactical delivery updates, issue resolution
- **Architecture Review Board**: At each gate + ad-hoc for major decisions
- **Sprint Reviews**: Every 2 weeks, demonstrate working software
- **Risk Review**: Monthly, risk register review and mitigation tracking

### 3.4 Risk Management

The supplier MUST maintain a risk register with the following categories:

| Risk Category | Examples | Mitigation |
|---------------|----------|------------|
| **Technical** | Technology incompatibility, performance issues | Proof-of-concept, load testing |
| **Security** | Data breach, vulnerability | Threat modeling, penetration testing |
| **Integration** | EPO/WIPO API failures | Circuit breakers, retry logic, stubs |
| **Schedule** | Delivery delays | Agile prioritization, MVP approach |
| **Resource** | Key personnel turnover | Knowledge sharing, documentation |
| **Compliance** | GDPR breach, accessibility failure | DPIA, automated testing, external audits |
| **Data Migration** | Data loss, corruption | Dry runs, checksums, rollback plan |

**Risk Reporting**:
- Monthly risk register updates to Project Board
- Critical risks escalated immediately
- Risk mitigation plans tracked with owners and deadlines

---

## 4. Vendor Qualifications

### 4.1 Mandatory Qualifications

Suppliers MUST demonstrate the following qualifications. Failure to meet any mandatory qualification will result in disqualification:

#### 4.1.1 G-Cloud Framework
- [ ] Active listing on G-Cloud 14 Framework (or successor framework)
- [ ] Pricing published on Digital Marketplace

#### 4.1.2 UK Government Experience
- [ ] Minimum 2 references for UK central government projects delivered in last 3 years
- [ ] At least 1 reference for OFFICIAL-SENSITIVE classification project
- [ ] Demonstrated experience with GDS Service Standard and Service Assessments

#### 4.1.3 Security Certifications
- [ ] Cyber Essentials Plus certification (current, within 12 months)
- [ ] ISO 27001 certification
- [ ] Evidence of successful ITHC penetration tests in last 2 years (NCSC-approved provider)

#### 4.1.4 Technical Certifications
- [ ] AWS Advanced Consulting Partner (or equivalent Azure/GCP government cloud tier)
- [ ] Minimum 3 AWS Certified Solutions Architects on proposed team
- [ ] Minimum 2 AWS Certified Security Specialists on proposed team

#### 4.1.5 Accessibility Expertise
- [ ] Evidence of WCAG 2.2 Level AA compliant projects (minimum 2 references)
- [ ] Accessibility specialists on team with recognized certifications (IAAP CPACC/WAS or equivalent)

#### 4.1.6 Patent Domain Knowledge
- [ ] Demonstrated experience in patent management, intellectual property, or legal document management systems (minimum 1 reference)
- [ ] Understanding of international patent standards (WIPO ST.96, PCT, EPO OPS)

#### 4.1.7 Financial Standing
- [ ] Company audited financial statements for last 2 years
- [ ] Minimum annual turnover of �15M (or parent company guarantee)
- [ ] Professional indemnity insurance of �10M
- [ ] Employer's liability insurance of �10M
- [ ] Public liability insurance of �10M

#### 4.1.8 Personnel Security
- [ ] Commitment to BPSS clearance for all personnel accessing IPO systems
- [ ] SC clearance for personnel accessing OFFICIAL-SENSITIVE patent data
- [ ] UK-based delivery team (majority of FTE on UK soil)

### 4.2 Desirable Qualifications

Suppliers SHOULD demonstrate the following qualifications (scored in evaluation):

- [ ] Experience with GOV.UK design system and GOV.UK services
- [ ] Prior delivery of patent examination or search systems
- [ ] Experience with WIPO ePCT integration
- [ ] Experience with EPO Open Patent Services integration
- [ ] Machine learning expertise for document classification and semantic search
- [ ] OCR and historical document digitization experience
- [ ] AWS Well-Architected Framework review experience
- [ ] DevSecOps maturity with DORA metrics tracking
- [ ] Contribution to open-source patent data projects
- [ ] Active participation in GDS community, conferences, or tech radar

---

## 5. Proposal Requirements

### 5.1 Proposal Format

Proposals MUST be submitted in the following format:

**Submission Format**: PDF, maximum file size 50MB
**Page Limit**: Maximum 100 pages (excluding appendices)
**Font**: Arial 11pt, 1.5 line spacing
**Language**: English (UK)
**Currency**: British Pounds Sterling (�)

### 5.2 Proposal Structure

Proposals MUST include the following sections:

#### 5.2.1 Executive Summary (Maximum 3 pages)
- Company overview
- Understanding of IPO requirements
- Proposed approach summary
- Value proposition
- Total contract cost (headline figure)

#### 5.2.2 Technical Approach (Maximum 30 pages)
- Solution architecture with C4 diagrams
- Technology stack selections with rationale
- Patent workflow implementation approach
- Integration strategy (WIPO, EPO, GOV.UK services)
- Security architecture for OFFICIAL-SENSITIVE classification
- Data migration strategy
- OCR and historical digitization approach
- ML/AI approach for classification and search
- Accessibility strategy (WCAG 2.2 Level AA)
- Performance and scalability approach
- Disaster recovery and business continuity

#### 5.2.3 Delivery Methodology (Maximum 10 pages)
- Agile delivery approach
- Sprint structure and cadence
- User research and testing strategy
- CI/CD pipeline approach
- DevSecOps practices
- Quality assurance strategy
- GDS Service Assessment preparation

#### 5.2.4 Project Plan and Timeline (Maximum 10 pages)
- High-level project plan with milestones
- Critical path analysis
- Resource allocation by role and sprint
- Architecture review gate preparation plans
- Risk mitigation timeline
- Dependencies and assumptions

#### 5.2.5 Team Structure and CVs (Maximum 20 pages)
- Organization chart with roles and reporting lines
- Key personnel CVs (maximum 2 pages per CV):
  - Project Manager
  - Technical Architect
  - Security Architect
  - Patent Domain Expert
  - Lead Developer (Backend)
  - Lead Developer (Frontend)
  - DevOps Lead
  - Accessibility Specialist
  - User Researcher
  - Data Migration Lead
- Commitment to personnel retention (notice period for key personnel changes)
- Escalation and backfill procedures

#### 5.2.6 Experience and References (Maximum 10 pages)
- Case studies of similar projects (minimum 3, maximum 5):
  - Project name, client, duration, budget
  - Technical summary (architecture, technology, scale)
  - Outcomes and benefits realized
  - Relevance to IPO Patent Management System
- References with contact details (minimum 3 references, all contactable):
  - Client name, project name, contact name, email, phone
  - Date of project delivery
  - Project value

#### 5.2.7 Compliance and Certifications (Maximum 5 pages)
- Evidence of Cyber Essentials Plus certification
- Evidence of ISO 27001 certification
- Evidence of AWS (or equivalent) partner tier
- Evidence of WCAG 2.2 Level AA project delivery
- GDPR and DPA 2018 compliance approach
- Security clearance commitment (BPSS, SC)

#### 5.2.8 Commercial Proposal (Maximum 10 pages)
- **Pricing Breakdown**:
  - Fixed price for each milestone (see Section 6.2)
  - Day rates for optional support period (24 months post-go-live)
  - Travel and expenses policy
  - Payment terms
- **Assumptions**: List all pricing assumptions
- **Exclusions**: Clearly state what is NOT included in pricing
- **Change Control**: Approach to managing scope changes

#### 5.2.9 Contract Terms (Maximum 5 pages)
- Acceptance of IPO standard terms and conditions OR proposed deviations with rationale
- Intellectual property ownership (IPO retains all IP rights)
- Open-source licensing approach
- Warranty terms (90-day post-go-live defect remediation)
- Liability caps and insurance
- Termination clauses

### 5.3 Appendices (Not Counted in Page Limit)

- **Appendix A**: Company registration documents
- **Appendix B**: Financial statements (last 2 years)
- **Appendix C**: Insurance certificates
- **Appendix D**: Security certifications
- **Appendix E**: Detailed CVs of proposed team (full CVs beyond 2-page summaries)
- **Appendix F**: Detailed project plan (Gantt chart or equivalent)
- **Appendix G**: Reference letters or testimonials

---

## 6. Evaluation Criteria

### 6.1 Evaluation Methodology

Proposals will be evaluated using a **60% Technical / 40% Cost** weighted scoring model.

**Stage 1: Compliance Check**
- Verify all mandatory qualifications met
- Verify proposal format and completeness
- Non-compliant proposals will be disqualified

**Stage 2: Technical Evaluation (60 points)**
- Technical Approach: 25 points
- Delivery Methodology: 10 points
- Team Capability: 15 points
- Experience and References: 10 points

**Stage 3: Cost Evaluation (40 points)**
- Lowest compliant bid = 40 points
- Other bids scored proportionally: (Lowest Price / Bid Price) � 40

**Stage 4: Shortlist Presentations**
- Top 3-5 scoring bidders invited for presentations (2-hour session)
- Presentations may adjust technical scores by �10%

**Stage 5: Contract Award**
- Highest combined score (Technical + Cost) wins contract
- IPO reserves right to negotiate with top-ranked supplier

### 6.2 Technical Scoring Criteria

#### 6.2.1 Technical Approach (25 points)

| Criterion | Points | Evaluation Focus |
|-----------|--------|------------------|
| **Solution Architecture** | 8 | Cloud-native design, microservices appropriateness, technology choices aligned with IPO standards, scalability and resilience |
| **Security Architecture** | 6 | OFFICIAL-SENSITIVE controls, threat model, encryption, audit logging, ITHC readiness |
| **Integration Strategy** | 4 | WIPO ST.96 compliance, EPO OPS integration, GOV.UK services integration, resilience patterns (circuit breakers, retries) |
| **Data Migration & Digitization** | 3 | Historical patent OCR approach, data migration with zero data loss, data quality assurance |
| **Accessibility** | 2 | WCAG 2.2 Level AA approach, automated testing, manual audits, user research with disabled users |
| **Innovation** | 2 | ML/AI for classification and search, novel approaches to patent examination efficiency, open-source contributions |

#### 6.2.2 Delivery Methodology (10 points)

| Criterion | Points | Evaluation Focus |
|-----------|--------|------------------|
| **Agile Practices** | 3 | Sprint structure, user stories, continuous delivery, alignment with GDS Service Manual |
| **Quality Assurance** | 3 | Testing strategy (unit, integration, E2E), CI/CD security gates, automated accessibility testing |
| **DevSecOps Maturity** | 2 | Infrastructure-as-Code, secrets management, SAST/DAST in CI/CD, DORA metrics tracking |
| **Risk Management** | 2 | Risk identification, mitigation strategies, contingency planning |

#### 6.2.3 Team Capability (15 points)

| Criterion | Points | Evaluation Focus |
|-----------|--------|------------------|
| **Team Structure** | 3 | Roles coverage, reporting lines, escalation procedures, co-location/remote balance |
| **Key Personnel Experience** | 8 | CVs demonstrate relevant experience (government, patent domain, security, accessibility), certifications, continuity commitment |
| **Knowledge Transfer** | 2 | Training approach, documentation, technical handover, sustainability |
| **Team Availability** | 2 | FTE commitment, UK-based team, security clearance timelines |

#### 6.2.4 Experience and References (10 points)

| Criterion | Points | Evaluation Focus |
|-----------|--------|------------------|
| **Relevant Case Studies** | 6 | Similarity to IPO project (government, OFFICIAL-SENSITIVE, patent/legal domain, scale), outcomes achieved |
| **Reference Quality** | 4 | Contactable references from UK government, positive feedback on delivery, security, accessibility |

### 6.3 Cost Scoring

**Total Contract Value** must include:
- All development, testing, and deployment costs
- Architecture and design effort
- Security compliance (ITHC, Cyber Essentials Plus)
- Data migration and OCR digitization
- Training and knowledge transfer
- Project management
- Travel and expenses
- Contingency

**Excluded from Total Contract Value** (priced separately):
- Optional 24-month support period (day rates for L1, L2, L3 support)

**Scoring Formula**:
```
Cost Score = (Lowest Bid Price / Supplier Bid Price) � 40 points
```

**Example**:
- Supplier A bids �7,000,000 � Cost Score = (7M / 7M) � 40 = 40 points
- Supplier B bids �8,500,000 � Cost Score = (7M / 8.5M) � 40 = 32.94 points
- Supplier C bids �6,500,000 � Cost Score = (6.5M / 6.5M) � 40 = 40 points (new lowest)

### 6.4 Award Decision

**Combined Score** = Technical Score (60 points max) + Cost Score (40 points max)

The supplier with the **highest combined score** will be awarded the contract, subject to:
- Successful reference checks
- Financial due diligence
- Security clearance initiation for key personnel
- Negotiation of final contract terms (if required)

IPO reserves the right to:
- Award to the second-ranked supplier if top-ranked supplier fails reference checks or due diligence
- Cancel the procurement if no suitable suppliers meet requirements
- Negotiate with top-ranked supplier to optimize value for money

---

## 7. Milestones and Payment Schedule

### 7.1 Milestone-Based Payments

Payments will be made against milestone completion with IPO acceptance. All milestones require formal sign-off by IPO Product Owner and Technical Architect.

| Milestone | Deliverables | % of Contract | Payment (�) | Target Date |
|-----------|--------------|---------------|-------------|-------------|
| **M0: Contract Signature** | Signed contract, project kick-off | 5% | 350,000 | 2026-02-01 |
| **M1: Requirements Review Gate** | Requirements review document, user stories, service blueprint, Gate 1 approval | 5% | 350,000 | 2026-02-28 |
| **M2: High-Level Design Gate** | HLD document, C4 diagrams, API specs, threat model, Gate 2 approval | 10% | 700,000 | 2026-03-31 |
| **M3: Detailed Design Gate** | DLD document, database schemas, API contracts, Gate 3 approval | 10% | 700,000 | 2026-05-15 |
| **M4: Alpha Phase Complete** | Working Alpha prototype, user research findings, technical feasibility proven | 15% | 1,050,000 | 2026-06-30 |
| **M5: Private Beta Launch** | Private Beta deployed to limited users (50 examiners, 100 applicants), UAT complete | 20% | 1,400,000 | 2026-09-30 |
| **M6: Public Beta Launch** | Public Beta with full functionality, load testing passed, ITHC passed, GDS Beta assessment passed | 15% | 1,050,000 | 2026-11-30 |
| **M7: Production Go-Live** | Production deployment, data migration complete, training complete, Gate 4 approval, GDS Live assessment passed | 15% | 1,050,000 | 2027-03-15 |
| **M8: Warranty Period End** | 90-day hypercare support, defect remediation, performance tuning, final handover | 5% | 350,000 | 2027-06-15 |
| **Total** | | **100%** | **7,000,000** | |

### 7.2 Milestone Acceptance Criteria

Each milestone requires:
- [ ] All deliverables submitted and reviewed
- [ ] Quality criteria met (testing, documentation, security scans)
- [ ] Demonstration to IPO stakeholders (where applicable)
- [ ] Formal acceptance sign-off by IPO Product Owner and Technical Architect
- [ ] Architecture Review Board approval for gate milestones (M1, M2, M3, M7)

**Milestone Rejection**: If milestone deliverables do not meet acceptance criteria:
1. IPO will provide written feedback with specific deficiencies
2. Supplier has 10 business days to remediate
3. If still not acceptable, payment withheld until remediation complete
4. Repeated milestone failures may trigger contract review or termination

### 7.3 Payment Terms

- **Invoice Submission**: Supplier submits invoice within 5 business days of milestone acceptance
- **Payment Processing**: IPO pays within 30 days of invoice receipt
- **Withholding**: IPO may withhold 10% of each payment until final acceptance (M8) to ensure quality and warranty support
- **Expenses**: Travel and expenses reimbursed monthly with receipts, subject to IPO travel policy (standard class rail, 4-star hotel max)

### 7.4 Optional Support Period Pricing

Suppliers MUST provide day rates for optional 24-month post-implementation support:

| Support Level | Response Time | Resolution Time | Required FTE | Day Rate (�) |
|---------------|---------------|-----------------|--------------|--------------|
| **L1 Support** | 15 minutes (business hours) | 4 hours (P1), 24 hours (P2) | 1 FTE | [Supplier to quote] |
| **L2 Support** | 30 minutes | 24 hours (P1), 5 days (P2) | 0.5 FTE | [Supplier to quote] |
| **L3 Support** | 2 hours | 5 days (P1), 30 days (P2) | 0.25 FTE | [Supplier to quote] |
| **Enhancement** | N/A | Agreed per change | On-demand | [Supplier to quote] |

**Support Hours**: 08:00-18:00 Monday-Friday (UK business hours), excluding UK bank holidays

**Out-of-Hours Support** (optional): 24/7 support for P1 incidents, quoted separately

---

## 8. Contract Terms and Conditions

### 8.1 Intellectual Property

**IP Ownership**: All intellectual property created under this contract, including but not limited to source code, documentation, architecture designs, and data models, SHALL be owned by the UK Intellectual Property Office.

**Open Source**: The supplier MUST use open-source licenses approved by IPO (MIT, Apache 2.0, BSD). Copyleft licenses (GPL, AGPL) are prohibited for proprietary IPO services but acceptable for infrastructure tooling.

**Third-Party Components**: Supplier must provide Software Bill of Materials (SBOM) listing all third-party dependencies with licenses. IPO retains right to reject incompatible licenses.

**Code Publication**: IPO intends to publish source code as open-source under MIT License after go-live (with security review). Supplier must design code with this intent.

### 8.2 Warranties

**Performance Warranty**: Supplier warrants that the solution will meet all functional and non-functional requirements specified in this SOW for 90 days post-go-live.

**Defect Remediation**: During warranty period, supplier will remediate defects at no additional cost:
- **P1 (Critical)**: System down, data loss � 4-hour response, 24-hour resolution
- **P2 (High)**: Major function unavailable � 8-hour response, 5-day resolution
- **P3 (Medium)**: Minor function issue � 24-hour response, 30-day resolution
- **P4 (Low)**: Cosmetic issue � 48-hour response, 90-day resolution

**Professional Standards**: Supplier warrants that all work will be performed to professional standards by qualified personnel.

### 8.3 Liability and Insurance

**Liability Cap**: Supplier's aggregate liability capped at 100% of total contract value (�7,000,000), except for:
- Fraud, gross negligence, or willful misconduct (unlimited liability)
- Data protection breaches (unlimited liability)
- Intellectual property infringement (unlimited liability)

**Insurance Requirements**:
- Professional Indemnity: �10,000,000
- Employer's Liability: �10,000,000
- Public Liability: �10,000,000
- Cyber Liability: �5,000,000

Insurance certificates must be provided annually throughout contract and warranty period.

### 8.4 Data Protection and Security

**GDPR Compliance**: Supplier will process personal data only as instructed by IPO and will comply with UK GDPR and Data Protection Act 2018.

**Data Processing Agreement**: Supplier will sign IPO standard Data Processing Agreement (DPA).

**Data Breach Notification**: Supplier must notify IPO within 4 hours of discovering a personal data breach.

**Data Residency**: All OFFICIAL-SENSITIVE data must remain within UK jurisdiction. No cross-border data transfers without IPO written consent.

**Security Clearance**: Personnel accessing OFFICIAL-SENSITIVE data require SC clearance. All personnel require BPSS clearance minimum. Supplier responsible for clearance costs.

**Security Incident Reporting**: Supplier must report security incidents within 1 hour to IPO CISO.

### 8.5 Termination

**Termination for Convenience**: IPO may terminate contract with 90 days written notice. IPO will pay for work completed to date plus reasonable wind-down costs.

**Termination for Cause**: IPO may terminate immediately if:
- Supplier materially breaches contract and fails to remedy within 30 days
- Supplier becomes insolvent or enters administration
- Supplier commits fraud or gross negligence
- Supplier suffers data breach due to negligence

**Exit Management**: Upon termination, supplier will:
- Provide complete knowledge transfer within 30 days
- Hand over all source code, documentation, infrastructure access
- Provide 90 days of transition support (paid at day rates)
- Return or securely delete all IPO data

### 8.6 Change Control

**Change Request Process**:
1. Either party may submit change request with impact assessment
2. Joint review of scope, cost, and timeline impact
3. IPO Product Owner approval required for acceptance
4. Formal change order issued with updated milestones and budget

**Minor Changes**: Changes <�10,000 or <5 days effort may be approved via email without formal change order.

**Major Changes**: Changes >�50,000 require Project Board approval.

### 8.7 Dispute Resolution

**Escalation Path**:
1. **Level 1**: Project Managers attempt resolution (5 business days)
2. **Level 2**: Escalate to Project Board (10 business days)
3. **Level 3**: Executive escalation (CIO/CEO level, 20 business days)
4. **Level 4**: Mediation via Centre for Effective Dispute Resolution (CEDR)
5. **Level 5**: Litigation in UK courts (England and Wales jurisdiction)

**Continuity During Disputes**: Supplier must continue performing during dispute resolution unless dispute relates to payment or safety.

### 8.8 Key Personnel

**Key Personnel**: The following roles are designated as key personnel and require 60 days notice for any changes:
- Project Manager
- Technical Architect
- Security Architect

**IPO Approval**: Replacement key personnel require IPO written approval with CV review.

**Retention**: Supplier commits to retaining key personnel for duration of contract. Replacement due to unavoidable circumstances (resignation, illness) permitted with immediate notification and backfill plan.

### 8.9 Compliance with Laws

Supplier will comply with all applicable UK laws including but not limited to:
- Patents Act 1977 (and amendments)
- UK GDPR and Data Protection Act 2018
- Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018
- Equality Act 2010
- Health and Safety at Work Act 1974
- Freedom of Information Act 2000
- Bribery Act 2010

---

## 9. Submission Instructions

### 9.1 Submission Deadline

**Deadline**: 2025-11-30 17:00 GMT

**Late Submissions**: Will NOT be accepted under any circumstances. IPO email server timestamp will be used as official submission time.

### 9.2 Submission Method

**Email Submission**:
- **To**: procurement@ipo.gov.uk
- **Subject**: "RFP Response: Patent Management System - [Supplier Company Name]"
- **Attachments**: Single PDF file (max 50MB) + separate Appendices PDF (if needed)

**Alternative Submission** (for large files >50MB):
- Upload to IPO secure file transfer: https://transfer.ipo.gov.uk
- Email notification to procurement@ipo.gov.uk with download link

### 9.3 Clarification Questions

Suppliers may submit clarification questions via email:

**Email**: procurement-questions@ipo.gov.uk
**Subject**: "Clarification: Patent Management System RFP - [Your Company Name]"
**Deadline**: 2025-11-10 17:00 GMT

**Response**: IPO will publish anonymized questions and answers to all registered suppliers by 2025-11-15.

**Supplier Registration**: Suppliers must register intent to bid by emailing procurement@ipo.gov.uk by 2025-10-25 to receive Q&A updates and amendments.

### 9.4 Supplier Presentations

**Shortlist Invitations**: Top 3-5 scoring suppliers will be invited to present on 2025-12-10 to 2025-12-15.

**Presentation Format**:
- **Duration**: 2 hours (90 minutes presentation + 30 minutes Q&A)
- **Location**: IPO offices, Newport, Wales OR virtual via Microsoft Teams
- **Attendees**: Maximum 6 supplier representatives
- **Content**: Technical architecture walkthrough, team introduction, live demo (optional), Q&A

**Presentation Scoring**: May adjust technical scores by �10% based on presentation quality, team capability demonstration, and Q&A responses.

### 9.5 Confidentiality

All information provided in this SOW is confidential and must not be disclosed to third parties without IPO written consent.

Supplier proposals will be treated as commercially confidential. However, IPO is subject to Freedom of Information Act 2000 and may be required to disclose information if FOI request received. Suppliers should clearly mark any genuinely commercially sensitive information.

---

## 10. Appendices

### Appendix A: IPO Enterprise Architecture Principles (Reference)

The complete IPO Enterprise Architecture Principles document is available separately. Key principles summarized:

1. **Cloud-First**: AWS GovCloud (UK), data residency, managed services
2. **API-First**: OpenAPI 3.0, OAuth 2.0, WIPO ST.96 compliance
3. **Security by Design**: OFFICIAL-SENSITIVE, MFA, encryption, ITHC, Cyber Essentials Plus
4. **Accessibility**: WCAG 2.2 Level AA mandatory
5. **Observability**: Logging, metrics, tracing, business KPIs
6. **Data Sovereignty**: UK jurisdiction, GDPR, data classification
7. **Patent Data Quality**: >98% OCR accuracy, semantic search, international standards
8. **Open Data**: Public APIs, Open Government Licence
9. **Approved Tech Stack**: Java/Python/TypeScript, PostgreSQL, Kafka, EKS
10. **Infrastructure as Code**: Terraform, immutable infrastructure
11. **Microservices**: Bounded contexts aligned with patent workflows
12. **Resilience**: 99.95% availability, circuit breakers, DR with RPO <1h, RTO <4h
13. **CI/CD**: Automated testing, SAST/DAST, 80% coverage
14. **Testing**: Unit, integration, E2E, performance, security, accessibility
15. **FinOps**: Cost tagging, optimization, showback
16. **Audit Logging**: 7-year retention, WORM storage, SIEM integration
17. **FOI Compliance**: Data design for transparency
18. **GDS Service Standard**: 18 points, Service Assessments at Beta and Live
19. **GOV.UK Design System**: Mandatory for public services
20. **International Standards**: WIPO ST.96, EPO OPS, PCT
21. **Examination Automation**: ML classification, AI search, ATRS compliance

**Full Document**: Contact procurement@ipo.gov.uk for complete principles document.

### Appendix B: Requirements Document (Reference)

The detailed requirements document (1000 lines) is available separately. It includes:
- 6 Business Requirements (processing efficiency, cost reduction, international integration, digital transformation, open data, compliance)
- 8 Functional Requirements (filing, classification, search, examiner workflow, applicant portal, publication, renewal, public API)
- 20+ Non-Functional Requirements (performance, availability, scalability, security, compliance, maintainability)
- 5 Integration Requirements (EPO, WIPO, GOV.UK Verify, GOV.UK Pay, GOV.UK Notify)
- Data models and retention policies
- Budget: �7M capital, �1.7M annual operational, �12.1M 3-year TCO

**Full Document**: Contact procurement@ipo.gov.uk for complete requirements document.

### Appendix C: Technology Code of Practice (TCoP) Assessment

The TCoP assessment identifies compliance gaps that the solution must address:

**Overall Compliance**: 81% (105/130 points) - GOOD with minor gaps

**Critical Gaps to Address**:
1. **Sustainability (TCoP Point 12)**: Carbon impact assessment required, energy-efficient architecture
2. **Open Source (TCoP Point 3)**: Code publication strategy, open-source licensing
3. **Service Standard (TCoP Point 13)**: Schedule GDS Service Assessments for Beta and Live phases

**Full Assessment**: Contact procurement@ipo.gov.uk for complete TCoP assessment.

### Appendix D: IPO Standard Terms and Conditions

IPO standard government contract terms available at: https://www.ipo.gov.uk/procurement/standard-terms

Key terms include:
- Crown Commercial Service framework terms (G-Cloud 14)
- Public Contracts Regulations 2015 compliance
- GDPR Data Processing Agreement template
- Security and clearance requirements
- Payment terms (30 days)
- Dispute resolution and jurisdiction (England and Wales)

### Appendix E: Glossary

| Term | Definition |
|------|------------|
| **ATRS** | Algorithmic Transparency Recording Standard - UK government standard for AI/algorithm transparency |
| **BPSS** | Baseline Personnel Security Standard - UK security clearance |
| **CPC** | Cooperative Patent Classification - international patent classification system |
| **DLD** | Detailed Design Document |
| **DPIA** | Data Protection Impact Assessment - GDPR requirement |
| **EPO** | European Patent Office |
| **GDS** | Government Digital Service - UK government digital transformation agency |
| **HLD** | High-Level Design Document |
| **IPC** | International Patent Classification |
| **ITHC** | IT Health Check - UK government penetration testing standard |
| **NCSC** | National Cyber Security Centre - UK government cyber security authority |
| **OCR** | Optical Character Recognition |
| **OGL** | Open Government Licence |
| **OPS** | Open Patent Services - EPO API |
| **PCT** | Patent Cooperation Treaty - WIPO international patent filing treaty |
| **SC** | Security Clearance - UK government security clearance level |
| **SIEM** | Security Information and Event Management |
| **ST.96** | WIPO Standard 96 - XML standard for patent data exchange |
| **TCoP** | Technology Code of Practice - UK government technology standards |
| **WCAG** | Web Content Accessibility Guidelines |
| **WIPO** | World Intellectual Property Organization |
| **WORM** | Write-Once-Read-Many - immutable storage |

### Appendix F: Contact Information

**Procurement Enquiries**:
- Email: procurement@ipo.gov.uk
- Phone: +44 (0)1633 814000

**Technical Enquiries** (during clarification period only):
- Email: procurement-questions@ipo.gov.uk

**Contract Authority**:
UK Intellectual Property Office
Concept House
Cardiff Road
Newport
South Wales
NP10 8QQ
United Kingdom

**Contracting Authority DUNS Number**: 12-345-6789 (placeholder)

---

## 11. Declaration and Signatures

By submitting a proposal in response to this Statement of Work, the supplier confirms:

- [ ] All information provided is accurate and complete
- [ ] The supplier meets all mandatory qualifications
- [ ] The supplier accepts IPO standard terms and conditions (or has clearly documented proposed deviations)
- [ ] The supplier commits to BPSS and SC clearance for personnel
- [ ] The supplier commits to Cyber Essentials Plus and ISO 27001 certifications
- [ ] The supplier understands the requirement for OFFICIAL-SENSITIVE security classification
- [ ] The supplier agrees to IPO intellectual property ownership of all deliverables
- [ ] Pricing is fixed for milestones and valid for 180 days from submission deadline
- [ ] The supplier has no conflicts of interest with IPO or UK government

**Supplier Authorized Signatory**:

Name: _______________________________

Title: _______________________________

Company: _______________________________

Signature: _______________________________

Date: _______________________________

---

**End of Statement of Work**

---

**Generated by**: ArcKit `/arckit.sow` command
**Generated on**: 2026-01-26 15:00 GMT
**ArcKit Version**: 0.11.2
**Project**: Patent Management System for the UK Intellectual Property Office (Project 001)
**AI Model**: claude-opus-4-5-20251101
**Generation Context**: Updated from v1.0 to template v0.11.2 format; aligned with requirements.md v2.0 (51 requirements, £1.75M annual savings)

---

**Document Version**: 2.0
**Next Steps**:
1. Supplier registration by 2025-10-25
2. Clarification questions by 2025-11-10
3. Proposal submission by 2025-11-30
4. Contract award by 2026-01-15

**For IPO Internal Use Only**:
- [ ] SOW reviewed by Enterprise Architect: _________________ Date: _______
- [ ] SOW reviewed by CISO: _________________ Date: _______
- [ ] SOW reviewed by Procurement: _________________ Date: _______
- [ ] SOW approved by Product Owner: _________________ Date: _______
- [ ] SOW approved by SRO (Chief Executive): _________________ Date: _______
