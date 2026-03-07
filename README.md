<h1>Medical RAG Assistant</h1>

<h2>Project Overview</h2>

<p>
This project implements an enterprise-style Retrieval Augmented Generation (RAG)
assistant capable of answering medical questions using information retrieved from
medical textbooks.
</p>

<p>
The assistant processes medical PDFs, builds a vector database using embeddings,
and retrieves relevant context to generate grounded answers using an LLM.
</p>

<h2>System Architecture</h2>

<ol>
<li>Medical PDFs are ingested</li>
<li>Text is extracted using PyMuPDF</li>
<li>Images are processed using OCR</li>
<li>Text is chunked using RecursiveCharacterTextSplitter</li>
<li>Embeddings are generated</li>
<li>Chunks are stored in ChromaDB</li>
<li>User questions trigger retrieval</li>
<li>Context is injected into a prompt</li>
<li>LLM generates a grounded answer</li>
</ol>

<h2>RAG Pipeline</h2>

<pre>
User Question
↓
Question Normalization
↓
Retriever (Chroma Vector DB)
↓
Context Injection
↓
Prompt Template
↓
LLM
↓
Grounded Answer
</pre>

<h2>Key Features</h2>

<ul>
<li>History-aware retrieval</li>
<li>OCR support for images inside PDFs</li>
<li>Structured markdown answers</li>
<li>Context grounded responses</li>
<li>Enterprise-style RAG architecture</li>
</ul>

<h2>Example Query</h2>

<pre>
Patient is pregnant with dyspnea.
What cardiovascular changes occur in pregnancy?
</pre>

<h2>Example Output</h2>

<pre>
### Answer

- Increased cardiac output
- Increased blood volume
- Reduced systemic vascular resistance

### Explanation

Pregnancy causes several cardiovascular adaptations to support
the increased metabolic demands of the mother and fetus.
</pre>

<h2>Project Structure</h2>

<pre>
medical-rag-assistant
│
├── notebooks
│   └── medical_rag_assistant.ipynb
│
├── data
│   └── bates.pdf
│
├── requirements.txt
├── README.html
└── .env.example
</pre>

<h2>How to Run</h2>

<pre>
pip install -r requirements.txt
</pre>

<p>
Add your API key to the .env file and run the notebook.
</p>

<h2>Technology Stack</h2>

<ul>
<li>LangChain</li>
<li>ChromaDB</li>
<li>OpenRouter LLM</li>
<li>PyMuPDF</li>
<li>Tesseract OCR</li>
<li>Python</li>
</ul>
