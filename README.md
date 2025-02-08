# PDF-Based Question Answering Chatbot

This project implements a chatbot that answers questions based on the content of a given PDF document. The system leverages NLP models for extracting text, embedding text, retrieving relevant content, and answering user queries efficiently. It uses tools such as FAISS for similarity search and Gradio for creating a user-friendly interface.

---

## Features

- PDF Text Extraction: Extracts text content from PDF files.
- Text Chunking: Splits the extracted text into manageable chunks for faster processing.
- Sentence Embedding: Converts chunks into dense embeddings using `SentenceTransformer`.
- FAISS Indexing: Builds an efficient FAISS index for fast similarity search.
- Question Answering: Uses a pre-trained RoBERTa-based model for extracting answers from relevant chunks.
- Interactive Interface: A simple and intuitive chatbot built with Gradio.

---

## Requirements

To use this project, ensure you have the following libraries installed:

- `transformers`
- `torch`
- `sentencepiece`
- `PyPDF2`
- `sentence-transformers`
- `faiss-cpu`
- `gradio`

You can install these dependencies with the following command:
```bash
pip install transformers torch sentencepiece PyPDF2 sentence-transformers faiss-cpu gradio
```




---

## How It Works

1. **Extract Text from PDF**: The `extract_text_from_pdf` function reads and extracts text from the provided PDF file.
2. **Text Chunking**: The extracted text is split into smaller chunks using the `split_text_into_chunks` function to speed up processing.
3. **FAISS Indexing**: The embeddings of text chunks are calculated using `SentenceTransformer` and stored in a FAISS index for efficient retrieval.
4. **Question Answering**: When a question is asked, relevant text chunks are retrieved using FAISS. The pre-trained RoBERTa model then provides an answer based on these chunks.
5. **Gradio Interface**: The chatbot is deployed as a Gradio app, providing a clean and simple interface for user interaction.

---

## Usage

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone <repository-url>
```

### 2. Run the Code
Ensure all required dependencies are installed. Then, run the code:
```bash
python chatbot.py
```

### 3. Upload Your PDF
Replace the `pdf_path` variable with the path to your desired PDF file. For example:
```python
pdf_path = "path/to/your/pdf/document.pdf"
```

### 4. Interact with the Chatbot
Once the app launches, you can enter questions in the Gradio interface. The chatbot will respond with answers extracted from the PDF content.

---


## Technologies Used

- **Natural Language Processing**:
  - Sentence Embeddings: `SentenceTransformer ("all-MiniLM-L6-v2")`
  - Question Answering: `transformers` RoBERTa-based model
- **Similarity Search**: `FAISS`
- **PDF Handling**: `PyPDF2`
- **Frontend Interface**: `Gradio`

---

## Example Workflow

1. **Upload PDF**: A PDF is uploaded to the system, and text is extracted.
2. **Ask a Question**: The user types a question in the Gradio interface.
3. **Answer Generation**:
   - Text chunks are retrieved from the FAISS index based on the question.
   - The QA model provides an answer by processing the retrieved text.

---



## Acknowledgments

This project utilizes:
- [Hugging Face Transformers](https://huggingface.co/transformers)
- [FAISS](https://github.com/facebookresearch/faiss)
- [Gradio](https://gradio.app/)


