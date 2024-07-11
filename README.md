## LLM Chatbot with RAG Assistance
![image](https://github.com/ajayjdv/LLM-chatbot-RAG-assistance/assets/169338278/474d9a82-0e7c-4d72-a7a2-d91d79290763)
![image](https://github.com/ajayjdv/LLM-chatbot-RAG-assistance/assets/169338278/5be8e46c-4ce4-49ad-a2e6-b43b2da63966)
![image](https://github.com/ajayjdv/LLM-chatbot-RAG-assistance/assets/169338278/2f767116-c100-4e50-8f0c-c5232cabc6d4)
![image](https://github.com/ajayjdv/LLM-chatbot-RAG-assistance/assets/169338278/ff557e5a-449c-41d9-bd06-0da8f06c91cd)

### Introduction
This project demonstrates how to build a local open-source LLM chatbot using Retrieval-Augmented Generation (RAG) to enhance the capabilities of a Large Language Model (LLM). By integrating Google’s Gemma-2b-it model with Hugging Face transformers, LangChain, and the Faiss vector database, the chatbot can answer specific questions with the aid of uploaded PDF documents.

Table of Contents
- [Introduction](introduction)
- [Features](features)
- [Installation](installation)
- [Usage](usage)
- [Architecture and Components](architecture-and-components)
- [Configuration](configuration)
- [Contributing](contributing)

Features
- Utilize Google’s Gemma-2b-it LLM model.
- Incorporate RAG to provide specific and contextually accurate answers.
- Upload PDF documents as a knowledge base.
- Efficient similarity search using Faiss vector database.
- Interactive user interface built with Streamlit.

Installation
Prerequisites
- Python 3.8 or higher
- CUDA-enabled GPU (for model inference with quantization)

Clone the Repository
```bash
git clone https://github.com/ajayjdv/LLM-chatbot-RAG-assistance.git
cd LLM-chatbot-RAG-assistance
```

Install Dependencies
```bash
pip install -r requirements.txt
```

Set Up Environment Variables
Create a `.env` file and add your Hugging Face access token:
```env
ACCESS_TOKEN=your_hugging_face_access_token
```

Usage
Start the Streamlit Application
```bash
streamlit run app.py
```

Interact with the Chatbot
1. Open the Streamlit application in your web browser.
2. Upload PDF documents via the sidebar to use as context.
3. Enter your question in the chat input field and receive responses from the chatbot.

Architecture and Components
RAG Pipeline
1. Document Storage:
   - Input documents -> text chunks -> encoder model -> vector database.
2. LLM Prompting:
   - User question -> encoder model -> vector database -> top-k relevant chunks -> generator LLM model.

Components
- Generator Component: Uses the Gemma-2b-it model to generate answers.
- Retriever Component: Employs the `all-MiniLM-L12-v2` encoder model to retrieve relevant document chunks.
- Document Loader: Loads PDF documents and splits them into manageable chunks.
- Vector Database: Stores encoded document chunks and facilitates similarity search using Faiss.

Configuration
Modify Parameters
You can adjust parameters such as `max_new_tokens` and the number of top-k similar chunks (`k`) via the Streamlit sidebar.

Contributing
Contributions are welcome! Please fork this repository and submit pull requests to contribute.

Steps to Contribute
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-name`.
3. Make your changes and commit them: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin feature-name`.
5. Submit a pull request.


