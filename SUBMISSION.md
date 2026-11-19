# Technical assignment — EstateLens

Demo: https://estate-lens-darglobal-wasalt.jocundclout8.chatgpt.site

EstateLens combines public DarGlobal development information and Wasalt listing data into a property research chatbot. It retrieves relevant evidence using structured filters and BM25 ranking, sends that evidence to a free OpenRouter model, and presents answers with links to original source pages.

The project includes a Dockerfile, Compose configuration, a robots-aware collection script, a dated dataset with provenance, automated tests and a deployed web interface. The hosted Worker and Docker app share the same request handler.

Suggested review flow:

1. Ask “Compare DG1 and Da Vinci Tower in Dubai.”
2. Ask “Show apartments in Jeddah under SAR 500,000.” Check the original asking prices in the source cards.
3. Ask “What amenities does AIDA in Muscat offer?”
4. Ask for a payment plan or exact price absent from the snapshot. The assistant should acknowledge missing evidence.
5. Open Source library, search a city and download the dataset.
6. Review README.md for the collection limitations, architecture and Docker reproduction steps.

The dataset is intentionally small and auditable: 12 records across 7 cities. DarGlobal direct HTTP collection returned a security challenge, so its official pages were extracted with the public web reader. Wasalt detail pages were successfully scraped directly. Source conflicts and suspicious reported areas are disclosed rather than silently corrected.

The deployed demo has a server-side OpenRouter key configured and passed six live checks, including cited answers, budget retrieval, missing-price handling and no-match handling. The currently deployed model is baidu/ernie-5.5-flash-preview:free. Free models can be temporarily unavailable or rate limited. API keys are excluded from the source package.
