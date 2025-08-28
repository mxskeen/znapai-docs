# OpenAI Speech

# Models available :

---

- text to speech :
    - gpt-4o-mini-tts

- speech recognition :
    - gpt-4o-transcribe
    - gpt-4o-mini-transcribe

# CURL

---

## Text to Speech Request

```jsx
curl --location 'https://api.znapai.com/v1/audio/speech' \
--header 'Authorization: Bearer $ZnapAI_API_KEY' \
--header 'Content-Type: application/json' \
--header 'Cookie: __cf_bm=mZz.MnT5136XgzIZvxoIc4T7kPqs_cv4QtQb3qkylTA-1747750591-1.0.1.1-8KIJDDSbWyQzysri05y.Xaq2wVpqNMTyiPr3wrvPcmGEeYpyEdL0dYk1i1cq5Al2CzSIv4NPj7MRgMVXNvE83unwu7HhL3uWQ6nexftqADc' \
--data '{
    "model": "gpt-4o-mini-tts",
    "input": "Today is a wonderful day to build something people love!",
    "voice": "coral",
    "instructions": "Speak in a cheerful and positive tone."
  }'
```

## Text to Speech Response

![image](./images/image.png)

## Speech to Text Request

```jsx
curl --location 'https://api.znapai.com/v1/audio/transcriptions' \
--header 'Authorization: Bearer $ZnapAI_API_KEY' \
--header 'Cookie: __cf_bm=mZz.MnT5136XgzIZvxoIc4T7kPqs_cv4QtQb3qkylTA-1747750591-1.0.1.1-8KIJDDSbWyQzysri05y.Xaq2wVpqNMTyiPr3wrvPcmGEeYpyEdL0dYk1i1cq5Al2CzSIv4NPj7MRgMVXNvE83unwu7HhL3uWQ6nexftqADc' \
--form 'file=@"hzgqik0Zb/tts_sample.mp3"' \
--form 'model="gpt-4o-transcribe"'
```

## Speech to Text Response

```
{
    "text": "The quick brown fox jumped over the lazy dog."
}
```
