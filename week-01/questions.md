# Week 01 Questions

Q1 - AI, ML, Deep Learning, Generative AI, Agents
A - 1) Ai : It is the ability of the computer to think like a human and make tasks to be done. eg, decision making
2) ML: It is the subset of ai, where the data is fed to the machine to learn. eg, pattern recognition.
3) dl: It resembles the human brain which solves the more complex tasks by using multiple hidden layer. eg: voice recognition
4) gen ai: it is the ai which generate something new based on the requirement using the given data. eg: text to image generation.
5) ai agents: these are like the assistance for human which automatically do the task on its own. eg: applying for the job.
   <img width="611" height="701" alt="image" src="https://github.com/user-attachments/assets/394667b1-c2db-41f1-9477-3c0bdddc85c6" />

Hierarchy: AI > ML > Deep Learning > Generative AI. Agents are better seen as a system or workflow that *uses* a generative model plus tools, so I did not force them into the chain.

<img width="611" height="701" alt="image" src="https://github.com/user-attachments/assets/394667b1-c2db-41f1-9477-3c0bdddc85c6" />

Key difference: a generative model produces content in response to a prompt. An agentic system uses a model to choose actions, call tools, look at the results and continue until the goal is reached.
E - Evidence
1) IBM, "AI vs. machine learning vs. deep learning vs. neural networks": https://www.ibm.com/think/topics/ai-vs-machine-learning-vs-deep-learning-vs-neural-networks
2) Anthropic, "Building effective agents": https://www.anthropic.com/engineering/building-effective-agents
3) Google, Machine Learning Crash Course, Large language models: https://developers.google.com/machine-learning/crash-course/llm
 V - Verification
I checked my definitions against the IBM article and the Anthropic article. IBM confirmed that ML is a subset of AI and deep learning a subset of ML, and says deep learning needs neural networks with more than three layers. Anthropic distinguishes workflows (LLMs and tools run through predefined code paths) from agents (LLMs direct their own process and tool use), which is why I treated agents as a system, not a model type. I changed "resembles the human brain" to "loosely inspired by" because that is an analogy, not an exact description. I did not find a single official definition of "generative AI" in these sources, so that definition is my own summary.

R - Reflection
I now see the terms as nested, not interchangeable. Agents confused me most because they are a system design, not a kind of model. My two original sources (a Medium post and a LinkedIn post) were weak, so I replaced them.


Q2 - Is Everything That Looks Intelligent Actually AI?

A - Answer

A. Calculator 25 x 16 = 400: Traditional software. Fixed arithmetic, same answer every time.

B. Temp > 80°C warning: Traditional software. One if-then rule a person wrote.

C. Spam detection: Machine learning. Learned from past emails.

D. Document summary: Generative AI. Writes new text.

E. Navigation ETA: Machine learning. Predicts from traffic and past data.

A normal program does exactly what its rules say. An AI system learns its behaviour from examples, so it can deal with inputs nobody wrote a rule for.

E - Evidence

IBM page from Q1.

V - Verification

A and B are plain logic. For C and E I only reasoned from the IBM definition of ML, and I haven't checked how a specific product does it. Real products often mix rules and ML, so I picked the main behaviour.

R - Reflection

Automated doesn't mean AI. My test now is whether the behaviour was learned from data or written by hand.


Q3 - What Happens When You Ask an LLM a Question?

A - Answer

The text you type is the prompt. It gets split into tokens, which are small chunks like words or parts of words. The model looks at those tokens plus the earlier conversation (the context) and works out a probability for each possible next token. That is next-token prediction. One token is picked and added to the text, and the loop repeats until the generated response is finished.

Training is when the model learns patterns from a huge amount of text. Inference is using the finished model to answer a prompt.

Diagram: Prompt -> Tokens -> Model processing -> Probability distribution -> Next token selection -> Generated response (loop back to model processing with the new token added).

It can sound fluent and still be wrong because it's built to produce likely-sounding text, not to check facts.

E - Evidence

