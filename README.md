# VaultLens: Privacy-First Automated Data EDA Observability 
All Rights Reserved - Only Recruiters, Employers, and those who request access are permitted to use/test

## Quick Start

**Install:**
```bash
pip install vault-lens
```

**Run with Ollama (Default - 100% Private):**
```bash
# First time: Install Ollama and pull model
# Visit https://ollama.com/download
ollama pull llama3.2

# Run VaultLens
python vaultlens/main.py --file test_data.csv
```

**Run with OpenAI (Non-Private Data):**
```bash
# Add your API key to .env file
echo "OPENAI_API_KEY=your-key-here" > .env

# Run with OpenAI flag
python vaultlens/main.py --file test_data.csv --model openai
```

## The Business Value

In modern data environments, companies face two major hurdles: **Data Privacy (GDPR/HIPAA)** and **Data Integrity**.

Most "AI Data Assistants" require uploading sensitive raw data to a third-party cloud, risking privacy breaches. Furthermore, LLMs often "hallucinate" mathematical statistics.

## Validation

Tested against the same 10K insurance dataset used in my [Insurance Claims Prediction](https://github.com/CharSiu8/insurance-claims-prediction-logistic-regression) project. The auditor correctly identified the same 982 null values in `credit_score` and 957 in `annual_mileage` that I found through manual EDA—confirming the pipeline replicates expert-level data quality checks automatically.

**This project solves these issues by:**

1. **Local-First Auditing:** All statistical analysis (null detection, type inconsistency checks, date validation) happens locally using Pandas—raw data never leaves your machine. 
2. **Hybrid Intelligence:** Deterministic Python logic ensures 100% mathematical accuracy. AI is used only to *interpret* the pre-computed findings and suggest remediation plans.
3. **Automation:** Built as a modular pipeline that can be integrated into automated workflows, rather than a manual "chat" interface.
4. **Flexible AI Providers:** Choose between Ollama (fully local, default) or OpenAI (cloud)—enabling 100% offline operation for maximum privacy.

## Requirements

To ensure privacy and performance, VaultLens requires:

* **Python:** `3.7` or higher.
* **Operating System:** Windows, macOS, or Linux.
* **Ollama:** For local AI analysis (recommended for private data)
* **Key Dependencies:** `pandas`, `openai`, `requests`, `python-dotenv`.

## License

© 2026 Steven Polino — All Rights Reserved

Recruiters/employers welcome to clone and test for evaluation purposes.

See [LICENSE](LICENSE) for full terms.
