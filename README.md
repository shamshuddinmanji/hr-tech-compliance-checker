# 🛡️ GenAI-Powered HR Tech Compliance Checker

> *Automating Third Party Risk Assessment for HR Technology Vendors using Generative AI*

---

## 📌 Overview

Organizations rely on dozens of third-party HR Tech systems — ATS, HRIS, Payroll, LMS, Background Verification, and more. Each of these vendors handles sensitive employee data, making **compliance verification** a critical but often manual, slow, and inconsistent process.

This project presents a **conceptual framework and prompt-based solution** for an AI-powered compliance checker that helps Third Party Risk Managers assess HR Tech vendors against major data privacy and security frameworks — automatically.

---

## 🎯 The Problem

| Challenge | Impact |
|---|---|
| Manual vendor reviews take days or weeks | Delays onboarding & renewals |
| Inconsistent assessment across reviewers | Compliance gaps go unnoticed |
| Keeping up with evolving regulations | GDPR, SOC 2, ISO 27001 updates missed |
| No standardized scoring for HR vendors | Risk comparison across vendors is impossible |

---

## 💡 The Solution

A **Gen AI-based compliance checker** that:

1. 📄 Accepts a vendor's **privacy policy, security documentation, or DPA** as input
2. 🤖 Uses a **Large Language Model (LLM)** with structured prompts to analyze the document
3. ✅ Maps findings against **compliance frameworks** (GDPR, SOC 2, ISO 27001)
4. 📊 Outputs a **Risk Score (0–5) + Gap Analysis + Actionable Recommendations**

---

## 🏗️ Architecture (Conceptual)

```
INPUT
  └── Vendor Policy Document (PDF / URL / Text)
        │
        ▼
PROCESSING
  └── Gen AI Engine (LLM + Structured Prompt Templates)
        │
        ├── Framework Mapping Layer
        │     ├── GDPR Articles Checklist
        │     ├── SOC 2 Trust Principles
        │     └── ISO 27001 Controls
        │
        ▼
OUTPUT
  └── Compliance Report
        ├── Overall Risk Score (0–5)
        ├── Framework-wise Gap Analysis
        ├── Red Flags & Observations
        └── Recommended Next Steps
```

---

## 🔍 Compliance Frameworks Covered

> Global frameworks only — applicable across all regions.

### 1. GDPR (General Data Protection Regulation)
- Lawful basis for data processing
- Data subject rights (access, deletion, portability)
- Data retention policies
- Cross-border data transfer safeguards
- Data breach notification timelines

### 2. SOC 2 (Trust Services Criteria)
- Security (CC6 controls)
- Availability
- Confidentiality
- Processing Integrity
- Privacy

### 3. ISO 27001
- Information Security Policy
- Access Control
- Cryptography
- Supplier Relationships (A.15)
- Incident Management

---

## 🧠 Sample Prompt Template

```
SYSTEM:
You are a Third Party Risk Assessment expert specializing in HR Technology vendors.
Analyze the provided vendor document and evaluate compliance against the specified framework.
Return a structured JSON response with risk_score, findings, gaps, and recommendations.

USER:
Vendor: [VENDOR A / VENDOR B — anonymized]
Framework: [GDPR / SOC2 / ISO27001]
Document: [PASTE VENDOR POLICY TEXT HERE]

Evaluate the following:
1. Does the vendor clearly define the purpose of data processing?
2. Are data subject rights explicitly mentioned and accessible?
3. Is there a defined data retention and deletion policy?
4. Are sub-processors / sub-contractors disclosed?
5. Is there a data breach notification policy with defined timelines?
6. Are cross-border data transfer mechanisms mentioned?

Output format:
{
  "vendor": "",
  "framework": "",
  "risk_score": 0-5,
  "risk_level": "Low / Medium / High / Critical",
  "findings": [],
  "gaps": [],
  "recommendations": [],
  "reviewed_on": ""
}
```

---

## 📋 Sample Output — Mock Assessment

```json
{
  "vendor": "Vendor A",
  "framework": "GDPR",
  "risk_score": 3,
  "risk_level": "Medium",
  "findings": [
    "Privacy policy clearly states lawful basis for processing candidate data",
    "Data subject access request process is documented",
    "Encryption at rest and in transit is confirmed"
  ],
  "gaps": [
    "No mention of data retention timelines for rejected candidates",
    "Sub-processors list is not publicly disclosed",
    "Data breach notification timeline exceeds GDPR's 72-hour requirement"
  ],
  "recommendations": [
    "Request vendor to share updated sub-processor list via DPA",
    "Negotiate SLA clause for breach notification within 48 hours",
    "Confirm data deletion policy for candidate records post 12 months"
  ],
  "reviewed_on": "2025-05-11"
}
```

> **Scoring Guide:**
> | Score | Risk Level |
> |---|---|
> | 5 | Low Risk — Fully Compliant |
> | 4 | Low-Medium — Minor Gaps |
> | 3 | Medium — Notable Gaps |
> | 2 | High — Significant Gaps |
> | 1 | Critical — Major Non-Compliance |
> | 0 | Unacceptable — Do Not Proceed |

---

## 📁 Repository Structure

```
hr-tech-compliance-checker/
│
├── README.md                        ← You are here
├── frameworks/
│   ├── gdpr_checklist.md
│   ├── soc2_checklist.md
│   └── iso27001_checklist.md
│
├── prompt_templates/
│   ├── gdpr_prompt.txt
│   ├── soc2_prompt.txt
│   └── general_tprm_prompt.txt
│
├── sample_outputs/
│   └── vendor_a_gdpr_assessment.json
│
└── docs/
    └── architecture_overview.png
```

---

## 🚀 How to Use (Conceptual Workflow)

1. **Collect** vendor's privacy policy, DPA, or security documentation
2. **Select** the relevant compliance framework for your region/requirement
3. **Paste** the document into the prompt template
4. **Run** the prompt via any LLM (ChatGPT, Claude, Gemini, or your enterprise AI tool)
5. **Review** the structured output and log findings in your TPRM system
6. **Act** on recommendations during vendor negotiations or renewal cycles

---

## 👤 Author

**Shamshuddin Manji**
Third Party Risk Manager | HR Tech Systems
*Generative AI Foundations for HR Professionals — Coursera (2025)*

---

## 📜 Disclaimer

This is a conceptual framework and educational project. The prompt templates and outputs are illustrative. Always involve legal and compliance teams for actual vendor risk decisions.

---

## ⭐ If you found this useful, give it a star!
