# Technology Code of Practice (TCoP) Review

> **Template Status**: Beta | **Version**: 0.11.2 | **Command**: `/arckit.tcop`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-TCOP-v2.0 |
| **Document Type** | Technology Code of Practice Review |
| **Project** | Patent Management System for the UK Intellectual Property Office (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 2.0 |
| **Created Date** | 2025-10-15 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Phase Gate (Alpha/Beta/Live) |
| **Next Review Date** | 2026-03-31 |
| **Owner** | Dr. Emily Roberts (Enterprise Architect) |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Project Team, Architecture Team, Digital Spend Control |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-15 | ArcKit AI | Initial creation from `/arckit.tcop` command | [PENDING] | [PENDING] |
| 2.0 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 format | [PENDING] | [PENDING] |

## Document Purpose

This document assesses the Patent Management System project against the UK Government Technology Code of Practice (TCoP) - a set of 13 criteria to help government design, build and buy technology. This assessment informs Digital Spend Control decisions and identifies gaps requiring remediation before proceeding through project phases.

---

## Executive Summary

**Overall TCoP Compliance**: 105/130 points (81%)

**Status**: ✅ **GOOD - Compliant with minor gaps**

**Critical Issues**: 1 blocking issue
**High Priority Issues**: 2 issues requiring attention
**Recommendations**: 5 actionable recommendations

### Key Findings

The Patent Management System demonstrates **strong alignment** with UK Government Technology Code of Practice at the requirements stage. The project excels in cloud-first architecture, security by design, open standards adoption, and reuse of government platform services (GOV.UK Pay, Notify, Verify).

However, **3 areas require attention** before proceeding to Beta phase:
1. **CRITICAL**: Sustainability and carbon impact assessment not addressed (TCoP Point 12)
2. **HIGH**: Code publication strategy undefined (TCoP Point 3)
3. **MEDIUM**: GDS Service Standard assessment not yet scheduled (TCoP Point 13)

**Recommendation**: Address critical sustainability gap immediately. Project is otherwise well-positioned for Alpha phase with strong technology foundations.

---

## TCoP Point-by-Point Assessment

### 1. Define User Needs ✅ COMPLIANT

**Principle**: Understand your users and their needs. Develop knowledge of how users interact with your technology initiatives.

**Reference**: https://www.gov.uk/guidance/define-user-needs

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] User personas documented (5 personas: First-Time Inventor, Patent Attorney, Patent Examiner, Corporate IP Manager, Public Researcher)
- [x] User Research Lead assigned (Sophie Martin from GDS seconded to IPO)
- [x] User satisfaction targets defined (85%+ in BR-004)
- [x] User acceptance testing planned with patent attorneys and examiners
- [x] User needs analysis conducted (personas document pain points and goals)
- [x] Ongoing user feedback mechanism planned (post-transaction surveys)

**Findings**:
- Comprehensive user personas covering all key stakeholder groups from first-time inventors to professional patent attorneys
- Clear articulation of user goals and pain points in requirements.md:215-248
- User research lead from GDS demonstrates commitment to user-centered design
- Measurable user satisfaction targets (85%+ satisfaction score)
- UAT involvement specified with James Chen (Senior Patent Examiner) as UAT lead

**Gaps**:
- User research not yet conducted (planned for Alpha phase)
- User journey maps not yet created (expected during Alpha)
- Quantitative user needs research pending (interviews and usability testing)

**Requirements Mapping**:
- BR-004: Public Service Digital Transformation → 85% user satisfaction target
- User Personas section: 5 detailed personas with goals, pain points, technical proficiency
- Stakeholder table includes end users (Patent Applicants, Patent Attorneys, Patent Examiners)

**Remediation**:
- **Action**: Conduct user research with 20+ patent examiners and 50+ applicants during Alpha phase
- **Owner**: Sophie Martin (User Research Lead)
- **Due**: Alpha phase (Q1 2026)
- **Risk if not addressed**: MEDIUM - Project proceeds with assumed user needs rather than validated needs

**Score**: 8/10

---

### 2. Make Things Accessible and Inclusive ✅ COMPLIANT

**Principle**: Make sure your technology, infrastructure and systems are accessible and inclusive for all users.

**Reference**: https://www.gov.uk/guidance/make-things-accessible

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] WCAG 2.2 Level AA compliance mandated (NFR-C-004)
- [x] Comprehensive accessibility features specified (keyboard navigation, screen readers, color contrast)
- [x] Automated accessibility testing in CI/CD pipeline (axe-core)
- [x] Manual testing with assistive technologies planned
- [x] User research with disabled users required before Beta and Live
- [x] External accessibility audit planned (annually)
- [x] Accessibility statement publication required

**Accessibility Features** (NFR-C-004:700-707):
- Keyboard navigation for all functions (no mouse required)
- Screen reader compatibility (JAWS, NVDA, VoiceOver)
- Color contrast ratios: 4.5:1 for normal text, 3:1 for large text
- Resizable text: Support 200% zoom without horizontal scrolling
- Alternative text for all images (critical for patent drawings)
- Form labels and error messages properly associated
- Accessibility statement published on /accessibility-statement page

**Testing Requirements** (NFR-C-004:709-713):
- Automated testing in CI/CD with build failure on WCAG violations
- Manual testing quarterly with assistive technologies
- User research with disabled users before Beta and Live phases
- External accessibility audit by specialist firm annually

**Findings**:
- Exemplary accessibility requirements covering all WCAG 2.2 AA criteria
- Testing strategy comprehensive (automated + manual + user research + external audit)
- Accessibility integrated into development lifecycle (CI/CD gates)
- Commitment to respond to accessibility issues within 5 business days
- Welsh language support planned (Welsh Language Act 1993 compliance) in NFR-U-003

**Gaps**:
- Accessibility audit not yet commissioned (expected before Beta launch)
- Testing with disabled users not yet scheduled
- Accessibility statement not yet drafted (will be created during Alpha)

