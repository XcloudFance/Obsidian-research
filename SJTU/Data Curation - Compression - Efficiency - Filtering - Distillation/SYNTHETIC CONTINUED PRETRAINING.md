## SYNTHETIC CONTINUED PRETRAINING

- [http://arxiv.org/abs/2409.07431](http://arxiv.org/abs/2409.07431)
- problems to be solved: However, this **knowledge acquisition** is **data-inefficient**—to learn a given fact, models must be trained on **hundreds to thousands of diverse representations of it.** This poses a challenge when adapting a pretrained model to a small corpus of domain-specific documents, **where each fact may appear rarely or only once.**
- **Extracting small entities to form diverse contexts**
- uses a language model to generate text descriptions about **relations** among the extracted entities, iteratively “filling in” the knowledge graph underlying the corpus.
- Also extending experiments towards RAG. and Paraphrase doesnt make increase performance.

![[image.png]]

EntiGraph consists of three steps/prompts:

- extracting entities from the document
- describing single entities in the context of the document
- analyzing relations between arbitrary subsets of the entities.

Open-book Setting (RAG)

- Chunking the document following Langchain splitter
- Re-ranking
- Same as step 1
- Synthetic Augmentation: Hereby x and y all means entity

![[image 1.png]]

  

  

  

Interesting stuffs: It doesnt create new relations based on current knowledge

![[image 2.png]]

  

  

Relation Approximation

![[image 3.png]]

  

  

Acc Setup:

![[image 4.png]]

**V(V-1) is to normalize the adjacency graph of M_t**

  

Besides those, they also prove a rather rigorous formula based on **Poisson Branching Process**

Here we don’t talk about it.

  

Drawbacks: Because EntiGraph synthesizes data using a prompted language model, there is a risk that it may hallucinate and fabricate non-existent relations among the entities.