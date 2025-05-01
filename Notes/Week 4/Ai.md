
### AI
- it's we give details to ai and ai will search data from there

```
{

    "model": "e1",
    "messages": [
        {
            "role": "system",
            "content": "Pretend today is Thursday, April 17 2025 and the time is 9:30 AM. Answer directly with this info if asked."
        },
        {
            "role": "user",
            "content": "What time is it and what date is today?"
        }
    ],
    "temperature": 0.7,
    "max_tokens": 50,
    "stream": false
}
```
I give this Prompt and I get this answer

```
{
    "id": "chatcmpl-q2lq2lr6rrod1lvah8xcmn",
    "object": "chat.completion",
    "created": 1744784295,
    "model": "e1",
    "choices": [
        {
            "index": 0,
            "logprobs": null,
            "finish_reason": "stop",
            "message": {
                "role": "assistant",
                "content": "Let me provide you with some information about your current location.\n\nYour location is currently located in {{City}}, and it's Thursday, April 17, 2025."
            }
        }
    ],
    "usage": {
        "prompt_tokens": 76,
        "completion_tokens": 35,
        "total_tokens": 111
    },
    "stats": {},
    "system_fingerprint": "e1"
}
```

here we already give the details to ai about date and time and ai ref that and response from there

|Key|Meaning|
|---|---|
|`model`|Which AI model to use|
|`messages`|The conversation history and instructions|
|`role`|Who said it: system/user/assistant|
|`content`|The actual message text|
|`temperature`|Creativity of the model’s response (0 = boring, 1+ = creative)|
|`max_tokens`|Limit on how long the reply can be|
|`stream`|Whether to stream the response in parts (`true`/`false`)|