**Requirements Mapping**:
- NFR-C-004: Accessibility (WCAG 2.2 Level AA) - comprehensive requirements
- BR-006: Regulatory and Compliance Assurance → WCAG 2.2 AA external audit verification
- Architecture Principle 4: Accessibility and Inclusive Design (WCAG 2.2 AA)
- NFR-U-003: Localization (Welsh Language Support) for accessibility to Welsh speakers

**Remediation**:
- **Action**: Commission external accessibility audit and schedule user testing with disabled users
- **Owner**: Sophie Martin (User Research Lead) + Development Team
- **Due**: Before Beta launch (Q2 2026)
- **Risk if not addressed**: HIGH - Non-compliance with Accessibility Regulations 2018, potential legal challenge

**Score**: 9/10

---

### 3. Be Open and Use Open Source ⚠️ PARTIAL

**Principle**: Publish your code and use open source software to improve transparency, flexibility and accountability.

**Reference**: https://www.gov.uk/guidance/be-open-and-use-open-source

**Compliance Status**: ⚠️ PARTIAL

**Evidence**:
- [x] Open data commitment (BR-005: publish all granted patents as open data)
- [x] Open Government Licence (OGL) applied to published patent data
- [x] Public API for patent data (FR-008)
- [x] Open source software usage in architecture (PostgreSQL, OpenSearch mentioned)
- [ ] Code publication strategy NOT defined
- [ ] Open source license for IPO code NOT specified
- [ ] GitHub/GitLab public repository NOT mentioned
- [ ] Contributing back to open source projects NOT addressed

**Open Source Components Used** (inferred from architecture principles):
| Component | License | Purpose |
|-----------|---------|---------|
| PostgreSQL | PostgreSQL License (permissive) | Relational database |
| OpenSearch | Apache 2.0 | Patent search engine |
| Terraform | MPL 2.0 | Infrastructure as Code |
| React | MIT | Frontend framework |
| Node.js | MIT | Backend runtime |

**Code Published**:
- Repository: NOT YET DEFINED ❌
- License: NOT YET DEFINED ❌
- Documentation: NOT YET DEFINED ❌

**Open Data Published** (BR-005):
- Public API providing access to all published patents
- Bulk data downloads in JSON, XML, CSV formats
- Open Government Licence (OGL) applied
- API documentation published on GOV.UK

**Findings**:
- Strong commitment to open data (patent data as public good)
- Open source software used extensively in architecture
- However, NO commitment to publishing IPO's custom application code
- No mention of contributing back to open source projects
- No GitHub organization or repository structure defined

**Gaps**:
- **CRITICAL GAP**: Code publication strategy undefined
- No public repository planned (GitHub Government or equivalent)
- No open source license selected for IPO code
- No plan to contribute improvements back to open source projects (e.g., GOV.UK Design System, patent classification libraries)
- No exemptions documented for code that cannot be published (if any)

**Requirements Mapping**:
- BR-005: Open Data and Transparency → Data published as open, but NOT code
- Architecture Principle 9: Approved Technology Stack → Uses open source (PostgreSQL, OpenSearch) but doesn't commit to publishing IPO code
- No requirement explicitly mandating code publication

**Remediation**:
- **Action**: Define code publication strategy and create public GitHub repository
- **Owner**: Dr. Emily Roberts (Enterprise Architect) + Development Team
- **Due**: Before Beta launch (Q2 2026)
- **Risk if not addressed**: MEDIUM - Violates TCoP Point 3, reduces transparency, limits collaboration
- **Recommended approach**:
  1. Create GitHub organization: `github.com/intellectual-property-office`
  2. Publish core application code under MIT or Apache 2.0 license
  3. Document security-sensitive code exemptions (if any, e.g., secrets management, authentication)
  4. Publish infrastructure-as-code (Terraform) and CI/CD pipelines
  5. Contribute bug fixes and enhancements to upstream open source projects

**Score**: 6/10

---

### 4. Make Use of Open Standards ✅ COMPLIANT

**Principle**: Build technology that uses open standards to ensure your technology works and communicates with other technology.

**Reference**: https://www.gov.uk/guidance/make-use-of-open-standards

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] RESTful APIs using JSON (FR-001, FR-008)
- [x] OpenAPI 3.0 specifications for all APIs (Architecture Principle 2)
- [x] OAuth 2.0 / OpenID Connect for authentication (INT-003 GOV.UK Verify)
- [x] SAML 2.0 for SSO (INT-003)
- [x] WIPO ST.96 XML standard for international patent data exchange (INT-002)
- [x] HTTP/HTTPS, TLS 1.3+
- [x] No vendor lock-in documented (cloud-agnostic where possible)

**Open Standards Used**:
| Standard | Purpose | Specification |
|----------|---------|---------------|
| HTTP/HTTPS | API communication | RFC 2616, RFC 2818 |
| TLS 1.3 | Encryption in transit | RFC 8446 |
| OAuth 2.0 | Authentication | RFC 6749 |
| OpenID Connect | Identity federation | OpenID Connect Core 1.0 |
| SAML 2.0 | Single Sign-On | SAML 2.0 specification |
| JSON | Data format | RFC 8259 |
| OpenAPI 3.0 | API documentation | OpenAPI Specification 3.0 |
| WIPO ST.96 | Patent data exchange | WIPO Standard ST.96 |

**International Patent Standards** (INT-001, INT-002):
- WIPO ST.96 XML format for all international patent data exchanges (PCT, EPO)
- Cooperative Patent Classification (CPC) - international classification system
- INPADOC patent family data format (EPO)

**API Design Standards** (Architecture Principle 2):
- RESTful resource naming (nouns, not verbs)
- Standard HTTP methods (GET, POST, PUT, DELETE, PATCH)
- JSON request/response format
- API versioning via URL path (/v1/, /v2/)
- OpenAPI 3.0 specifications published

**Findings**:
- Exemplary use of open standards across all integration points
- WIPO ST.96 compliance ensures international interoperability with EPO, USPTO, WIPO
- API-first architecture with OpenAPI specifications enables third-party integration
- No proprietary data formats or protocols used
- Strong commitment to avoiding vendor lock-in

**Gaps**:
- None identified - comprehensive open standards adoption

