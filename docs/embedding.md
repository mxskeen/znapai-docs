# OpenAI Embedding

# Models available :

---

- embedding
    - text-embedding-3-large
    - text-embedding-3-small

# CURL

---

## Request

```jsx
curl --location 'https://api.znapai.com/v1/embeddings' \
--header 'Authorization: Bearer $ZnapAI_API_KEY' \
--header 'Content-Type: application/json' \
--header 'Cookie: __cf_bm=UpB_XYjSk8hSFktl84v_gcl_oe.d60w8NaqQ1MCRjmg-1747824055-1.0.1.1-DCGlWQ8pImXEcj.feLaZ7Mws.cBOZeSMdIwM3kt735WBMpM86r2TdtcukNNm.c1L_JWyPe4O8RfsWvMfUKjANlokm4gGHZfRHuj3QUSs4ns' \
--data '{
    "input": "The food was delicious and the waiter...",
    "model": "text-embedding-3-large",
    "encoding_format": "float"
  }'
```

## Response

```jsx
{
    "model": "text-embedding-3-large",
    "data": [
        {
            "embedding": [
                -0.010992265,
                0.0027546093,
                -0.0057185953,
                -0.008060995,
                0.0006436691,
                0.010560427,
                -0.011234357,
                ...
            ],
            "index": 0,
            "object": "embedding"
        }
    ],
    "object": "list",
    "usage": {
        "completion_tokens": 0,
        "prompt_tokens": 8,
        "total_tokens": 8,
        "completion_tokens_details": null,
        "prompt_tokens_details": null
    }
}
```