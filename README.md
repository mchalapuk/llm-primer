# llm-primer
> Base knowledge needed to effectively use large language models (LLMs)

## How to Use It?

First, read through the whole document without clicking on any links.

Then:
* If your goal is to just understand this new and crazy field, stop here.
* If your goal is to start using ChatGPT, the time to start using it is now.
  Consult the document again when constructing specific prompts.
* If your goal is to start building AI systems, you'll probably need to dive
  deeper into linked whitepapers and courses.

## Key Concepts

### ⇨ Large Language Model

Large Language Model (LLM) is an artificial neural network trained on large quantities of
unlabeled text using self-supervised learning or semi-supervised learning. LLMs use deep
neural networks (with multiple layers of perceptrons) that have large number of parameters
(connections between network layers; hundreds of billions or even trillions).

Even though LLMs are trained on a simple task along the lines of predicting the next word
in a sentence, large language models with sufficient training and high parameter counts are
found to capture:

* much of the syntax and semantics of human language,
* considerable general knowledge,
* detailed specialist knowledge (law, medicine, engineering, etc),
* great quantity of facts about the world.

Since 2018 LLMs perform suprisingly well at a wide variety of tasks, including (but not
limited to) document generation, question answering, instruction following, brainstorming,
and chat. Over the years, LLMs have been improved by orders of magnitude.

In 2024, LLMs are able to:

* Pass the Uniform Bar Exam exam (US national and state law) with a score in the 90th percentile,
* Pass all three parts of the United States medical licensing examination within a comfortable range,
* Pass Stanford Medical School final exam in clinical reasoning with an overall score of 72%,
* Receive B- on the Wharton MBA exam,
* Score in the 99th percentile on the 2020 Semifinal Exam of the USA Biology Olympiad,
* Receive the highest score on the following Advanced Placement examinations for college-level
  courses: Art History, Biology, Environmental Science, Macroeconomics, Microeconomics,
  Psychology, Statistics, US Government and US History,
* Pass the Scholastic Aptitude Test (SAT) with a score of 88%,
* Pass the Introductory Sommelier, Certified Sommelier, and Advanced Sommelier exams
  at respective rates of 92%, 86%, and 77%,
* Pass the turing test (arguably).