**Requirements Mapping**:
- BR-003: International Patent Data Exchange → WIPO ST.96 compliance
- INT-002: WIPO Integration → WIPO ST.96 XML format
- FR-008: Public Patent Search API → OpenAPI 3.0 specification
- NFR-I-001: API Design Standards → RESTful, JSON, OpenAPI 3.0
- Architecture Principle 2: API-First Integration → OpenAPI 3.0, OAuth 2.0, OpenID Connect

**Remediation**: None required

**Score**: 9/10

---

### 5. Use Cloud First ✅ COMPLIANT

**Principle**: Consider using public cloud solutions first as stated in the Cloud First policy.

**Reference**: https://www.gov.uk/guidance/use-cloud-first

**Compliance Status**: ✅ COMPLIANT (EXEMPLARY)

**Evidence**:
- [x] Public cloud evaluated first and selected (AWS GovCloud UK)
- [x] Cloud First policy compliance documented (BR-002)
- [x] 100% migration to cloud within 18 months
- [x] Cloud-native services prioritized (managed databases, serverless, auto-scaling)
- [x] Infrastructure-as-Code implemented (Terraform)
- [x] Cloud cost optimization strategy defined (FinOps)
- [x] No on-premise infrastructure retained

**Cloud Strategy**:
- **Primary Cloud**: AWS GovCloud (UK) - eu-west-2 (London) primary, eu-west-1 secondary
- **Services Used**: RDS (PostgreSQL), S3, Lambda, EKS, OpenSearch, CloudWatch, KMS, Secrets Manager
- **Justification**: Government-approved cloud for OFFICIAL-SENSITIVE data, IL3 compliance
- **Cloud-Native Approach**: Auto-scaling, managed services, serverless where appropriate

**Cost Optimization** (Architecture Principle 15):
- Right-sizing based on actual usage patterns
- Auto-scaling for elastic workloads (scale up/down automatically)
- Data lifecycle policies (Hot → Warm → Cold → Archive storage tiers)
- Reserved instances for predictable workloads
- Budget alerts and FinOps monitoring

**Findings**:
- Exemplary cloud-first approach with 100% cloud target
- AWS GovCloud (UK) appropriate for OFFICIAL-SENSITIVE patent data
- Cloud-native architecture (not "lift-and-shift") with microservices, serverless
- £1.75M annual cost savings through cloud migration (BR-002)
- Infrastructure-as-Code (Terraform) enables repeatability and disaster recovery
- Multi-region strategy within UK for resilience

**Gaps**:
- None identified - exemplary cloud adoption

**Requirements Mapping**:
- BR-002: Cost Reduction through Cloud Modernization → £1.75M annual savings
- Architecture Principle 1: Cloud-First with Government Cloud Standards → AWS GovCloud UK
- NFR-S-001: Horizontal Scaling → Auto-scaling in cloud
- Architecture Principle 10: Infrastructure as Code → Terraform for all infrastructure

**Remediation**: None required

**Score**: 10/10

---

### 6. Make Things Secure ✅ COMPLIANT

**Principle**: Keep systems and data safe with the appropriate level of security.

**Reference**: https://www.gov.uk/guidance/make-things-secure

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] Risk assessment planned (OFFICIAL-SENSITIVE data classification)
- [x] Security accreditation targeted (Cyber Essentials Plus, IL3)
- [x] Cyber Essentials Plus certification planned (BR-006)
- [x] NCSC guidance followed (OFFICIAL-SENSITIVE controls)
- [x] Threat modeling documented (Architecture Principle 3)
- [x] Penetration testing planned (Annual ITHC by NCSC-approved provider)
- [x] Security monitoring and logging comprehensive (NFR-C-002)
- [x] Incident response plan documented (Architecture Principle)
- [x] Security by Design principles applied throughout

**Security Measures**:
| Measure | Implementation | Compliance |
|---------|----------------|------------|
| Authentication | GOV.UK Verify, MFA for examiners | ✅ NFR-SEC-001 |
| Encryption at rest | AES-256 (RDS, S3, EBS) | ✅ NFR-SEC-003 |
| Encryption in transit | TLS 1.3+ | ✅ NFR-SEC-003 |
| Access controls | RBAC, least privilege, MFA | ✅ NFR-SEC-002 |
| Security scanning | SAST (SonarQube), DAST, Snyk | ✅ NFR-SEC-004 |
| Vulnerability management | 24hr critical, 7-day high | ✅ NFR-SEC-004 |
| Penetration testing | Annual ITHC | ✅ BR-006 |
| Audit logging | 7-year retention, tamper-evident | ✅ NFR-C-002 |

**Data Classification**:
- **OFFICIAL-SENSITIVE**: Unpublished patent applications (18-month confidentiality)
- **PUBLIC**: Published patents (after 18 months)

**OFFICIAL-SENSITIVE Controls** (NFR-C-003):
- Personnel: BPSS for all staff, SC (Security Check) for examiners
- Network segregation: Private subnet for patent database (no direct internet access)
- Multi-Factor Authentication (MFA): Mandatory for all examiner access
- Encryption: AES-256 at rest, TLS 1.3 in transit
- Audit logging: All access to unpublished applications logged
- Data residency: UK-only data centers (AWS eu-west-2, eu-west-1)

**Vulnerability Management** (NFR-SEC-004):
- SAST: SonarQube in CI/CD pipeline
- Dependency scanning: Snyk (fail build on CVSS ≥7.0)
- DAST: OWASP ZAP scans weekly in pre-production
- Container scanning: Trivy for Docker images
- Penetration testing: Annual ITHC by NCSC-approved provider
- Remediation SLA: 24 hours (critical), 7 days (high), 30 days (medium)

**Findings**:
- Comprehensive security requirements covering all NCSC Cloud Security Principles
- Appropriate data classification (OFFICIAL-SENSITIVE) with matching controls
- Annual ITHC penetration testing by NCSC-approved provider demonstrates rigor
- Multi-factor authentication mandatory for examiners handling sensitive patent data
- Threat modeling addressing state-sponsored IP theft and corporate espionage
- Security integrated into CI/CD pipeline (fail-fast on vulnerabilities)

