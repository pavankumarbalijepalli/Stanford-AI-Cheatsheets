Here’s a comprehensive list of evaluation benchmarks, tests, and frameworks—including Needle in a Haystack and its advanced successors—for evaluating language models, especially long‑context, retrieval-augmented, agentic, reasoning, and multimodal abilities. Everything is grouped and cited.


---

🧠 Long‑Context & “Needle‑in‑a‑Haystack”-Style Benchmarks

Needle‑in‑a‑Haystack (NIAH): Inserts a “needle” sentence into an extended text (“haystack”) and tests whether the model can locate and extract it to answer a related question. Measures raw retrieval capability and context awareness  .

NeedleBench / mmNeedle (MultiModal Needle‑in‑a‑Haystack): Extends NIAH to support multimodal input (images & text) and enriched retrieval requiring locating sub‑images within many candidates  .

RULER (Real Context Size): A synthetic, configurable suite built around the needle paradigm. Supports multiple needles, multi‑hop tracing, aggregation, and longer lengths to assess real long‑context capabilities beyond keyword matching  .

BABILong: A reasoning‑in‑a‑haystack benchmark with 20 reasoning task categories (fact chaining, deduction, aggregation) over documents up to tens of millions of tokens—models typically use only part of context  .

LV‑Eval: Balanced long‑context benchmark across 5 length bands up to 256 K tokens, injecting confusing facts and keyword‑recall metrics, testing ability to resist distractions and address needle challenges  .

LongBench, InfiniteBench, ZeroSCROLLS, L‑Eval, etc.: Collections of tasks (QA, summarization, code, retrieval) spanning context lengths from ~1 K to 100 K+ tokens. Often include needle‑style tasks or synthetic distractors  .



---

🧠 Additional Long‑Context & Novelty Benchmarks

ETHIC: Measures Information Coverage (IC)—how much of context was needed to answer questions. Designed to challenge models beyond superficial needle retrieval by requiring reasoning across text with high IC  .

NoCha (“Novel Claim Challenge”): Provides minimal pairs of true/false claims about recently published books, testing whether models can verify both for correctness using full book context—beyond literal keyword matching  .

Visual Haystacks (VHs): Tests multimodal MLLMs on image retrieval amid large pools; simple questions require object presence in one or few images among thousands  .



---

📚 General LLM Benchmark Suites (Reasoning, Knowledge, Code, Common Sense)

GLUE, SuperGLUE, MultiNLI, WinoGrande, Natural Questions, QuAC, PIQA, SciQ, OpenBookQA, TriviaQA, ARC, HellaSwag, TruthfulQA, GPQA, AGIEval, MathVista, OlympicArena—natural language understanding, reasoning, and common sense across domains  .

MMLU: Massive Multitask Language Understanding with 57 domains in advanced academic subjects. Widely used but contaminated and partially phased out by 2025  .

BIG‑Bench (BBH, BBEH): A suite of >200 diverse tasks, including adversarial variants for robustness and reasoning extremes  .

GSM8K: Grade‑school math word problems requiring multi‑step reasoning.

HumanEval / MBPP / APPS / BigCodeBench: Code generation benchmarks measuring functional correctness via unit tests or bug fixing  .



---

📊 Retrieval‑Augmented & Agentic/Evaluation Frameworks

BeIR: Standard for evaluating retrieval across domain/task types (fact-checking, QA, duplicate detection) – measures retrieval effectiveness across dense/sparse/hybrid systems  .

FRAMES: End‑to‑end RAG benchmark evaluating factual accuracy, retrieval relevance, reasoning over multi-hop queries  .

MultiMedQA / LegalBench / FinBen: Domain-specific QA benchmarks focusing on factuality, comprehension, bias in medical, legal, and financial contexts  .

MuSR: Multi‑step reasoning benchmark including murder mystery, object placement, team allocation tasks—requires chain‑of‑thought and integration across context  .



---

🧾 Summary Table

Benchmark / Eval	Purpose / Trait

Needle‑in‑a‑Haystack (NIAH)	Simple needle retrieval in long context
NeedleBench / mmNeedle	Text/image retrieval in long/haystack multimodal context
RULER	Configurable multi-needle and multi-hop context scaling
BABILong	Complex reasoning over long documents (millions tokens)
LV‑Eval	Accurate, controlled long‑context QA with confusion
ETHIC	Measures information coverage across long context
NoCha	True/false claim verification across novel-length books
Visual Haystacks	Large-scale image retrieval in visual haystacks
SCROLLS, LongBench, etc.	Multi-task long-context evaluation (QA, summarization, etc.)
MMLU, BIG‑Bench, ARC, etc.	General knowledge & reasoning across diverse domains
HumanEval, MBPP, APPS	Code generation and bug fixing task performance
BeIR, FRAMES	Retrieval/ RAG system evaluation
MuSR	Multi‑step reasoning tasks requiring integration



---

These benchmarks span basic needle recall to advanced reasoning and retrieval, across modalities and context lengths from a few thousand to millions of tokens. They test not only retrieval but also comprehension, multi-hop inference, contradiction detection, and task-specific reasoning.

Let me know if you’d like in-depth descriptions or performance comparisons for any benchmark or model!


---
---


Here’s a comprehensive and extensive list of LLM and LLM‑agent evaluation metrics, covering everything from classic NLP metrics to the newest benchmarks, component-level agent-specific scores, safety, fairness, and more. This draws on recent literature and surveys for full coverage.


