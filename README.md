# Privacy-First Automated Data Observability Pipeline

## The Business Value
In modern data environments, companies face two major hurdles: **Data Privacy (GDPR/HIPAA)** and **Data Integrity**.

Most "AI Data Assistants" require uploading sensitive raw data to a third-party cloud, risking privacy breaches. Furthermore, LLMs often "hallucinate" mathematical statistics.

## See related project that uses the same data: https://github.com/CharSiu8/insurance-claims-prediction-logistic-regression

**This project solves these issues by:**
1. **Local-First Auditing:** All statistical analysis (null detection, type inconsistency checks, date validation) happens locally using Pandas—raw data never leaves your machine.
2. **Hybrid Intelligence:** Deterministic Python logic ensures 100% mathematical accuracy. AI is used only to *interpret* the pre-computed findings and suggest remediation plans.
3. **Automation:** Built as a modular pipeline that can be integrated into automated workflows, rather than a manual "chat" interface.

## Tech Stack & Architecture
- **Language:** Python 3.x
- **Data Engineering:** Pandas
- **AI Integration:** OpenAI API (GPT-4o-mini)
- **Security:** python-dotenv (Environment Variable Management)
- **Version Control:** Git/GitHub

### Project Structure
| File | Purpose |
|------|---------|
| `main.py` | Application entry point and pipeline coordinator |
| `auditor.py` | Statistical engine—performs all data quality checks locally |
| `reporter.py` | Serializes audit results to JSON |
| `analyzer.py` | Sends audit metadata to OpenAI for interpretation |
| `.env` | Secure storage for API keys (ignored by Git) |

### Data Flow
```
CSV File → auditor.py (local analysis) → reporter.py (JSON) → analyzer.py (AI interpretation) → Summary
```

## Privacy Architecture
- **What stays local:** Raw data, all statistical computations
- **What is sent to OpenAI:** Only audit metadata (column names, data types, row indices with issues)—no actual data values are transmitted

## Impact
By automating the Exploratory Data Analysis (EDA) phase, this tool reduces the "Data Cleaning" bottleneck—which typically takes up 80% of a Data Scientist's time—allowing for faster, safer insights.
