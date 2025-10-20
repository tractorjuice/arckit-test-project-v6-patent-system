# ArcKit Full Test Plan

**Test Repository**: `/tmp/arckit-test-project-v6-patent-system`
**Date**: 2025-10-20
**Version**: v0.2.1 (all 16 commands including ServiceNow, Wardley Maps, Diagrams, and Security Assessments)

---

## Test Scenario: UK Government AI Chatbot Project

We'll test all ArcKit commands by simulating a realistic UK Government project:

**Project**: Benefits Eligibility Chatbot for Department for Work and Pensions (DWP)
**Type**: HIGH-RISK AI system (affects access to benefits)
**Requirements**: TCoP compliance, AI Playbook compliance, ATRS publication

---

## Phase 1: Establish Architecture Principles

### Test: `/arckit.principles`

**Command**:
```bash
/arckit.principles Create architecture principles for UK Government Department for Work and Pensions (DWP) focused on cloud-first, security-by-design, accessibility WCAG 2.2 AA, and AI responsible deployment
```

**Expected Output**:
- File: `.arckit/memory/architecture-principles.md`
- Sections:
  - Strategic Principles (Cloud-First, API-First, Security-by-Design)
  - Data Principles (Privacy-by-Design, Single Source of Truth)
  - Technology Standards (approved cloud providers, languages, frameworks)
  - Accessibility Requirements (WCAG 2.2 AA)
  - AI/ML Principles (responsible AI, human oversight)
  - Exception Process

**Success Criteria**:
- ✅ File created with comprehensive principles
- ✅ UK Government specific (GOV.UK services, Digital Marketplace, Cyber Essentials)
- ✅ AI-specific principles included
- ✅ Validation gates defined

---

## Phase 2: Define Requirements

### Test: `/arckit.requirements`

**Command**:
```bash
/arckit.requirements Build a benefits eligibility chatbot for DWP that uses GPT-4 to answer citizen questions about Universal Credit, Job Seekers Allowance, and disability benefits. Must handle 10,000 concurrent users, comply with UK GDPR, WCAG 2.2 AA accessibility, integrate with existing DWP systems, provide accurate eligibility guidance, support English and Welsh languages, and include human-in-the-loop review before advice is shown to citizens.
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/requirements.md`
- Requirements categories:
  - Business Requirements (BR-001+): Why build this, business goals
  - Functional Requirements (FR-001+): What it does (chatbot, Q&A, eligibility checks)
  - Non-Functional Requirements:
    - NFR-S-xxx: Security (UK GDPR, data encryption, Cyber Essentials)
    - NFR-P-xxx: Performance (10K concurrent users, response times)
    - NFR-A-xxx: Accessibility (WCAG 2.2 AA, screen readers)
    - NFR-C-xxx: Compliance (UK GDPR, DPA 2018, Equality Act 2010)
    - NFR-E-xxx: Equity/Fairness (bias testing, protected characteristics)
  - Integration Requirements (INT-001+): DWP systems integration
  - Data Requirements (DR-001+): Personal data handling, retention
  - Success Criteria: Measurable KPIs

**Success Criteria**:
- ✅ Comprehensive requirements (50+ requirements)
- ✅ All requirement types covered
- ✅ Each requirement has acceptance criteria
- ✅ Priorities defined (MUST/SHOULD/MAY)
- ✅ UK Government compliance built in

---

## Phase 3: UK Government Compliance Assessments

### Test 3a: `/arckit.tcop`

**Command**:
```bash
/arckit.tcop Assess Technology Code of Practice compliance for DWP benefits eligibility chatbot in Private Beta phase
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/tcop-assessment.md`
- Assessment of all 13 TCoP points:
  1. User Needs
  2. Accessibility (WCAG 2.2 AA)
  3. Open Source
  4. Open Standards
  5. Cloud First
  6. Security (Cyber Essentials)
  7. Privacy (UK GDPR, DPIA)
  8. Share/Reuse (GOV.UK services)
  9. Integration (API-first)
  10. Data
  11. Purchasing (Digital Marketplace)
  12. Sustainable
  13. Service Standard
- Overall score: X/130 points
- Compliance status for each point
- Gap analysis
- Remediation actions

**Success Criteria**:
- ✅ All 13 points assessed
- ✅ Score calculated
- ✅ Gaps identified
- ✅ Next actions provided

### Test 3b: `/arckit.ai-playbook`

