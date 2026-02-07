# Testing

```bash
curl -i --location --request POST "$DIFY_API_BASE_URL/datasets/$DIFY_DATASET_ID/retrieve" \
  --header 'Content-Type: application/json' \
  --header "Authorization: Bearer $DIFY_API_KEY" \
  --data @assets/example-request.json
```

Checklist:
- 200 response with `query` and `records` fields.
- `records` can be empty if no matches.
