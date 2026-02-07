# Request/response

## Input
```json
{
  "query": "test",
  "retrieval_model": {
    "search_method": "keyword_search",
    "reranking_enable": false,
    "reranking_mode": null,
    "reranking_model": {
      "reranking_provider_name": "",
      "reranking_model_name": ""
    },
    "weights": {
      "vector_weight": 0,
      "keyword_weight": 1
    },
    "top_k": 2,
    "score_threshold_enabled": false,
    "score_threshold": 0
  }
}
```

## Field notes
- `query` (required): user query string.
- `retrieval_model` (optional): per-request retrieval settings.
- `search_method`: retrieval method (example uses `keyword_search`).
- `reranking_enable`: enable or disable reranking.
- `reranking_mode`: reranking mode or null.
- `reranking_model`: object with provider/model names when reranking is enabled.
- `weights.vector_weight/keyword_weight`: weighting values for vector/keyword retrieval.
- `top_k`: number of chunks to return.
- `score_threshold_enabled`: gate results by score threshold.
- `score_threshold`: numeric threshold value when enabled.

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
