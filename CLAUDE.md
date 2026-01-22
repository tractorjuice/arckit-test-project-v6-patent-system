# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an **ArcKit demonstration repository** showcasing enterprise architecture governance artifacts for the UK Intellectual Property Office (IPO) Patent Management System modernization project.

ArcKit provides 40 slash commands for generating architecture artifacts. This repository contains example outputs and can be used to generate additional documents.

## Using ArcKit Commands

```bash
# Start Claude Code in this directory
claude

# Generate artifacts using slash commands:
/arckit.principles Create principles for UK government IP services
/arckit.stakeholders Analyze stakeholders for patent management modernization
/arckit.requirements Create requirements for online patent application system
/arckit.wardley Create Wardley map for patent system procurement strategy
```

## Repository Structure

```
.arckit/
├── memory/                    # Global architecture principles
├── templates/                 # Document templates (40 types)
└── scripts/bash/              # create-project.sh, generate-document-id.sh

.claude/commands/              # ArcKit slash commands (arckit.*.md)

projects/
└── 001-patent-management-system-for-the-intellectual-property-office/
    ├── requirements.md        # Business, functional, non-functional requirements
    ├── stakeholder-drivers.md # Stakeholder analysis with goals and outcomes
    ├── sow.md                 # Statement of Work (vendor RFP)
    ├── evaluation-criteria.md # Vendor scoring framework
    ├── tcop-assessment.md     # Technology Code of Practice compliance
    ├── traceability-matrix.md # Requirements to design mapping
    ├── analysis-report.md     # Governance quality analysis
    └── wardley-maps/          # Strategic Wardley maps
```

## Key Patterns

**Requirement ID Prefixes** used throughout artifacts:
- `BR-xxx`: Business Requirements
- `FR-xxx`: Functional Requirements
- `NFR-xxx`: Non-Functional (NFR-P performance, NFR-SEC security, NFR-S scalability, NFR-A availability, NFR-C compliance)
- `INT-xxx`: Integration Requirements
- `DR-xxx`: Data Requirements

**Traceability Chain**: Stakeholders → Goals → Requirements → Design Components → User Stories

**UK Government Context**: This project targets UK public sector with GDS Service Standard, Technology Code of Practice (TCoP), NCSC security frameworks, and Digital Marketplace procurement (G-Cloud/DOS).

## Generating New Artifacts

Commands check prerequisites before generating. Typical workflow:

1. `/arckit.principles` → Global principles (`.arckit/memory/architecture-principles.md`)
2. `/arckit.stakeholders` → Stakeholder analysis
3. `/arckit.risk` → Risk register (HM Treasury Orange Book)
4. `/arckit.sobc` → Strategic Outline Business Case (Green Book 5-case model)
5. `/arckit.requirements` → Comprehensive requirements
6. `/arckit.data-model` → Data model with ERD and GDPR compliance
7. `/arckit.research` → Technology research with build vs buy analysis
8. `/arckit.wardley` → Strategic Wardley maps
9. `/arckit.sow` → Statement of Work (vendor RFP)
10. `/arckit.evaluate` → Vendor evaluation framework
11. `/arckit.tcop` → Technology Code of Practice assessment
12. `/arckit.traceability` → Requirements traceability matrix

All commands use templates from `.arckit/templates/` and output to the project directory.
