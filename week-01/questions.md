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

Q2 - Is Everything That Looks Intelligent Actually AI?

A - Answer

A. Calculator: 25 x 16 = 400
Classification: Traditional software (not AI)
Why: It does fixed arithmetic and gives the same answer every time.

B. If temperature > 80°C, display WARNING
Classification: Traditional software (not AI)
Why: It is one if-then rule that a person wrote by hand.

C. Email system marks a message as spam from patterns learned from past emails
Classification: Machine learning
Why: The behaviour was learned from past email data, not written as fixed rules.

D. AI assistant writes a summary of a document
Classification: Generative AI
Why: It creates new text instead of only sorting or predicting.

E. Navigation app predicts arrival time from traffic and historical data
Classification: Machine learning
Why: It predicts a result from live traffic data and past patterns.

Difference: A normal program does exactly what its written rules say. An AI system learns its behaviour from examples, so it can handle inputs nobody wrote a rule for.

E - Evidence

1) IBM, "AI vs. machine learning vs. deep learning vs. neural networks" (same page as Q1), used for the definition of ML: https://www.ibm.com/think/topics/ai-vs-machine-learning-vs-deep-learning-vs-neural-networks
2) DeepMind, "Traffic prediction with advanced Graph Neural Networks", used for the Maps ETA example: https://deepmind.google/discover/blog/traffic-prediction-with-advanced-graph-neural-networks/

V - Verification

A and B are plain logic, so no source is needed. For E, the DeepMind blog says Google Maps uses machine learning to combine live traffic with historical traffic patterns, and that a Graph Neural Network predicts travel time for each road segment. For C, I reasoned from IBM's definition of machine learning. I did not find a source for how my own email provider filters spam (Q8 covers Gmail separately). Real products often mix fixed rules and ML, so I picked the main behaviour in each case.

R - Reflection
Automated does not mean AI. My test is now: was the behaviour learned from data, or written by hand?



Q3 - What Happens When You Ask an LLM a Question?

A - Answer

The text I type is the prompt. It is split into tokens, which are small chunks such as words or parts of words. The model reads those tokens plus the earlier conversation (the context) and works out a probability for each possible next token. This is next-token prediction. One token is chosen and added to the text, and the loop repeats until the generated response is finished.

Training is when the model learns patterns from a huge amount of text. Inference is using the finished model to answer a prompt.

Flow diagram:
Prompt -> Tokens -> Model processing -> Probability distribution -> Next token selection -> Generated response
(After each selection, the new token is added and the loop goes back to Model processing.)

It can sound fluent and still be wrong because it is built to produce likely-sounding text. Nothing in the loop checks facts.

E - Evidence

1) Google, Machine Learning Crash Course, Large language models: https://developers.google.com/machine-learning/crash-course/llm
2) "Attention Is All You Need": https://arxiv.org/abs/1706.03762

V - Verification

Google's course page describes the module as teaching how LLMs learn to predict text output, from tokens to Transformers. That matches my next-token description. I saw this in the module description and did not work through the whole module. I did not try to check the transformer maths.

R - Reflection

Fluent does not mean true. I still want to understand how the context limit affects what the model can use.


Q4 - Hallucination Experiment

A - Answer

Question (same wording for both tools): Which paper introduced the Transformer architecture? Give the title, the authors, the year, and the venue where it was published.

Tool 1: Claude
Response summary: "Attention Is All You Need" by Vaswani, Shazeer, Parmar, Uszkoreit, Jones, Gomez, Kaiser and Polosukhin. Published in 2017 at NIPS (now NeurIPS).
Verified claim: title, all eight authors, year, venue.
Evidence: arXiv listing and NeurIPS proceedings page.
Result: Correct.
Lesson: It gave no sources, so I had to check everything myself.