**Gaps**:
- Cyber Essentials Plus certification not yet obtained (planned before Beta)
- ITHC penetration test not yet scheduled (expected before Beta launch)
- Threat model not yet completed (planned during Alpha)
- IL3 accreditation process not yet started (required for OFFICIAL-SENSITIVE data)

**Requirements Mapping**:
- BR-006: Regulatory and Compliance Assurance → Cyber Essentials Plus, Annual ITHC
- NFR-SEC-001 to NFR-SEC-004: Comprehensive security requirements
- NFR-C-003: Government Security Classification (OFFICIAL-SENSITIVE controls)
- Architecture Principle 3: Security by Design (Government Security Classification)

**Remediation**:
- **Action**: Commission Cyber Essentials Plus assessment and schedule ITHC penetration test
- **Owner**: Michael Brown (CISO)
- **Due**: Before Beta launch (Q2 2026)
- **Risk if not addressed**: CRITICAL - Cannot launch public Beta without security accreditation

**Score**: 9/10

---

### 7. Make Privacy Integral ✅ COMPLIANT

**Principle**: Make sure users rights are protected by integrating privacy as an essential part of your system.

**Reference**: https://www.gov.uk/guidance/make-privacy-integral

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] Data Protection Impact Assessment (DPIA) planned (NFR-C-001)
- [x] UK GDPR compliance documented comprehensively
- [x] Privacy policy publication required
- [x] Cookie consent not applicable (government service, no tracking cookies)
- [x] User data minimization practiced (only collect necessary data)
- [x] Data retention policy defined and implemented
- [x] Right to access (DSAR) process documented
- [x] Right to erasure implemented (with exceptions for published data)
- [x] Privacy by Design principles applied
- [x] ICO guidance followed

**Personal Data Processing** (NFR-C-001:632-635):
| Data Type | Purpose | Legal Basis | Retention |
|-----------|---------|-------------|-----------|
| Applicant name, address, email, phone | Patent application correspondence | Legitimate interest (statutory function) | Until grant/refusal + 7 years |
| Inventor names | Published with patent (statutory requirement) | Legal obligation (Patents Act 1977) | Permanent (published data) |
| User account credentials | Authentication | Contract (service agreement) | 3 years after last login |

**Privacy Features**:
- [x] Consent management: Applicants consent to data processing at filing
- [x] Data export capability: JSON export of all applicant data (GDPR portability)
- [x] Data deletion capability: Withdraw applications before publication (erasure right)
- [x] Anonymization: Public search queries anonymized for analytics
- [x] Privacy dashboard: Applicants can view all their data in self-service portal

**Data Subject Rights** (NFR-C-001:625-630):
- **Right to access**: Applicants can download all their data (JSON export via applicant portal)
- **Right to erasure**: Withdraw applications before 18-month publication (cannot erase published data)
- **Right to rectification**: Update personal details in applicant portal
- **Right to portability**: Export application data in machine-readable format (JSON)
- **Data breach notification**: ICO notified within 72 hours of discovery

**Data Retention** (NFR-C-001:637-640):
- Active applications: Until grant/refusal + 7 years
- Granted patents: Permanent retention (national archive, statutory requirement)
- User accounts: Deleted 3 years after last login (with warning email)
- Audit logs: 7 years (security), 25 years (patent access for litigation)

**Data Residency** (NFR-C-001:642):
- All personal data stored in UK AWS regions (eu-west-2 London, eu-west-1 Ireland within UK jurisdiction)
- No cross-border data transfers (except WIPO/EPO with adequacy determination)

**Findings**:
- Comprehensive GDPR compliance with all data subject rights implemented
- Privacy by Design principles applied (data minimization, pseudonymization)
- Clear data retention policies aligned with statutory requirements and GDPR
- Data residency within UK ensures compliance with data protection laws
- DPIA planned before Beta launch (best practice for government services)
- Conflict resolution: Right to erasure NOT applicable to published patents (statutory requirement to maintain patent register overrides GDPR)

**Gaps**:
- DPIA not yet completed (planned during Alpha phase)
- Privacy policy not yet drafted (will be published before Beta)
- Data Protection Officer (Laura Davies) assigned but DPO review not yet conducted

**Requirements Mapping**:
- NFR-C-001: UK GDPR and Data Protection → Comprehensive compliance
- BR-006: Regulatory and Compliance Assurance → DPIA completed and approved
- Architecture Principle 7: Privacy by Design
- Architecture Principle 6: Patent Data Sovereignty and Lifecycle

**Remediation**:
- **Action**: Complete DPIA with Laura Davies (DPO) and draft privacy policy
- **Owner**: Laura Davies (Data Protection Officer) + Legal Team
- **Due**: Before Beta launch (Q2 2026)
- **Risk if not addressed**: HIGH - Non-compliance with UK GDPR, potential ICO enforcement action

**Score**: 9/10

---

### 8. Share, Reuse and Collaborate ✅ COMPLIANT

**Principle**: Avoid duplicating effort and unnecessary costs by collaborating across government and sharing and reusing technology.

**Reference**: https://www.gov.uk/guidance/share-and-reuse-technology

**Compliance Status**: ✅ COMPLIANT (EXEMPLARY)

**Evidence**:
- [x] Cross-government Digital Marketplace used for procurement (BC-004)
- [x] GOV.UK Pay reused for payment processing (INT-004)
- [x] GOV.UK Notify reused for email/SMS notifications (INT-005)
- [x] GOV.UK Verify reused for authentication (INT-003)
- [x] GOV.UK Design System used for UI consistency (Architecture Principle 19)
- [x] Code sharing: Open data API enables other departments to reuse patent data
- [x] Knowledge sharing: User research lead seconded from GDS

**Reused Government Services**:
| Service | Provider | Purpose | Requirements Reference |
|---------|----------|---------|------------------------|
| GOV.UK Pay | GDS | Payment processing (filing fees, renewals) | INT-004 |
| GOV.UK Notify | GDS | Email/SMS notifications | INT-005 |
| GOV.UK Verify | GDS | User authentication (applicants) | INT-003 |
| GOV.UK Design System | GDS | Frontend UI components, patterns | Architecture Principle 19 |
| Digital Marketplace | GDS | Vendor procurement (G-Cloud) | BC-004 |

