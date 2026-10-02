Week 01 Questions

Q1 - AI, ML, Deep Learning, Generative AI, Agents

A - Answer

1) AI: It is the ability of a computer to think like a human and get tasks done. Example: decision making.
2) ML: It is a subset of AI, where data is fed to the machine so it can learn. Example: pattern recognition.
3) DL: It is loosely inspired by the human brain and solves more complex tasks by using multiple hidden layers. Example: voice recognition.
4) Generative AI: It is AI that generates something new based on a requirement, using the data it learned from. Example: text-to-image generation.
5) AI agents: These are like assistants for humans that do a task on their own. Example: applying for a job.

Hierarchy: AI > ML > Deep Learning > Generative AI. Agents are better seen as a system or workflow that uses a generative model plus tools, so I did not force them into the chain.

<img width="611" height="701" alt="image" src="https://github.com/user-attachments/assets/394667b1-c2db-41f1-9477-3c0bdddc85c6" />

Key difference: a generative model produces content in response to a prompt. An agentic system uses a model to choose actions, call tools, look at the results and continue until the goal is reached.

E - Evidence

1) IBM, "AI vs. machine learning vs. deep learning vs. neural networks": https://www.ibm.com/think/topics/ai-vs-machine-learning-vs-deep-learning-vs-neural-networks
2) Anthropic, "Building effective agents": https://www.anthropic.com/engineering/building-effective-agents
3) Google, Machine Learning Crash Course, Large language models: https://developers.google.com/machine-learning/crash-course/llm

V - Verification

I checked my definitions against the IBM article and the Anthropic article. IBM confirmed that ML is a subset of AI and deep learning is a subset of ML, and says deep learning needs neural networks with more than three layers. Anthropic distinguishes workflows (LLMs and tools run through predefined code paths) from agents (LLMs direct their own process and tool use), which is why I treated agents as a system, not a model type. Google's course page describes language models as learning to predict text output, which I used to check the generative AI side. I changed "resembles the human brain" to "loosely inspired by" because that is an analogy, not an exact description. I did not find a single official definition of "generative AI" in these sources, so that definition is my own summary.

R - Reflection

I now see the terms as nested, not interchangeable. Agents confused me most because they are a system design, not a kind of model. My two original sources (a Medium post and a LinkedIn post) were weak, so I replaced them.