Tool 2: ChatGPT
Response summary: Gave the title "Attention Is All You Need", all eight authors, the year 2017 and the venue "Advances in Neural Information Processing Systems 30 (NIPS 2017)".
Verified claim: title, authors, year, venue.
Evidence: arXiv listing and NeurIPS proceedings page.
Result: Correct on all four.
Lesson: Both tools got a very famous paper right, so this test did not catch an error. ChatGPT also gave no sources, so I still had to check everything myself.

Full raw answers are saved in evidence/q4-answers.md.

E - Evidence

1) arXiv listing: https://arxiv.org/abs/1706.03762
2) NeurIPS proceedings page: https://papers.neurips.cc/paper/7181-attention-is-all-you-need

V - Verification

I compared the title, authors, year and venue in both answers with the arXiv page and the NeurIPS proceedings page. arXiv shows the title, the eight authors and a first submission date of 12 June 2017. The NeurIPS page lists the same eight authors in the same order and names the venue as "Advances in Neural Information Processing Systems 30 (NIPS 2017)". Both tools matched on all of these. One small difference: ChatGPT's summary said NeurIPS while its full answer said NIPS 2017. Both are the same conference, which was renamed in 2018. I did not check the paper's experimental results.

R - Reflection

Both answers were correct, so my test did not expose a failure. I think this is because the paper is extremely well known, so its details appear many times in the data the models learned from. An AI answer can sound convincing because the model produces fluent, likely text, and a confident tone looks the same whether the facts are right or wrong. A better test would use a less famous paper, where the model has less to go on and is more likely to make something up.


Q5 - AI Assistant vs Search vs Authoritative Reference

A - Answer

Question used for all three: What is the difference between TCP and UDP?

AI assistant (ChatGPT): TCP is connection-oriented and gives reliable, ordered, error-checked delivery. UDP is connectionless and favours speed and lower overhead, with no guarantee of delivery or ordering. It also mentioned flow and congestion control for TCP.
Accuracy: matched the RFCs on the basics.
Explanation: clear and short.
Traceability: it named the RFCs but gave no links.
Ease of verification: easy once I knew which RFCs to open.

Web search: I opened three pages (sslinsights.com, networkinterview.com, ccbp.in). All three gave the same core points: TCP is connection-oriented and reliable, UDP is connectionless, lighter and faster.
Accuracy: good on the basics, but some wording was loose (see below).
Explanation: easy to read, with comparison tables.
Traceability: weak. I could not tell who wrote the pages or whether they were reviewed.
Ease of verification: medium.

Authoritative reference: RFC 9293 (TCP, August 2022) is the current TCP specification and replaces RFC 793. RFC 768 (UDP, 1980) says UDP uses a minimum of protocol mechanism and that delivery and duplicate protection are not guaranteed.
Accuracy: highest, they are the standards.
Explanation: dense and formal.
Traceability: excellent, numbered and dated.
Ease of verification: slower to read but easy to cite.

Where the sources differed:
- Some search pages say UDP has "no error checking". UDP actually has a checksum in its header, so the better statement is that it detects errors but does not fix them or retransmit.
- RFC 768 does not use the word "connectionless" and does not mention ordering. ChatGPT's "no ordering guarantee" is true in practice, but it is not the literal wording of RFC 768.
- "UDP prioritizes speed" needs care. Lower overhead usually means lower latency, but UDP itself does not promise speed. I would write "usually lower latency, not guaranteed".

When I would use each: AI for a quick first explanation, search to compare sources and find references, and an authoritative source whenever the answer feeds a design, safety or security decision, or something I have to cite.

E - Evidence

1) TCP: https://www.rfc-editor.org/rfc/rfc9293
2) UDP: https://www.rfc-editor.org/rfc/rfc768

V - Verification

ChatGPT said its answer came from the RFCs, but I did not take that on trust. I checked RFC 9293: it was published in August 2022 and obsoletes RFC 793, so it is the right current TCP reference. I checked RFC 768: its introduction says delivery and duplicate protection are not guaranteed, and that applications needing ordered reliable streams should use TCP. I read the abstract and introduction of both RFCs. I did not read the full TCP specification, so the flow-control and congestion-control claims are only checked at the level of "RFC 9293 is the right document".