**Command**:
```bash
/arckit.ai-playbook Assess AI Playbook compliance for DWP benefits eligibility chatbot using GPT-4 - this is a HIGH-RISK AI system affecting access to benefits
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/ai-playbook-assessment.md`
- Risk Level: HIGH-RISK
- Assessment of 10 principles (each 0-10):
  1. Understanding AI
  2. Lawful/Ethical Use (DPIA, EqIA, Human Rights)
  3. Security (prompt injection, data poisoning)
  4. Human Control (human-in-the-loop MANDATORY)
  5. Lifecycle Management
  6. Right Tool Selection
  7. Collaboration
  8. Commercial Partnership
  9. Skills/Expertise
  10. Organizational Alignment
- Assessment of 6 ethical themes (each 0-10):
  1. Safety/Security/Robustness
  2. Transparency/Explainability (ATRS MANDATORY)
  3. Fairness/Bias/Discrimination
  4. Accountability/Responsibility
  5. Contestability/Redress
  6. Societal Wellbeing
- Overall score: X/160 points
- Go/No-Go decision
- Mandatory documentation checklist (ATRS, DPIA, EqIA, Human Rights, Bias Audit)

**Success Criteria**:
- ✅ HIGH-RISK determined correctly
- ✅ All 10 principles + 6 themes assessed
- ✅ Blocking issues flagged (e.g., missing DPIA)
- ✅ Human-in-the-loop requirement flagged
- ✅ ATRS publication requirement flagged

### Test 3c: `/arckit.atrs`

**Command**:
```bash
/arckit.atrs Generate ATRS record for DWP benefits eligibility chatbot using GPT-4, in Private Beta phase, processing citizen questions about benefits eligibility
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/atrs-record.md`
- **Tier 1 - Public Summary**:
  - Name, description, contact (plain English)
  - Organization: DWP
  - Function: Benefits and welfare
  - Phase: Private Beta
  - Region: England and Wales
- **Tier 2 - Detailed Information**:
  - Section 1: Owner (SRO, team, external suppliers)
  - Section 2: Description (GPT-4, generative AI, rationale)
  - Section 3: Decision-Making (human-in-the-loop, contestability)
  - Section 4: Data (personal data, UK data residency, security)
  - Section 5: Impact Assessments (DPIA, EqIA, Human Rights)
  - Section 6: Fairness/Bias (bias testing, protected characteristics)
  - Section 7: Technical (model performance, explainability)
  - Section 8: Testing (security, prompt injection testing)
  - Section 9: Transparency (GOV.UK publication)
  - Section 10: Governance (oversight board, incident management)
  - Section 11: Compliance (UK GDPR, DPA 2018, Equality Act)
  - Section 12: Performance (KPIs, user feedback)
  - Section 13: Review schedule
- Publication checklist at end

**Success Criteria**:
- ✅ Tier 1 clear and accessible
- ✅ Tier 2 comprehensive and technical
- ✅ All mandatory sections completed
- ✅ Publication checklist provided
- ✅ Ready for GOV.UK repository publication

### Test 3d: `/arckit.secure`

**Command**:
```bash
/arckit.secure Generate UK Government Secure by Design assessment for DWP benefits chatbot in Beta phase handling OFFICIAL-SENSITIVE data
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/ukgov-secure-by-design.md`
- **NCSC CAF Assessment** (14 principles, 4 objectives):
  - Objective A: Managing Security Risk (4 principles)
  - Objective B: Protecting Against Cyber Attack (6 principles)
  - Objective C: Detecting Cyber Security Events (2 principles)
  - Objective D: Minimising Impact of Incidents (2 principles)
- **Cyber Essentials** compliance (5 controls)
- **UK GDPR** compliance assessment
- Data classification: OFFICIAL-SENSITIVE
- SIRO sign-off requirements
- CAF Score: X/14 principles achieved
- Critical security issues and remediation actions

**Success Criteria**:
- ✅ All 14 NCSC CAF principles assessed
- ✅ Cyber Essentials 5 controls checked
- ✅ UK GDPR compliance verified (DPIA, DPO, ICO reporting)
- ✅ Data classification appropriate for personal benefits data
- ✅ Actionable security remediation plan

---

## Phase 3.5: Strategic Planning & Architecture

### Test 3.5a: `/arckit.wardley`

**Command**:
```bash
/arckit.wardley Create procurement strategy Wardley Map for DWP benefits eligibility chatbot showing build vs buy decisions
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/wardley-maps/procurement-strategy.md`
- Wardley Map in OnlineWardleyMaps format
- Components positioned by evolution stage:
  - BUILD: Benefits rules engine (Custom 0.42) - domain expertise
  - BUILD: Human review queue (Custom 0.45) - HIGH-RISK AI requirement
  - BUY (G-Cloud): GPT-4 (Product 0.72) - commercial LLM
  - BUY (G-Cloud): Cloud hosting (Commodity 0.95)
  - REUSE: GOV.UK Notify (Commodity 0.92)
  - REUSE: GOV.UK Design System (Product 0.75)
