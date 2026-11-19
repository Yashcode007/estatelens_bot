# Validation results

Tested 20 November 2026, India time (19 November UTC).

Live URL: https://estate-lens-darglobal-wasalt.jocundclout8.chatgpt.site

Live free model: `baidu/ernie-5.5-flash-preview:free` via OpenRouter.

| Question | Observed result | Status |
| --- | --- | --- |
| Compare DG1 and Da Vinci Tower in Dubai. | Cited comparison of location, status, units and amenities; disclosed unknown prices and conflicting size ranges. | Pass |
| Show apartments in Jeddah under SAR 500,000. | Al Bawadi at SAR 280,000 and Al Faiha at SAR 340,000; flagged unusual reported areas. | Pass |
| What amenities does AIDA in Muscat offer? | Cited pools, fitness/wellness, parks, hiking/cycling, dining and retail. | Pass |
| Show Wasalt villas in Riyadh. | Al-Arid villa, SAR 1,900,000, 210 sqm, seven bedrooms, six bathrooms. | Pass |
| What is the exact price of DG1? | Explained that the asking price was not captured. | Pass |
| Show villas in Riyadh under SAR 100. | No matching evidence; did not claim no such property exists on the websites. | Pass |

Full requests, answers, source IDs, timings and model metadata: `tests/results/live-validation.json`. The five AI answers took approximately 1.3–5.7 seconds in this run; free-model latency can vary. The no-match response is generated from retrieval without an LLM call.

Also verified:

- All 11 automated application tests pass.
- Docker image builds and runs as a non-root user with a health check.
- Health, catalog and chat endpoints respond in Docker.
- The deployed application serves HTML, a 12-record catalog and a health response with AI configured.
- The redesigned browser JavaScript parses and the Worker output builds.

The latest UI refinements are in this source package. The live URL retains the earlier UI because publishing the new UI through the available hosting pipeline requires a Git commit/push, which was not authorized for this revision. The retrieval and chatbot request handler are the same in both versions.

Interactive visual browser QA remains unverified: the browser runtime could not start and the managed preview relay failed. Live API checks establish answer behavior, not complete visual or accessibility coverage. Citation IDs and expected source records were checked automatically; the representative answers above were also reviewed against the collected records. Citation checks alone cannot guarantee every future generated claim.