**Shared Components** (potential for other departments):
| Component | Repository | Reusable by |
|-----------|------------|-------------|
| Patent data API | (To be published) | Other IP offices, gov departments |
| Open data publishing pattern | (To be published) | Departments with open data mandates |
| WIPO ST.96 integration | (To be published) | International patent offices |

**Findings**:
- Exemplary reuse of GDS platform services (Pay, Notify, Verify, Design System)
- Avoids reinventing common government services (payments, notifications, identity)
- £1.75M cost savings partially attributed to reusing managed services vs. building custom
- User research lead seconded from GDS demonstrates cross-government collaboration
- Procurement via Digital Marketplace (G-Cloud framework) enables SME participation
- Open data API enables other departments and researchers to reuse patent data

**Gaps**:
- Code sharing: IPO code not yet published for reuse by other departments (see TCoP Point 3)
- Collaboration: No mention of collaboration with other IP offices (EPO, WIPO) on open source tools
- Knowledge sharing: No mention of publishing case studies or contributing to GDS blogs

**Requirements Mapping**:
- INT-003: GOV.UK Verify Integration → Reuse of government identity service
- INT-004: GOV.UK Pay Integration → Reuse of government payment service
- INT-005: GOV.UK Notify Integration → Reuse of government notification service
- Architecture Principle 19: GOV.UK Design System → UI consistency across government
- BC-004: Procurement via G-Cloud framework (Digital Marketplace)

**Remediation**:
- **Action**: Publish case studies and code examples to benefit other departments
- **Owner**: Dr. Emily Roberts (Enterprise Architect) + Communications Team
- **Due**: After Beta launch (Q4 2026)
- **Risk if not addressed**: LOW - Missed opportunity for cross-government collaboration

**Score**: 10/10

---

### 9. Integrate and Adapt Technology ✅ COMPLIANT

**Principle**: Your technology should work with existing technologies, processes and infrastructure in your organisation, and adapt to future demands.

**Reference**: https://www.gov.uk/guidance/integrate-and-adapt-technology

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] Integration with existing systems documented (INT-001 EPO, INT-002 WIPO)
- [x] API-first approach for flexibility (Architecture Principle 2)
- [x] Microservices architecture for adaptability (Architecture Principle 11)
- [x] Technology roadmap defined (Timeline section)
- [x] Legacy system migration plan (8-month phased migration)
- [x] Change management process established
- [x] Scalability for future growth (NFR-S-001: 10% annual growth)

**Integration Points**:
| System | Integration Type | Status | Requirements Reference |
|--------|------------------|--------|------------------------|
| EPO (European Patent Office) | REST API (EPO OPS) | Planned | INT-001 |
| WIPO (PCT applications) | SFTP batch + SOAP/REST | Planned | INT-002 |
| IP5 offices (USPTO, JPO, etc.) | Public APIs | Planned | INT-003 |
| GOV.UK Verify | SAML 2.0 SSO | Planned | INT-003 |
| GOV.UK Pay | REST API | Planned | INT-004 |
| GOV.UK Notify | REST API | Planned | INT-005 |
| Legacy patent system | Hybrid integration during migration | 8 months | Data Migration section |

**Future Adaptability**:
- [x] Microservices architecture (bounded contexts for patent workflows)
- [x] Containerization (Docker, Amazon EKS)
- [x] CI/CD pipeline for rapid changes (Architecture Principle 13)
- [x] Feature flags for gradual rollout
- [x] API versioning strategy (URL-based: /v1/, /v2/)
- [x] Event-driven architecture for workflow orchestration (Architecture Principle 11)

**Technology Debt Management**:
- Legacy system migration: 8-month phased migration with parallel run
- API versioning: 12-month deprecation policy for breaking changes
- Database schema evolution: Liquibase or Flyway for version control
- Backward compatibility: API contract testing to prevent breaking changes

**Findings**:
- API-first architecture enables future integrations without core changes
- Microservices architecture allows independent scaling and evolution of services
- Event-driven patterns (Kafka) enable workflow adaptability
- Legacy migration strategy demonstrates pragmatic integration approach
- API versioning strategy prevents breaking existing integrations
- Horizontal scaling supports 10% annual growth (NFR-S-001)

**Gaps**:
- Technology roadmap defined only at high level (detailed roadmap needed for Alpha)
- Change management process mentioned but not detailed
- Technical debt tracking not explicitly mentioned (recommend Jira or similar)

**Requirements Mapping**:
- Architecture Principle 2: API-First Integration → RESTful APIs with versioning
- Architecture Principle 11: Microservices for Patent Examination Workflow
- NFR-S-001: Horizontal Scaling → Future growth supported
- INT-001 through INT-005: Integration with existing systems

**Remediation**:
- **Action**: Develop detailed technology roadmap and technical debt tracking process
- **Owner**: Dr. Emily Roberts (Enterprise Architect)
- **Due**: Alpha phase (Q1 2026)
- **Risk if not addressed**: LOW - Project can proceed, but long-term adaptability may suffer

**Score**: 9/10

---

### 10. Make Better Use of Data ✅ COMPLIANT

**Principle**: Use data more effectively by improving your technology, infrastructure and processes.

**Reference**: https://www.gov.uk/guidance/make-better-use-of-data

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] Data strategy documented (Architecture Principle 6, 7, 8)
- [x] Data quality standards defined (Architecture Principle 7)
- [x] Analytics and reporting capabilities (NFR-M-001)
- [x] Data-driven decision making processes
- [x] Performance metrics and KPIs defined (Business Metrics in NFR-M-001)
- [x] Data governance framework
- [x] Open data published (BR-005)
- [x] Machine learning opportunities identified (FR-002, FR-003)

**Data Usage**:
| Data Type | Purpose | Quality Measures |
|-----------|---------|------------------|
| Patent applications | Examination workflow | Completeness (100% required fields), Accuracy (CPC classification >80%) |
| Prior art search results | Patent examination | Relevance rating >70% (examiner feedback) |
| Public search queries | Service improvement, analytics | Anonymized, aggregated for trends |
| Renewal payments | Financial forecasting | 99.5% on-time collection target |
| Business metrics | Performance monitoring | Real-time dashboards, SLO tracking |

