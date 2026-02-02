# Testing

```bash
curl -i --location --request POST "https://qyyqlnwqwgvzxnccnbgm.supabase.co/functions/v1/sci_search" \
  --header 'Content-Type: application/json' \
  --header 'x-region: us-east-1' \
  --header "x-api-key: $TIANGONG_AI_APIKEY" \
  --data @assets/example-request.json
```

Checklist:
- 200 response; `data` array present or empty.
- 400 only when `query` missing.
- 500 indicates backend issue (check Supabase logs).
