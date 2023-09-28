# Langchain
Learning of Langchain

https://python.langchain.com/docs/get_started/introduction

What is LangChain:

LangChain is a framework for developing applications powered by language models. It enables applications that:

Are context-aware: connect a language model to sources of context (prompt instructions, few shot examples, content to ground its response in, etc.)
Reason: rely on a language model to reason (about how to answer based on provided context, what actions to take, etc.)
The main value props of LangChain are:

Components: abstractions for working with language models, along with a collection of implementations for each abstraction. Components are modular and easy-to-use, whether you are using the rest of the LangChain framework or not
Off-the-shelf chains: a structured assembly of components for accomplishing specific higher-level tasks
Off-the-shelf chains make it easy to get started. For complex applications, components make it easy to customize existing chains and build new ones.


QuickStart :

Installing Langchain using pip 
```
pip install langchain
```

Then comes the Environment Setup   

Building an application
Now we can start building our language model application. LangChain provides many modules that can be used to build language model applications. Modules can be used as stand-alones in simple applications and they can be combined for more complex use cases.

The most common and most important chain that LangChain helps create contains three things:

LLM:

The language model is the core reasoning engine here. In order to work with LangChain, you need to understand the different types of language models and how to work with them.
Prompt Templates: This provides instructions to the language model. This controls what the language model outputs, so understanding how to construct prompts and different prompting strategies is crucial.
Output Parsers: These translate the raw response from the LLM to a more workable format, making it easy to use the output downstream.
In this getting started guide we will cover those three components by themselves, and then go over how to combine all of them. Understanding these concepts will set you up well for being able to use and customize LangChain applications. Most LangChain applications allow you to configure the LLM and/or the prompt used, so knowing how to take advantage of this will be a big enabler.

LLMs

There are two types of language models, which in LangChain are called:

LLMs: this is a language model which takes a string as input and returns a string

ChatModels: this is a language model which takes a list of messages as input and returns a message

The input/output for LLMs is simple and easy to understand - a string. But what about ChatModels? The input there is a list of ChatMessages, and the output is a single ChatMessage. A ChatMessage has two required components:

content: This is the content of the message.

role: This is the role of the entity from which the ChatMessage is coming from.

LangChain provides several objects to easily distinguish between different roles:

HumanMessage: A ChatMessage coming from a human/user.

AIMessage: A ChatMessage coming from an AI/assistant.

SystemMessage: A ChatMessage coming from the system.

FunctionMessage: A ChatMessage coming from a function call.

If none of those roles sound right, there is also a ChatMessage class where you can specify the role manually. For more information on how to use these different messages most effectively, see our prompting guide.

LangChain provides a standard interface for both, but it's useful to understand this difference in order to construct prompts for a given language model. The standard interface that LangChain provides has two methods:

predict: Takes in a string, returns a string

predict_messages: Takes in a list of messages, returns a message.

Prompt templates
Most LLM applications do not pass user input directly into an LLM. Usually they will add the user input to a larger piece of text, called a prompt template, that provides additional context on the specific task at hand.

In the previous example, the text we passed to the model contained instructions to generate a company name. For our application, it'd be great if the user only had to provide the description of a company/product, without having to worry about giving the model instructions.

PromptTemplates help with exactly this! They bundle up all the logic for going from user input into a fully formatted prompt