R - Reflection

All three agreed on the basics, so the main difference was traceability: only the RFC gave something official to cite. ChatGPT named the right standards, but a name is not proof until I open the document. A search result is not automatically reliable either, because some pages are shallow, anonymous or slightly loose with wording.


Q6 - What Is an AI Agent?

A - Answer

LLM: a model that generates text one token at a time.
LLM application: a product built around an LLM, such as a chat app.
RAG system: an LLM that looks up relevant documents first, then answers using them.
Tool-using assistant: an LLM that can call tools such as search or a calculator.
AI agent: a system where the model decides which tools to use, in what order, and when to stop.

Architecture diagram:
User request -> Model -> Tool call -> Tool result -> Decision
Decision = need more: go back to Model
Decision = done: Final response

A chatbot answers once. An agent plans, acts, looks at the result and repeats.

Example: a trip assistant that checks flights, compares prices, and books the cheapest one once I approve.

E - Evidence

Anthropic, "Building effective agents": https://www.anthropic.com/engineering/building-effective-agents

V - Verification

Anthropic describes agents as systems where the LLM directs its own process and tool use, in contrast to workflows with predefined code paths. It also describes the basic building block as an LLM with retrieval, tools and memory, which fits my RAG and tool-using definitions. I read this through extracts of the article, not every section. My RAG definition comes mostly from general knowledge.

R - Reflection

Companies define "agent" differently, so I focused on behaviour: does it pick its own steps and loop?


Q7 - Where Should Humans Still Decide?

A - Answer

1) Medical advice summary
What could go wrong: wrong or made-up advice.
Required verification: compare with clinical guidelines.
Who approves: a doctor.

2) Contract summary
What could go wrong: a missed clause.
Required verification: read the original clauses.
Who approves: a lawyer.

3) Money transfer suggestion
What could go wrong: wrong amount or wrong recipient.
Required verification: check the bank record.
Who approves: the account owner.

4) Code change to a live system
What could go wrong: a hidden bug or security hole.
Required verification: tests and code review.
Who approves: a senior engineer.

5) Published report
What could go wrong: false claims or fake citations.
Required verification: open every source.
Who approves: the editor or author.

Rule: the more costly or hard to undo the outcome, the more evidence and human sign-off I need before acting.

E - Evidence

NIST AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework

V - Verification

I did not open the nist.gov page directly. Several secondary summaries of the framework say it is organised around Govern, Map, Measure and Manage, and that it expects organisations to define and document human roles and responsibilities for overseeing AI systems. One summary says NIST describes human-AI setups as ranging from fully autonomous to fully manual, and that some systems need human oversight while others may not. That supports my rule that oversight should grow with risk. The failure cases in my list are my own reasoning from what I learned about hallucination, not from NIST.

R - Reflection

AI output is a draft to check, not a decision.


Q8 - Find AI Around You

A - Answer

1) Gmail spam filter
AI involved: yes (machine learning).
Task: classification.
Evidence: Google Workspace blog, https://workspace.google.com/blog/product-announcements/ridding-gmail-of-100-million-more-spam-messages-with-tensorflow
Conclusion: Google says it uses TensorFlow to complement its existing ML models and block image-based spam, hidden content and mail from newly created domains.

2) Google Maps ETA
AI involved: yes (machine learning).
Task: prediction.
Evidence: DeepMind blog, "Traffic prediction with advanced Graph Neural Networks", https://deepmind.google/discover/blog/traffic-prediction-with-advanced-graph-neural-networks/
Conclusion: a Graph Neural Network predicts travel time for each road segment from traffic data.

3) Phone calculator app
AI involved: no.
Task: fixed arithmetic.
Evidence: none needed. It follows fixed rules and gives the same answer every time (my own reasoning).
Conclusion: not AI.

4) Fixed-timer traffic signal near my home
AI involved: probably not.
Task: timing.
Evidence: Not enough public evidence to conclude.
Conclusion: Not enough public evidence to conclude.

