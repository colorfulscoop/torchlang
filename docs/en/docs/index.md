# convmodel

**convmodel** provides a conversation model based on GPT-2 provided by [transformers](https://github.com/huggingface/transformers) :wink:.

:sparkles: Features :sparkles:

* convmodel utilizes GPT2 model to generate response.
* convmodel handles multi-turn conversation.
* convmodel provides an useuful interface to generate a response from a given context.

```py
>>> from convmodel import ConversationModel
>>> model = ConversationModel.from_pretrained("model")
>>> model.generate(context=["こんにちは"], do_sample=True, top_p=0.95, top_k=50)
ConversationModelOutput(responses=['こんにちは♪'], context=['こんにちは'])
```

| position | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| word | \<sep\> | Hello | \<sep\> | How | are | you | \<sep\> | Good | thank | you |
| input_ids | 50256 | 15496 | 50256 | 2437 | 389 | 345 | 50256 | 10248 | 5875 | 345 |
| token_type_ids | 0 | 0 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
| attention_mask | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| | | | | | | | ↓ | ↓ | ↓ | ↓ |
| generated word | - | - | - | - | - | - | Good | thank | you | \<sep\> |

Streamlit interface is available now to try your conversation model as an experimental feature from v0.1.0 :sparkles:

![convmodel_streamlit](img/convmodel_streamlit.jpg)

Enjoy talking with your conversational AI :wink: