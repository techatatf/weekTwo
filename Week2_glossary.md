# Week 2 Master Glossary: Managing Your Digital Twin's Working Memory (High School Edition)

Welcome to the **Week 2 Master Glossary**! This comprehensive guide brings together all 40 essential terms, visual metaphors, and code tools from Episodes 6 through 9. It is designed to help high school students master how an AI "Digital Twin" cleans text, manages context limits, understands mathematical meaning, and grounds its answers using Retrieval-Augmented Generation (RAG).

---

## Section 1: Data Preparation & String Surgery (Episode 6)

1. **Digital Twin Working Memory:** The personalized memory system built for an AI assistant using your notes, diary entries, and text logs. *(Metaphor: Giving a genius AI with amnesia a reading habit so it remembers your life).*
2. **String Surgery:** Cleaning, slicing, and organizing messy text data using Python so an AI can process it without errors. *(Metaphor: An operating room where you use scalpels to cut away messy log formatting).*
3. **String Indexing & Slicing (`[start:end]`):** Selecting specific characters in a string by their numerical slot index. *(Metaphor: A train made of numbered carriages where `[0:5]` uncouples the first 5 cars).*
4. **Regular Expressions (Regex / `re.findall`):** Pattern-matching "fingerprints" used to search and extract specific structures like emails or dates. *(Metaphor: A glowing surgical arc that sweeps over text and pulls out matching patterns).*
5. **Raw String Prefix (`r'...'`):** Telling Python to treat backslashes literally so regex patterns aren't misinterpreted. *(Metaphor: Putting caution tape over code strings so Python doesn't alter backslashes).*
6. **Text Normalization (`.strip()`, `.lower()`):** Stripping outer spaces and converting text to lowercase so words match identical meanings. *(Metaphor: Ironing clothes and putting text into school uniforms so `"Running"` and `"running"` look identical).*
7. **Smart Chunking (`smart_chunk()`):** Slicing long text documents into bite-sized word blocks that fit through LLM processing limits. *(Metaphor: Chopping a giant paper scroll so rectangular chunks can parade through a narrow gap in a red LIMIT wall).*
8. **Chunk Overlap (`overlap=20`):** Sharing a repeating buffer of words between adjacent chunks to prevent losing context across boundaries. *(Metaphor: Overlapping roof shingles so no sentence meaning leaks through chunk gaps).*
9. **Metadata Tagging (`add_metadata()`):** Attaching source filename, chunk ID, and word count tags to every chunk. *(Metaphor: Stamping a library call-number sticker on every page torn out of a binder).*
10. **TextProcessor Pipeline:** An all-in-one class that runs cleaning, regex extraction, and chunking in a single call. *(Metaphor: An automated factory conveyor belt moving raw text from `RAW` to `CLEAN` to `CHUNK`).*

---

## Section 2: Memory Limits & Context Management (Episode 7)

11. **Context Window:** The maximum token reading limit an LLM can hold in active memory at one time. *(Metaphor: A rectangular index card reading window placed over a book).*
12. **Token & Tokenization (`count_tokens()`):** Text building blocks (approx. 4 characters or 0.75 words) used by LLMs. *(Metaphor: Colored poker chips or Lego blocks filling up the reading window bucket).*
13. **Token Budget Allocation:** Dividing up the context window limit among different information categories. *(Metaphor: Splitting a monthly allowance into Rent, Food, and Fun envelopes).*
14. **Three-Zone Window Anatomy:** Structuring the context window into System Prompt (top instructions), Conversation History (middle chat log), and Retrieved Context (bottom RAG facts). *(Metaphor: A 3-tiered bento box with separate compartments).*
15. **FIFO Truncation (`truncate_to_limit()`):** Automatically deleting the oldest chat messages first when memory limits are reached. *(Metaphor: A conveyor belt queue where old messages fall off the back into a recycle bin).*
16. **Truncation Guard (`len(messages) > 1`):** A safety loop check preventing the system from deleting the user's last message. *(Metaphor: An emergency stop latch keeping the final document safe in a shredder).*
17. **Sliding Window Algorithm:** Advancing a fixed-size reading window across long text step-by-step with overlap. *(Metaphor: Reading a long scroll with a magnifying glass while keeping part of the previous sentence in view).*
18. **Window Overlap Buffer:** Retaining trailing tokens from a previous window step to maintain reading flow. *(Metaphor: Turning a page while keeping your thumb on the last sentence of the previous page).*
19. **ContextManager Class:** The controller that monitors token counts and balances space between chat logs and RAG chunks. *(Metaphor: A strict bouncer managing how many people fit into a room).*
20. **Token Usage Ratio:** A summary metric showing used tokens, total limit, and available space. *(Metaphor: A smartphone battery level widget).*

---

## Section 3: Mathematical Meaning & Vector Embeddings (Episode 8)