5) ChatGPT (the AI chat assistant I use)
AI involved: yes (language model).
Task: generation.
Evidence: Google ML Crash Course, https://developers.google.com/machine-learning/crash-course/llm
Conclusion: language models learn to predict text output. The exact internals of a commercial product are not public.

Rule-based alternative (Gmail): a keyword rule like "block mail containing 'lottery winner'" would catch some spam. But spammers change their wording, and Google's blog says ML helps catch spam that slips past existing protections, including messages designed to hide in legitimate traffic. That is why ML is used.

E - Evidence

See the sources in each row above. The Gmail blog is from 2019, so it shows ML was in use then, not exactly how Gmail works today.

V - Verification

I asked ChatGPT for ideas of everyday AI examples. It listed things like recommendations, navigation, face unlock and spam filtering, but it only pointed to vague "AI-learning resources" with no checkable links, so I did not use it as evidence. For Maps I read DeepMind's own blog post. For Gmail I read Google's own blog post, which states that ML is used. A news report on that post (Digital Trends) says ML works alongside Gmail's rule-based filters. That "rules plus ML" detail comes from the report, not from Google's post. I could not verify how the traffic signal works.

R - Reflection

AI is already inside many ordinary apps, often working in the background. But not everything that sounds smart is AI, and when I cannot verify something it is better to write "Not enough public evidence to conclude" than to guess.


Q9 - Prediction, Classification, Generation

A - Answer

A. Predicting house prices: Prediction. It outputs a number.
B. Does an image contain a cat: Classification. Cat or not cat.
C. Writing an email from a short instruction: Generation. It creates new text.
D. Will a customer cancel a subscription: Classification. It gives a yes/no label (people also call this prediction because it is about the future).
E. Summarising a research paper: Generation. It creates new, shorter text.
F. Is a transaction fraudulent: Classification. Fraud or not fraud.
G. Image from a text description: Generation. It creates a new image.
H. Predicting the next word or token: Prediction. It guesses the most likely next token.

Why next-token prediction matters: writing, summarising, coding and question answering are all done by predicting one token at a time, again and again. One simple task sits underneath many different apps.

E - Evidence

Google Machine Learning Crash Course link from Q3: https://developers.google.com/machine-learning/crash-course/llm

V - Verification

Google's course page describes LLMs as learning to predict text output, which matches H. I saw the module description, not the full lessons. Some real systems mix task types, so I picked the main behaviour in each case.

R - Reflection

D was the confusing one. I decided by output: a number is prediction, a label is classification.


Q10 - My AI Verification Protocol

A - Answer

1) Define the problem. Write what I need and what "correct" means. Catches vague prompts.
2) Inspect assumptions. List what the AI assumed. Catches wrong starting points.
3) Check sources. Open every link it gives, and look for links if it gave none. Catches invented or missing citations.
4) Cross-check. Compare with another tool or an official reference. Catches one-model mistakes.
5) Test the result. Run it, calculate it, try a known case. Catches answers that only look right.
6) Accept, reject or revise. Decide, and note why. Stops silent acceptance.
7) Document. Log the prompt, tool, checks and outcome. Makes the work traceable later.

Example: the AI says a recipe for 4 people needs 300 g of raw rice. I set the goal, ask whether that is raw or cooked, check a cooking site, work out the portions, find it is too much, change the amount, and log what I changed.

E - Evidence

Course handout workflow (define, ask, inspect, verify, conclude, document, reflect), plus my Q4 and Q5 experiments.

V - Verification

Steps 3 and 4 came straight from Q4 and Q5: in both, ChatGPT gave no checkable links or only named documents, so I had to open the arXiv and NeurIPS pages and the RFCs myself. Step 5 comes from Q5, where checking the RFC wording showed that "no error checking" and "UDP is faster" were looser than the standard. The other steps follow the course workflow and are my own reasoning, not something I tested this week.

R - Reflection

I will revisit this protocol at the end of Week 16.