- Strategic recommendations (% build/buy/reuse)
- Visualization link to create.wardleymaps.ai

**Success Criteria**:
- ✅ Map shows clear build vs buy rationale
- ✅ UK Government Digital Marketplace alignment
- ✅ Evolution stages correct (Genesis → Custom → Product → Commodity)
- ✅ Strategic recommendations actionable

### Test 3.5b: `/arckit.diagram`

**Command**:
```bash
/arckit.diagram container Generate C4 container diagram for DWP benefits chatbot showing GOV.UK services and AWS infrastructure
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/diagrams/container-benefits-chatbot.md`
- Mermaid C4 container diagram showing:
  - Frontend: GOV.UK Design System
  - Backend: Node.js API, GPT-4 integration
  - Custom: Benefits rules engine, Human review queue
  - Data: PostgreSQL RDS, S3 audit logs
  - External: GOV.UK Notify, DWP legacy systems
- Component inventory with evolution stages
- Architecture decisions and rationale
- UK GDPR compliance notes

**Success Criteria**:
- ✅ Valid Mermaid syntax
- ✅ Components annotated with evolution stages from Wardley Map
- ✅ GOV.UK services clearly marked [REUSE]
- ✅ Renders correctly on GitHub/mermaid.live

---

## Phase 4: Vendor Procurement (Optional - can test if desired)

### Test 4a: `/arckit.sow`

**Command**:
```bash
/arckit.sow Generate Statement of Work for vendor RFP to build the benefits eligibility chatbot, 9-month timeline, £1.5M budget, procurement via G-Cloud framework
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/sow.md`
- Sections:
  - Executive Summary
  - Scope of Work
  - Technical Requirements (from requirements.md)
  - Deliverables
  - Timeline (9 months)
  - Budget (£1.5M)
  - Vendor Qualifications
  - Evaluation Criteria
  - Contract Terms
  - Acceptance Criteria

**Success Criteria**:
- ✅ All requirements from requirements.md included
- ✅ UK Government specific (G-Cloud, Security Clearance, IR35)
- ✅ Measurable acceptance criteria
- ✅ Ready for Digital Marketplace RFP

### Test 4b: `/arckit.evaluate`

**Command**:
```bash
/arckit.evaluate Create evaluation framework for benefits chatbot vendors
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/evaluation-criteria.md`
- Technical evaluation (100 points):
  - AI/ML expertise
  - UK Government experience
  - Security capabilities
  - Accessibility expertise
  - Integration capabilities
- Cost evaluation methodology
- Reference check templates
- Scoring matrix

**Success Criteria**:
- ✅ Fair and unbiased scoring
- ✅ All critical requirements weighted
- ✅ Decision matrix provided

---

## Phase 4.5: ServiceNow Service Management

### Test: `/arckit.servicenow`

**Command**:
```bash
/arckit.servicenow Generate ServiceNow service design for DWP benefits eligibility chatbot - Tier 1 HIGH-RISK AI service with 24/7 support
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/servicenow-design.md`
- **Service Overview**: Tier 1 (99.95% SLA)
- **CMDB Design**: 8+ CIs derived from architecture
  - Web Application CI
  - API Gateway CI
  - GPT-4 Integration CI
  - Benefits Rules Engine CI (Custom)
  - Human Review Queue CI (Custom)
  - PostgreSQL RDS CI (Commodity)
  - GOV.UK Notify CI (External REUSE)
  - DWP Legacy System CI (External)
- **SLA Definitions**: Derived from NFRs
  - Availability: 99.95% (Tier 1)
  - Performance: <500ms p95 response time
  - Incident response: P1 15 min, P2 4 hours
- **Incident Management**: Priority matrix, categories, assignment groups, runbooks
- **Change Management**: HIGH-RISK AI requires ECAB + senior leadership approval
- **Monitoring & Alerting**: Bias metrics, human-in-loop SLA tracking
- **Service Transition Plan**: Go-live checklist (40+ items)

**Success Criteria**:
- ✅ CMDB structure maps 1:1 to architecture diagrams
- ✅ SLAs derived from NFRs (not arbitrary)
- ✅ HIGH-RISK AI reflected in change control (ECAB required)
- ✅ Human-in-the-loop monitoring included
- ✅ ITIL v4 aligned
- ✅ UK Government compliance (DPIA, ATRS) referenced

