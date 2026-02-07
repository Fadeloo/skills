# Request/response

## Input
```json
{
  "query": "test",
  "retrieval_model": {
    "top_k": 8
  }
}
```

## Field notes
- `query` (required): user query string.
- `retrieval_model` (optional): per-request retrieval settings.
- `retrieval_model.top_k`: optional; number of chunks to return. If no results, increase `top_k` moderately and retry.

## Output
```json
{
  "query": {
    "content": "test"
  },
  "records": [
    {
      "segment": {
        "id": "7fa6f24a-8679-48ea-8f8f-4f775e7a69ce",
        "position": 1,
        "document_id": "0f3cce4a-6f98-49b3-b1e2-58f8f2c9d9d6",
        "content": "Hello, world.",
        "score": 0.0,
        "document": {
          "id": "0f3cce4a-6f98-49b3-b1e2-58f8f2c9d9d6",
          "name": "test.txt",
          "data_source_type": "upload_file",
          "created_at": 1716968248,
          "updated_at": 1716968248
        }
      }
    }
  ]
}
```