#### Further Reading 
* [Large Langauge Model](https://en.wikipedia.org/wiki/Large_language_model) on Wikipedia.
* [GPT-4 Passes the Bar Exam](https://law.stanford.edu/2023/04/19/gpt-4-passes-the-bar-exam-what-that-means-for-artificial-intelligence-tools-in-the-legal-industry/)
  on Stanford Law Blog.
* [Is GPT-4 Really Human-Like?](https://medium.com/@marco.murgia/is-gpt-4-really-human-like-43e8e2465217) -
 an article about GPT-4 turing test by Marco Murgia.
* [The exams Chat-GPT has passed so far (2023)](https://www.businessinsider.com/list-here-are-the-exams-chatgpt-has-passed-so-far-2023-1?IR=T) by Business Insider.

### ⇨ Tokenization

A token is a basic unit of text/code used by LLM to process or generate language. Tokens
can be words, characters, subwords, or symbols, depending on the type and the size of the model.
The number of tokens each model uses varies among different LLMs and is referred to as
vocabulary size. Tokens are used on both input and output of LLM neural networks.

LLMs, like all neural networks, are mathematical functions whose inputs and outputs are
lists of numbers. For this reason, each LLM input prompt is split into a list of smaller
units (tokens) and then mapped to number representations that can be processed by the LLM.
This process is refered to as tokenization. The reverse of this process must be applied
before sending the LLM response to the user.

A tokenizer is a software component (separate from the neural network) that converts
text to a list of integers. The mapping between text token and its number representation
is chosen before the learning process and frozen forever.
A secondary function of tokenizers is text compression. Common words or even phrases like
"you are" or "where is" can be encoded into one token. This significantly saves compute.

The OpenAI GPT series uses a tokenizer where 1 token maps to around 4 characters, or around
0.75 words, in common English text. Uncommon English text is less predictable, thus less
compressible, thus requiring more tokens to encode.

#### Further Reading
* [What are Tokens?](https://learn.microsoft.com/en-us/semantic-kernel/prompt-engineering/tokens)
  on Microsoft Semantic Kernel.

### ⇨ Transformer Architecture

Transformer is a revolutionary way to construct LLMs, using the multi-head self-attention
mechanism introduced in "Attention Is All You Need" whitepaper (Google, 2017).
The attention mechanism allows for modeling of dependencies between tokens without any
degradation of information caused by distances between those tokens in long input
or output sequences.
The output of transformer-based LLMs does not only contain perfectly coherent human
language but also suggest processeses that resemble deep reasoning or cognition.

Transformer has the ability to generate coherent human language text sequences that
match provided input text sequence (both syntactically and semantically).
This generation process is referred to as inference.
The model is trained on a task of prediction (probability) of a single token based
on the input token sequence.
During the inference, the model is invoked iteratively in an auto-regressive manner,
consuming the previously generated tokens as additional input when generating the next.
This process is continued until a stop condition occurs which, in a default case, is
a special token indicating the end of output sequence.

This new architecture allowed for increased parallelisation and shorter training times
when compared to the older models and has led to the development of pretrained systems,
such as the original Generative Pre-Trained Transformer (GPT) by OpenAI and Bidirectional
Encoder Representations from Transformers (BERT) by Google, both in 2018.

In 2023, transformer is still the state-of-the-art architecture for LLMs.

#### Further Reading
* [Attention is What You Need](https://arxiv.org/pdf/1706.03762.pdf) - Original
  whitepaper describing the transformer architecture.
* [Transformer Architecture](https://en.wikipedia.org/wiki/Transformer_(machine_learning_model))
  on Wikipedia.
* [Timeline History of Large Language Models](https://voicebot.ai/large-language-models-history-timeline/) on voicebot.ai.
* [GPT-3](https://en.wikipedia.org/wiki/GPT-3) on Wikipedia.
* [BERT (language model)](https://en.wikipedia.org/wiki/BERT_(language_model)) on Wikipedia.

### ⇨ Emergent Abilities

Abilities gained by LLMs which were not predicted by extrapolation of the performance of
smaller models are referred to as emergent abilities.
These abilities are not programmed-in or designed. They are being discovered during LLMs
usage or testing, in some cases only after the LLM has been made available to the general
public.

As new, bigger versions of LLMs are released, some abilities increase from near-zero
performance to sometimes state-of-the-art performance.
The sharpness of the change in performance and its unpredictability is completely different
from what is observed in the biological world and is what makes emergent abilities an
interesting phonemenon and a subject of substantial study.

Examples of abilities that emerged so far in LLMs:
* Correct elementary-level arithmetics,
* Reading comprehension,
* Cause-effect chain understanding,
* Truthful question answering and fact checking,
* Logical fallacy detection,
* Multi-step reasoning,
* Ability to perform tasks that were not included in their training examples
  ("zero-shot" and "few-shot" learning),
* Rich semantic understanding of International Phonetic Alphabet,
* Classification of geometric shapes coded in SVG images.

The popular opinion is that these abilities are in fact emergent (impossible to predict)
but some researchers argue that they are actually predictably acquired according to a
smooth scaling law.

#### Further Reading
* [Emergence (philosophy, systems theory, science, art)](https://en.wikipedia.org/wiki/Emergence)
  on Wikipedia.
* [Emergent Abilities of Large Language
  Models](https://www.assemblyai.com/blog/emergent-abilities-of-large-language-models/)
  by Ryan O'Connor at AssemblyAI.
* [137 emergent abilities of large language models](https://www.jasonwei.net/blog/emergence)
  by Jason Wei.
* [Emergent Abilities of Large Language Models](https://openreview.net/pdf?id=yzkSU5zdwD) -
  Analysis of many emergent abilities (Google, Aug '22).
* [Are Emergent Abilities of Large Language Models a
  Mirage?](https://arxiv.org/pdf/2304.15004.pdf) - Whitepaper challenging the emergence
  phenomenon by providing more metrics and better statistics.

### ⇨ Hallucination

Hallucination (on confabulation or delusion) is a phenomenon in which the content generated
by a LLM is nonsensical or untrue or unfaithful to the provided source content.
Hallucinations are often expressed by LLMs in a very confident way which lowers their
detectability.

Why LMMs hallucinate?
* The LLM training dataset may include fictional content, as well as subjective content
  like opinions and beliefs. 
* LLMs are not generally optimized to say “I don’t know” when they don’t have enough
  information. When the LLM has no answer, it generates whatever is the most probable
  response. 
* Prompts which are logically incorrect or messy or even in any way uncommon may
  significantly flatten token probability distribution and lead to hallucination.

In transformers, hallucinations seems to be cascading. Hallucinated tokens lead to more
hallucinated tokens as the coherence is being enforced by the attention mechanism.
On a higher level of abstraction, the same problem is observed in chat systems based on LLMs
where previous messages generated by the LLM are included in next input prompts.
Garbage in, garbage out.

OpenAI and Google's DeepMind developed a technique called reinforcement learning with
human feedback (RLHF) to tackle ChatGPT's hallucination problem.
Although they have been able to significantly reduce hallucination in GPT-3.5 and GPT-4
models, the phenomenon is considered to be a major (and still not completely understood)
problem in LLM technology in 2023.

#### Further Reading
* [Hallucination (artificial intelligence)](https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence))
  on Wikipedia.
* [Reinforcement learning from human feedback](https://en.wikipedia.org/wiki/Reinforcement_learning_from_human_feedback)
  on Wikipedia.
* [Illustrating Reinforcement Learning from Human Feedback (RLHF)](https://huggingface.co/blog/rlhf) -
  an article on Hugging Face Blog.
* [Survey of Hallucination in Natural Language Generation](https://arxiv.org/pdf/2202.03629.pdf) -
  a whitepaper on hallucination.
* [Fine-Tuning Language Models from Human Preferences](https://arxiv.org/pdf/1909.08593.pdf) -
  a whitepaper on RLHF.
  
### ⇨ Context Window

Context window (or context size) is the number of tokens the model can consider when
generating responses to prompts. The sum of input prompt and generated response must be
smaller in size than the context window. Otherwise, the language model breaks down and
starts generating nonsense. Context window is one the the biggest limitations of LLMs.

#### Further Reading
* [LMM Engineering Context Windows](https://blendingbits.io/p/llm-engineering-context-windows) -
  article on blendingbits.io.
* [The Secret Sauce behind 100K context window in LLMs: all tricks in one
  place](https://blog.gopenai.com/how-to-speed-up-llms-and-use-100k-context-window-all-tricks-in-one-place-ffd40577b4c)
  on blog.gopenai.com
* [Extending Context is Hard…but not Impossible†](https://kaiokendev.github.io/context) -
  article on kaiokendev.github.io.

### ⇨ LLM Training

Training of a large language model involves the following steps:

1. **Data Gathering**. The first step is to gather the training dataset, which is the
   resource that the LLM will be trained on. The data can come from various sources
   such as books, websites, articles, and open datasets. 
2. **Data Cleanup**. The data then needs to be cleaned and prepared for training.
   This may involve removing hate speech, converting the dataset to lowercase and
   removing stop words. 
3. **Data Tokenization**. Tokenisation involves choosing token vocabulary, coding the
   tokenizer and converting all training data from text into arrays of integers.
4. **Model Selection and Configuration**. The architecture of the model needs to be
   specified and hyper-parameters (like the number of network layers) configured.
   Decisions made in this step determine number of parameters that the model will have. 
5. **Model Training**. The model is trained on the pre-processed data using a technique
   called self-supervised learning in which the model trains itself by leveraging one
   part of the data to predict the other part and generate labels accurately. In effect,
   this learning method converts an unsupervised learning problem into a supervised one.
   During the training weights in the model's parameters are adjusted based on the
   difference between its prediction and the actual next word. This process is repeated
   millions of times until the model reaches a satisfactory level of performance.
   Since the training phase requires an immense computing power it is typically
   parallelised into hundred or even thousands of processes.
6. **Model Evaluation**. After training, the model is evaluated on a test dataset that
   has not been used to train the model. This provides a measure of performance.
7. **Model Fine-Tuning**. Based on the evaluation results, the model may require some
   fine-tuning by adjusting its hyperparameters, changing the architecture, or training
   on additional data to improve its performance.

Training LLM from scratch is costly.
Lambdalabs estimated a hypothetical cost of around $4.6 million US dollars to train GPT-3.
For this reason, LLMs are trained by very few entities that have access to this type of
resources and are engaged in active research of the field. 
Most users will use pre-trained and already fine-tuned LLMs via commercial APIs,
while more advanced users will fine-tune a pre-trained open-source model.

#### Further Reading
* [Large Language Model Training in 2023](https://research.aimultiple.com/large-language-model-training/)
  by Cem Dilmegani on research.aimultiple.com.
* [Self-Supervised Learning: Benefits & Uses in 2023](https://research.aimultiple.com/self-supervised-learning/)
  by Cem Dilmegani on research.aimultiple.com.
* [Current Best Practices for Training LLMs from
  Scratch](https://uploads-ssl.webflow.com/5ac6b7f2924c656f2b13a88c/6435aabdc0a041194b243eef_Current%20Best%20Practices%20for%20Training%20LLMs%20from%20Scratch%20-%20Final.pdf)
  from Weights & Biases.
* [Training a causal language model from scratch](https://huggingface.co/learn/nlp-course/chapter7/6)
  from NLP Course on Hugging Face.

### ⇨ Prompt Engineering

Prompt engineering or in-context prompting is a trial-and-error process in which LLM input
prompt is created and optimised with a goal of influencing the LLMs behaviour without
changing weights of the neural network. The effect of prompt engineering methods can vary
a lot among models, thus requiring heavy experimentation and heuristics.

Prompt engineering is being used in 3 different ways:
* LLM researchers use prompt engineering to improve the capacity of LLMs on a wide range
  of common and complex tasks such as question answering and arithmetic reasoning.
  Many basic prompting techniques (like "zero-shot" and "few-shot" prompting) were
  introduced in LLM research papers.
* Software developers create advanced prompting techniques that interface with LLMs
  and other tools and enable writing robust AI applications.
  The process of engineering prompts can be accelerated by using software libraries
  that feature prompt templating and high-level abstractions over communication with LMMs.
* It is theorised that in-context prompting will be a high demand skill as more
  organizations adopt LLM AI models.
  This can lead to prompt engineering being a profession in of its own.
  A good prompt engineer will have the ability to help organizations get the most out
  of their LLMs by designing prompts that produce the results optimised in context of
  the specific organisation.

#### Further Reading
* [Prompt Engineering Overview](https://learn.microsoft.com/en-us/semantic-kernel/prompt-engineering/)
  on Microsoft Semantic Kernel.

### ⇨ Prompt Injection

Prompt injection is an attack against applications that have been built on top of LLMs.
The injection can occur when the app uses untrusted text (which comes from the user) as
part of the prompt.
The attack, when carefully constructed, allows the hacker to get the model to say anything
that they want, including printing out the whole prompt itself.

#### Further reading
* [Prompt Injection Defensive Measures](https://learnprompting.org/docs/category/-defensive-measures)
  on learnprompting.org.
* [Prompt Injection Explained](https://simonwillison.net/2023/May/2/prompt-injection-explained/)
  by Simon Willison.

### ⇨ Embeddings

Embeddings are vectors or arrays of numbers that represent the meaning and the context
of tokens processed by an LLM.
Embeddings are generated by LLMs and are used by them internally to store syntactic
and semantical information about the processed language.
They help LLMs with text classification, summarization, translation, and generation.

Typically, LLMs can be invoked in embedding mode in which embedding vectors
for given input text are returned to the user (without generating any output tokens).
Those embeddings are typically used to index texts in vector databases.

#### Further Reading
* [What are embeddings?](https://learn.microsoft.com/en-us/semantic-kernel/memories/embeddings)
  on Microsoft Semantic Kernel.

### ⇨ Vector Database

A vector database is a software solution for storing, indexing, and searching across
a massive dataset of unstructured data that leverages the power of embeddings from
machine learning models.

Embeddings capture the meaning and context of words or data.
This means that similar words will generate similar embedding vectors, and different
words will generate different vectors.
A vector database can measure reletedness of different language sequences by comparing
directions of their embedding vectors.

The technique of querying data related to a specific text and using it as part of
LLM prompt is refered to as "semantic memory" and is considered to be a solution to
the problem of limited context window.

#### Further Reading
* [Vector Database](https://en.wikipedia.org/wiki/Vector_database) on Wikipedia.
  
## Prompting Techniques

### ⇨ Role Play
A prompt that instructs the model to play a specific role in the conversation is
referred to as role play (also memetic proxy).
Role-playing prompts shift the "mindset" of langauge models and allows them
to generate output which is consistent with a desired persona.

Role play prompts to models optimised for chat are written in second person form.
Typically, setences in those prompts start with "You are a..." or  "Act as a..."
or "Your job is to...".
Prompts to models optimised for text completion are written in third person
and describe all participants of the conversation.
They typically use sentences like "This is a transcript of a conversation between..."
and "His job is to...".
Advanced prompts may contain multiple (or all) of the above as the description
of the LLM persona gets more elaborate.

Role play technique is typically employed when a task to be done by a LLM is performed
by a specialist (like a lawyer, data scientist or SEO expert) in the real world.
It is often combined with specification of a clear goal for the whole conversaion
which gives the model a certain pro-activeness in its pursuit.

#### Examples

Second person form (for models optimised for chat):
> Act as an AI and machine learning specialist, help me integrate AI or machine
> learning into my project. Ask me about my project's goals, the problems I want
> to solve with AI or machine learning, and any specific techniques or algorithms
> I'm interested in, and then provide advice on implementation and best practices.

Third person form (for models optimised for text completion):
> This is a transcript of acenversation between an AI and machine learning specialist
> and an entrepreneur. The job of the specialist is to help the entrepreneur integrate
> AI or machine learning into their project. The specialist is proactive in asking about
> project's goals, the problems that needs to be solved with AI or machine learning,
> and any specific techniques or algorithms the entrepreneur is interested in. After
> the interview, the specialist provides advice on implementation and best practices.<br>
>
> AI Specialist: Hello! How can I help you?<br>
> Entrepreneur: Hello. I'm seeking advice on how to integrate machine learning into my project.<br>
> AI Specialist: <br>

#### Further Reading
* [Role Based Prompts for ChatGPT (Act as a ...)](https://stackdiary.com/chatgpt/role-based-prompts/) -
  a collection of role playing prompts ready to be used in the chat (stackdiary.com).
* [Role-Play with Large Language Models](https://arxiv.org/pdf/2305.16367.pdf) -
  Whitepaper (Google DeepMind, 2023).

### ⇨ Inception
Inception is also called First Person Instruction. It is encouraging the model to think
a certain way by including the start of the model’s response in the prompt.
This technique works great with models optimised for text completion and might not work
at all with models optimised for chat or instruction following.

#### Example

> Q: What is the meaning of life?<br>
> A: Here's what some of the greatest minds have been thinking about it:<br>

Model's completion:
> 1. Socrates: "The unexamined life is not worth living."
> 2. Albert Einstein: “Try not to become a man of success, but rather try to become a man of value.” 
> 3. Buddha: “The way is not in the sky. The way is in the heart.” 
> 4. Benjamin Franklin: “Be at war with your vices, at peace with your neighbors, and let every new year find you a better man.”
> 5. Dalai Lama: “The purpose of our lives is to be happy.”

#### Further Reading
* [Riley Goodside's Example @ Twitter](https://twitter.com/goodside/status/1583262455207460865?s=20&t=8Hz7XBnK1OF8siQrxxCIGQ)

### ⇨ Few-Shot
A technique of including one or more examples of already solved tasks in the
prompt is referred to as few-shot prompting.
The LLM learns from the examples and construct a response to the
question or a task specified at the end of the prompt.
The output is expected to be in exactly the same format as in the examples. 

Few shot prompting tends to break down when more complex logic is required
to complete the task.
LLMs can't reason outside of what is being read/written by them.
If the examples contain only questions and answers and the task is not common,
LLM will not able to figure out the algorithm for getting the answer.

The limitations of Few-Shot technique can be mitigated by combining it with
Chain-of-Thoughts technique.
If step-by-step reasoning added to each example the model will be able to
reproduce this reasoning in its output. 

#### Example
The following example uses few-shot technique to perform sentiment analysis.

> This is awesome! // Negative<br>
> This is bad! // Positive<br>
> Wow that movie was rad! // Positive<br>
> What a horrible show! //<br>

The LLM is expected to output just one word, either "Negative" or "Positive".

#### Further Reading
* [Few Shot Prompting](https://www.promptingguide.ai/techniques/fewshot) on promptingguide.org.
* [Language Models are Few-Shot Learners](https://arxiv.org/pdf/2005.14165.pdf) - Whitepaper (OpenAI, 2020).

### ⇨ Zero-Shot
LLMs with high enough parameter count (or models fine-tuned to follow instructions)
are able to perform tasks without any example provided in the prompt.
This technique is referred to as "zero-shot" prompting.

When compared to "few-shot" prompting this technique onsumes less of context window
space as the prompt doesn't contain any examples.
On the other hand, "few-shot" is more reliable, especially for more complex tasks.

#### Example

> Classify the text into neutral, negative or positive.<br>
> Text: I think the vacation is okay.<br>
> Sentiment:<br>

#### Further Reading
* [MULTITASK PROMPTED TRAINING ENABLES ZERO-SHOT TASK GENERALIZATION](https://arxiv.org/pdf/2110.08207.pdf) -
  Whitepaper (HuggingFace, Big Science, 2022).

### ⇨ Chain of Thought
Self-attention mechanism is a breakthrough technology that enabled creating LLMs
with emergent abilities that resemble cognition.
It is a very particular type of cognition though, and one with a significant limitation.
The attention mechanism operates on tokens which are things that model reads or generates.
This means that self-attention models are not able to "think" of something without outputting it.

The lack of reasoning outside of LMMs input/output is a fundamental limitation which renders
even the best models unable to natively perform complex cognitive tasks that humans are good at.
Attention-based models are not able to understand complex relationships, algorithms or mathematical
formulas just by looking at example questions and answers.

Chain of Thought (CoT) is a prompting technique that aims to enable more complex reasoning
capabilities in LLMs.
The technique encourages the model to generate a series of intermediate reasoning steps which
works around the complex reasoning limitation by adding more information to the attention
mechanism.

CoT technique has been used in the following forms:
1. **Zero-Shot CoT**:
   In the most basic form of the technique, the user asks the (chat-optimised) model to write
   down its reasoning.
   Sentences like "Tell me your thought process." or "Write down each step of your reasoning."
   should open the model to complex reasoning.
3. **Zero-Shot CoT with Inception**:
   When working with text-completion models, CoT may be combined with Inception technique
   where then answer is started with "Let's think step by step." sentence.
5. **Few-Shot CoT**:
   Including multiple demonstrations of tasks, reasonining steps and final solutions
   before asking the actual question is the most effective variant of the technique
   that maximises the models ability to solve cognitively complex tasks.
   This variant of the technique is typically used with models optimised for text completion.

#### Examples

One-shot Chain-of-Thought with Inception:
> Q: I went to the market and bought 10 apples. I gave 2 apples to the neighbor and 2 to the repairman. I then went and bought 5 more apples and ate 1. How many apples did I remain with?<br>
> A: Let's think step-by-step.<br>

Few-shot Chain-of-Thought:
> Q: Is the sum of odd numbers equal to sum of even numbers in this group? 4, 8, 9, 15, 12, 2, 1.<br>
> A: The sum of odd numbers (9, 15, 1) is 25. The sum of even numbers (4, 8, 12, 2) is 26. The sums are not equal. The answer is no.<br>
> 
> Q: Is the sum of odd numbers equal to sum of even numbers in this group? 6, 7, 9, 17, 14, 4, 1, 10.<br>
> A: <br>

#### Further Reading
* [SHOW YOUR WORK: SCRATCHPADS FOR INTERMEDIATE COMPUTATION WITH LANGUAGE MODELS](https://arxiv.org/pdf/2112.00114.pdf) -
  Whitepaper (Google Brain, 2021).
* [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/pdf/2201.11903.pdf) -
  Whitepaper (Google Brain, 2023).

### ⇨ Self-Ask
Self-Ask is a Few-Shot prompting technique that builds on top of chain-of-thought prompting.
In this method, the model explicitly asks itself follow-up questions, and then answers them.

#### Example

> Question: Who lived longer, Theodor Haecker or Harry VaughanWatkins?<br>
> Are follow up questions needed here: Yes.<br>
> Follow up: How old was Theodor Haecker when he died?<br>
> Intermediate answer: Theodor Haecker was 65 years old when he died.<br>
> Follow up: How old was Harry Vaughan Watkins when he died?<br>
> Intermediate answer: Harry Vaughan Watkins was 69 years old when he died.<br>
> So the final answer is: Harry Vaughan Watkins<br>
> 
> Question: Who was president of the U.S. when superconductivity was discovered?<br>
> Are follow up questions needed here:<br>

An example answer (GPT-3) to the above prompt.
> Yes.<br>
> Follow up: When was superconductivity discovered?<br>
> Intermediate answer: Superconductivity was discovered in 1911.<br>
> Follow up: Who was president of the U.S. in 1911?<br>
> Intermediate answer: William Howard Taft.<br>
> So the final answer is: William Howard Taft.<br>

#### Further Reading
* [MEASURING AND NARROWING THE COMPOSITIONALITY GAP IN LANGUAGE MODELS](https://ofir.io/self-ask.pdf) -
Whitepaper (Oct, 2022).

## Prompt Chaining Techniques

Prompt chaining is a set of programming techniques that combine multiple LLM calls,
with parts of output of one step being parts of the input to the next.
The combination of LLM capabilities and imperative control flow enables accomplishing
tasks which are cognitively complex and in a way that is perceived to be transparent
and controllable.

The process of breaking down (or factoring) sophisticated learning and reasoning tasks
into many small and mostly independent tasks is referred to as Factored Cognition.
Programs which are based on prompt chaining are sometimes referred to as Language
Model Cascades.

#### Further Reading

* [PromptChainer: Chaining Large Language Model Prompts through Visual Programming](https://arxiv.org/pdf/2203.06566.pdf) -
  Whitepaper (Google Research, 2022).
* [Language Model Cascades](https://arxiv.org/pdf/2207.10342.pdf) -
  Whitepaper (2022).
* [Factored Cognition Primer](https://primer.ought.org/) - A course on writing LLM programs.
* [promptingguide.ai](https://www.promptingguide.ai/).

### ⇨ Self-Consistency
Self-Consistency is a prompt chaining technique that aims to improve
Chain-of-Though technique by generating a diverse set of reasoning paths
and then selecting the most consistent answer.

The technique builds on the following assumptions:
1. Complex reasoning tasks typically admit multiple reasoning paths that reach
 a single answer.
2. The more that deliberate thinking and analysis is required for a problem,
 the greater the diversity of reasoning paths that can recover the answer.

Self-Consistency employs multiple inferences (minimum 3) of the same prompt
which contains a question.
With high probability, not all inferences produce the same final answer.
The answers are aggregated (typically using unweighted sum) and the
highest-scoring answer is returned as the most consistent (majority vote).

The downside of Self-Consistency technique is increased cost of compute (at least 3x).
In a setup where sample inference is parallelised, response time difference
is negligible.

#### Further Reading
* [SELF-CONSISTENCY IMPROVES CHAIN OF THOUGHT REASONING IN LANGUAGE MODELS](https://arxiv.org/pdf/2203.11171.pdf)

### ⇨ Tool Prompting
Tools are functions that LLM agents can use to interact with external resources.
These tools can be generic utilities (e.g. web search, wiki search,
current date/time/weather) or other LLM chains/agents.

The LLM is prompted with a list of tools that are available for its usage,
a description of response syntax, and instructions to stop inference after
requesting a tool call.
LMM responses that contain tool calls are parsed, after which tool implementations
are invoked with the parameters requested by the LLM.
Responses from the tools are fed back to the LLM in the next prompt.

Tool prompting can be seen as LMM-level variant of Inversion of Control (IoC)
design pattern.

### ⇨ ReAct
ReAct is a prompt chaining technique that combines Chain-of-Thought and Tool Prompting
techniques.

TODO

#### Further Reading
* [REACT: SYNERGIZING REASONING AND ACTING IN LANGUAGE MODELS](https://arxiv.org/pdf/2210.03629.pdf)

### ⇨ Summarization
Summarization is a set of prompt chaining techniques that create a shorter
version of a document that captures all the important information.
Summarization is considered to be a solution to the context window problem.

TODO

#### Further Reading
* [5 Levels Of Summarization: Novice to Expert](https://github.com/gkamradt/langchain-tutorials/blob/main/data_generation/5%20Levels%20Of%20Summarization%20-%20Novice%20To%20Expert.ipynb)
* [Mastering ChatGPT: Effective Summarization with LLMs](https://towardsdatascience.com/chatgpt-summarization-llms-chatgpt3-chatgpt4-artificial-intelligence-16cf0e3625ce)

### ⇨ Three of Thought
TODO

### ⇨ Graph of Thought
TODO

## Further Reading

* [Practical Guide for LLMs](https://github.com/Mooler0410/LLMsPracticalGuide) -
  a low-level guide to various LLMs.
* [Unifying Large Language Models and
Knowledge Graphs](https://arxiv.org/pdf/2306.08302.pdf) - Whitepaper, 2023.