---

## Phase 5: Quality Analysis

### Test: `/arckit.analyze`

**Command**:
```bash
/arckit.analyze
```

**Expected Output**:
- **Console output** (no file written - read-only analysis)
- Comprehensive analysis report:
  - **Executive Summary**:
    - Overall governance health score (A-F)
    - Total findings by severity
    - Recommendation (PROCEED / RESOLVE ISSUES / REWORK)
  - **Findings Table**:
    - Requirements quality issues
    - Principles alignment issues
    - Traceability gaps
    - UK Gov compliance issues
  - **Coverage Matrices**:
    - Requirements coverage: X%
    - Principles compliance: X%
    - Traceability: X%
  - **UK Gov Compliance Dashboard**:
    - TCoP score: X/130
    - AI Playbook score: X/160
    - ATRS completeness: X%
  - **Metrics Dashboard**:
    - Quality score
    - Alignment score
    - Traceability score
    - Compliance score
  - **Next Steps**:
    - Critical actions
    - Suggested commands
    - Re-run guidance

**Expected Findings** (examples):
- ✅ HIGH-RISK AI system detected
- ⚠️ DPIA not yet completed (BLOCKING for high-risk AI)
- ⚠️ Human-in-the-loop not fully specified in requirements
- ⚠️ Bias testing methodology not documented
- ✅ Requirements comprehensive (50+ requirements)
- ✅ TCoP compliance good (Cloud-First, Accessibility, Security)
- ⚠️ ATRS not yet published on GOV.UK (required before live)

**Success Criteria**:
- ✅ Analysis runs without errors
- ✅ Detects UK Gov compliance issues
- ✅ Identifies HIGH-RISK AI requirements
- ✅ Provides actionable recommendations
- ✅ Calculates governance health score
- ✅ No files modified (read-only)

---

## Phase 6: Traceability

### Test: `/arckit.traceability`

**Command**:
```bash
/arckit.traceability Generate traceability matrix from requirements through design to tests
```

**Expected Output**:
- File: `projects/001-benefits-chatbot/traceability-matrix.md`
- Requirements → Design → Tests mapping
- Coverage statistics
- Gaps identified
- Orphan detection

**Success Criteria**:
- ✅ All requirements mapped
- ✅ Coverage percentage calculated
- ✅ Gaps highlighted
- ✅ Go/no-go recommendation

---

## Expected Test Results Summary

### Installation Verification
- ✅ 16 commands installed (complete set)
- ✅ 6 security/compliance templates installed
- ✅ Project structure correct
- ✅ Git repository initialized

### Command Functionality (All 16 Commands)

**Core Commands**:
- ✅ `/arckit.principles` - Creates architecture principles
- ✅ `/arckit.requirements` - Creates comprehensive requirements (50+ reqs)
- ✅ `/arckit.sow` - Generates vendor RFP

**Vendor Management**:
- ✅ `/arckit.evaluate` - Creates evaluation framework and scores vendors

**Design Review**:
- ✅ `/arckit.hld-review` - Reviews High-Level Design
- ✅ `/arckit.dld-review` - Reviews Detailed Design

**Strategic Planning**:
- ✅ `/arckit.wardley` - Creates strategic Wardley Maps for build vs buy

**Architecture Diagrams**:
- ✅ `/arckit.diagram` - Generates Mermaid diagrams (C4, deployment, sequence, data flow)

**Service Management**:
- ✅ `/arckit.servicenow` - Generates ServiceNow service design (CMDB, SLAs, monitoring)

**Traceability & Quality**:
- ✅ `/arckit.traceability` - Generates traceability matrix
- ✅ `/arckit.analyze` - Performs comprehensive governance analysis

**UK Government Compliance**:
- ✅ `/arckit.tcop` - Assesses all 13 TCoP points
- ✅ `/arckit.ai-playbook` - Assesses 10 principles + 6 themes for AI
- ✅ `/arckit.atrs` - Generates complete ATRS record (Tier 1 + Tier 2)

**Security Assessment**:
- ✅ `/arckit.secure` - UK Gov Secure by Design (NCSC CAF, Cyber Essentials, UK GDPR)
- ✅ `/arckit.mod-secure` - MOD Secure by Design (JSP 440, IAMM, security clearances)

