# ArcKit Test Project v1

**Full-featured test project for ArcKit - Enterprise Architecture Governance Toolkit**

🎯 **Purpose**: Test all ArcKit features with a realistic UK Government AI project scenario

---

## 🚀 Quick Start

### GitHub Codespaces (Recommended)

1. Click the green **"Code"** button above
2. Select **"Open with Codespaces"** → **"New codespace"**
3. ArcKit is pre-configured - start Claude Code or Codex CLI!
4. Follow **[QUICKSTART.md](QUICKSTART.md)** for test commands

---

## 📋 Test Scenario

**Project**: AI-Powered Patent Prior Art Search System for UK Intellectual Property Office (IPO)

**Details**:
- **System**: HIGH-RISK AI system (affects patent grant decisions and legal rights)
- **Scope**: Machine learning system using NLP and semantic search for global patent databases
- **Purpose**: Suggest prior art for patent examiners to improve patent quality
- **Requirements**: TCoP compliance, AI Playbook, ATRS, UK GDPR, explainability for legal challenges
- **Compliance**: Patent data security (OFFICIAL-SENSITIVE), transparency requirements
- **Procurement**: Via G-Cloud Digital Marketplace

---

## ✅ Pre-Installed Commands (17 total)

All commands ready in `.claude/commands/`:
n**OpenAI Codex CLI users**: Commands also available in `.codex/prompts/` - use `/prompts:arckit.command` format. See [.codex/README.md](.codex/README.md).

### Core Governance
- `/arckit.principles` - Architecture principles
- `/arckit.stakeholders` - Stakeholder drivers, goals, and outcomes analysis
- `/arckit.requirements` - Comprehensive requirements

### Strategic Planning
- `/arckit.wardley` - Wardley Mapping for build vs buy decisions
- `/arckit.diagram` - Architecture diagrams with Mermaid

### Vendor Management
- `/arckit.sow` - Statement of Work (RFP)
- `/arckit.evaluate` - Vendor evaluation framework

### Design Review
- `/arckit.hld-review` - High-level design review
- `/arckit.dld-review` - Detailed design review

### Service Management
- `/arckit.servicenow` - ServiceNow service design (NEW!)

### Traceability
- `/arckit.traceability` - Requirements traceability matrix

### UK Government
- `/arckit.tcop` - Technology Code of Practice (13 points)
- `/arckit.ai-playbook` - AI Playbook (10 principles + 6 themes)
- `/arckit.atrs` - Algorithmic Transparency Record

### Quality Assurance
- `/arckit.analyze` - Governance quality analysis

---

## 📚 Documentation

- **[QUICKSTART.md](QUICKSTART.md)** - Fast start with all commands
- **[TEST-PLAN.md](TEST-PLAN.md)** - Detailed test plan with expected outputs

---

## 🎯 What Gets Tested

### Core Features
- ✅ Architecture principles generation
- ✅ Comprehensive requirements (50+ requirements)
- ✅ Vendor procurement (SOW, evaluation)
- ✅ Requirements traceability

### Strategic Planning (NEW!)
- ✅ Wardley Mapping for build vs buy decisions
- ✅ Component evolution analysis (Genesis → Commodity)
- ✅ UK Government Digital Marketplace procurement strategy
- ✅ GOV.UK services reuse identification

### Architecture Diagrams
- ✅ C4 Model diagrams (Context, Container, Component)
- ✅ Deployment diagrams (Cloud First compliance)
- ✅ Sequence diagrams (API interactions)
- ✅ Data flow diagrams (UK GDPR/PII handling)
- ✅ Integration with Wardley Map evolution stages
- ✅ Mermaid syntax for GitHub rendering

### ServiceNow Service Management (NEW!)
- ✅ CMDB design from architecture diagrams
- ✅ SLA definitions from NFRs
- ✅ Incident management design (P1-P5 priority matrix)
- ✅ Change management plan with risk assessment
- ✅ Monitoring & alerting plan
- ✅ Service transition plan and go-live checklist
- ✅ ITIL v4 alignment

### UK Government Features
- ✅ Technology Code of Practice - All 13 points
- ✅ AI Playbook - 10 principles + 6 ethical themes
- ✅ ATRS - Full transparency record
- ✅ Digital Marketplace - G-Cloud procurement

### Quality Assurance
- ✅ Governance health scoring
- ✅ Requirements quality checks
- ✅ Compliance verification
- ✅ Actionable recommendations

---

## 📊 Expected Results

After testing, you'll have:

```
projects/001-benefits-chatbot/
├── requirements.md (~50+ requirements)
├── wardley-maps/
│   └── procurement-strategy.md (Build vs Buy analysis)
├── diagrams/
│   ├── context-benefits-chatbot.md (C4 context diagram)
│   ├── container-benefits-chatbot.md (Technical architecture)
│   └── dataflow-pii-handling.md (UK GDPR compliance)
├── tcop-assessment.md (TCoP score ~70-90%)
├── ai-playbook-assessment.md (HIGH-RISK assessment)
├── atrs-record.md (Complete ATRS)
├── sow.md (Vendor RFP)
├── evaluation-criteria.md (Scoring framework)
├── servicenow-design.md (Service management design)
└── traceability-matrix.md (Requirements mapping)

.arckit/memory/
└── architecture-principles.md (UK Gov principles)
```

Plus analysis report from `/arckit.analyze` showing governance health score (B grade expected).

---

## 📖 More Information

- **ArcKit Repository**: https://github.com/tractorjuice/arc-kit
- **Latest Release**: v0.2.1
- **Issues**: https://github.com/tractorjuice/arc-kit/issues

---

**Ready to test?** Open in Codespaces and follow [QUICKSTART.md](QUICKSTART.md)! 🚀
