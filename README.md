# LLM Experiments & Exercises
This repo collects a series of notebooks that explore different features and functionality of LLM-based applications, including memory management, RAG implementations, and knowledge graph retrieval. 

## Simple Chat
Very basic implementation of a single turn GPT chat interaction.

## Multi-Turn Chat
- Stores and re-uses conversation history 
- Not doing anything smart with history. This implementation will eventually overrun the context window. 

## Basic RAG
A basic LLM RAG app using LangChain and the Chroma vector store, built from the [LangChain RAG tutorial](https://python.langchain.com/v0.2/docs/tutorials/rag/).

- Source content is pulled from a provided web location, is split and embedded, then stored in an ephemeral (session-based) vector store.
- Uses a retriever in generation to search the vector store and inject relevant documents into the query before generating a response.

## Conversational RAG
A conversational RAG LLM app using LangChain & Chroma, built from the [LangChain RAG](https://python.langchain.com/v0.2/docs/tutorials/rag/) and
[Conversational RAG](https://python.langchain.com/v0.2/docs/tutorials/qa_chat_history/) tutorials.

- Integrates chat history into subsequent queries, programmatically updated in function calls
- Implements chain tracing with LangSmith

## Stateful Conversational RAG
A state-managed conversational RAG LLM app with memory, built with LangChain and Chroma from the [LangChain RAG](https://python.langchain.com/v0.2/docs/tutorials/rag/) and
[Conversational RAG](https://python.langchain.com/v0.2/docs/tutorials/qa_chat_history/) tutorials.

- Adds stateful management of chat history with LangChain Expression Language (LCEL) 
- Sources multiple web based documents

## Conversational RAG Agent
An agent-based conversational RAG LLM app, built from the [LangChain RAG](https://python.langchain.com/v0.2/docs/tutorials/rag/) and
[Conversational RAG](https://python.langchain.com/v0.2/docs/tutorials/qa_chat_history/) tutorials.

- Adds a retrieval "agent" capable of manipulating steps of the process
- Adds tools the agent can access for stored document retrieval

## Conversational Wikidata RAG Agent
A conversational application using LangChain's prebuilt ReAct agent that can query Wikidata for up-to-date facts and incorporate them into generated responses.

- accesses data via the Wikidata SPARQL endpoint to support inference 
- supports return of implicit facts in the dataset not explicitly on individual records
- defines a narrow scope of functionality in order to deal with the wide ranging schema of 

## Local Wikidata RAG Agent
A conversational agent using a locally hosted LLM and LangChain that can query Wikidata for up-to-date facts and incorporate them into generated responses.

> [!CAUTION]
> Using a locally hosted model (one that will run on a MacBook Pro) with this configuration leads to mixed results on anything beyond the most straightforward questions. See notebook for details. 