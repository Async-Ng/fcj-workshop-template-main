---
title: "Week 13 Worklog"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 1.13. </b> "
---

### Objectives for Week 13

- Complete and fix the AI Search (semantic search) feature in the FindNest project.
- Perform end-to-end testing from frontend → API Gateway → Lambda → Bedrock/DynamoDB.
- Improve prompts, handle errors, and optimize response performance.

### Tasks planned this week

| Day | Task                                                            | Start Date | End Date   | Notes                                 |
| --- | --------------------------------------------------------------- | ---------- | ---------- | ------------------------------------- |
| Mon | Experiment with different prompts to improve semantic search    | 01/12/2025 | 01/12/2025 | Compare few-shot vs minimal prompts   |
| Tue | Debug Lambda search handler and validate Bedrock requests       | 02/12/2025 | 02/12/2025 | Fix input format for Bedrock          |
| Wed | Add input validation and fallback logic                         | 03/12/2025 | 03/12/2025 | Prevent returning noisy results       |
| Thu | Optimize DynamoDB queries and add temporary caching             | 04/12/2025 | 04/12/2025 | Use TTL and in-memory cache in Lambda |
| Fri | Integration testing with FE, collect feedback, fix UI edgecases | 05/12/2025 | 05/12/2025 | Align request/response schema         |

### Results for Week 13

- AI Search now returns results that better match user queries; semantic relevance improved noticeably.
- Latency reduced by ~30% for common queries thanks to temporary Lambda caching and DynamoDB query optimization.
- Input parsing errors were handled; the frontend now receives clear error codes for malformed requests.
- End-to-end integration (FE → API Gateway → Lambda → Bedrock/DynamoDB) is stable in dev/staging environments.
