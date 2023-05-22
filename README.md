# OpenAI sandbox

A repo for examples of and utils for using the `openai` python library.

Lessons from https://learn.deeplearning.ai/chatgpt-prompt-eng/

## Setup

Create virtual env and install requirements:

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## API key

See api_key.py

## What's this?

Basically examples of using `openai.ChatCompletion.create` on the
`gpt-3.5-turbo` model to build applications:

- that use natural language instead of code
- that can use the powerful general-purpose functionality of LLMs

## How does ChatGPT work in the context of this API?

It has a memory of the conversation so far (called 'context'), and uses that
to generate the next response. This is built up as a list and passed to the
`ChatCompletion.create` call to get the next reponse.

The 'system' role is used to give the model some context about how to behave.
e.g. 'be a friendly chatbot!'

```python
messages =  [  
    {'role':'system', 'content':'You are an assistant that speaks like Shakespeare.'},    
    {'role':'user', 'content':'tell me a joke'},   
    {'role':'assistant', 'content':'Why did the chicken cross the road'},   
    {'role':'user', 'content':'I don\'t know'},
]
openai.ChatCompletion.create(model="gpt-3.5-turbo", messages=messages)
```
