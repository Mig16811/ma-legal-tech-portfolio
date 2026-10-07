Portfolio: Legal Tech & AI Compliance Architect
Welcome to my professional portfolio. I am a Senior Jurist and Legal Tech Architect specializing in European Union digital regulations (AI Act, GDPR, DSA, DMA, NIS2, DORA). Below is an architectural overview of my active projects, demonstrating how I bridge traditional legal advisory with practical software engineering to automate compliance and mitigate corporate risk.

🏛️ Project 1: MA Legal Tech Suite (EU Compliance RAG Platform)
Live Concept: prova-legal.eu (Demonstration Environment)
Executive Summary
A comprehensive Retrieval-Augmented Generation (RAG) web application engineered from scratch to operationalize regulatory compliance. Designed for corporate and legal departments, this system transforms static EU legislation into an interactive, zero-data-leakage querying engine.
System Architecture & Tech Stack
•	Frontend & Core: Python, Streamlit (Hosted via Render).
•	Data Ingestion: 6-tier YAML semantic index strictly grounded in official EU CELEX legal databases.
•	AI Integration: Configured for local Large Language Models (LLMs) like Qwen 2.5 and Mistral Nemo via Model Context Protocol (MCP).
•	Infrastructure: Docker, Cloudflare DNS, Local Navidrome server integration for private cloud synchronization via Syncthing.

### 🔍 Code Snapshot: Security & Access Governance
Below is a brief snippet demonstrating the core B2B security logic from `app_hub.py`. In this public showcase, actual production keys and client tokens have been strictly redacted to ensure zero data leakage, demonstrating secure coding practices.

```python
import os

# =====================================================================
# SYSTEM SECURITY & B2B LICENSE GOVERNANCE
# =====================================================================

# 1. Primary Master Key (Secured via Environment Variable)
MASTER_KEY_1 = os.getenv("MASTER_KEY_PROVA_LEGAL", "DEFAULT_SECURE_FALLBACK")

# 2. Hardcoded Subsidiary Master Key (Anti-lockout failsafe)
MASTER_KEY_2 = "[REDACTED_FAILSAFE_KEY_FOR_SECURITY]"

# 3. Client Access Tiers
CHAVES_ACESSO = {
    "[REDACTED_CLIENT_TOKEN_1]": "SUITE_1",
    "[REDACTED_CLIENT_TOKEN_2]": "SUITE_2",
}

def validar_licenca_api(chave):
    """
    Validates the provided license key against administrative and client tiers,
    granting appropriate system access levels for compliance tool suites.
    """
    chave = chave.strip()
    
    # Administrative validation allowing access via primary OR subsidiary key
    if chave == MASTER_KEY_1 or chave == MASTER_KEY_2:
        return "MASTER", "✅ Administrative Access Granted."
        
    # Client tier validation
    if chave in CHAVES_ACESSO:
        nivel = CHAVES_ACESSO[chave]
        return nivel, f"✅ License confirmed. {nivel} tier unlocked."
        
    return None, "❌ License Error: Invalid or unrecognized key."

```

Business Value (Why it matters)
•	Risk Mitigation: Ensures precise legal answers grounded only in official CELEX data, avoiding AI hallucinations.
•	Data Privacy: By utilizing local LLM deployment and MCP, sensitive corporate prompts and data never leave the internal network, ensuring absolute GDPR and NDA compliance.
•	Operational Efficiency: Drastically reduces the time required for legal research, regulatory tracking, and impact analysis for frameworks like NIS2 and the AI Act.

⚙️ Project 2: Automated Legal Document Transformation Pipeline
Executive Summary
A custom Python automation architecture designed to optimize knowledge management and accelerate third-party due diligence and contract review processes.
System Architecture & Tech Stack
•	Core: Python, Document Parsing Libraries, VS Code.
•	Workflow: Programmatically extracts content from disparate MS Word documents (.docx), generates contextual internal headings based on file metadata, and dynamically merges them into unified, AI-ready .txt outputs.
Business Value
•	Process Automation: Eliminates manual formatting overhead in legal departments.
•	Due Diligence Acceleration: Prepares massive datasets (e.g., hundreds of vendor contracts) for rapid AI ingestion and compliance auditing, a critical asset for M&A or supply chain risk assessments.

📱 Project 3: Legal Operations & Smart Workflows
Executive Summary
Implementation of no-code management systems and advanced interactive documentation to standardize corporate governance.
Tech Stack
•	AppSheet, Google Workspace APIs, Nitro PDF Pro.
Business Value
•	Cross-Departmental Synergy: Developed mobile applications linking Google Sheets and Drive to coordinate property and asset management.
•	Contract Standardization: Engineered dynamic, pre-fillable interactive PDF forms with embedded logic, checkboxes, and digital signature workflows to reduce administrative friction in procurement and corporate HR.