21. **Vector Embedding:** A list of numerical coordinates representing a concept's meaning in multi-dimensional space. *(Metaphor: Giving every concept its own GPS coordinates).*
22. **3D Vector Space:** A mathematical grid where words sit as floating points, and spatial distance equals semantic closeness. *(Metaphor: A floating galaxy of star systems where similar concepts cluster together).*
23. **Word2Vec:** Google's breakthrough algorithm that learns word meanings automatically by analyzing neighbor words in sentences. *(Metaphor: A detective learning what words mean by observing who they hang out with).*
24. **Skip-gram Architecture:** A training method where a model takes a center target word and predicts its surrounding context words. *(Metaphor: Throwing a target dart at a center word and guessing which context darts land around it).*
25. **One-Hot Encoding:** Representing a word as a long list of zeros with a single `1` at its dictionary index. *(Metaphor: A giant light switch board where only switch #4 turns on).*
26. **Embedding Matrix ($W$ Matrix):** The neural network weight matrix whose rows contain the learned word coordinate vectors. *(Metaphor: A golden lookup table matrix labeled `W = embedding table`).*
27. **Cosine Similarity:** A metric that measures the angle theta between two vectors to determine directional closeness, ignoring vector length. *(Metaphor: Two flashlights pointing in a dark room—$0^\circ$ angle = identical meaning).*
28. **Euclidean Distance vs. Cosine Similarity:** Euclidean distance measures tip-to-tip straight lines, whereas Cosine Similarity measures directional angle (ideal for text). *(Metaphor: Two runners heading up the same hill—Euclidean sees distance; Cosine sees identical direction).*
29. **Vector Arithmetic:** Performing addition/subtraction on word coordinates to manipulate meanings ($King - Man + Woman = Queen$). *(Metaphor: Taking 3 steps North and 2 steps East to land on a new concept coordinate).*
30. **Dimensionality Reduction (PCA vs. t-SNE):** Methods for squashing high-dimensional vectors down to 2D for screen plotting. *(Metaphor: PCA casts a flat 2D shadow of a 3D sculpture; t-SNE groups marbles into distinct clusters on a table).*

---

## Section 4: RAG System Architecture & Evaluation (Episode 9)

31. **Retrieval-Augmented Generation (RAG):** Fetching relevant private document chunks and feeding them to an LLM prompt to generate grounded answers. *(Metaphor: Taking an open-book exam with a helpful research assistant).*
32. **Six-Stage RAG Pipeline:** The complete data flow: `LOAD` $\rightarrow$ `SPLIT` $\rightarrow$ `EMBED` $\rightarrow$ `STORE` $\rightarrow$ `RETRIEVE` $\rightarrow$ `GENERATE`. *(Metaphor: An automated 6-box conveyor belt assembly line).*
33. **Document & DocumentLoader:** Universal data structures that ingest text or JSON files and attach source metadata tags. *(Metaphor: A digital document scanner placing files into binders with source labels).*
34. **Vector Store:** A specialized database storing vector embeddings alongside original text chunks and source metadata. *(Metaphor: A futuristic library database cylinder connected to a 3D vector space).*
35. **Flat Index Search:** A search method that calculates cosine similarity against every stored vector in the database. *(Metaphor: A librarian checking every single book on the shelf one by one).*
36. **Nearest-Neighbor Retrieval:** Extracting the top $K$ stored chunks whose vector coordinates sit closest to the user's question vector. *(Metaphor: Dropping an orange query marker into a galaxy and pulling out the 3 closest chunk dots).*
37. **Grounding Prompt Directive:** Explicit prompt instructions commanding the LLM to answer strictly using provided context and cite sources. *(Metaphor: A judge commanding a witness to speak only based on physical exhibit evidence).*
38. **Grounded Answer vs. Hallucination:** A grounded answer is 100% backed by retrieved chunks with citations; an ungrounded hallucination is made up by the LLM. *(Metaphor: Split screen—Left: Vanilla LLM guessing with a red X; Right: Digital Twin stating facts with a citation and green checkmark).*
39. **Faithfulness Evaluation:** An automated check measuring the fraction of key answer words supported by retrieved chunks. *(Metaphor: A digital fact-checker highlighting matching words and awarding a truth score).*
40. **RAGSystem Capstone Class:** The master class combining Loader, Processor, Store, and ContextManager into a complete working system. *(Metaphor: The complete brain engine of your Digital Twin answering `"What did I eat last Tuesday?"` from your personal diary).*

---

## How Week 2 Builds Your Digital Twin's Memory (Master Summary)

```
[ Messy Data ] ──(Ep6 TextProcessor)──> [ Clean Chunks & Metadata ]
                                                │
                                                ▼
[ User Query ] ──(Ep8 EmbeddingModel)─> [ Vector Store (Ep9) ]
                                                │
                                                ▼ (Nearest-Neighbor Cosine Search)
                                        [ Top Retrieved Chunks ]
                                                │
                                                ▼
[ Chat History ] ─(Ep7 ContextManager)─> [ Token Window Budget ]
                                                │
                                                ▼
                                    [ Grounded RAG Answer + Citation ]
```

---

**Master Summary:** Total: 40 terms across 4 episodes | 100% grounded in Week 2 Production Packages | High School Edition