**Analytics & Reporting** (NFR-M-001:739-744):
- [x] Real-time dashboards: Examiner productivity, application backlog, search usage
- [x] KPI tracking: Time to first office action, backlog reduction, user satisfaction
- [x] User behavior analytics: Anonymized search queries, filing patterns
- [x] Performance monitoring: API latency, error rates, availability
- [x] Cost optimization insights: Cloud cost by service, FinOps dashboards

**Open Data** (BR-005):
- [x] Published patents available via public API (no authentication required)
- [x] Bulk data downloads in JSON, XML, CSV formats
- [x] Open Government Licence (OGL) applied
- [x] API documentation published on GOV.UK Developer Hub
- [x] 1M+ API requests per month target (within 12 months of launch)

**Machine Learning / AI** (FR-002, FR-003):
- ML-assisted patent classification (CPC/IPC codes) - FR-002
- Semantic prior art search using NLP models - FR-003
- Model performance monitoring (precision >80%, recall >75%)
- Explainable AI for transparency in ML recommendations
- Human-in-the-loop (examiner approval required for all ML suggestions)

**Findings**:
- Strong data strategy covering quality, governance, open data, and ML/AI
- Business metrics tracked in real-time enable data-driven decision making
- Open data commitment (published patents) supports innovation ecosystem
- ML opportunities identified with appropriate human oversight (examiners retain decision authority)
- Data quality standards defined (accuracy, completeness, timeliness)
- Anonymized analytics respect user privacy while enabling service improvement

**Gaps**:
- Data governance framework mentioned but not detailed (roles, processes)
- Data catalog not mentioned (recommend data.gov.uk publication)
- Data science team not identified (who will build ML models?)

**Requirements Mapping**:
- BR-005: Open Data and Transparency → Public API, bulk downloads, OGL
- NFR-M-001: Observability and Monitoring → Business metrics dashboards
- FR-002: ML-Assisted Patent Classification → ML/AI for efficiency
- FR-003: Semantic Prior Art Search → NLP for improved search
- Architecture Principle 7: Patent Prior Art Search and Data Quality
- Architecture Principle 8: Open Data and Transparency

**Remediation**:
- **Action**: Define data governance framework (roles, processes, stewardship) and publish to data.gov.uk
- **Owner**: Data Team (to be established) + Laura Davies (DPO for governance)
- **Due**: Beta phase (Q3 2026)
- **Risk if not addressed**: LOW - Data usage is strong, governance formalization can follow

**Score**: 9/10

---

### 11. Define Your Purchasing Strategy ✅ COMPLIANT

**Principle**: Your purchasing strategy must show you've considered commercial and technology aspects, and contractual limitations.

**Reference**: https://www.gov.uk/guidance/define-your-purchasing-strategy

**Compliance Status**: ✅ COMPLIANT

**Evidence**:
- [x] Procurement strategy documented (Budget section, BC-004)
- [x] Digital Marketplace considered/used (G-Cloud framework - BC-004)
- [x] Commercial considerations documented (3-year TCO calculated)
- [x] Technology options analysis (cloud-first decision, AWS GovCloud UK)
- [x] Supplier lock-in risks assessed (open standards, API-first reduce lock-in)
- [x] SME participation encouraged (G-Cloud framework enables SME access)
- [x] Contract terms considered (GOV.UK services have standard SLAs)

**Procurement Approach**:
- **Route**: G-Cloud framework (Digital Marketplace)
- **Contract Value**: £7M capital expenditure, £1.7M annual operational
- **Contract Length**: 3-year initial contract (with option to extend)
- **Exit Strategy**: Open standards and API-first architecture enable vendor switching

**Commercial Considerations**:
| Factor | Analysis | Risk Mitigation |
|--------|----------|-----------------|
| Total Cost of Ownership | £12.1M over 3 years (£7M capital + £5.1M operational) | FinOps monitoring, cost optimization |
| Vendor lock-in | AWS cloud (medium risk) | Open standards, Terraform IaC enables multi-cloud |
| SME access | G-Cloud framework enables SME participation | Lot structure allows smaller contracts |
| ROI | £5.25M savings over 3 years (£1.75M/year savings) | Business case approved by HM Treasury |

**Technology Considerations**:
- [x] Build vs buy analysis: Build custom platform (reusing GDS services)
- [x] Open source alternatives evaluated (PostgreSQL, OpenSearch chosen over proprietary)
- [x] SaaS vs hosted vs on-premise: Cloud-native (AWS managed services) chosen
- [x] Interoperability requirements: Open standards (WIPO ST.96) ensure international compatibility

**Findings**:
- Clear procurement strategy via G-Cloud framework (compliant with government procurement rules)
- 3-year TCO calculated (£12.1M) with ROI demonstrated (£5.25M net savings)
- Vendor lock-in risk mitigated through open standards and Infrastructure-as-Code
- SME participation enabled through G-Cloud framework
- Exit strategy: Open standards and API-first architecture enable vendor switching if needed
- Budget approved by HM Treasury (business case submitted and approved)

**Gaps**:
- Detailed contract terms not yet negotiated (expected during procurement phase)
- Specific vendors not yet selected (procurement not yet started)
- Social Value Model application not mentioned (required for contracts >£5M)

**Requirements Mapping**:
- Budget section: £7M capital, £1.7M annual operational costs
- BC-004: Procurement via G-Cloud framework (Digital Marketplace)
- BR-002: £1.75M annual cost savings (ROI justification)
- Architecture Principle 1: Cloud-First → AWS GovCloud UK selected

**Remediation**:
- **Action**: Apply Social Value Model (required for contracts >£5M) during procurement
- **Owner**: Procurement Team + Tim Moss (SRO)
- **Due**: Before contract award (Q1 2026)
- **Risk if not addressed**: MEDIUM - Non-compliance with government procurement policy

**Score**: 8/10

---

### 12. Make Your Technology Sustainable ❌ NON-COMPLIANT

**Principle**: Increase sustainability throughout the lifecycle of your technology.

**Reference**: https://www.gov.uk/guidance/make-your-technology-sustainable

**Compliance Status**: ❌ NON-COMPLIANT

**Evidence**:
- [ ] Carbon impact assessment NOT completed
- [ ] Energy-efficient infrastructure mentioned (cloud optimization for COST, not carbon)
- [ ] Green hosting provider NOT explicitly selected (AWS not certified green in requirements)
- [ ] Carbon offsetting strategy NOT mentioned
- [ ] E-waste and disposal plan NOT mentioned (no hardware as cloud-based)
- [ ] Sustainable procurement practices NOT mentioned
- [ ] Digital sustainability principles NOT applied
- [ ] Greening Government ICT Strategy compliance NOT addressed

**Sustainability Measures**:
| Measure | Implementation | Impact |
|---------|----------------|--------|
| Cloud region selection | AWS eu-west-2 (London) | Unknown - carbon impact not assessed ❌ |
| Code efficiency | Performance optimization (NFR-P-001) | Reduced compute time ✅ |
| Caching strategy | CloudFront CDN, Redis | Reduced server load ✅ |
| Auto-scaling | Scale down during low usage (nights, weekends) | Energy savings (not quantified) ⚠️ |
| Data lifecycle | Hot/Warm/Cold/Archive storage tiers | Reduced storage footprint ✅ |

**Hardware Lifecycle**:
- Not applicable (cloud-based, no physical hardware)
- AWS responsible for data center sustainability

**Carbon Footprint**:
- Estimated annual carbon: NOT CALCULATED ❌
- Reduction target: NOT SET ❌

**Findings**:
- **CRITICAL GAP**: No carbon impact assessment conducted or planned
- Cloud optimization focused on COST reduction (£1.75M savings) but not carbon reduction
- Data lifecycle policies reduce storage footprint (sustainability benefit not quantified)
- Auto-scaling reduces idle resources (sustainability benefit but not measured)
- No mention of Greening Government ICT Strategy (mandatory for government projects)
- No carbon reduction targets set (Net Zero by 2050 is UK government commitment)

**Gaps**:
- **CRITICAL**: Carbon impact assessment NOT conducted
- Green hosting certification not verified (AWS sustainability credentials not mentioned)
- Carbon reduction targets not set
- Sustainability metrics not tracked (no carbon dashboard)
- Greening Government ICT Strategy compliance not addressed
- Social Value Model (sustainability weighting in procurement) not applied

**Requirements Mapping**:
- No requirements explicitly address sustainability or carbon reduction
- Architecture Principle 15 (FinOps) focuses on cost optimization, not carbon
- NFR-S-002 (Data Volume Scaling) mentions lifecycle policies but not for carbon reasons

**Remediation**:
- **Action**: Conduct carbon impact assessment and set carbon reduction targets
- **Owner**: Infrastructure Team + Sustainability Lead (to be appointed)
- **Due**: IMMEDIATELY - Before Alpha phase (Q1 2026)
- **Risk if not addressed**: CRITICAL - Non-compliance with TCoP Point 12, Greening Government ICT Strategy, and UK Net Zero commitment
- **Recommended approach**:
  1. Conduct carbon impact assessment using Cloud Carbon Footprint tool or similar
  2. Set carbon reduction target (e.g., 30% reduction over 3 years)
  3. Select AWS regions with renewable energy commitments
  4. Track carbon metrics in FinOps dashboards
  5. Include sustainability in Social Value Model for procurement
  6. Publish annual sustainability report

**Score**: 4/10

---

### 13. Meet the Service Standard ⚠️ PARTIAL

**Principle**: Services must comply with the Service Standard requirements.

**Reference**: https://www.gov.uk/service-manual/service-standard

**Compliance Status**: ⚠️ PARTIAL

**Is this a public-facing service?**: Yes

**Evidence**:
- [x] Service Standard assessment planned (BR-004)
- [x] User needs addressed (TCoP Point 1)
- [x] Solves a whole problem (patent lifecycle end-to-end)
- [x] Simple to use (user personas indicate focus on usability)
- [x] Accessible (WCAG 2.2 AA - TCoP Point 2)
- [x] Privacy-preserving (UK GDPR compliance - TCoP Point 7)
- [x] Multidisciplinary team (stakeholders include user research, architecture, security)
- [x] Continuous improvement (observability and metrics enable data-driven improvement)
- [ ] Service Assessment NOT yet scheduled
- [ ] GDS assessment panel NOT yet engaged

**Service Standard Assessment**:
- **Phase**: Pre-Alpha (requirements complete, design not started)
- **Assessment Date**: NOT YET SCHEDULED ❌
- **Assessment Result**: NOT YET CONDUCTED ❌

**GDS Service Standard (18 Points)** - Preliminary Self-Assessment:
| Point | Title | Status | Evidence |
|-------|-------|--------|----------|
| 1 | Understand users and their needs | ✅ | User personas, user research planned |
| 2 | Solve a whole problem for users | ✅ | End-to-end patent lifecycle |
| 3 | Provide a joined up experience | ✅ | Integrated applicant portal, examiner desktop |
| 4 | Make the service simple to use | ⚠️ | Usability testing not yet conducted |
| 5 | Make sure everyone can use the service | ✅ | WCAG 2.2 AA compliance |
| 6 | Have a multidisciplinary team | ✅ | Team includes user research, architecture, security |
| 7 | Use agile ways of working | ⚠️ | Agile not explicitly mentioned in requirements |
| 8 | Iterate and improve frequently | ✅ | CI/CD pipeline, metrics for improvement |
| 9 | Create a secure service | ✅ | Comprehensive security requirements |
| 10 | Define success metrics | ✅ | KPIs defined (user satisfaction, backlog, processing time) |
| 11 | Choose the right tools and technology | ✅ | Cloud-first, open standards, API-first |
| 12 | Make new source code open | ⚠️ | Code publication strategy undefined (TCoP Point 3) |
| 13 | Use and contribute to open standards | ✅ | WIPO ST.96, OpenAPI 3.0, OAuth 2.0 |
| 14 | Operate a reliable service | ✅ | 99.95% availability target |
| 15 | Support a sustainable service | ⚠️ | Carbon assessment missing (TCoP Point 12) |
| 16 | Plan for being offline | ⚠️ | Offline mode not mentioned |
| 17 | Make your service sustainable | ⚠️ | Same as Point 15 - carbon assessment missing |
| 18 | Test the end-to-end service | ⚠️ | Testing strategy defined but not yet executed |

