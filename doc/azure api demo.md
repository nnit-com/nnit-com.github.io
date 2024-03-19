https://nnitasia-openai-01-ins.openai.azure.com/

python**

```python
1#Note: The openai-python library support for Azure OpenAI is in preview.
2      #Note: This code sample requires OpenAI Python library version 0.28.1 or lower.
3import os
4import openai
5
6openai.api_type = "azure"
7openai.api_base = "https://nnitasia-openai-01-ins.openai.azure.com/"
8openai.api_version = "2023-07-01-preview"
9openai.api_key = os.getenv("OPENAI_API_KEY")
10
11message_text = [{"role":"system","content":"You are an AI assistant that helps people find information."}]
12
13completion = openai.ChatCompletion.create(
14  engine="gpt-35-turbo-talu-test",
15  messages = message_text,
16  temperature=0.7,
17  max_tokens=800,
18  top_p=0.95,
19  frequency_penalty=0,
20  presence_penalty=0,
21  stop=None
22)
```

https://nnitasia-openai-01-ins.openai.azure.com/openai/deployments/gpt-35-turbo-talu-test/chat/completions?api-version=2023-07-01-preview



key:





