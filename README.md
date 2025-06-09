# PDF Semantic Search and Q&A with LLM Integration

This project provides an end-to-end pipeline for extracting text from PDF files, semantically chunking and embedding the content, and enabling natural language question-answering using a Large Language Model (LLM). The implementation leverages [PyMuPDF](https://pymupdf.readthedocs.io/) for PDF parsing, [FAISS](https://github.com/facebookresearch/faiss) for vector similarity search, [Sentence Transformers](https://www.sbert.net/) for creating embeddings, and the [Groq API](https://console.groq.com/docs/quickstart) for LLM-powered answers.

## Features

- **PDF Upload & Text Extraction:** Upload a PDF and automatically extract its full text content.
- **Semantic Chunking:** Split the text into manageable, semantically meaningful chunks.
- **State-of-the-Art Embedding:** Use the `all-MiniLM-L6-v2` model to encode text chunks into embeddings.
- **FAISS Vector Search:** Efficiently find the most relevant chunks in response to user queries.
- **LLM-Powered Q&A:** Send the retrieved context and user question to a Groq-hosted LLM for a detailed, contextual answer.

## Requirements

- Python 3.7+
- Google Colab (for interactive notebook and file upload)
- Libraries:
  - `pymupdf`
  - `faiss-cpu`
  - `sentence-transformers`
  - `requests`
  - `groq` (Groq API client)

## Setup

1. **Clone the repository:**
    ```bash
    git clone https://github.com/Mitha-20-07/project_1.git
    cd project_1
    ```

2. **Install dependencies:**
    - If running in Colab, these will be installed automatically.
    - If running locally, install with:
      ```bash
      pip install pymupdf faiss-cpu sentence-transformers requests
      ```

3. **Configure Groq API:**
    - Obtain your [Groq API key](https://console.groq.com/).
    - Replace the placeholder in `GROQ_API_KEY = " "` with your actual key.

## Usage

1. **Upload a PDF file:**  
   When prompted, upload the desired PDF document (e.g., `Abstract ID FIBT306.pdf`).

2. **Ask a question:**  
   Enter your question in the prompt. The app will:
   - Search for the most relevant text chunks using semantic similarity.
   - Combine the context with your question.
   - Generate a detailed answer using the LLM via Groq API.

3. **View the answer:**  
   The answer will be printed in the output.

## Example

```
Enter your question: What is the main objective of the research in the PDF?
Answer: [LLM-generated detailed answer based on PDF content]
```

## Notes

- The default embedding model is `all-MiniLM-L6-v2`, which provides good performance for semantic retrieval tasks.
- The number of chunks and retrieval depth can be adjusted in the code (`words_per_chunk`, `top_k`).
- Currently, the Groq API key is hardcoded; for production use, consider using environment variables for security.

## License

This project is provided for educational purposes and does not include any warranty.  
Refer to the source repository for licensing details.
