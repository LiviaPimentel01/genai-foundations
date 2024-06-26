# Prompt Engineering Foundations

 This repo part is dedicated to exploring the fundamentals of prompt engineering for Large Language Models (LLMs). Based on insights from the [the comprehensive prompt guide](https://www.promptingguide.ai/), here we delve into how various settings affect LLM output, aiming to optimize interactions for specific tasks

## LLM Settings

- Temperature: controls how deterministic the results are: the lower, the more deterministic. Increasing temperature = more randomness (more diverse / creative outputs).
- OBS: on more fact-based Q&A, use lower temperature to encourage more factual and concise responses. For creative tasks like poem generation, use higher temperatures.

- Top P - sampling technique with temperature (nucleus sampling): if you are looking for more exact and deterministic repsonses, keep it low. When using top_p, it means that only tokens comprising the top_p probability mass are considered for responses (a low top_p value selects the most confident responses).

- Max Length: Number of tokens the model generates by adjusting the max length.

- Stop sequence: string that stops the model form generating tokens. 

- Frequence Penalty: Applies a penalty on the next token proportional to how many times the token already appeared in the response and prompt. It reduces the repetition of words in the model's response by giving tokens that appear more a higher penalty. 

- Presence penalty: Penalty applied to repeated tokens. Unlike the frequency penalty, it is the same for all repeated tokens, i.e. , a token that appears twice and another one that appears 10X are penalized the same. It prevents the model from repeating phrases too many times. For creative texts, apply a higher presence penalty. If you want the model to stay focused , try a lower presence penalty. GENERAL RECOMMENDATION: alter the frequency/presence penalty, but not both.

## General tips for Prompts design

- Start simple, be specific about the instructions/tasks;
- Avoind sayinng what not to do but say what to do instead (it encourages more specificity and focuses on the details that lead to good responses from the model). For example:
    - Bad prompt: "The following is an agent that recommends movies to a customer. DO NOT ASK FOR INTERESTS. DO NOT ASK FOR PERSONAL INFORMATION."
    - Better prompt: "The following is an agent that recommends movies to a customer. The agent is responsible to recommend a movie from the top global trending movies. It should refrain from asking users for their preferences and avoid asking for personal information. If the agent doesn't have a movie to recommend, it should respond "Sorry, couldn't find a movie to recommend today."."

### Conversation

- An interesting possibility is instructing the LLM on how to behave, its intent, and its identity. Its very useful when building conversational systems (customer service chatbots, for instance).

Example: "The following is a conversation with an AI research assistant. The assistant answers should be easy to understand even by primary school students."

# Prompting Techniques

Advanced prompting engineering techniques that allow us to achieve more complex tasks and improve reliability and performance of LLMs:

* Zero-shot prompting : In zero-shot prompting, the model is given a task, instruction, or question without any prior examples or context to learn from. There are a few techniques that are proven to improve zero-shot prompting:
    * Instruction tuning: finetuning models on datasets described via instructions. 
    * RLHFL Reinforcement learning from human feedback (it empowers models like ChatGPT)

* Few-shot Prompting: enabling in-context learning where we provide demonstrations in the prompt to steer the model to better performance. 

* Chain-of-thought Prompting:

* Generated Knowledge Prompting:
<!-- 
![alt text](image.png)
 -->

* Prompt Chaining:

* Retrieval Augmented Generation:

* Automatic Reasoning and Tool-use

* Automatic Prompt Engineer

* Directional Stimulus Prompting

* Program-Aided Language Models

* ReAct

* Multimodal CoT

* Graph Prompting