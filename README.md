# [AI]Teaching Reflection Model

Update: 2025.2.8 Released the first version V1.0. The model can work for a teaching or observation reflection of an English reading and thinking class. For other types of courses, it will be ok in the coming updates. 

## Introduction

This AI model project (Teaching Reflection Model) is based on Deepseek-r1(8b) pretrained by Deepseek AI Co., Ltd. I use Ollama to deploy the model with system prompts locally, my own data and AI data augmentation to provide imitating materials for LLM and RAG techniques, and a vector database with embedding models to make it work correctly and efficiently.

Recently, many young teachers have found it hard to finish a teaching reflection report or course observation reflection after having a lesson. The standardized works make teachers tired and confused. In that case, I try to use system prompts, embedding models, the RAG technique, and a local vector database to create this teaching reflection model. You just need to give it a short abstract about the lesson, it will quickly generate a 1000-word report with the correct format.

In order to achieve my goal, I tried to find some teaching reflection reports and course observation reports which were written by myself before. Then, I created a database with these reports and used some prompts to guide LLM to imitate the styles and format. I then added some system prompts that aimed to stop the LLM from copying data directly from the database, so that it wouldn't use the data from my reports directly but newly generated every word. It was useful to avoid the condition in which AI generated something that was not related to the abstract given by the user but was concluded in the database. In that case, the "delusion" in the RAG process could be greatly avoided. 

The AI-generated report is that this:

![](C:\Users\kingx\Desktop\Teaching Reflection Model V1.0\pictures\QQ20250214-164650.png)

## How to use

**Step 1**: Download and install Ollama.

**Step 2**: Install Deepseek-r1(8b) qualified mode in Ollama

```bash
ollama run deepseek-r1
```

**Step 3**: Install an embedding model like` nomic-embedded-text`

```bash
ollama pull nomic-embed-text
```

**Step 4**: Install the `TeachingReflectionModel` in Ollama

```bash
ollama create TeachingReflectionModel -f .\TeachingReflectionModel
```

**Step 5**: Run the model to check

```bash
ollama run TeachingReflectionModel
```

**Step 6**: Install local AI assistants like Cherry Studio or Anything LLM from their official website.

**Step 7**: Choose Ollama as the LLM provider and `TeachingReflectionModel` as the Chatting model.

**Step 8**: Choose Ollama as an Embedder provider and `nomic-embedded-text` as the embedding model.

**Step 9**: Type the name of the course, abstract of the course, and teaching objectives in short. AI model will generate good work for you automatically.

Also, if you like, you can use API to call other online LLM to work with you.
