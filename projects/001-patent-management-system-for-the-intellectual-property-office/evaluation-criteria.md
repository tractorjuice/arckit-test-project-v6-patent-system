# Vendor Evaluation Criteria: Patent Management System for the UK Intellectual Property Office

**Document Type**: Vendor Evaluation Framework
**RFP ID**: RFP-IPO-PMS-2025-001
**Project ID**: 001
**Version**: 1.0
**Date**: 2025-10-15
**Evaluation Lead**: Dr. Emily Roberts (Enterprise Architect)
**Evaluation Committee**: Enterprise Architecture Team, CISO, Product Owner, Procurement

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
   “
2. Mandatory Qualifications Check (Pass/Fail) [2 days]
   “ (Qualified vendors only proceed)
3. Individual Technical Scoring (Blind to Cost) [1 week]
   “
4. Consensus Technical Scoring Meeting [1 day]
   “
5. Shortlist Top 3-5 Vendors [1 day]
   “
6. Cost Proposals Opened (Shortlisted only) [1 day]
   “
7. Cost Scoring [1 day]
   “
8. Combined Technical + Cost Scoring [1 day]
   “
9. Vendor Presentations & Q&A [1 week]
   “
10. Reference Checks (Parallel with presentations) [1 week]
   “
11. Final Scoring Adjustment & Selection [2 days]
   “
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

**Scoring Scale** (applied to each subcriterion):
- **Excellent (90-100%)**: Exceeds expectations; innovative approach; demonstrates deep expertise; minimal risks
- **Good (75-89%)**: Meets all expectations; sound approach; minor concerns requiring clarification
- **Adequate (60-74%)**: Meets most expectations; workable approach; some concerns or gaps
- **Weak (40-59%)**: Meets minimum expectations; significant concerns; substantial gaps or risks
- **Unacceptable (0-39%)**: Does not meet expectations; major flaws; unworkable approach

---

## 5. Final Scoring Formula

**Final Score = (Technical Score × 0.60) + (Cost Score × 0.40)**

**Cost Scoring**: Lowest Price Best Value
- Formula: `Cost Score = (Lowest Price / Vendor Price) × 40`

**Minimum Technical Threshold**: Vendors must score **e42/60 (70%)** to be considered for shortlist.

---

**Document Version**: 1.0
**Generated**: 2025-10-15 via ArcKit Evaluation Tool
**Next Steps**: Await proposal submissions on 2025-11-30, conduct mandatory qualifications check, begin scoring
