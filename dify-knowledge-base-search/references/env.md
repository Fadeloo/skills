# Env (caller side)
- Base URL: `$DIFY_API_BASE_URL` (e.g., `https://api.dify.ai/v1`)
- Dataset ID: `$DIFY_DATASET_ID`
- API key: `$DIFY_API_KEY`

Endpoint: `${DIFY_API_BASE_URL}/datasets/${DIFY_DATASET_ID}/retrieve`
Headers:
- `Content-Type: application/json`
- `Authorization: Bearer $DIFY_API_KEY`
