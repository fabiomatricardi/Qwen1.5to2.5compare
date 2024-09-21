# Compare the Qwen models from version 1.5 to 2.5
Compare NLP tasks on Qwen1.5, Qwen2 and Qwen2.5 using llamaCPP and 1.5B/1.8B GGUF models

# qwen GGUF models
- qwen1_5-1_8b-chat-q5_k_m.gguf
- qwen2-1_5b-instruct-q5_k_m.gguf
- qwen2.5-1.5b-instruct-q5_k_m.gguf

You can download the GGUF files in their official repos:
- [https://huggingface.co/Qwen/Qwen1.5-1.8B-Chat-GGUF](https://huggingface.co/Qwen/Qwen1.5-1.8B-Chat-GGUF)
- [https://huggingface.co/Qwen/Qwen2-1.5B-Instruct-GGUF](https://huggingface.co/Qwen/Qwen2-1.5B-Instruct-GGUF)
- [https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct-GGUF](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct-GGUF)

#### LlamaCPP 
Tested with Python 3.11 on Windows 11

This venv contains:
- tiktoken 
- llama-cpp-python
```
python -m venv venv
venv\script\activate

pip install llama-cpp-python==0.2.90 tiktoken
```

It is intended to test LlamaCPP python for All Qwen series


### Prompt catalog
The scope is to create an automate verification of the main downstream NLP tasks used the most
```
prmpt_tasks = ["introduction",
               "explain in one sentence",
               "explain in three paragrapghs",
               "summarize",
               "Summarize in two sentences",
               "Write in a list the three main key points",
               "Table of Contents",
               "RAG",
               "Truthful RAG",
               "write content from a reference",
               "extract 5 topics",
               "Creativity: 1000 words SF story",
               "Reflection prompt"
               ]
```

### App description
The App has a plain textual interface in the terminal
- at the end of every assistant reply the user is asked to prompt an evaluation of the inference
- inference KPIs (speed, tokens, time and so on) are also presented
- it sill start with the 13 prompt templates
- after that a normal user/assistant Chat turn based style will be applied
- all user/assistant chat text are logged into TXT file saved into `logs` subdirectory