**Findings**:
- Service Standard assessment planned for Beta and Live phases (BR-004)
- Many Service Standard points addressed in requirements (user needs, accessibility, security)
- However, assessment NOT yet scheduled with GDS
- Some Service Standard points have gaps (agile working, code publication, sustainability, offline mode)
- Strong foundation for Service Standard compliance, but assessment needed to validate

**Gaps**:
- GDS Service Standard assessment NOT yet scheduled
- Assessment panel NOT yet engaged
- Alpha and Beta assessment dates not set
- Agile ways of working not explicitly documented
- Offline mode/degraded functionality not addressed
- Code publication strategy undefined (impacts Service Standard Point 12)
- Sustainability assessment missing (impacts Service Standard Points 15 and 17)

**Requirements Mapping**:
- BR-004: Public Service Digital Transformation → GDS Service Standard assessment passed (Beta and Live)
- Architecture Principle 18: GDS Service Standard Compliance
- Timeline: No Service Assessment dates in milestones (only Beta launch dates)

**Remediation**:
- **Action**: Engage GDS to schedule Service Standard assessments for Alpha, Beta, and Live phases
- **Owner**: Sarah Williams (Product Owner) + Sophie Martin (User Research Lead)
- **Due**: Before Alpha phase (Q1 2026)
- **Risk if not addressed**: HIGH - Cannot launch public Beta without GDS Service Standard assessment
- **Recommended timeline**:
  - Alpha assessment: Before Alpha phase complete (Feb 2026)
  - Beta assessment: Before Public Beta launch (Sep 2026)
  - Live assessment: Before Production Go-Live (Dec 2026)

**Score**: 7/10

---

## Overall Compliance Summary

### Compliance Scorecard

| TCoP Point | Title | Score /10 | Status | Critical Issues |
|------------|-------|-----------|--------|-----------------|
| 1 | Define User Needs | 8 | ✅ | No |
| 2 | Make Things Accessible and Inclusive | 9 | ✅ | No |
| 3 | Be Open and Use Open Source | 6 | ⚠️ | No |
| 4 | Make Use of Open Standards | 9 | ✅ | No |
| 5 | Use Cloud First | 10 | ✅ | No |
| 6 | Make Things Secure | 9 | ✅ | No |
| 7 | Make Privacy Integral | 9 | ✅ | No |
| 8 | Share, Reuse and Collaborate | 10 | ✅ | No |
| 9 | Integrate and Adapt Technology | 9 | ✅ | No |
| 10 | Make Better Use of Data | 9 | ✅ | No |
| 11 | Define Your Purchasing Strategy | 8 | ✅ | No |
| 12 | Make Your Technology Sustainable | 4 | ❌ | Yes |
| 13 | Meet the Service Standard | 7 | ⚠️ | No |

**Overall Score**: 105/130 (81%)

### Critical Issues Requiring Immediate Action

1. **TCoP Point 12 - Sustainability**: Carbon impact assessment NOT conducted
   - Risk: Non-compliance with Greening Government ICT Strategy and UK Net Zero commitment
   - Impact: Project cannot proceed to Live phase without sustainability assessment

### Recommendations

**High Priority**:
- Conduct carbon impact assessment and set carbon reduction targets (TCoP Point 12)
- Define code publication strategy and create public GitHub repository (TCoP Point 3)
- Engage GDS to schedule Service Standard assessments (TCoP Point 13)

**Medium Priority**:
- Conduct user research with 20+ examiners and 50+ applicants (TCoP Point 1)
- Commission Cyber Essentials Plus assessment and schedule ITHC (TCoP Point 6)
- Complete DPIA with DPO (TCoP Point 7)
- Apply Social Value Model during procurement (TCoP Point 11)

**Low Priority**:
- Develop detailed technology roadmap and technical debt tracking (TCoP Point 9)
- Define data governance framework and publish to data.gov.uk (TCoP Point 10)
- Publish case studies and code examples for cross-government benefit (TCoP Point 8)

---

## Next Steps

**Immediate Actions** (0-30 days):
- [ ] Appoint Sustainability Lead for carbon impact assessment (CRITICAL)
- [ ] Engage GDS to schedule Service Standard assessments (HIGH)
- [ ] Create GitHub organization: `github.com/intellectual-property-office` (HIGH)

**Short-term Actions** (1-3 months):
- [ ] Complete carbon impact assessment and set reduction targets
- [ ] Conduct user research with 20+ examiners, 50+ applicants
- [ ] Draft code publication policy
- [ ] Complete GDS Alpha Assessment

**Long-term Actions** (3-12 months):
- [ ] Publish code to GitHub under open source license
- [ ] Complete DPIA and obtain DPO approval
- [ ] Obtain Cyber Essentials Plus certification
- [ ] Schedule and complete ITHC penetration test
- [ ] Complete GDS Beta and Live Assessments

**Review Schedule**: After Alpha phase (March 2026)

---

## Approval

| Role | Name | Date | Signature |
|------|------|------|-----------|
| Project Lead | Sarah Williams | | |
| Technical Architect | Dr. Emily Roberts | | |
| Senior Responsible Owner | Tim Moss | | |
| Digital Spend Control (if applicable) | [PENDING] | | |

---

**Generated by**: ArcKit `/arckit.tcop` command
**Generated on**: 2026-01-26 14:30 GMT
**ArcKit Version**: 0.11.2
**Project**: Patent Management System for the UK Intellectual Property Office (Project 001)
**AI Model**: claude-opus-4-5-20251101
**Generation Context**: Updated from v1.0 to align with template v0.11.2 format; source documents: requirements.md v2.0, stakeholder-drivers.md v2.0, architecture-principles.md v2.1