### UK Government Features
- ✅ TCoP: All 13 points assessed with scoring
- ✅ AI Playbook: Risk-based assessment (High/Medium/Low)
- ✅ ATRS: Two-tier public disclosure template
- ✅ Digital Marketplace: G-Cloud procurement support
- ✅ GOV.UK services: Integration guidance (Pay, Notify, Design System)
- ✅ Compliance: GDPR, Equality Act, DPA 2018, WCAG 2.2 AA

### Quality Assurance
- ✅ Analyze command detects issues before implementation
- ✅ Governance health scoring (A-F grades)
- ✅ Actionable recommendations provided
- ✅ Read-only analysis (no files modified)

---

## Test Execution

To run the full test:

1. **Start in test repository**:
   ```bash
   cd /tmp/arckit-test-project
   claude  # or your AI assistant
   ```

2. **Run commands in sequence**:
   ```bash
   # Phase 1: Principles
   /arckit.principles Create architecture principles for UK Government DWP...

   # Phase 2: Requirements
   /arckit.requirements Build a benefits eligibility chatbot for DWP...

   # Phase 3: UK Gov Compliance
   /arckit.tcop Assess TCoP compliance for DWP benefits chatbot in Private Beta
   /arckit.ai-playbook Assess AI Playbook compliance for HIGH-RISK chatbot
   /arckit.atrs Generate ATRS record for DWP benefits chatbot

   # Phase 4: Vendor Procurement (optional)
   /arckit.sow Generate SOW for vendor RFP, 9-month, £1.5M, G-Cloud
   /arckit.evaluate Create evaluation framework for vendors

   # Phase 5: Quality Analysis
   /arckit.analyze

   # Phase 6: Traceability
   /arckit.traceability Generate traceability matrix
   ```

3. **Verify outputs**:
   ```bash
   # Check all files created
   tree projects/001-benefits-chatbot/

   # Check file sizes (should be substantial)
   wc -l projects/001-benefits-chatbot/*.md
   ```

---

## Success Metrics

**Overall Test Pass Criteria**:
- ✅ All 16 commands execute without errors
- ✅ All expected files created
- ✅ UK Government features work correctly (TCoP, AI Playbook, ATRS, Security Assessments)
- ✅ ServiceNow, Wardley Maps, and Diagram commands work correctly
- ✅ Analyze command detects real issues
- ✅ Output quality is high (comprehensive, actionable, realistic)
- ✅ Ready for real-world UK Government project use

**Target Governance Health Score** (from `/arckit.analyze`):
- **B grade (80-89%)** or higher for comprehensive test project
- Critical issues flagged and documented
- Remediation guidance provided

---

## Known Expected Issues

The analyze command **should** detect these issues (by design):

1. **DPIA not completed** - CRITICAL for HIGH-RISK AI (blocking)
2. **Human-in-the-loop not fully documented** - HIGH (required for high-risk)
3. **Bias testing methodology incomplete** - HIGH (fairness requirement)
4. **ATRS not published to GOV.UK** - MEDIUM (required before live)
5. **No actual HLD/DLD yet** - MEDIUM (design phase not started)

These are **expected findings** that demonstrate the analyze command is working correctly by identifying real gaps in a test project.

---

## Test Repository Location

**Path**: `/tmp/arckit-test-project-v6-patent-system`

**Contents**:
```
/tmp/arckit-test-project-v6-patent-system/
├── .arckit/
│   ├── memory/
│   │   └── architecture-principles.md (after /arckit.principles)
│   ├── scripts/
│   └── templates/ (6 security & compliance templates)
│       ├── servicenow-design-template.md
│       ├── tcop-review-template.md
│       ├── ukgov-secure-by-design-template.md
│       ├── mod-secure-by-design-template.md
│       ├── wardley-map-template.md
│       └── architecture-diagram-template.md
├── .claude/
│   └── commands/ (16 commands - complete set)
├── projects/
│   └── 001-benefits-chatbot/ (after /arckit.requirements)
│       ├── requirements.md
│       ├── wardley-maps/ (after /arckit.wardley)
│       ├── diagrams/ (after /arckit.diagram)
│       ├── sow.md (after /arckit.sow)
│       ├── evaluation-criteria.md (after /arckit.evaluate)
│       ├── tcop-review.md (after /arckit.tcop)
│       ├── ai-playbook-assessment.md (after /arckit.ai-playbook)
│       ├── atrs-record.md (after /arckit.atrs)
│       ├── ukgov-secure-by-design.md (after /arckit.secure)
│       ├── servicenow-design.md (after /arckit.servicenow)
│       └── traceability-matrix.md (after /arckit.traceability)
└── README.md
```

**Ready for testing!** 🚀
