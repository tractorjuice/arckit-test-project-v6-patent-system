# Vendor Evaluation Criteria: Patent Management System for the UK Intellectual Property Office

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.evaluate`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-EVAL-v2.0 |
| **Document Type** | Vendor Evaluation Framework |
| **Project** | Patent Management System for the UK Intellectual Property Office (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 2.0 |
| **Created Date** | 2025-10-15 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | On-Demand |
| **Next Review Date** | 2026-02-28 |
| **Owner** | Dr. Emily Roberts (Enterprise Architect) |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Evaluation Committee, Procurement Team, Architecture Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-15 | ArcKit AI | Initial creation from `/arckit.evaluate` command | [PENDING] | [PENDING] |
| 2.0 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 format | [PENDING] | [PENDING] |

## Document Purpose

This document defines the criteria, scoring methodology, and process for evaluating vendor proposals for the Patent Management System (PMS) modernization project. It ensures objective, transparent, and auditable vendor selection aligned with UK Government procurement standards and the project requirements.

---

## 1. Evaluation Overview

### 1.1 Purpose

This document defines the criteria, scoring methodology, and process for evaluating vendor proposals for the Patent Management System (PMS) modernization project. The goal is to select the vendor that provides the best value considering technical capability, government experience, security compliance, patent domain expertise, and cost.

### 1.2 Evaluation Principles

- **Objective**: Criteria are measurable and consistently applied across all vendors
- **Transparent**: Vendors understand how they will be evaluated (criteria published in SOW)
- **Fair**: All vendors evaluated against identical criteria with same reviewers
- **Documented**: Scores and rationale captured for audit trail and FOI compliance
- **Value-Based**: Best value for money, not necessarily lowest cost
- **Compliance-Driven**: Mandatory qualifications are non-negotiable (government standards)

### 1.3 Evaluation Team

| Name | Role | Department | Evaluation Focus | Voting |
|------|------|------------|------------------|--------|
| Dr. Emily Roberts | Evaluation Lead & Enterprise Architect | IPO Technology | Technical architecture, principles alignment | Yes |
| Michael Brown | Security Evaluator | IPO Security (CISO) | Security architecture, OFFICIAL-SENSITIVE controls | Yes |
| David Thompson | Domain Evaluator | IPO International Cooperation | Patent domain expertise, WIPO/EPO integration | Yes |
| Sarah Williams | Business Evaluator | IPO Patents Directorate (Product Owner) | Requirements understanding, user needs | Yes |
| Sophie Martin | Accessibility Evaluator | GDS (seconded to IPO) | WCAG 2.2 AA compliance, user research approach | Yes |
| James Matthews | Financial Evaluator | IPO Finance | Cost evaluation, budget alignment, value for money | Yes |
| Laura Davies | Observer (non-voting) | IPO Compliance (DPO) | GDPR compliance review | No |
| Richard Thompson | Observer (non-voting) | IPO Legal | Contract terms review | No |

### 1.4 Conflict of Interest

All evaluators must disclose any conflicts of interest with vendors before evaluation begins:
- [ ] Personal relationships with vendor employees (friends, family)
- [ ] Financial interests in vendor companies (shares, investments)
- [ ] Prior employment with vendor within 2 years
- [ ] Concurrent consulting arrangements or side businesses
- [ ] Any other relationships that could impair objectivity

**Disclosure Procedure**: Evaluators complete Conflict of Interest Form (Appendix D) and submit to Evaluation Lead within 2 business days of vendor shortlist announcement.

**Recusal**: Evaluators with conflicts must recuse themselves from evaluation of that specific vendor.

---

## 2. Evaluation Process

### 2.1 Process Flow

```
1. Proposals Received (2025-11-30 17:00 GMT)
   ↓
2. Mandatory Qualifications Check (Pass/Fail) [2 days]
   ↓ (Qualified vendors only proceed)
3. Individual Technical Scoring (Blind to Cost) [1 week]
   ↓
4. Consensus Technical Scoring Meeting [1 day]
   ↓
5. Shortlist Top 3-5 Vendors [1 day]
   ↓
6. Cost Proposals Opened (Shortlisted only) [1 day]
   ↓
7. Cost Scoring [1 day]
   ↓
8. Combined Technical + Cost Scoring [1 day]
   ↓
9. Vendor Presentations & Q&A [1 week]
   ↓
