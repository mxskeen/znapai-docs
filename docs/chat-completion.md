# OpenAI Chat Completion

# Models available :

---

- chat completion :
    - Reasoning models
        - o1
        - o3
        - o1-mini
        - o3-mini
        - o4-mini
    - Flagship chat models
        - gpt-4o
        - gpt-4.1
    - Cost-optimized models
        - gpt-4o-mini
        - gpt-4.1-mini

# CURL

---

## Request

```jsx
curl "https://api.znapai.com/v1/chat/completions" \
    -H "Content-Type: application/json" \
    -H "Authorization: Bearer $ZnapAI_API_KEY" \
    -d '{
        "model": "gpt-4o-mini",
        "messages": [
            {
                "role": "user",
                "content": "Hello!"
            }
        ]
    }'
```

## Response

```jsx
{
  "id": "chatcmpl-B8rLGf4crBdVhX7a13Ae37NI9h2Re",
  "created": 1741451370,
  "model": "gpt-4o-mini-2024-07-18",
  "object": "chat.completion",
  "system_fingerprint": "fp_ded0d14823",
  "choices": [
    {
      "finish_reason": "stop",
      "index": 0,
      "message": {
        "content": "Hello! How can I assist you today?",
        "role": "assistant",
        "tool_calls": null,
        "function_call": null
      }
    }
  ],
  "usage": {
    "completion_tokens": 9,
    "prompt_tokens": 9,
    "total_tokens": 18,
    "completion_tokens_details": {
      "accepted_prediction_tokens": 0,
      "audio_tokens": 0,
      "reasoning_tokens": 0,
      "rejected_prediction_tokens": 0
    },
    "prompt_tokens_details": {
      "audio_tokens": 0,
      "cached_tokens": 0
    }
  },
  "service_tier": null,
  "prompt_filter_results": [
    {
      "prompt_index": 0,
      "content_filter_results": {
        "hate": {
          "filtered": false,
          "severity": "safe"
        },
        "jailbreak": {
          "filtered": false,
          "detected": false
        },
        "self_harm": {
          "filtered": false,
          "severity": "safe"
        },
        "sexual": {
          "filtered": false,
          "severity": "safe"
        },
        "violence": {
          "filtered": false,
          "severity": "safe"
        }
      }
    }
  ]
}
```

# OpenAI Python SDK

---

## Request

```python
import openai
client = openai.OpenAI(
    api_key="$ZnapAI_API_KEY",
    base_url="https://api.znapai.com/"
)

completion = client.chat.completions.create(
    model="gpt-4o-mini",
    messages = [
        {
            "role": "user",
            "content": "hello"
        }
    ]
)

print(completion)
```

## Response

```json
ChatCompletion(
    id="chatcmpl-B8rcl2URnUYhj9VxmdGfijfyxcpnQ",
    choices=[
        Choice(
            finish_reason="stop",
            index=0,
            logprobs=None,
            message=ChatCompletionMessage(
                content="Hello! How can I assist you today?",
                refusal=None,
                role="assistant",
                audio=None,
                function_call=None,
                tool_calls=None
            )
        )
    ],
    created=1741452455,
    model="gpt-4o-mini-2024-07-18",
    object="chat.completion",
    service_tier=None,
    system_fingerprint="fp_ded0d14823",
    usage=CompletionUsage(
        completion_tokens=9,
        prompt_tokens=8,
        total_tokens=17,
        completion_tokens_details=CompletionTokensDetails(
            accepted_prediction_tokens=0,
            audio_tokens=0,
            reasoning_tokens=0,
            rejected_prediction_tokens=0
        ),
        prompt_tokens_details=PromptTokensDetails(
            audio_tokens=0,
            cached_tokens=0
        )
    ),
    prompt_filter_results=[
        {
            "prompt_index": 0,
            "content_filter_results": {
                "hate": {"filtered": False, "severity": "safe"},
                "jailbreak": {"filtered": False, "detected": False},
                "self_harm": {"filtered": False, "severity": "safe"},
                "sexual": {"filtered": False, "severity": "safe"},
                "violence": {"filtered": False, "severity": "safe"},
            }
        }
    ]
)

```

# OpenAI NodeJS SDK

---

## Request

```jsx
import OpenAI from "openai";
const openai = new OpenAI({
  apiKey: "$ZnapAI_API_KEY",
  baseURL: "https://api.znapai.com/"
});

const completion = await openai.chat.completions.create({
    model: "gpt-4o-mini",
    messages: [
        {
            role: "user",
            content: "hello",
        },
    ]
});

console.log(completion);
```

## Response

```json
{
  id: 'chatcmpl-B8rhDVgIgWwO4xTCcUoYHAWgdreVh',
  created: 1741452731,
  model: 'gpt-4o-mini-2024-07-18',
  object: 'chat.completion',
  system_fingerprint: 'fp_ded0d14823',
  choices: [ { finish_reason: 'stop', index: 0, message: [Object] } ],
  usage: {
    completion_tokens: 9,
    prompt_tokens: 8,
    total_tokens: 17,
    completion_tokens_details: {
      accepted_prediction_tokens: 0,
      audio_tokens: 0,
      reasoning_tokens: 0,
      rejected_prediction_tokens: 0
    },
    prompt_tokens_details: { audio_tokens: 0, cached_tokens: 0 }
  },
  service_tier: null,
  prompt_filter_results: [ { prompt_index: 0, content_filter_results: [Object] } ]
}
```