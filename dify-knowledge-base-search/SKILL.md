---
name: dify-knowledge-base-search
description: Dify dataset retrieve API for knowledge base chunk search/testing. Use when integrating or debugging Dify knowledge base retrieval requests, retrieval_model options, or response shaping.
---

# Dify Knowledge Base Search

## Required parameters
- `data`: JSON payload containing the `query` string (optional `retrieval_model`).
- Read from ENV:
  - `DIFY_API_BASE_URL`: base API URL; include `/v1` in the value.
  - `DIFY_DATASET_ID`: knowledge base (dataset) ID.
  - `DIFY_API_KEY`: Dify API key; send as `Authorization: Bearer <DIFY_API_KEY>`.

## Quick start
- Endpoint: `${DIFY_API_BASE_URL}/datasets/${DIFY_DATASET_ID}/retrieve`
- Header: `Authorization: Bearer <DIFY_API_KEY>`
- Body: JSON with `query` (optional `retrieval_model`); `assets/example-request.json` shows the format.

- Example call:
  ```bash
  curl -sS --location --request POST "$DIFY_API_BASE_URL/datasets/$DIFY_DATASET_ID/retrieve" \
    --header 'Content-Type: application/json' \
    --header "Authorization: Bearer $DIFY_API_KEY" \
    --data @assets/example-request.json
  ```

## Request & output
- POST `{ "query": string, "retrieval_model"?: object }`.
- `retrieval_model` fields: `search_method`, `reranking_enable`, `reranking_mode`, `reranking_model`, `weights`, `top_k`, `score_threshold_enabled`, `score_threshold` (see `references/request-response.md`).
- Responses: 200 with `{ query, records: [...] }`.

## References
- `references/env.md`
- `references/request-response.md`
- `references/testing.md`

## Assets
- `assets/example-request.json`
