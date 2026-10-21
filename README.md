# <WardLedger>

> Fill this top section from your Examate project card on Day 1. Replace every line in angle brackets.

## Problem
<Research teams working with multiple healthcare investment funds often struggle to manage each client's information separately.

All five clients use the same public hospital reports, presentations, and sustainability reports, but each also has private meeting notes and financial models.

Managing these files in separate folders manually can lead to mistakes and accidentally expose confidential client information.

Even a small data leak could reveal a client's investment opinions or research strategy to competitors.

WardLedger aims to solve this problem by bringing public research and private client information into one workspace while ensuring that each client can access only the information they are authorized to see.
>

## Who it is for
<Research operations lead at a Chennai healthcare-sector advisory boutique serving multiple investment fund clients.

Healthcare-sector research analyst who needs to analyze public hospital reports alongside confidential, client-specific meeting notes and financial models.>

## Signature feature
<A tenant-isolated research workspace with PostgreSQL row-level security and a per-answer source wall that distinguishes citations from shared public reports and the current client's private notes, preventing cross-client information leakage.>

## Hardest problem (my interview story)
<The hardest problem is ensuring strict isolation between five investment fund clients while allowing all of them to access the same public hospital research documents. Every document chunk must carry a tenant ID and a visibility flag indicating whether it is public or client-private, with PostgreSQL row-level security enforcing access restrictions rather than relying only on the LLM prompt. I will test the system with more than 100 adversarial prompts designed to expose another client's private information and aim for zero cross-tenant leaks.>

## Dataset

| Source | Link | Documents | Pages | Licence / terms |
|---|---|---|---|---|
| Apollo Hospitals | [Investor Relations](https://www.apollohospitals.com/investor-relations) | Annual reports, investor presentations and BRSRs for 3 years | To be counted | Publicly available documents; check individual reuse terms |
| Fortis Healthcare | [Official Website](https://www.fortishealthcare.com/) | Annual reports, investor presentations and BRSRs for 3 years | To be counted | Publicly available documents; check individual reuse terms |
| Max Healthcare | [Official Website](https://www.maxhealthcare.in/) | Annual reports, investor presentations and BRSRs for 3 years | To be counted | Publicly available documents; check individual reuse terms |
| Narayana Health | [Official Website](https://www.narayanahealth.org/) | Annual reports, investor presentations and BRSRs for 3 years | To be counted | Publicly available documents; check individual reuse terms |
| KIMS Hospitals | [Official Website](https://www.kimshospitals.com/) | Annual reports, investor presentations and BRSRs for 3 years | To be counted | Publicly available documents;

Target dataset: At least 15 annual reports, 30 investor presentations, and 5,000+ pages of public hospital-sector research, supplemented by synthetic private notes for five clients. Actual document counts and page totals will be recorded after collection and ingestion.

## 10 real questions
See [docs/QUESTIONS.md](docs/QUESTIONS.md).

## Run it
```bash
python -m venv .venv

# Activate the environment
source .venv/bin/activate
# Windows: .venv\Scripts\activate

pip install -r requirements-dev.txt

# Configure environment variables
cp .env.example .env
# Windows: copy .env.example .env

uvicorn app.main:app --reload

# Health check
curl localhost:8000/health
```

## Live link
<Added in Week 2>