10. Reference Checks (Parallel with presentations) [1 week]
   ↓
11. Final Scoring Adjustment & Selection [2 days]
   ↓
12. Selection Approval & Award [1 day]
```

### 2.2 Timeline

| Phase | Duration | Deadline | Responsible |
|-------|----------|----------|-------------|
| Proposals Due | - | 2025-11-30 17:00 GMT | Vendors |
| Mandatory Qualifications Check | 2 days | 2025-12-02 | Procurement + Evaluation Lead |
| Individual Technical Scoring | 1 week | 2025-12-09 | All voting evaluators |
| Consensus Scoring Meeting | 1 day | 2025-12-10 | Evaluation committee (facilitated) |
| Shortlist Determination | 1 day | 2025-12-11 | Evaluation Lead + Product Owner |
| Cost Evaluation | 1 day | 2025-12-12 | Finance evaluator |
| Combined Scoring | 1 day | 2025-12-13 | Evaluation Lead |
| Vendor Presentations | 5 days | 2025-12-16 to 2025-12-20 | Shortlisted vendors |
| Reference Checks | 1 week | 2025-12-16 to 2025-12-20 | Evaluation team (parallel) |
| Final Scoring & Selection | 2 days | 2025-12-23 | Evaluation committee |
| Executive Approval | 1 day | 2025-12-24 | CTO/CIO + SRO |
| Vendor Notification | 1 day | 2026-01-02 | Procurement |
| Contract Award | - | 2026-01-15 | Per SOW timeline |

### 2.3 Scoring Independence

To ensure objectivity:
- **Technical evaluation** conducted **blind to cost** (cost proposals opened only for shortlisted vendors)
- Individual evaluators score independently before consensus meeting
- Scores normalized if evaluator scoring patterns show bias (e.g., consistently scoring all vendors high/low)
- Consensus meeting facilitated by Evaluation Lead to discuss discrepancies and reach agreement

---

## 3. Mandatory Qualifications (Pass/Fail)

Before scoring, vendors MUST meet ALL mandatory qualifications listed in SOW Section 4.1. Failure on ANY item results in immediate disqualification.

### 3.1 Mandatory Qualification Checklist

| ID | Qualification | Evidence Required | Pass/Fail | Notes |
|----|---------------|-------------------|-----------|-------|
| **MQ-1** | Active G-Cloud 14 Framework listing | Listing ID from Digital Marketplace | [ ] Pass [ ] Fail | Non-negotiable for UK government procurement |
| **MQ-2** | Minimum 2 UK central government references (last 3 years) | Reference contact details with project descriptions | [ ] Pass [ ] Fail | Must be central government, not local/devolved |
| **MQ-3** | At least 1 OFFICIAL-SENSITIVE project reference | Reference confirmation of security classification | [ ] Pass [ ] Fail | Critical for handling unpublished patent data |
| **MQ-4** | GDS Service Standard experience | Evidence of GDS Service Assessment participation | [ ] Pass [ ] Fail | Mandatory for public-facing services |
| **MQ-5** | Cyber Essentials Plus certification (current, <12 months) | Certificate number and expiry date | [ ] Pass [ ] Fail | Minimum security certification |
| **MQ-6** | ISO 27001 certification | Certificate number and expiry date | [ ] Pass [ ] Fail | Information security management system |
| **MQ-7** | ITHC penetration test evidence (last 2 years, NCSC-approved) | ITHC report summary or certificate | [ ] Pass [ ] Fail | Demonstrates security testing capability |
| **MQ-8** | AWS Advanced Consulting Partner (or equivalent Azure/GCP govt cloud tier) | Partner tier evidence from cloud provider | [ ] Pass [ ] Fail | Required cloud expertise for government cloud |
| **MQ-9** | Minimum 3 AWS Certified Solutions Architects on proposed team | Certificate numbers for named team members | [ ] Pass [ ] Fail | Team capability, not just company |
| **MQ-10** | Minimum 2 AWS Certified Security Specialists on proposed team | Certificate numbers for named team members | [ ] Pass [ ] Fail | Security expertise on delivery team |
| **MQ-11** | WCAG 2.2 Level AA project evidence (minimum 2 references) | Reference projects with accessibility audits | [ ] Pass [ ] Fail | Accessibility is non-negotiable |
| **MQ-12** | Accessibility specialists with IAAP certifications | CPACC/WAS certificates for named team members | [ ] Pass [ ] Fail | Professional accessibility expertise |
| **MQ-13** | Patent/IP/legal document management experience (minimum 1 reference) | Reference project description | [ ] Pass [ ] Fail | Domain knowledge critical |
| **MQ-14** | Understanding of WIPO ST.96, PCT, EPO OPS | Technical approach demonstrates understanding | [ ] Pass [ ] Fail | International standards knowledge |
| **MQ-15** | Company financial statements (last 2 years) | Audited financial statements attached | [ ] Pass [ ] Fail | Financial stability check |
| **MQ-16** | Minimum annual turnover £15M (or parent company guarantee) | Financial statements or guarantee letter | [ ] Pass [ ] Fail | Financial capacity for £7M project |
| **MQ-17** | Professional indemnity insurance £10M | Insurance certificate | [ ] Pass [ ] Fail | Risk mitigation |
| **MQ-18** | Employer's liability insurance £10M | Insurance certificate | [ ] Pass [ ] Fail | Legal requirement |
| **MQ-19** | Public liability insurance £10M | Insurance certificate | [ ] Pass [ ] Fail | Risk mitigation |
| **MQ-20** | Commitment to BPSS clearance for all personnel | Signed commitment in proposal | [ ] Pass [ ] Fail | Security clearance for IPO systems access |
| **MQ-21** | Commitment to SC clearance for OFFICIAL-SENSITIVE access | Signed commitment in proposal | [ ] Pass [ ] Fail | Security clearance for patent data access |
| **MQ-22** | UK-based delivery team (majority FTE in UK) | Team location plan in proposal | [ ] Pass [ ] Fail | On-site collaboration and data sovereignty |
| **MQ-23** | Proposal submitted on time (2025-11-30 17:00 GMT) | Email server timestamp | [ ] Pass [ ] Fail | Late submissions not accepted |
| **MQ-24** | Proposal follows required format (PDF, max 100 pages) | Format check | [ ] Pass [ ] Fail | Compliance with SOW requirements |
| **MQ-25** | All required proposal sections completed | Completeness check | [ ] Pass [ ] Fail | Missing sections = incomplete proposal |
| **MQ-26** | Cost proposal separate from technical proposal | Separate PDF file | [ ] Pass [ ] Fail | Enables blind technical evaluation |
| **MQ-27** | Key personnel CVs included (10 roles specified) | CV attachments for all 10 key roles | [ ] Pass [ ] Fail | Team capability assessment |
| **MQ-28** | Minimum 3 contactable references provided | Reference contact details with email/phone | [ ] Pass [ ] Fail | Reference check enablement |

### 3.2 Disqualification Procedure

1. **Initial Review**: Procurement team conducts initial completeness check (MQ-23 to MQ-28)
2. **Technical Review**: Evaluation Lead and subject matter experts verify qualifications (MQ-1 to MQ-22)
3. **Failure Identification**: If any mandatory qualification fails, vendor flagged for disqualification
4. **Confirmation**: Evaluation Lead confirms failure with supporting evidence
5. **Clarification Window**: Vendor has **48 hours** to provide clarification if failure due to misunderstanding or missing evidence (not to meet qualification retroactively)
6. **Final Determination**: Evaluation Lead makes final disqualification decision
7. **Notification**: Vendor notified of disqualification with specific reason cited (no detailed feedback at this stage)

**Record Keeping**: All disqualifications documented with rationale for audit trail and potential appeals.

---

## 4. Technical Evaluation Criteria (60 Points)

Technical proposals are scored **blind to cost** to ensure unbiased technical assessment. Cost proposals remain sealed until shortlist is determined.

### 4.1 Criteria Summary

| Category | Weight | Max Points | Primary Evaluator(s) |
|----------|--------|------------|----------------------|
| **1. Technical Approach and Solution Design** | 42% | 25 | Dr. Emily Roberts (Enterprise Architect), Michael Brown (CISO) |
| **2. Delivery Methodology and Project Approach** | 17% | 10 | Dr. Emily Roberts, Sarah Williams (Product Owner) |
| **3. Team Qualifications and Experience** | 25% | 15 | All voting evaluators |
| **4. Relevant Experience and References** | 16% | 10 | Sarah Williams, David Thompson, Sophie Martin |
| **TOTAL TECHNICAL SCORE** | **100%** | **60** | All voting evaluators |

### 4.2 Category 1: Technical Approach and Solution Design (25 points)

**Purpose**: Evaluate the proposed technical solution's quality, feasibility, and alignment with requirements and architecture principles.

#### Subcriteria

| Subcriterion | Points | Evaluation Questions |
|--------------|--------|---------------------|
| **1.1 Architecture Quality** | 8 | • Is the architecture well-designed, scalable, and maintainable?<br>• Does it follow cloud-native best practices (microservices, etc.)?<br>• Are components loosely coupled with clear boundaries?<br>• Is the architecture aligned with IPO enterprise principles? |
| **1.2 Technology Stack** | 5 | • Are technology choices appropriate for requirements?<br>• Do choices align with IPO approved stack or have good justification?<br>• Is the stack modern, supportable, with active community?<br>• Are there lock-in risks or vendor dependencies? |
| **1.3 Scalability & Performance** | 4 | • Does solution meet NFR-P-001, NFR-P-002 performance requirements?<br>• Is horizontal scaling strategy credible (NFR-S-001)?<br>• Are bottlenecks identified and addressed?<br>• Is performance testing approach sound? |
| **1.4 Security & Compliance** | 5 | • Are OFFICIAL-SENSITIVE controls comprehensive (NFR-C-003)?<br>• Does solution meet UK GDPR requirements (NFR-C-001)?<br>• Is threat model thoughtful and complete?<br>• Are NFR-SEC-001 to NFR-SEC-004 security requirements met? |
| **1.5 Integration Approach** | 3 | • Is integration with WIPO/EPO sound (INT-001, INT-002)?<br>• Is GOV.UK services integration appropriate (INT-003 to INT-005)?<br>• Are integration risks identified and mitigated? |

### 4.3 Category 2: Delivery Methodology and Project Approach (10 points)

**Purpose**: Evaluate the vendor's approach to delivering the project, managing risks, and ensuring quality.

#### Subcriteria

| Subcriterion | Points | Evaluation Questions |
|--------------|--------|---------------------|
| **2.1 Development Methodology** | 3 | • Is Agile/GDS Service Manual approach appropriate?<br>• Is sprint/iteration planning realistic?<br>• How will vendor adapt to IPO governance processes? |
| **2.2 Project Timeline & Phasing** | 3 | • Is timeline realistic given scope (18 months)?<br>• Are phases logically sequenced (Alpha, Beta, Live)?<br>• Are architecture review gates planned? |
| **2.3 Risk Management** | 2 | • Are key risks identified proactively?<br>• Are mitigation strategies credible?<br>• Does vendor show awareness of patent domain risks? |
| **2.4 Quality Assurance** | 2 | • Is testing strategy comprehensive (NFR-M-003)?<br>• Is accessibility testing planned (NFR-C-004)?<br>• Are GDS Service Assessments planned? |

### 4.4 Category 3: Team Qualifications and Experience (15 points)

**Purpose**: Evaluate the vendor's team expertise, experience, and ability to deliver.

#### Subcriteria

| Subcriterion | Points | Evaluation Questions |
|--------------|--------|---------------------|
| **3.1 Key Personnel Qualifications** | 6 | • Do key personnel have strong relevant experience?<br>• Are AWS/security certifications current?<br>• Is team composition appropriate (seniority mix)? |
| **3.2 Team Size & Allocation** | 3 | • Is team size adequate for £7M, 18-month project?<br>• Are key personnel dedicated (not spread thin)?<br>• Are backup resources identified? |
| **3.3 Domain Expertise** | 3 | • Does team have patent/IP domain experience?<br>• Do they understand WIPO ST.96, PCT, EPO OPS?<br>• Have they solved similar problems before? |
| **3.4 Technology Expertise** | 3 | • Does team have deep AWS GovCloud expertise?<br>• Do they have WCAG 2.2 AA experience?<br>• Are there capability gaps requiring training? |

### 4.5 Category 4: Relevant Experience and References (10 points)

**Purpose**: Evaluate vendor's track record delivering similar projects successfully.

#### Subcriteria

| Subcriterion | Points | Evaluation Questions |
|--------------|--------|---------------------|
| **4.1 Reference Project Relevance** | 5 | • Are reference projects similar in scope and complexity?<br>• Do they demonstrate UK government experience?<br>• Were projects successful (on time, on budget, quality)? |
| **4.2 Industry Experience** | 3 | • Does vendor have patent/IP/legal domain experience?<br>• Do they understand government procurement?<br>• Can they provide industry-relevant insights? |
| **4.3 Innovation & Thought Leadership** | 2 | • Is vendor recognized as technology leader?<br>• Do they contribute to open source or GDS community?<br>• Do they demonstrate innovative approaches? |

### 4.6 Scoring Rubric (Per Subcriterion)

| Score | Description |
|-------|-------------|
| **Excellent (90-100%)** | Exceeds expectations; innovative approach; demonstrates deep expertise; minimal risks |
| **Good (75-89%)** | Meets all expectations; sound approach; minor concerns requiring clarification |
| **Adequate (60-74%)** | Meets most expectations; workable approach; some concerns or gaps |
| **Weak (40-59%)** | Meets minimum expectations; significant concerns; substantial gaps or risks |
| **Unacceptable (0-39%)** | Does not meet expectations; major flaws; unworkable approach |

---

## 5. Cost Evaluation (40 Points)

Cost proposals are opened **only for shortlisted vendors** after technical evaluation is complete.

### 5.1 Cost Scoring Methodology

**Method**: Lowest Price Best Value

- Lowest cost proposal receives 40 points
- Other proposals scaled proportionally
- Formula: `Cost Score = (Lowest Price / Vendor Price) × 40`

### 5.2 Cost Analysis Template

| Vendor | Total Cost | Cost per Technical Point | Rank by Cost | Rank by Value | Notes |
|--------|------------|--------------------------|--------------|---------------|-------|
| Vendor A | £[X] | £[X/pt] | | | |
| Vendor B | £[X] | £[X/pt] | | | |
| Vendor C | £[X] | £[X/pt] | | | |

**Cost Breakdown Comparison**:

| Cost Category | Vendor A | Vendor B | Vendor C | Notes |
|---------------|----------|----------|----------|-------|
| Development & Implementation | £[X] | £[X] | £[X] | |
| Architecture & Design | £[X] | £[X] | £[X] | |
| Security & Compliance | £[X] | £[X] | £[X] | |
| Data Migration | £[X] | £[X] | £[X] | |
| Training & Knowledge Transfer | £[X] | £[X] | £[X] | |
| Project Management | £[X] | £[X] | £[X] | |
| Contingency | £[X] | £[X] | £[X] | |
| **Total** | **£[X]** | **£[X]** | **£[X]** | |

---

## 6. Final Scoring Formula

**Final Score = (Technical Score) + (Cost Score)**

Where:
- Technical Score: 0-60 points (60% weight)
- Cost Score: 0-40 points (40% weight)
- Maximum Total: 100 points

**Minimum Technical Threshold**: Vendors must score **≥42/60 (70%)** to be considered for shortlist.

### 6.1 Combined Scoring Summary

| Vendor | Technical Score (60) | Cost Score (40) | **Final Score (100)** | Rank |
|--------|---------------------|-----------------|----------------------|------|
| Vendor A | ___ | ___ | **___** | |
| Vendor B | ___ | ___ | **___** | |
| Vendor C | ___ | ___ | **___** | |

---

## 7. Vendor Presentations

Shortlisted vendors present their proposals to the evaluation committee.

### 7.1 Presentation Format

**Duration**: 2 hours
- Vendor presentation: 90 minutes
- Q&A: 30 minutes

**Location**: IPO offices, Newport, Wales OR virtual via Microsoft Teams

**Attendees**:
- Evaluation committee (all members)
- Key stakeholders (SRO, Technical Leads)
- Note-taker (non-voting)

**Presentation Content**:
1. Company overview (5 min)
2. Team introductions (5 min)
3. Solution architecture walkthrough (30 min)
4. Patent workflow implementation (20 min)
5. Security and compliance approach (15 min)
6. Project approach and timeline (10 min)
7. Demo (if applicable) (5 min)
8. Q&A (30 min)

### 7.2 Presentation Evaluation

Presentations are NOT separately scored but may adjust existing scores (±10%) based on:
- Clarifications that resolve concerns (improve scores)
- Red flags or concerning answers (lower scores)
- Team chemistry and communication effectiveness
- Quality of live demo (if provided)

---

## 8. Reference Checks

### 8.1 Reference Check Process

For each shortlisted vendor, contact **all provided references** (minimum 3).

**Reference Check Questions**:

1. **Project Scope**: Can you describe the project the vendor delivered for you?
2. **On-Time Delivery**: Was the project delivered on schedule?
3. **On-Budget Delivery**: Was the project delivered within budget?
4. **Quality**: Was the quality of deliverables high?
5. **Team Effectiveness**: How effective was the vendor's team?
6. **Issue Resolution**: How did the vendor handle problems or conflicts?
7. **Technical Expertise**: Did the team demonstrate strong technical skills?
8. **Post-Go-Live Support**: How was support during warranty/maintenance phase?
9. **Would You Hire Again?**: Would you engage this vendor for another project?

### 8.2 Reference Check Impact

Reference checks do NOT add points but may **disqualify** or **lower scores**:
- **Disqualification**: Multiple negative references or single highly negative reference
- **Score Adjustment**: Concerning patterns may lower relevant subcriteria scores by 10-20%

---

## 9. Final Selection Decision

### 9.1 Decision Factors

**Quantitative (Objective)**:
- Final combined score
- Cost relative to £7M budget
- Technical score threshold (minimum 42/60 required)

**Qualitative (Subjective)**:
- Cultural fit and communication style
- Confidence in delivery based on presentations and references
- Strategic partnership potential
- Risk tolerance

### 9.2 Decision Matrix

| Vendor | Final Score | Technical Score | Cost | Reference Check | Cultural Fit | Risk Level | Recommendation |
|--------|-------------|-----------------|------|-----------------|--------------|------------|----------------|
| Vendor A | ___ | ___ | £X | Positive | Good | Low | [ ] Select |
| Vendor B | ___ | ___ | £Y | Very Positive | Excellent | Low | [ ] Select |
| Vendor C | ___ | ___ | £Z | Mixed | Good | Medium | [ ] Select |

### 9.3 Selection Approval

**Decision Authority**: Tim Moss (SRO) + CTO/CIO

**Approval Requirements**:
- Evaluation summary presented to decision authority
- Rationale for selection documented
- Risks and mitigation strategies outlined
- Budget approval confirmed

**Approvals**:

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Evaluation Lead | Dr. Emily Roberts | _________ | [DATE] |
| Product Owner | Sarah Williams | _________ | [DATE] |
| CISO | Michael Brown | _________ | [DATE] |
| Senior Responsible Owner | Tim Moss | _________ | [DATE] |

---

## 10. Documentation and Records

### 10.1 Required Documentation

All evaluation materials must be retained for **7 years** (UK Government retention policy):
- [ ] SOW document
- [ ] All vendor proposals (technical and cost)
- [ ] Individual scoring sheets
- [ ] Consensus scoring sheets
- [ ] Presentation notes
- [ ] Reference check notes
- [ ] Selection decision memo
- [ ] Approval signatures

### 10.2 Confidentiality

Evaluation materials are confidential:
- Evaluators sign non-disclosure agreement
- Proposals not shared outside evaluation committee
- Scores and vendor comparisons remain confidential
- Vendor debriefs do not disclose competitor information
- FOI requests handled per IPO disclosure policy

---

## Appendices

### Appendix A: Individual Evaluator Scorecard

[Complete scoring template for each evaluator to fill out independently]

### Appendix B: Consensus Scoring Worksheet

[Template for facilitated consensus scoring meeting]

### Appendix C: Reference Check Template

[Detailed reference check questionnaire]

### Appendix D: Conflict of Interest Form

[Form for evaluators to disclose any conflicts]

### Appendix E: Related Documents

| Document | Version | Link |
|----------|---------|------|
| Statement of Work | 2.0 | `sow.md` |
| Requirements | 2.0 | `requirements.md` |
| TCoP Assessment | 2.0 | `tcop-assessment.md` |
| Traceability Matrix | 2.0 | `traceability-matrix.md` |
| Architecture Principles | 2.1 | `.arckit/memory/architecture-principles.md` |

---

**Generated by**: ArcKit `/arckit.evaluate` command
**Generated on**: 2026-01-26 15:15 GMT
**ArcKit Version**: 0.11.2
**Project**: Patent Management System for the UK Intellectual Property Office (Project 001)
**AI Model**: claude-opus-4-5-20251101
**Generation Context**: Updated from v1.0 to template v0.11.2 format; aligned with SOW v2.0 and requirements v2.0
