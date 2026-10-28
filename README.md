# Brightwater Robotics: Agentforce Data Library Demo Content

A ready-made set of fictional HR and finance documents for workshops that teach how to build an **Agentforce Data Library** (a vector-search knowledge source) and ground an Agentforce agent in it.

Brightwater Robotics, Inc. is **entirely fictional**. Because every fact in these documents is invented, a base model cannot know any of them. When the agent answers correctly after you attach the library, the audience can see that the answer came from the documents.

## What's in the box

| File | Pages | What it demonstrates |
|------|------:|----------------------|
| [`pdfs/BW_Employee_Handbook_Part1_Welcome_and_Employment.pdf`](pdfs/BW_Employee_Handbook_Part1_Welcome_and_Employment.pdf) | 6 | Prose plus tables: onboarding, pay, reviews, referrals, severance |
| [`pdfs/BW_Employee_Handbook_Part2_Time_Off_and_Benefits.pdf`](pdfs/BW_Employee_Handbook_Part2_Time_Off_and_Benefits.pdf) | 5 | Table-heavy retrieval: PTO tiers, holidays, health plans, 401(k) |
| [`pdfs/BW_Employee_Handbook_Part3_Conduct_Security_and_Hybrid_Work.pdf`](pdfs/BW_Employee_Handbook_Part3_Conduct_Security_and_Hybrid_Work.pdf) | 4 | Security, AI-tool rules, hybrid work |
| [`pdfs/BW_Travel_and_Expense_Policy_2026.pdf`](pdfs/BW_Travel_and_Expense_Policy_2026.pdf) | 8 | Long document with tiers, caps, exceptions, and edge cases |
| [`pdfs/BW_Travel_and_Expense_Quick_Reference_FAQ.pdf`](pdfs/BW_Travel_and_Expense_Quick_Reference_FAQ.pdf) | 3 | Short Q&A for precise retrieval |
| [`pdfs/BW_Travel_and_Expense_Policy_2024_ARCHIVED.pdf`](pdfs/BW_Travel_and_Expense_Policy_2024_ARCHIVED.pdf) | 3 | Deliberately conflicting, superseded version (for the freshness discussion) |

Supporting material:

- [`docs/DEMO_SCRIPT.md`](docs/DEMO_SCRIPT.md): 25 test questions with expected answers and section references, including multi-step, version-conflict, and out-of-scope questions. **Presenter's answer key. Do not upload it to the library.**
- [`docs/WORKSHOP_GUIDE.md`](docs/WORKSHOP_GUIDE.md): facilitator checklist and suggested agenda.
- [`src/`](src): Python scripts that generate the PDFs.

## Quick start

1. Download the six files in [`pdfs/`](pdfs).
2. In your Salesforce org, create an Agentforce Data Library and upload them. See [`docs/WORKSHOP_GUIDE.md`](docs/WORKSHOP_GUIDE.md) for a checklist.
3. Wait for indexing to finish, attach the library to your agent, and try the questions in [`docs/DEMO_SCRIPT.md`](docs/DEMO_SCRIPT.md).

Tip: ask 2 or 3 questions **before** attaching the library, then ask them again **after**. The contrast is the point of the demo.

## Rebuilding or customizing the PDFs

The PDFs are generated from Python so you can change any fact and rebuild.

```bash
python -m venv .venv && source .venv/bin/activate   # optional
pip install -r requirements.txt
python src/build_all.py
```

| Script | Produces |
|--------|----------|
| `src/handbook_part1.py` | Handbook Part 1 |
| `src/handbook_part2.py` | Handbook Part 2 |
| `src/handbook_part3.py` | Handbook Part 3 |
| `src/te_policy_2026.py` | Travel and Expense Policy 2026 |
| `src/te_2024_and_faq.py` | Archived 2024 policy and the Quick Reference FAQ |
| `src/bw_pdf.py` | Shared layout and styling helpers |

If you change a number, search the other PDFs and `docs/DEMO_SCRIPT.md` for the old value so the documents stay consistent.

## Repository layout

```
.
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── requirements.txt
├── pdfs/                  # The six documents to upload
├── docs/
│   ├── DEMO_SCRIPT.md     # Test questions and expected answers
│   └── WORKSHOP_GUIDE.md  # Facilitator checklist
├── src/                   # PDF generators
└── .github/workflows/     # CI that rebuilds the PDFs
```

## Disclaimer

All companies, people, policies, figures, systems (Harbor, Wayfarer, Ledgerly, Keystone), phone numbers, and email addresses are invented for training purposes. Phone numbers use the `555` range and email addresses use the reserved `.example` domain. Nothing here is legal, HR, or tax advice, and none of it reflects any real organization's policies.

This project is not affiliated with or endorsed by Salesforce. Agentforce is a trademark of Salesforce, Inc.

## License

[MIT](LICENSE). Replace the placeholder name in the license file with your own before publishing.
