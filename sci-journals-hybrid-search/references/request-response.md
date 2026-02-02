# Request/response

## Input
```json
{
  "query": "What are the global trade characteristics of critical metal material flows?",
  "topK": 3,
  "extK": 2,
  "filter": {
    "journal": ["JOURNAL OF INDUSTRIAL ECOLOGY"]
  },
  "datefilter": {
    "date": {
      "gte": 1262304000
    }
  },
  "getMeta": true
}
```

## Field notes
- `query` (required): user question or keywords; accepts mixed languages.
- `topK`: number of top matches to retrieve before expansion.
- `extK`: expand each topK hit by N adjacent chunks (before/after), then merge into combined chunks.
- `filter.journal`: array of journal names for filtering.
- `datefilter.date.gte/lte`: UNIX seconds; typically filters by publication date.
- `getMeta`: when true, returns complete metadata for matched papers.

## Output
- 200 `{ "data": [...] }` or `[]` if none.
- 400 if `query` missing; 500 on backend errors.