---

1️⃣ Language‑Model & Natural Language Generation (NLG) Metrics

These are used for general LLM output tasks (translation, summarization, generation):

Perplexity (PPL) – measures how well the model predicts text; lower is better  

BLEU (Bilingual Evaluation Understudy) – n‑gram overlap for translation/generation  

METEOR – uses precision, recall, stemming, synonym matching  

ROUGE (ROUGE‑N, ROUGE‑L, ROUGE‑W, ROUGE‑S, ROUGE‑SU) – summary/translation recall‑oriented overlaps  

LEPOR (and variants hLEPOR, nLEPOR) – length, precision, position, recall penalties, language‑independent  

Word Error Rate (WER), NIST – other traditional translation metrics (not fully listed but implied via BLEU page)  

Token‑sort Ratio, Token‑set Ratio, Keyword presence, Language check – Microsoft list of other reference‑based metrics  



---

2️⃣ Semantic, Factuality & Context Metrics

Evaluate meaning, relevance, truthfulness:

Answer Correctness / Accuracy – does output match ground truth  

Semantic Similarity / BERTScore‑style – contextual embedding similarity to references  

Hallucination Rate / Factual Consistency – detecting misinformation or invented details  

Relevance / Informativeness – how well the response addresses the prompt; measured via human or automated ratings  



---

3️⃣ Safety, Fairness, & Responsible Metrics

Detect harmful or biased behavior:

Bias Score / Fairness Score – check for demographic or other systematic bias  

Toxicity / Offensive Content Detection – safety / harm avoidance  

AILuminate safety benchmark (MLCommons) – model ratings across violence, hate, self‑harm, IP infringement, etc.  



---

4️⃣ Efficiency & Calibration Metrics

Resource and reliability considerations:

Inference Latency & Resource Use – runtime speed, compute cost, energy consumption  

Calibration – degree to which the model’s confidence matches actual correctness (under‑ vs over‑confident)  



---

5️⃣ Holistic & Multi‑scenario Benchmarks (HELM‑style)

Evaluate across many dimensions and tasks:

HELM metrics from Stanford’s Holistic Evaluation:

Accuracy, Calibration, Robustness, Fairness/Bias, Toxicity, Efficiency

Applied across 16 core scenarios + targeted reasoning/disinformation tests  




---

6️⃣ Task‑Specific & Benchmark Based Metrics

Used for particular domains or tasks:

MMLU (Massive Multitask Language Understanding) – multiple‑choice subject benchmarks (57 subjects) measuring broad knowledge and reasoning  

HumanEval / CodeBench / ICE‑Score – code generation and execution correctness metrics

HumanEval uses functional correctness over coding problems

ICE‑Score: LLM‑judged code correctness and human preference without explicit oracle  




---

7️⃣ LLM‑Agent & Tooling Metrics

Measure agents built on LLMs that call tools, plan, and act autonomously:

Task Completion / Success Rate – whether the chain of actions achieved the goal  

Tool Correctness / Tool‑Calling Accuracy – whether the agent selected and used the right tool or API action  

Contextual Relevancy / Retriever Quality – whether retrieval-augmented context fed to the LLM was relevant and accurate  

Agentic Reasoning / Workflow Reasoning Metrics – evaluation of planning steps, chain-of-thought, reasoning over multiple steps  

Component‑Level Evaluation – splitting evaluations for each module: planning, retrieval, generation, tool use  

AgentQuest metrics (from the AgentQuest modular benchmark): two new metrics that track agent progress and failure points in multi-step tasks  



---

✅ Summary Table

Category	Metrics Included

Classic NLG / LM	Perplexity, BLEU, METEOR, ROUGE, LEPOR, WER, NIST, token‑ratio, language‑check
Semantic & Relevance	Answer correctness, semantic similarity (BERTScore), relevance/informativeness
Factuality & Hallucination	Hallucination rate, factual consistency
Safety & Fairness	Bias score, toxicity detection, AILuminate risk ratings
Efficiency & Calibration	Inference latency, compute/energy, calibration
Holistic Benchmarks	HELM: accuracy, robustness, fairness, etc across scenarios
Task‑Specific / Benchmarks	MMLU, HumanEval, ICE‑Score (code), domain‑specific
LLM‑Agent Behavior	Task completion, tool correctness, reasoning/chain‑of‑thought quality, retrieval relevance, component‑level breakdown
Agent Benchmark Frameworks	AgentQuest metrics for modular agent assessment



---

🧠 Additional Considerations

Human evaluation remains the gold standard for many subjective metrics like fluency, coherence, relevance, preference—but is costly and slower. Most automated metrics correlate somewhat with humans but often fail on nuance  .

Benchmark contamination is a risk: models trained on evaluation sets can inflate scores. Many modern benchmarks try to mitigate that  .

Custom task‑specific metrics are often necessary in production; you may build tailored scoring for your own summarization or agent workflows beyond standard metrics  .



---

📌 Final Note

This list covers virtually all known metrics, from classic reference‑based scores to state‑of‑the‑art agent evaluation frameworks, safety/risk, fairness, semantic, execution‑based metrics, and modular agent components. If there’s any specific subset or sub‑category (for example, retrieval‑augmented generation metrics or multi‑agent systems) you’d like broken out further, I’d be glad to dive deeper!


