<h1 align="center">Medical RAG Assistant</h1>

<p align="center">
<b>Retrieval Augmented Generation (RAG) system for answering medical questions using textbook context.</b>
</p>

<hr>

<h2>📌 Project Overview</h2>

<p>
This project implements a <b>Retrieval Augmented Generation (RAG)</b> assistant capable of answering
medical questions using information retrieved from medical textbooks.
</p>

<p>
The system processes medical PDFs, extracts text (including text inside images using OCR),
stores semantic embeddings in a vector database, and retrieves relevant context when a user
asks a question. The retrieved information is then provided to a language model to generate
<b>context-grounded responses</b>.
</p>

<hr>

<h2>🏗 System Architecture</h2>

<table border="1" cellpadding="8">
<tr>
<th>Step</th>
<th>Description</th>
</tr>

<tr>
<td><b>1</b></td>
<td>Medical PDF documents are ingested</td>
</tr>

<tr>
<td><b>2</b></td>
<td>Text is extracted using <b>PyMuPDF</b></td>
</tr>

<tr>
<td><b>3</b></td>
<td>Images inside PDFs are processed using <b>Tesseract OCR</b></td>
</tr>

<tr>
<td><b>4</b></td>
<td>Text is split into chunks using <b>RecursiveCharacterTextSplitter</b></td>
</tr>

<tr>
<td><b>5</b></td>
<td>Embeddings are generated for each chunk</td>
</tr>

<tr>
<td><b>6</b></td>
<td>Embeddings are stored in <b>ChromaDB</b></td>
</tr>

<tr>
<td><b>7</b></td>
<td>User queries trigger similarity-based retrieval</td>
</tr>

<tr>
<td><b>8</b></td>
<td>Relevant context is injected into a prompt</td>
</tr>

<tr>
<td><b>9</b></td>
<td>The LLM generates a grounded response</td>
</tr>

</table>

<hr>

<h2>🔄 RAG Pipeline</h2>

<pre>
User Question
     ↓
Question Normalization
     ↓
Vector Retrieval (ChromaDB)
     ↓
Context Injection
     ↓
Prompt Template
     ↓
LLM Response Generation
     ↓
Context-Grounded Answer
</pre>

<hr>

<h2>✨ Key Features</h2>

<ul>
<li><b>Context-based question answering</b> using medical textbook data</li>
<li><b>OCR support</b> for extracting text from images inside PDFs</li>
<li><b>Semantic search</b> using vector embeddings</li>
<li><b>History-aware questions</b> using conversation context</li>
<li><b>Markdown formatted answers</b> for readable output</li>
</ul>

<hr>

<h2>💬 Example Query</h2>

<pre>
Patient is pregnant with dyspnea.
What cardiovascular changes occur in pregnancy?
</pre>

<h2>📖 Example Output</h2>

<pre>
### Answer

- Increased cardiac output
- Increased blood volume
- Reduced systemic vascular resistance

### Explanation

Pregnancy causes several cardiovascular adaptations to support
the increased metabolic demands of the mother and fetus.
</pre>

<hr>

<h2>📂 Project Structure</h2>

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

<hr>

<h2>⚙️ How to Run</h2>

<pre>
pip install -r requirements.txt
</pre>

<p>
Add your API key to the <b>.env</b> file and run the notebook in Google Colab.
</p>

<hr>

<h2>🧰 Technology Stack</h2>

<table border="1" cellpadding="8">
<tr>
<th>Component</th>
<th>Technology</th>
</tr>

<tr>
<td><b>LLM Framework</b></td>
<td>LangChain</td>
</tr>

<tr>
<td><b>Vector Database</b></td>
<td>ChromaDB</td>
</tr>

<tr>
<td><b>LLM Provider</b></td>
<td>OpenRouter</td>
</tr>

<tr>
<td><b>PDF Processing</b></td>
<td>PyMuPDF</td>
</tr>

<tr>
<td><b>OCR</b></td>
<td>Tesseract</td>
</tr>

<tr>
<td><b>Language</b></td>
<td>Python</td>
</tr>

</table>

<hr>

<p align="center">
<b>End of Project Documentation</b>
</p>
