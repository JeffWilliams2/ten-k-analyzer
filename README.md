# 10-K Analyzer

> Ask natural-language questions about SEC filings. Get cited answers in seconds.

**Status:** Phase 3 of build plan — coming soon

Open-source RAG engine for SEC 10-K filings. Section-aware chunking, citation-backed answers, year-over-year comparison.

**Live demo:** *coming soon*
**Built on:** [genai-rag-template] Private repo
**Commercial version:** *coming soon*

## What makes this different

Generic chunking destroys long-form documents. This analyzer chunks 10-Ks by section (Item 1A Risk Factors, Item 7 MD&A, etc.) and stores section as metadata in the vector database. At query time, retrieval is filtered by section, so questions about risk factors return coherent risk factor content — not random fragments from across the filing.

## Features (planned)

- [ ] EDGAR API ingestion
- [ ] Section-aware chunking
- [ ] Cited answers with source links
- [ ] Year-over-year diff for any section
- [ ] Multi-company comparison mode
- [ ] Streamlit demo UI

## Stack

Next.js, FastAPI, pgvector.

## Local development

```bash
git clone https://github.com/YOUR_USERNAME/10-k-analyzer
cd 10-k-analyzer
cp .env.example .env
docker compose up -d
pnpm install
python ingestion/edgar.py --ticker AAPL --years 2022,2023,2024
pnpm dev
```

## Roadmap

- [ ] EDGAR ingestion pipeline
- [ ] Section-aware chunker
- [ ] Single-question RAG mode (free tier)
- [ ] Comparison mode
- [ ] Public demo deployed
- [ ] Blog post published

## Disclaimer

For educational and research purposes. Not investment advice. SEC filings contain forward-looking statements that may not reflect current company performance.

## License

MIT
