# Contributing

Thanks for helping improve this demo content.

## Ground rules

- **Keep everything fictional.** Do not add real company names, real people, real customer data, credentials, or real phone numbers. Use `.example` domains and `555` phone numbers.
- **Keep facts consistent across documents.** If you change a number in one PDF (for example, the gift limit), update every document and `docs/DEMO_SCRIPT.md` that mentions it.
- **Do not edit PDFs by hand.** Edit the content in `src/` and rebuild with `python src/build_all.py`.
- **Keep PDFs text-based.** Scanned images will not index well in a vector database.

## Workflow

1. Fork the repo and create a branch.
2. Edit the relevant script in `src/`.
3. Run `python src/build_all.py` and open the changed PDFs.
4. Update `docs/DEMO_SCRIPT.md` if any answer changed.
5. Open a pull request describing what changed and why.
