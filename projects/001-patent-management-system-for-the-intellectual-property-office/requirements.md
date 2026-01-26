# Project Requirements: Patent Management System for the UK Intellectual Property Office

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.requirements`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-REQ-v2.0 |
| **Document Type** | Business and Technical Requirements |
| **Project** | Patent Management System for IPO (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 2.0 |
| **Created Date** | 2025-10-15 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Enterprise Architecture Team |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Project Team, Architecture Team, IPO Executive Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-15 | ArcKit AI | Initial creation from `/arckit.requirements` command | PENDING | PENDING |
| 2.0 | 2026-01-26 | ArcKit AI | Updated to align with ArcKit template v0.11.2 | PENDING | PENDING |

## Document Purpose

This document defines the comprehensive business, functional, non-functional, data, and integration requirements for the UK Intellectual Property Office Patent Management System modernization. It serves as the authoritative source for:
- Vendor RFP evaluation criteria
- Architecture design decisions
- Test case development
- Stakeholder sign-off and acceptance criteria

---

## Executive Summary

### Business Context

The UK Intellectual Property Office (IPO) is the official government body responsible for intellectual property rights in the United Kingdom. The current patent management infrastructure relies on legacy systems developed over the past 20+ years, resulting in fragmented workflows, manual processes, and limited integration with international patent offices.

This Patent Management System (PMS) modernization initiative aims to transform patent application processing, examination, publication, and lifecycle management through a cloud-native, API-first platform. The system must handle the complete patent lifecycle from initial filing through grant, renewal, opposition, and eventual expiry, while maintaining compliance with UK patent law, international treaties (PCT, EPC), and UK Government technology standards.

The modernization directly supports the UK's commitment to innovation, economic growth, and international collaboration in intellectual property protection. By improving processing efficiency, reducing examination backlogs, and enhancing public access to patent information, the IPO can better serve inventors, businesses, and the broader innovation ecosystem.

### Objectives

- **Modernize Patent Workflows**: Replace legacy systems with cloud-native platform reducing patent examination time by 30%
- **International Integration**: Seamless data exchange with WIPO, EPO, and IP5 offices using international standards (WIPO ST.96)
- **Public Service Excellence**: Provide 24/7 public patent search, filing, and status tracking with 99.95% availability
- **Regulatory Compliance**: Full compliance with UK Government Technology Code of Practice, GDPR, and accessibility standards
- **Operational Efficiency**: Reduce operational costs by £2M annually through automation and cloud optimization

### Expected Outcomes

- **Processing Time Reduction**: Average time to first office action reduced from 18 months to 12 months (33% improvement)
- **Cost Savings**: £2M annual operational cost reduction through cloud efficiency and automation
- **User Satisfaction**: Achieve 85%+ satisfaction score from patent applicants and examiners
- **Backlog Reduction**: Reduce examination backlog from 15,000 to 5,000 applications within 24 months
- **Digital Adoption**: 90% of patent applications filed electronically (up from 65%)
- **International Competitiveness**: Match or exceed processing times of EPO and USPTO

### Project Scope

**In Scope**:
- Patent application intake (all filing routes: direct UK, PCT national phase, priority claims)
- Automated classification (CPC/IPC) with ML-assisted assignment
- Prior art search platform (UK, international, and non-patent literature)
- Examiner workflow and case management
- Applicant prosecution and correspondence management
- Publication system (18-month publication, grant publication)
- Grant and refusal decision processing
- Renewal fee management and legal status tracking
- Opposition proceedings workflow
- Public patent search portal and open data APIs
- Integration with WIPO, EPO, and IP5 offices
- Historical patent digitization and OCR processing
- Applicant self-service portal

**Out of Scope**:
- Trade mark management (separate system)
- Design rights management (separate system)
- Copyright registration (not registered in UK)
- Patent attorney licensing and regulation
- Fee payment infrastructure (will integrate with GOV.UK Pay)
- Email/SMS notifications (will integrate with GOV.UK Notify)

---

## Stakeholders

| Stakeholder | Role | Organization | Involvement Level |
|-------------|------|--------------|-------------------|
| Tim Moss | Chief Executive | IPO | Executive Sponsor, Decision maker |
| Sarah Williams | Director of Patents | IPO Patents Directorate | Product Owner, Requirements definition |
| James Chen | Senior Patent Examiner | IPO Patents Directorate | User representative, UAT lead |
| Dr. Emily Roberts | Enterprise Architect | IPO Technology | Technical oversight, Architecture review |
| Michael Brown | CISO | IPO Security | Security review, Risk assessment |
| Laura Davies | Data Protection Officer | IPO Compliance | GDPR compliance, DPIA review |
| David Thompson | Head of International Cooperation | IPO International | WIPO/EPO integration requirements |
| Sophie Martin | User Research Lead | GDS (seconded to IPO) | User research, Accessibility testing |
| Patent Applicants | External users | Industry, Inventors | User acceptance, Feedback |
| Patent Attorneys | Professional representatives | Private sector | Requirements input, UAT |

---

## Business Requirements

### BR-001: Patent Processing Efficiency

**Description**: Reduce average time to first office action from 18 months to 12 months through workflow automation, ML-assisted classification, and examiner productivity tools.

**Rationale**: Current processing times exceed those of comparable IP offices (EPO: 14 months, USPTO: 16 months), impacting UK competitiveness. Delays frustrate applicants and create uncertainty for innovation investment decisions.

**Success Criteria**:
- Average time to first office action ≤ 12 months (measured monthly)
- 90th percentile processing time ≤ 18 months
- Examination backlog reduced to <5,000 applications
- Examiner productivity increased by 25% (applications processed per examiner per year)

**Priority**: MUST_HAVE

**Stakeholder**: Sarah Williams (Director of Patents) — addresses Goal G-1 from Stakeholder Analysis

**Aligns with Principle**: Scalability and Elasticity (Principle 1)

---

### BR-002: Cost Reduction through Cloud Modernization

**Description**: Achieve £2M annual operational cost savings by migrating from on-premise data centers to government-approved cloud services.

**Rationale**: Current on-premise infrastructure requires significant capital expenditure. Cloud services provide pay-as-you-go pricing and managed services.

**Success Criteria**:
- Infrastructure costs reduced by £1.5M annually
- Staffing costs reduced by £500K annually through automation
- 100% migration to cloud within 18 months
- Cloud cost optimization achieving <30% idle resource utilization

**Priority**: MUST_HAVE

**Stakeholder**: Tim Moss (Chief Executive), CFO — addresses Goal G-2 from Stakeholder Analysis

**Aligns with Principle**: Scalability and Elasticity (Principle 1)

---

### BR-003: International Patent Data Exchange

**Description**: Establish seamless automated data exchange with international patent offices (WIPO, EPO, USPTO, JPO, KIPO, CNIPA) using WIPO ST.96 XML standard.

**Rationale**: UK patent system is deeply integrated with international patent frameworks (PCT, European Patent Convention). Efficient data exchange reduces duplicate data entry.

**Success Criteria**:
- 100% of PCT national phase entries received via automated WIPO ePCT interface
- EPO patent family data synchronized daily with <24 hour latency
- IP5 patent data feeds operational for prior art search
- WIPO ST.96 compliance for all international patent data exchanges
- Zero manual data entry for international applications

**Priority**: MUST_HAVE

**Stakeholder**: David Thompson (Head of International Cooperation) — addresses Goal G-3 from Stakeholder Analysis

**Aligns with Principle**: Interoperability and Integration (Principle 3)

---

### BR-004: Public Service Digital Transformation

**Description**: Provide world-class digital services with 90% digital adoption rate and 85%+ user satisfaction.

**Rationale**: Current paper-based and legacy online services create friction. Digital transformation is mandated by UK Government Digital Strategy.

**Success Criteria**:
- 90% of patent applications filed electronically (vs. 65% current)
- 85% user satisfaction score (measured via post-transaction surveys)
- 99.95% availability for public-facing services
- WCAG 2.2 Level AA accessibility compliance
- GDS Service Standard assessment passed (Beta and Live phases)

**Priority**: MUST_HAVE

**Stakeholder**: Sophie Martin (User Research Lead), Patent Applicants — addresses Goal G-4 from Stakeholder Analysis

**Aligns with Principle**: Accessibility and Inclusive Design (Principle 14)

---

### BR-005: Open Data and Transparency

**Description**: Publish all granted patents and patent applications (post-18-month publication) as open data via public APIs and bulk downloads.

**Rationale**: Patent data is a public good that drives innovation. Open data aligns with UK Government transparency commitments.

**Success Criteria**:
- Public API providing access to all published patents
- Bulk data downloads available in JSON, XML, and CSV formats
- Open Government Licence (OGL) applied to published data
- API documentation published on GOV.UK
- 1M+ API requests per month within 12 months of launch

**Priority**: SHOULD_HAVE

**Stakeholder**: David Thompson, Public/Industry — addresses Goal G-5 from Stakeholder Analysis

**Aligns with Principle**: Single Source of Truth (Principle 8)

---

### BR-006: Regulatory and Compliance Assurance

**Description**: Ensure full compliance with UK patent law, UK GDPR, Government Security Classifications (OFFICIAL-SENSITIVE), Accessibility Regulations 2018, and Technology Code of Practice.

**Rationale**: As a government body, IPO must comply with all applicable UK legislation. Patent data contains commercially sensitive information.

**Success Criteria**:
- Data Protection Impact Assessment (DPIA) completed and approved
- Cyber Essentials Plus certification obtained
- Annual ITHC (IT Health Check) penetration testing passed
- Technology Code of Practice assessment score >80%
- WCAG 2.2 Level AA compliance verified via external audit
- All OFFICIAL-SENSITIVE patent data stored within UK jurisdiction

**Priority**: MUST_HAVE

**Stakeholder**: Michael Brown (CISO), Laura Davies (DPO) — addresses Goal G-6 from Stakeholder Analysis

**Aligns with Principle**: Security by Design (Principle 4)

---

## Functional Requirements

### User Personas

#### Persona 1: First-Time Inventor (Sarah)
- **Role**: Independent inventor seeking first patent
- **Goals**: File patent application, understand process, track status
- **Pain Points**: Complexity of patent system, legal jargon, uncertainty
- **Technical Proficiency**: Medium
- **Frequency**: One-time user

#### Persona 2: Patent Attorney (David)
- **Role**: Professional patent attorney representing multiple clients
- **Goals**: File bulk applications efficiently, track multiple cases
- **Pain Points**: Legacy systems require duplicate data entry
- **Technical Proficiency**: High
- **Frequency**: Daily user (100+ applications per year)

#### Persona 3: Patent Examiner (Dr. Emily)
- **Role**: Substantive patent examiner (mechanical engineering)
- **Goals**: Conduct prior art searches, assess patentability efficiently
- **Pain Points**: Toggling between multiple systems, poor search tools
- **Technical Proficiency**: High
- **Frequency**: Daily user (8-10 hours per day)

#### Persona 4: Corporate IP Manager (James)
- **Role**: IP manager for large company managing 500+ patents
- **Goals**: Monitor portfolio, ensure renewals, track competitors
- **Pain Points**: No bulk download APIs, manual portfolio tracking
- **Technical Proficiency**: High
- **Frequency**: Weekly user

#### Persona 5: Public Researcher (Dr. Aisha)
- **Role**: Academic researcher studying innovation trends
- **Goals**: Bulk download patent data, API access
- **Pain Points**: Data not machine-readable
- **Technical Proficiency**: High (programmer)
- **Frequency**: Monthly user

---

### Use Cases

#### UC-001: File Patent Application Online

**Actor**: Patent Applicant (Persona 1, 2, 4)

**Preconditions**:
- User is authenticated via GOV.UK Verify or Government Gateway
- User has prepared patent specification documents

**Main Flow**:
1. User navigates to patent filing portal
2. System displays filing form with guided steps
3. User enters bibliographic data (title, inventors, applicants)
4. System validates data in real-time
5. User uploads specification documents (PDF, DOCX)
6. System validates document format and size
7. User reviews application summary
8. System calculates filing fee
9. User completes payment via GOV.UK Pay integration
10. System generates filing receipt with application number
11. System sends confirmation email via GOV.UK Notify

**Postconditions**:
- Application created with unique application number
- Documents stored in secure document management
- Filing receipt sent to applicant
- Workflow initiated for formalities examination

**Alternative Flows**:
- **Alt 3a**: If user is a registered patent attorney, then client selection interface displayed
- **Alt 6a**: If document validation fails, then error message with guidance displayed

**Exception Flows**:
- **Ex 1**: Payment failure — system saves draft, prompts retry
- **Ex 2**: Session timeout — system preserves draft for 30 days

**Business Rules**:
- Filing date assigned when all mandatory documents received and fee paid
- Maximum file size 100MB per document
- Accepted formats: PDF, DOCX, TIF for drawings

**Priority**: CRITICAL

---

### Functional Requirements Detail

#### FR-001: Multi-Channel Patent Application Filing

**Description**: System must support patent application filing via online portal, API, and paper mail (digitized on receipt).

**Relates To**: BR-004, UC-001

**Acceptance Criteria**:
- [ ] Given authenticated user, when filing online, then confirmation email sent within 30 seconds
- [ ] Given attorney with API credentials, when submitting via REST API, then application accepted immediately
- [ ] Given paper application, when received by mail, then entered into system within 2 business days
- [ ] Given incomplete application, when validated, then clear error messages returned
- [ ] Given file upload >100MB, then upload rejected with clear message

**Data Requirements**:
- **Inputs**: Bibliographic data, specification documents, fee payment
- **Outputs**: Application number, filing receipt, confirmation email
- **Validations**: Mandatory fields, document format, fee calculation

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: INT-003 (GOV.UK Verify), INT-004 (GOV.UK Pay), INT-005 (GOV.UK Notify)

**Assumptions**: Users have internet access and modern browsers

**Aligns with Principle**: Interoperability and Integration (Principle 3)

---

#### FR-002: ML-Assisted Patent Classification

**Description**: System must automatically suggest CPC/IPC classification codes using ML models, requiring examiner approval.

**Relates To**: BR-001

**Acceptance Criteria**:
- [ ] Given filed patent, when classification runs, then top 5 CPC codes suggested with confidence scores within 1 hour
- [ ] Given suggested classifications, when examiner reviews, then accept/reject/modify with rationale recorded
- [ ] Given classification model, when performance monitored, then precision >80% and recall >75%
- [ ] Given highly novel technology, when model uncertain (<50% confidence), then escalate to senior examiner

**Data Requirements**:
- **Inputs**: Patent title, abstract, claims, description
- **Outputs**: CPC/IPC codes with confidence scores
- **Validations**: Confidence threshold, human verification

**Priority**: SHOULD_HAVE

**Complexity**: HIGH

**Dependencies**: Patent document indexing complete

**Assumptions**: Sufficient training data available from historical UK patents

**Aligns with Principle**: Maintainability and Evolvability (Principle 13)

---

#### FR-003: Semantic Prior Art Search

**Description**: Prior art search must support semantic search using NLP models to find relevant prior art based on technical concepts.

**Relates To**: BR-001

**Acceptance Criteria**:
- [ ] Given search query, when semantic search runs, then results ranked by technical similarity
- [ ] Given search results, when examiner reviews, then relevance rating >70%
- [ ] Given search query across UK, EPO, USPTO, then results returned in <5 seconds (p95)
- [ ] Given foreign language patent, when translation applied, then search includes translated documents

**Data Requirements**:
- **Inputs**: Search query (free text, claim language)
- **Outputs**: Ranked list of prior art documents with relevance scores
- **Validations**: Source attribution, date verification

**Priority**: SHOULD_HAVE

**Complexity**: HIGH

**Dependencies**: INT-001 (EPO), INT-002 (WIPO), search index built

**Assumptions**: Machine translation quality sufficient for technical documents

**Aligns with Principle**: Data Quality and Lineage (Principle 7)

---

#### FR-004: Examiner Workflow Dashboard

**Description**: Examiner desktop must provide unified dashboard showing assigned applications, pending actions, deadlines, and productivity metrics.

**Relates To**: BR-001

**Acceptance Criteria**:
- [ ] Given authenticated examiner, when dashboard loads, then all assigned cases displayed with status and priority
- [ ] Given pending deadline <7 days, then case highlighted in red with warning
- [ ] Given examiner workload, when viewing productivity, then monthly statistics shown
- [ ] Given case in dashboard, when single-click access, then navigate to case details in <1 second

**Data Requirements**:
- **Inputs**: Examiner ID, case assignments, deadline dates
- **Outputs**: Dashboard view, workload metrics, deadline alerts
- **Validations**: Role-based access control

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: User authentication (NFR-SEC-001)

**Assumptions**: Examiners have assigned workload quotas

**Aligns with Principle**: Observability and Operational Excellence (Principle 5)

---

#### FR-005: Applicant Self-Service Portal

**Description**: Applicants must have secure online portal to file applications, track status, respond to office actions, pay fees.

**Relates To**: BR-004

**Acceptance Criteria**:
- [ ] Given authenticated applicant, when viewing portal, then all applications displayed with real-time status
- [ ] Given office action issued, when notification sent, then applicant sees action in portal within 1 minute
- [ ] Given applicant response, when submitted, then timestamped and attached to application
- [ ] Given patent portfolio, when viewing renewals, then all patents with upcoming deadlines shown

**Data Requirements**:
- **Inputs**: User credentials, application data, documents
- **Outputs**: Application status, correspondence, payment receipts
- **Validations**: Access control (own applications only)

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: INT-003 (GOV.UK Verify), INT-004 (GOV.UK Pay)

**Assumptions**: Applicants prefer self-service over phone/email

**Aligns with Principle**: Accessibility and Inclusive Design (Principle 14)

---

#### FR-006: Patent Publication Workflow

**Description**: System must automatically publish patent applications 18 months after filing/priority date.

**Relates To**: BR-003, Legal requirement (Patents Act 1977 s.16)

**Acceptance Criteria**:
- [ ] Given patent application, when 18 months elapsed, then published on next weekly publication date (Thursday)
- [ ] Given publication, when occurs, then PDF generated and uploaded to public website
- [ ] Given granted patent, when grant decision issued, then B-publication generated with granted claims
- [ ] Given application withdrawn before 18 months, then publication cancelled

**Data Requirements**:
- **Inputs**: Application data, priority date, legal status
- **Outputs**: A-publication (application), B-publication (grant)
- **Validations**: 18-month deadline, withdrawal status

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: Document generation, public website integration

**Assumptions**: Weekly publication cycle maintained (Thursdays)

**Aligns with Principle**: Single Source of Truth (Principle 8)

---

#### FR-007: Renewal Fee Management

**Description**: System must track renewal deadlines, send automated reminders, process payments, update legal status.

**Relates To**: BR-002 (Financial Sustainability)

**Acceptance Criteria**:
- [ ] Given granted patent, when renewal deadline approaches, then reminders sent at 6, 3, 1 months, 1 week before
- [ ] Given renewal fee paid, when confirmed, then legal status updated and renewal certificate issued
- [ ] Given renewal deadline missed, when grace period active, then reminder sent with late fee warning
- [ ] Given renewal not paid within grace period, then patent marked as "Lapsed"

**Data Requirements**:
- **Inputs**: Patent number, grant date, payment status
- **Outputs**: Renewal reminders, legal status updates, certificates
- **Validations**: Payment verification, deadline calculation

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: INT-004 (GOV.UK Pay), INT-005 (GOV.UK Notify)

**Assumptions**: Renewal fee schedule maintained centrally

**Aligns with Principle**: Resilience and Fault Tolerance (Principle 2)

---

#### FR-008: Public Patent Search API

**Description**: Provide RESTful API with OpenAPI specification for public access to published patent data.

**Relates To**: BR-005

**Acceptance Criteria**:
- [ ] Given API user, when accessing /patents endpoint, then published patents returned in JSON with pagination
- [ ] Given API query parameters, when filtering, then results filtered accordingly
- [ ] Given API request exceeding rate limit (100 req/hour), then HTTP 429 returned with Retry-After header
- [ ] Given unpublished confidential application, when API queried, then application excluded from results

**Data Requirements**:
- **Inputs**: Query parameters, authentication (optional for higher limits)
- **Outputs**: JSON response with patent data
- **Validations**: Rate limiting, publication status check

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

**Dependencies**: Search index, API gateway

**Assumptions**: API documentation published on GOV.UK

**Aligns with Principle**: Interoperability and Integration (Principle 3)

---

## Non-Functional Requirements (NFRs)

### Performance Requirements

#### NFR-P-001: Response Time

**Requirement**:
- Public-facing pages: <2 seconds page load time (95th percentile)
- Applicant portal: <3 seconds page load time (95th percentile)
- Examiner desktop: <1 second for case switching
- API responses: <200ms (95th percentile)

**Measurement Method**: Real User Monitoring (RUM) and synthetic monitoring

**Load Conditions**:
- Peak load: 5,000 concurrent users (public search)
- Patent filing: 500 applications/day (peak: 1,000/day)
- Public search: 100,000 searches/day

**Priority**: CRITICAL

**Aligns with Principle**: Performance and Efficiency (Principle 11)

---

#### NFR-P-002: Throughput

**Requirement**: System must handle 100,000 patent searches per day at peak load

**Scalability**: Must scale horizontally to support 3x growth over 3 years

**Priority**: CRITICAL

**Aligns with Principle**: Scalability and Elasticity (Principle 1)

---

### Availability and Resilience Requirements

#### NFR-A-001: Availability Target

**Requirement**:
- Public-facing services: 99.95% uptime (21.6 minutes/month downtime)
- Applicant portal: 99.9% uptime (43.2 minutes/month)
- Examiner desktop: 99.5% uptime (3.6 hours/month)
- Planned maintenance: Maximum 4 hours/month, scheduled Saturday 2am-6am

**Maintenance Windows**: Saturdays 02:00-06:00 GMT

**Priority**: CRITICAL

**Aligns with Principle**: Availability and Reliability (Principle 12)

---

#### NFR-A-002: Disaster Recovery

**RPO (Recovery Point Objective)**: <1 hour (maximum acceptable data loss)

**RTO (Recovery Time Objective)**: <4 hours for public services

**Backup Requirements**:
- Continuous backup: Database replication to secondary region
- Daily full backup: Retained for 90 days
- Monthly archive backup: Retained for 7 years
- Backup testing: Quarterly restore drills

**Failover Requirements**:
- Multi-AZ deployment: Automatic failover within 5 minutes
- Cross-region failover: Manual trigger (target: 2 hours)

**Priority**: CRITICAL

**Aligns with Principle**: Resilience and Fault Tolerance (Principle 2)

---

#### NFR-A-003: Fault Tolerance

**Requirement**: System must gracefully degrade when external dependencies fail

**Resilience Patterns Required**:
- [x] Circuit breaker for external APIs (EPO, WIPO, GOV.UK services)
- [x] Retry with exponential backoff (max 3 retries)
- [x] Timeout on all network calls (API: 30s, Search: 10s)
- [x] Bulkhead isolation for critical resources
- [x] Graceful degradation with warning banners

**Priority**: CRITICAL

**Aligns with Principle**: Resilience and Fault Tolerance (Principle 2)

---

### Scalability Requirements

#### NFR-S-001: Horizontal Scaling

**Requirement**: Application tier must auto-scale horizontally without code changes

**Growth Projections**:
- Year 1: 50,000 applications, 100K public search users/month
- Year 2: 55,000 applications (10% growth)
- Year 3: 60,000 applications (10% growth)

**Scaling Triggers**:
- Auto-scale UP when: CPU >70% or Memory >80% for 5 minutes
- Auto-scale DOWN when: CPU <30% and Memory <50% for 15 minutes

**Priority**: CRITICAL

**Aligns with Principle**: Scalability and Elasticity (Principle 1)

---

#### NFR-S-002: Data Volume Scaling

**Requirement**: Database must handle data growth to 10TB over 10 years

**Data Archival Strategy**:
- **Hot storage**: Active applications <2 years old
- **Warm storage**: Published patents 2-10 years
- **Cold storage**: Historical patents >10 years
- **Archive**: Pre-1950 patents

**Priority**: HIGH

**Aligns with Principle**: Data Sovereignty and Governance (Principle 6)

---

### Security Requirements

#### NFR-SEC-001: Authentication

**Requirement**: All users must authenticate via GOV.UK Verify or Government Gateway

**Multi-Factor Authentication (MFA)**:
- Required for: Patent examiners, administrators, external access
- MFA methods: TOTP authenticator app, hardware tokens (YubiKey for admins)

**Session Management**:
- Session timeout: 30 minutes inactivity for applicants, 2 hours for examiners
- Absolute session timeout: 8 hours
- Re-authentication required for: Payment processing, document submission

**Priority**: CRITICAL

**Aligns with Principle**: Security by Design (Principle 4)

---

#### NFR-SEC-002: Authorization

**Requirement**: Role-based access control (RBAC) with least privilege principle

**Roles and Permissions**:
- **Public User**: Search published patents
- **Applicant**: File and view own applications
- **Patent Attorney**: File on behalf of clients
- **Patent Examiner**: Search all patents, examine assigned applications
- **Senior Examiner**: Approve grant/refusal decisions
- **Administrator**: User management, system configuration

**Privilege Elevation**: Requires manager approval and time-limited

**Priority**: CRITICAL

**Aligns with Principle**: Security by Design (Principle 4)

---

#### NFR-SEC-003: Data Encryption

**Requirement**:
- Data in transit: TLS 1.3+ with forward secrecy
- Data at rest: AES-256 encryption for all data stores
- Key management: Managed key service with automatic key rotation (90 days)

**Encryption Scope**:
- [x] Database encryption at rest
- [x] Object storage encryption
- [x] Block volume encryption
- [x] Backup encryption
- [x] Application-level field encryption for PII

**Priority**: CRITICAL

**Aligns with Principle**: Security by Design (Principle 4)

---

#### NFR-SEC-004: Secrets Management

**Requirement**: No secrets (API keys, passwords, certificates) in code or configuration files

**Secrets Storage**: Managed secrets service with access logging

**Secrets Rotation**: Automatic rotation every 90 days

**Priority**: CRITICAL

**Aligns with Principle**: Security by Design (Principle 4)

---

#### NFR-SEC-005: Vulnerability Management

**Requirement**:
- Dependency scanning in CI/CD pipeline (no critical/high vulnerabilities)
- Static application security testing (SAST)
- Dynamic application security testing (DAST)
- Penetration testing: Annual ITHC by NCSC-approved provider

**Remediation SLA**:
- Critical vulnerabilities (CVSS 9.0-10.0): 24 hours
- High vulnerabilities (CVSS 7.0-8.9): 7 days
- Medium vulnerabilities (CVSS 4.0-6.9): 30 days

**Priority**: CRITICAL

**Aligns with Principle**: Security by Design (Principle 4)

---

### Compliance and Regulatory Requirements

#### NFR-C-001: Data Privacy Compliance

**Applicable Regulations**: UK GDPR, Data Protection Act 2018

**Compliance Requirements**:
- [x] Data subject rights (access, deletion, portability)
- [x] Consent management and audit trail
- [x] Privacy by design and by default
- [x] Data breach notification within 72 hours
- [x] Data protection impact assessment (DPIA) completed

**Data Residency**: All personal and OFFICIAL-SENSITIVE data stored in UK data centers

**Data Retention**:
- Active applications: Until grant/refusal + 7 years
- Granted patents: Permanent retention
- User accounts: Deleted 3 years after last login

**Priority**: CRITICAL

**Aligns with Principle**: Data Sovereignty and Governance (Principle 6)

---

#### NFR-C-002: Audit Logging

**Requirement**: Comprehensive audit trail for compliance and forensics

**Audit Log Contents** (for sensitive operations):
- Who: User/service identity, IP address
- What: Action performed
- When: Timestamp (UTC, millisecond precision)
- Where: System component
- Why: Context (request ID, transaction ID)
- Result: Success/failure with error details

**Operations Requiring Audit**:
- View unpublished patent application
- Download patent documents
- Issue office action
- Grant/refuse patent
- Administrative actions

**Log Retention**: 7 years for compliance logs (immutable storage)

**Log Integrity**: Tamper-evident logging (cryptographic hashing)

**Priority**: CRITICAL

**Aligns with Principle**: Observability and Operational Excellence (Principle 5)

---

#### NFR-C-003: Government Security Classification

**Data Classification**: Patent applications before 18-month publication are **OFFICIAL-SENSITIVE**

**Mandatory Controls**:
- [x] Personnel: BPSS for all staff, SC for examiners
- [x] Network segregation: Private subnet for patent database
- [x] MFA for all examiner access
- [x] Encryption: AES-256 at rest, TLS 1.3 in transit
- [x] Audit logging: All access logged
- [x] Data residency: UK-only data centers

**Priority**: CRITICAL

**Aligns with Principle**: Security by Design (Principle 4)

---

#### NFR-C-004: Accessibility (WCAG 2.2 Level AA)

**Requirement**: All public-facing services must comply with WCAG 2.2 Level AA

**Accessibility Features**:
- [x] Keyboard navigation for all functions
- [x] Screen reader compatibility
- [x] High contrast mode support
- [x] Color contrast ratios: 4.5:1 for normal text, 3:1 for large text
- [x] Resizable text: Support 400% zoom
- [x] Alternative text for images
- [x] Accessible forms with proper labels and error messages
- [x] Captions for video/audio content
- [x] Accessibility statement published

**Testing**: Automated accessibility testing in CI/CD + manual testing with assistive technologies

**Priority**: CRITICAL

**Aligns with Principle**: Accessibility and Inclusive Design (Principle 14)

---

### Usability Requirements

#### NFR-U-001: User Experience

**Requirement**: System must be intuitive for users with varying technical proficiency

**UX Standards**:
- Consistent with GOV.UK Design System
- Accessibility: WCAG 2.2 Level AA compliance
- Mobile responsive design
- Browser support: Chrome, Firefox, Safari, Edge - last 2 versions

**User Onboarding**: Interactive guidance, contextual help, comprehensive documentation

**Priority**: HIGH

**Aligns with Principle**: Accessibility and Inclusive Design (Principle 14)

---

#### NFR-U-002: Localization and Internationalization

**Requirement**: Support for English and Welsh languages

**Localization Scope**:
- [x] UI text translation (Welsh Language Act compliance)
- [x] Date/time format per locale
- [x] Currency formatting (GBP)
- [x] Number formatting

**Priority**: SHOULD_HAVE

**Aligns with Principle**: Accessibility and Inclusive Design (Principle 14)

---

### Maintainability and Supportability Requirements

#### NFR-M-001: Observability

**Requirement**: Comprehensive instrumentation for monitoring and troubleshooting

**Telemetry Requirements**:
- **Logging**: Structured JSON logs with correlation IDs
- **Metrics**: RED metrics (Rate, Errors, Duration), resource utilization
- **Tracing**: Distributed tracing for request flows
- **Dashboards**: Real-time operational dashboards
- **Alerts**: SLO-based alerting with actionable runbooks

**Log Levels**: DEBUG, INFO, WARN, ERROR, FATAL

**Priority**: CRITICAL

**Aligns with Principle**: Observability and Operational Excellence (Principle 5)

---

#### NFR-M-002: Documentation

**Requirement**: Comprehensive documentation for operators and developers

**Documentation Types**:
- [x] Architecture documentation (C4 model)
- [x] API documentation (OpenAPI 3.0 specs)
- [x] Runbooks for operational procedures
- [x] Troubleshooting guides
- [x] User manuals
- [x] Admin guides

**Documentation Format**: Markdown in Git repository, published via docs site

**Documentation Currency**: Updated within 5 days of code changes

**Priority**: HIGH

**Aligns with Principle**: Maintainability and Evolvability (Principle 13)

---

#### NFR-M-003: Operational Runbooks

**Requirement**: Runbooks for common operational tasks and incident response

**Runbook Coverage**:
- [x] Deployment procedures
- [x] Rollback procedures
- [x] Backup and restore procedures
- [x] Incident response for common failure modes
- [x] Scaling procedures
- [x] Disaster recovery procedures

**Priority**: CRITICAL

**Aligns with Principle**: Observability and Operational Excellence (Principle 5)

---

### Portability and Interoperability Requirements

#### NFR-I-001: API Standards

**Requirement**: All APIs must follow OpenAPI 3.0 standards

**API Design Principles**:
- RESTful design with standard HTTP methods
- JSON request/response format
- Versioning via URL path (e.g., /v1/, /v2/)
- Consistent error response format
- HATEOAS for discoverability

**Priority**: HIGH

**Aligns with Principle**: Interoperability and Integration (Principle 3)

---

#### NFR-I-002: Integration Capabilities

**Requirement**: System must integrate with external government and international systems

**Integration Patterns**:
- [x] RESTful API integration
- [x] Event-driven integration (pub/sub)
- [x] File-based integration (SFTP for WIPO)
- [x] Webhooks for real-time notifications

**Integration SLA**: 99.5% success rate, <5 second latency

**Priority**: CRITICAL

**Aligns with Principle**: Interoperability and Integration (Principle 3)

---

#### NFR-I-003: Data Portability

**Requirement**: Users/administrators must be able to export their data

**Export Formats**: CSV, JSON, XML, PDF

**Export Scope**: Complete application data, correspondence history

**Import Capability**: Bulk import from standard formats (WIPO ST.96 XML)

**Priority**: SHOULD_HAVE

**Aligns with Principle**: Data Sovereignty and Governance (Principle 6)

---

## Integration Requirements

### External System Integrations

#### INT-001: European Patent Office (EPO) Integration

**Purpose**: Exchange patent family data and retrieve prior art from EPO databases

**Integration Type**: Real-time REST API (EPO Open Patent Services)

**Data Exchanged**:
- **From EPO to IPO**: Patent family data (daily), EPO patent documents (on-demand)
- **From IPO to EPO**: UK patent data (daily)

**Integration Pattern**: Request/response REST API

**Authentication**: OAuth 2.0 client credentials

**Error Handling**: Circuit breaker, retry with exponential backoff, fallback to cached data

**SLA**: Latency <2 seconds, Availability 99.5%, Rate limit 1,000 requests/day

**Owner**: David Thompson (Head of International Cooperation)

**Priority**: CRITICAL

**Aligns with Principle**: Interoperability and Integration (Principle 3)

---

#### INT-002: WIPO Integration

**Purpose**: Receive PCT applications entering UK national phase

**Integration Type**: File-based exchange (SFTP) + ePCT web services

**Data Exchanged**:
- **From WIPO to IPO**: PCT applications (daily batch, WIPO ST.96 format)
- **From IPO to WIPO**: UK search reports (weekly batch)

**Integration Pattern**: Batch file transfer + web services

**Authentication**: SFTP SSH key, SAML 2.0 for ePCT

**Error Handling**: File validation, error quarantine, manual review queue

**SLA**: Daily batch processed by 06:00 GMT

**Owner**: David Thompson (Head of International Cooperation)

**Priority**: CRITICAL

**Aligns with Principle**: Interoperability and Integration (Principle 3)

---

#### INT-003: GOV.UK Verify Integration

**Purpose**: User authentication via GOV.UK Verify / Government Gateway

**Integration Type**: SAML 2.0 Single Sign-On

**Data Exchanged**:
- **From GOV.UK to IPO**: User identity assertion, verification level

**Integration Pattern**: SAML 2.0 redirect flow

**Authentication**: SAML 2.0 with signed assertions

**Error Handling**: Fallback to Government Gateway, graceful error messages

**SLA**: Availability 99.9%, Response time <3 seconds

**Owner**: IPO Technology Team

**Priority**: CRITICAL

**Aligns with Principle**: Security by Design (Principle 4)

---

#### INT-004: GOV.UK Pay Integration

**Purpose**: Payment processing for filing fees and renewal fees

**Integration Type**: REST API

**Data Exchanged**:
- **From IPO to GOV.UK Pay**: Payment requests, amounts, references
- **From GOV.UK Pay to IPO**: Payment confirmations, receipts

**Integration Pattern**: Request/response REST API with webhooks

**Authentication**: API key with HMAC signatures

**Error Handling**: Payment status polling, retry logic, refund capability

**SLA**: Availability 99.9%, Payment confirmation <5 seconds

**Owner**: IPO Finance Team

**Priority**: CRITICAL

**Aligns with Principle**: Loose Coupling (Principle 9)

---

#### INT-005: GOV.UK Notify Integration

**Purpose**: Send email and SMS notifications

**Integration Type**: REST API

**Data Exchanged**:
- **From IPO to GOV.UK Notify**: Notification requests, templates, personalization data

**Notification Types**: Filing confirmation, office actions, renewal reminders, payment receipts

**Integration Pattern**: Asynchronous REST API

**Authentication**: API key

**Error Handling**: Retry with exponential backoff, delivery status tracking

**SLA**: Availability 99.9%, Delivery <1 minute for email, <5 minutes for SMS

**Owner**: IPO Technology Team

**Priority**: CRITICAL

**Aligns with Principle**: Asynchronous Communication (Principle 10)

---

## Data Requirements

### Data Entities

#### Entity 1: Patent Application

**Description**: Core entity representing a patent application through its lifecycle

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| application_id | UUID | Yes | Unique identifier | Primary key |
| application_number | String(20) | Yes | Official number (e.g., GB2025123456A) | Unique, indexed |
| filing_date | Date | Yes | Date of filing | Indexed |
| publication_date | Date | No | 18-month publication date | Indexed |
| grant_date | Date | No | Date of grant | Indexed |
| title | String(500) | Yes | Patent title | Full-text indexed |
| abstract | Text | Yes | Patent abstract | Full-text indexed |
| legal_status | Enum | Yes | Current status | 'filed', 'published', 'under_examination', 'granted', 'refused', 'lapsed' |
| cpc_codes | Array[String] | No | CPC classification codes | Indexed |
| ipc_codes | Array[String] | No | IPC classification codes | Indexed |
| applicant_id | UUID | Yes | Foreign key to Applicant | Indexed |
| examiner_id | UUID | No | Assigned examiner | Indexed |
| created_at | Timestamp | Yes | Record creation | Auto-generated |
| updated_at | Timestamp | Yes | Last update | Auto-generated |

**Relationships**:
- Many-to-one with Applicant via applicant_id
- One-to-many with Patent Document via application_id
- One-to-many with Office Action via application_id

**Data Volume**: 50,000 applications/year × 50 years = 2.5M records

**Access Patterns**: Search by number, date range, classification, applicant, legal status

**Data Classification**: OFFICIAL-SENSITIVE (unpublished), PUBLIC (after 18 months)

**Data Retention**: Permanent (national archive)

---

#### Entity 2: Applicant

**Description**: Individual or organization filing patent applications

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| applicant_id | UUID | Yes | Unique identifier | Primary key |
| name | String(255) | Yes | Applicant name | Encrypted, indexed |
| address | JSON | Yes | Full address | Encrypted |
| email | String(255) | Yes | Contact email | Encrypted, unique, indexed |
| phone | String(20) | No | Contact phone | Encrypted |
| applicant_type | Enum | Yes | Type | 'individual', 'company', 'university', 'government' |
| country_code | String(2) | Yes | Country of residence | ISO 3166-1 alpha-2 |
| created_at | Timestamp | Yes | Record creation | Auto-generated |
| updated_at | Timestamp | Yes | Last update | Auto-generated |

**Relationships**:
- One-to-many with Patent Application via applicant_id

**Data Volume**: 30,000 applicants/year

**Access Patterns**: Lookup by ID, email, name

**Data Classification**: OFFICIAL (personal data, GDPR protected)

**Data Retention**: 10 years after last application

---

#### Entity 3: Patent Document

**Description**: Documents associated with patent applications (specifications, drawings, office actions)

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| document_id | UUID | Yes | Unique identifier | Primary key |
| application_id | UUID | Yes | Foreign key to Application | Indexed |
| document_type | Enum | Yes | Type | 'specification', 'claims', 'drawings', 'abstract', 'office_action', 'response' |
| storage_key | String(512) | Yes | Object storage key | Unique |
| file_name | String(255) | Yes | Original file name | |
| file_size | BigInt | Yes | Size in bytes | |
| mime_type | String(100) | Yes | MIME type | |
| upload_date | Timestamp | Yes | Upload timestamp | Indexed |
| checksum | String(64) | Yes | SHA-256 hash | Integrity verification |

**Relationships**:
- Many-to-one with Patent Application via application_id

**Data Volume**: 200K documents/year × 50 years = 10M documents

**Access Patterns**: Lookup by application_id, document_type

**Data Classification**: OFFICIAL-SENSITIVE (unpublished), PUBLIC (after publication)

**Data Retention**: Permanent

---

### Data Quality Requirements

**Data Accuracy**: <0.1% error rate for bibliographic data, validation rules enforced at entry

**Data Completeness**: All mandatory fields populated, null handling for optional fields

**Data Consistency**: Cross-system reconciliation with EPO/WIPO data weekly

**Data Timeliness**: New applications indexed within 24 hours of publication

**Data Lineage**: Full audit trail from source to target, transformation logic documented

---

### Data Migration Requirements

**Migration Scope**: 2.5M historical patent records, 10M documents from legacy systems

**Migration Strategy**: Phased migration with parallel run validation

**Data Transformation**:
- Legacy format to WIPO ST.96 XML
- OCR processing for scanned documents
- Data cleansing and deduplication

**Data Validation**: Automated validation scripts, sampling verification, reconciliation reports

**Rollback Plan**: Legacy system maintained in read-only mode for 6 months post-migration

**Migration Timeline**: 9 months (3 phases of 3 months each)

---

## Constraints and Assumptions

### Technical Constraints

**TC-1**: Must integrate with GOV.UK Verify/Government Gateway for authentication (no custom authentication)

**TC-2**: Must deploy to UK-based cloud infrastructure meeting OFFICIAL-SENSITIVE requirements

**TC-3**: Must use UK Government approved security products and services

**TC-4**: Must follow GDS Service Standard and GOV.UK Design System

**TC-5**: Must support WIPO ST.96 XML standard for international data exchange

---

### Business Constraints

**BC-1**: Go-live target December 2026 to align with ministerial commitments

**BC-2**: Budget cap of £7M capital expenditure

**BC-3**: Must maintain service continuity during migration (no extended outages)

**BC-4**: Must preserve all historical patent records (legal requirement)

**BC-5**: Must support existing fee structures and payment methods

---

### Assumptions

**A-1**: Users have internet access and modern browsers (Chrome, Firefox, Safari, Edge - last 2 versions)

**A-2**: GOV.UK Pay, GOV.UK Notify, and GOV.UK Verify services maintain 99.9% availability

**A-3**: EPO and WIPO APIs maintain backward compatibility during project timeline

**A-4**: Sufficient training data available from historical UK patents for ML classification model

**A-5**: Patent examiners will adopt new workflows with appropriate training and change management

**Validation Plan**: Assumptions reviewed monthly at Architecture Review Board, documented risks for each assumption

---

## Success Criteria and KPIs

### Business Success Metrics

| Metric | Baseline | Target | Timeline | Measurement Method |
|--------|----------|--------|----------|-------------------|
| Time to first office action | 18 months | 12 months | 12 months post-launch | Case management reporting |
| Electronic filing rate | 65% | 90% | 12 months post-launch | Filing channel analytics |
| User satisfaction (applicants) | Unknown | 85% | 6 months post-launch | Post-transaction surveys |
| User satisfaction (examiners) | Unknown | 85% | 6 months post-launch | Staff surveys |
| Operational cost savings | £0 | £2M/year | Year 2 | Finance reporting |
| Examination backlog | 15,000 | 5,000 | 24 months post-launch | Backlog reporting |

---

### Technical Success Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| System availability (public) | 99.95% | Uptime monitoring |
| API response time (p95) | <200ms | APM tooling |
| Page load time (p95) | <2 seconds | Real User Monitoring |
| Error rate | <0.1% | Log aggregation |
| Deployment frequency | Weekly | CI/CD metrics |
| Mean time to recovery (MTTR) | <15 minutes | Incident tracking |
| Security vulnerabilities (critical/high) | 0 | Vulnerability scanning |

---

### User Adoption Metrics

| Metric | Target | Timeline | Measurement Method |
|--------|--------|----------|-------------------|
| Monthly active users (public) | 100,000 | 12 months post-launch | Analytics platform |
| API requests per month | 1,000,000 | 12 months post-launch | API gateway metrics |
| Self-service rate | 80% | 12 months post-launch | Channel analytics |

---

## Dependencies and Risks

### Dependencies

| Dependency | Description | Owner | Target Date | Status | Impact if Delayed |
|------------|-------------|-------|-------------|--------|-------------------|
| GOV.UK Verify integration | Authentication service | GDS | 2026-03-31 | On Track | HIGH - Blocks user authentication |
| GOV.UK Pay integration | Payment processing | GDS | 2026-03-31 | On Track | HIGH - Blocks fee collection |
| EPO API access | Prior art search data | EPO | 2026-06-30 | On Track | MEDIUM - Limits search capability |
| WIPO ePCT access | PCT national phase | WIPO | 2026-06-30 | On Track | HIGH - Blocks PCT processing |
| Cloud accreditation | OFFICIAL-SENSITIVE approval | IPO Security | 2026-02-28 | At Risk | CRITICAL - Blocks deployment |
| Data migration tools | Legacy data extraction | IPO Technology | 2026-04-30 | On Track | HIGH - Blocks go-live |

---

### Risks

| Risk ID | Description | Probability | Impact | Mitigation Strategy | Owner |
|---------|-------------|-------------|--------|---------------------|-------|
| R-1 | Cloud accreditation delayed | MEDIUM | CRITICAL | Early engagement with NCSC, parallel accreditation activities | Michael Brown |
| R-2 | Data migration quality issues | MEDIUM | HIGH | Extensive validation, parallel run period, rollback capability | Dr. Emily Roberts |
| R-3 | User adoption resistance | MEDIUM | MEDIUM | Change management program, training, super-user network | Sarah Williams |
| R-4 | International integration delays | LOW | MEDIUM | Early API testing, fallback to manual processes | David Thompson |
| R-5 | Budget overrun | LOW | HIGH | Contingency budget, scope management, regular reviews | Tim Moss |
| R-6 | ML classification accuracy | MEDIUM | MEDIUM | Human-in-the-loop validation, continuous model improvement | Dr. Emily Roberts |

**Risk Scoring**: Probability × Impact = Risk Level
- High Risk (Red): Requires executive escalation
- Medium Risk (Yellow): Active monitoring and mitigation
- Low Risk (Green): Accepted

---

## Requirement Conflicts & Resolutions

> **Purpose**: Document conflicting requirements that arise from competing stakeholder drivers and show how conflicts were resolved.
>
> **Source**: Conflicts identified from stakeholder analysis (`stakeholder-drivers.md`) and requirements elicitation.
>
> **Principle**: Be transparent about trade-offs - don't hide conflicts or pretend both requirements can be fully satisfied.

### Conflict C-1: Automation Speed vs. Examiner Job Security

**Conflicting Requirements**:
- **Requirement A**: BR-001 — 30% reduction in examination time through ML-assisted classification and automation
- **Requirement B**: Stakeholder driver — Examiners concerned about job displacement from automation

**Stakeholders Involved**:
- **Sarah Williams (Director of Patents)**: Wants efficiency gains to meet ministerial KPIs and reduce backlog
- **James Chen (Senior Examiner)**: Wants tools that enhance examiner capability, not replace examiners

**Nature of Conflict**:
Full automation would reduce examiner workload but creates anxiety about job security and potential quality issues from over-reliance on ML.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| **Option 1**: Full automation | ✅ Maximum efficiency<br>✅ Fastest backlog reduction | ❌ Examiner resistance<br>❌ Quality risk | Director happy<br>Examiners unhappy |
| **Option 2**: No automation | ✅ Examiner comfort<br>✅ Human quality control | ❌ No efficiency gains<br>❌ Backlog persists | Examiners happy<br>Director frustrated |
| **Option 3**: Human-in-the-loop | ✅ Efficiency gains<br>✅ Examiner empowerment | ❌ Slower than full automation<br>❌ Training needed | Both satisfied |

**Resolution Strategy**: INNOVATE

**Decision**: Option 3 — Human-in-the-loop automation
- ML provides suggestions, examiner makes final decisions
- Automation handles administrative tasks, examiners focus on substantive examination
- Training program to upskill examiners as "AI supervisors"

**Rationale**: This approach achieves 25% efficiency gains (vs. 30% target) while maintaining examiner engagement and quality oversight. Examiners become more productive, not redundant.

**Decision Authority**: Sarah Williams (Director of Patents) with input from Staff Council

**Impact on Requirements**:
- **Modified**: FR-002 acceptance criteria changed from "automatic classification" to "ML-suggested classification with examiner approval"
- **Added**: Non-functional requirement for ML confidence threshold (<50% triggers human escalation)

**Stakeholder Management**:
- **Sarah Williams**: Accepted 25% efficiency target with commitment to review after 12 months
- **James Chen**: Appointed as change champion, leads examiner training program

**Future Consideration**: Re-evaluate automation level after 12 months of production data and examiner feedback

---

### Conflict C-2: Open Data vs. Security Classification

**Conflicting Requirements**:
- **Requirement A**: BR-005 — Publish all patents as open data via public APIs
- **Requirement B**: NFR-C-003 — Unpublished applications are OFFICIAL-SENSITIVE, strict access controls

**Stakeholders Involved**:
- **David Thompson (Head of International)**: Wants maximum openness for innovation ecosystem
- **Michael Brown (CISO)**: Wants strict security to protect commercially sensitive pre-publication data

**Nature of Conflict**:
Legal requirement to protect unpublished applications for 18 months creates tension with open data aspirations. Any data leak of unpublished applications would be a serious security incident.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| **Option 1**: Open everything | ✅ Maximum transparency | ❌ Legal violation<br>❌ Commercial harm | David happy<br>CISO very unhappy |
| **Option 2**: Restrict everything | ✅ Maximum security | ❌ No open data benefit<br>❌ Misses government transparency goals | CISO happy<br>David unhappy |
| **Option 3**: Publication-based access | ✅ Legal compliance<br>✅ Open data for published | ❌ More complex architecture | Both satisfied |

**Resolution Strategy**: COMPROMISE

**Decision**: Option 3 — Strict separation based on publication status
- Published patents (post-18-month): Open data via public API, bulk downloads, OGL license
- Unpublished applications: OFFICIAL-SENSITIVE, role-based access, full audit trail

**Rationale**: This approach satisfies legal requirements while maximizing openness for published data. Architectural separation ensures no accidental disclosure of unpublished applications.

**Decision Authority**: Michael Brown (CISO) with legal review

**Impact on Requirements**:
- **Modified**: FR-008 acceptance criteria explicitly excludes unpublished applications
- **Added**: Architectural requirement for separate data stores (public vs. confidential)
- **Added**: Automated publication workflow with security classification transition

**Stakeholder Management**:
- **David Thompson**: Satisfied with comprehensive open data for published patents
- **Michael Brown**: Satisfied with strict controls for unpublished applications

**Future Consideration**: None - this is a legal requirement that cannot change

---

### Conflict C-3: Cost Reduction vs. Comprehensive Security

**Conflicting Requirements**:
- **Requirement A**: BR-002 — £2M annual cost savings through cloud migration
- **Requirement B**: NFR-SEC-001 to NFR-SEC-005 — Comprehensive security controls including annual ITHC, 24/7 monitoring

**Stakeholders Involved**:
- **Tim Moss (CEO)/Finance Team**: Wants maximum cost savings to demonstrate ROI
- **Michael Brown (CISO)**: Wants comprehensive security controls regardless of cost

**Nature of Conflict**:
Security controls (penetration testing, 24/7 SOC, hardware tokens) add significant operational cost, potentially reducing the £2M savings target.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| **Option 1**: Minimize security spend | ✅ Maximum cost savings | ❌ Increased risk<br>❌ Potential breach costs | Finance happy<br>CISO very unhappy |
| **Option 2**: Full security investment | ✅ Comprehensive protection | ❌ Reduced savings<br>❌ Higher OpEx | CISO happy<br>Finance less happy |
| **Option 3**: Risk-based security | ✅ Proportionate controls<br>✅ Acceptable savings | ❌ Not maximum of either | Both satisfied |

**Resolution Strategy**: COMPROMISE

**Decision**: Option 3 — Risk-based security investment
- Mandatory controls (ITHC, encryption, MFA): Full investment (~£400K/year)
- Enhanced controls (24/7 SOC): Use managed service (~£150K/year vs. £300K in-house)
- Net savings: £1.75M (vs. £2M target)

**Rationale**: Government security requirements are non-negotiable, but can be met cost-effectively through managed services and automation. £1.75M savings still delivers strong ROI.

**Decision Authority**: Tim Moss (CEO) with CISO recommendation

**Impact on Requirements**:
- **Modified**: BR-002 success criteria adjusted from £2M to £1.75M savings
- **Retained**: All security requirements (NFR-SEC-001 to NFR-SEC-005) unchanged

**Stakeholder Management**:
- **Tim Moss/Finance**: Accepted £1.75M target given security requirements are non-negotiable
- **Michael Brown**: Satisfied that all security controls are maintained

**Future Consideration**: Review managed security service costs annually for optimization opportunities

---

## Timeline and Milestones

### High-Level Milestones

| Milestone | Description | Target Date | Dependencies |
|-----------|-------------|-------------|--------------|
| Requirements Approval | Stakeholder sign-off on requirements | 2025-10-31 | This document |
| Design Complete | HLD and DLD approved | 2025-12-15 | Requirements |
| Alpha Phase Complete | Core functionality demonstrated | 2026-02-28 | Design |
| Private Beta Launch | Internal users and limited externals | 2026-06-30 | Alpha, Cloud accreditation |
| GDS Service Assessment (Beta) | Pass Beta assessment | 2026-08-31 | Private Beta |
| Public Beta Launch | All users, feedback collection | 2026-09-30 | Beta assessment passed |
| GDS Service Assessment (Live) | Pass Live assessment | 2026-11-30 | Public Beta |
| Production Go-Live | Full production launch | 2026-12-15 | Live assessment passed |

---

## Budget

### Cost Estimate

| Category | Estimated Cost | Notes |
|----------|----------------|-------|
| Development team (18 months) | £3,500,000 | 15 FTEs average |
| Architecture & design | £400,000 | Enterprise architect, solution architects |
| User research | £250,000 | GDS support, accessibility testing |
| Security & compliance | £500,000 | ITHC, accreditation, security consultancy |
| Data migration | £800,000 | Migration tools, validation, parallel run |
| Training | £350,000 | Examiner training, documentation |
| Contingency (15%) | £1,200,000 | Risk buffer |
| **Total Capital** | **£7,000,000** | |

### Ongoing Operational Costs

| Category | Annual Cost | Notes |
|----------|-------------|-------|
| Cloud infrastructure | £800,000 | Compute, storage, networking |
| Support & maintenance | £600,000 | L2/L3 support, bug fixes |
| Third-party services | £200,000 | EPO API, managed security |
| Licenses | £100,000 | Software licenses |
| **Total Annual OpEx** | **£1,700,000** | |

### Financial Summary

- **3-Year TCO**: £12.1M (£7M capital + £5.1M operational)
- **3-Year Savings**: £5.25M (£1.75M/year × 3 years)
- **Net Cost**: £6.85M
- **ROI**: Positive from Year 4 onwards

---

## Approval

### Requirements Review

| Reviewer | Role | Status | Date | Comments |
|----------|------|--------|------|----------|
| Sarah Williams | Director of Patents | ☐ Pending | [DATE] | |
| Dr. Emily Roberts | Enterprise Architect | ☐ Pending | [DATE] | |
| Michael Brown | CISO | ☐ Pending | [DATE] | |
| Laura Davies | Data Protection Officer | ☐ Pending | [DATE] | |
| David Thompson | Head of International | ☐ Pending | [DATE] | |

### Sign-Off

By signing below, stakeholders confirm that requirements are complete, understood, and approved to proceed to design phase.

| Stakeholder | Signature | Date |
|-------------|-----------|------|
| Tim Moss, Chief Executive | _________ | [DATE] |
| Sarah Williams, Director of Patents | _________ | [DATE] |

---

## Appendices

### Appendix A: Glossary

- **BPSS**: Baseline Personnel Security Standard (security clearance level)
- **CPC**: Cooperative Patent Classification
- **DPIA**: Data Protection Impact Assessment
- **EPO**: European Patent Office
- **GDS**: Government Digital Service
- **IPO**: UK Intellectual Property Office
- **ITHC**: IT Health Check (UK government penetration testing)
- **MFA**: Multi-Factor Authentication
- **NCSC**: National Cyber Security Centre
- **PCT**: Patent Cooperation Treaty
- **RBAC**: Role-Based Access Control
- **SC**: Security Check (security clearance level)
- **ST.96**: WIPO XML standard for patent data exchange
- **WCAG**: Web Content Accessibility Guidelines
- **WIPO**: World Intellectual Property Organization

### Appendix B: Reference Documents

- Architecture Principles: `.arckit/memory/architecture-principles.md`
- Stakeholder Analysis: `projects/001-patent-management-system-for-the-intellectual-property-office/stakeholder-drivers.md`
- UK Government Technology Code of Practice: https://www.gov.uk/guidance/the-technology-code-of-practice
- GDS Service Standard: https://www.gov.uk/service-manual/service-standard
- GOV.UK Design System: https://design-system.service.gov.uk/
- WIPO ST.96 Standard: https://www.wipo.int/standards/en/st96.html
- NCSC Cloud Security Principles: https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles

### Appendix C: Requirements Traceability Matrix Summary

| Requirement | Stakeholder Goal | Architecture Principle | Test Coverage |
|-------------|------------------|----------------------|---------------|
| BR-001 | G-1: Processing efficiency | Principle 1: Scalability | Performance tests |
| BR-002 | G-2: Cost reduction | Principle 1: Scalability | Cost monitoring |
| BR-003 | G-3: International integration | Principle 3: Interoperability | Integration tests |
| BR-004 | G-4: Digital transformation | Principle 14: Accessibility | Accessibility audit |
| BR-005 | G-5: Open data | Principle 8: Single Source of Truth | API tests |
| BR-006 | G-6: Compliance | Principle 4: Security by Design | Security audit |

---

**Generated by**: ArcKit `/arckit.requirements` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Patent Management System for IPO (Project 001)
**AI Model**: Claude Opus 4.5
**Generation Context**: Updated from v1.0 to align with template v0.11.2, incorporating stakeholder analysis and conflict resolution