- Google ML Crash Course, Large language models: https://developers.google.com/machine-learning/crash-course/llm
- Attention Is All You Need: https://arxiv.org/abs/1706.03762

V - Verification

[Open the Google page and confirm it describes language models as predicting the next token.] I didn't try to check the transformer maths.

R - Reflection

Fluent doesn't mean true. I still want to understand how the context limit affects what the model can use.


Q6 - What Is an AI Agent?

A - Answer

- LLM: a model that generates text one token at a time.
- LLM application: a product built around an LLM, like a chat app.
- RAG system: an LLM that looks up relevant documents first, then answers using them.
- Tool-using assistant: an LLM that can call tools like search or a calculator.
- AI agent: a system where the model decides which tools to use, in what order, and when to stop.

Flow: User request -> Model -> Tool call -> Tool result -> Decision (back to model, or final response).

A chatbot answers once. An agent plans, acts, looks at the result and repeats. Example: a trip assistant that checks flights, compares prices and books the cheapest one once I approve.

E - Evidence

https://www.anthropic.com/engineering/building-effective-agents

V - Verification

[Check this page's workflow vs agent definitions against my list.] I took the RAG meaning from general knowledge, not this source.

R - Reflection

Companies define "agent" differently, so I focused on behaviour: does it pick its own steps and loop?


Q7 - Where Should Humans Still Decide?

A - Answer

1. Medical advice summary. What could go wrong: wrong or made-up advice. Verification: compare with clinical guidelines. Approver: doctor.

2. Contract summary. What could go wrong: missed clause. Verification: read the original clauses. Approver: lawyer.

3. Money transfer suggestion. What could go wrong: wrong amount or recipient. Verification: check the bank record. Approver: account owner.

4. Code change to a live system. What could go wrong: hidden bug or security hole. Verification: tests and review. Approver: senior engineer.

5. Published report. What could go wrong: false claims, fake citations. Verification: open every source. Approver: editor or author.

Rule: the more costly or hard to undo the outcome, the more evidence and human sign-off I need first.

E - Evidence

NIST AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework

V - Verification

[Skim the NIST page and confirm it talks about human oversight.] The failure cases are my own reasoning from what I learned about hallucination.

R - Reflection

AI output is a draft to check, not a decision.


Q9 - Prediction, Classification, Generation

A - Answer

A. House prices: Prediction. Outputs a number.

B. Cat in image: Classification. Cat or not.

C. Email from instruction: Generation. New text.

D. Customer cancels: Classification. Yes/no label (people also call it prediction).

E. Summarise a paper: Generation. New shorter text.

F. Fraud: Classification. Fraud or not.

G. Image from text: Generation. New image.

H. Next token: Prediction. Guesses the most likely next token.

Writing, summarising, coding and Q&A are all done by predicting one token at a time, again and again. That's why one simple task sits under so many apps.

E - Evidence

Google ML Crash Course link from Q3.

V - Verification

[Confirm the page describes next-token probability.] Some systems mix types, so I picked the main one.

R - Reflection

D was the confusing one. I decided by output: a number is prediction, a label is classification.


Q10 - My AI Verification Protocol

A - Answer

1. Define the problem. Write what I need and what "correct" means. Catches vague prompts.
2. Inspect assumptions. List what the AI assumed. Catches wrong starting points.
3. Check sources. Open every link it gives. Catches invented citations.
4. Cross-check. Compare with another tool or an official reference. Catches one-model mistakes.
5. Test the result. Run it, calculate it, try a known case. Catches answers that only look right.
6. Accept, reject or revise. Decide and note why. Stops silent acceptance.
7. Document. Log the prompt, tool, checks and outcome. Makes it traceable.

Example: AI says a recipe for 4 needs 300 g raw rice. I set the goal, ask raw or cooked, check a cooking site, work out the portions, find it's too much, change it and log it.

E - Evidence

Course handout workflow, plus my Q4 and Q5 experiments.

V - Verification

[After doing Q4/Q5, confirm each step matches a mistake you actually saw or could see.]

R - Reflection

I'll revisit this at the end of Week 16.
