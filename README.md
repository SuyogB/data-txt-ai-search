data-txt-ai-search
This repository contains a Jupyter Notebook that implements a vector-based retrieval system using a manually loaded .txt file (data.txt). The project leverages OpenAI embeddings and FAISS for querying data stored in the text file. This system allows you to ask specific questions about the data and retrieve relevant information using OpenAI’s language model.

Features
Manual Data Ingestion: The website data is manually copied into a data.txt file.
Text Chunking: The text data is split into smaller chunks to optimize embeddings creation using the RecursiveCharacterTextSplitter.
Embeddings with OpenAI: Uses OpenAIEmbeddings to convert text chunks into vector embeddings.
Vector Store (FAISS): A FAISS index is used to store and retrieve vector embeddings, allowing fast similarity searches.
Question Answering: Queries are answered using the FAISS index and OpenAI’s language model (RetrievalQA).
Installation
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/data-txt-ai-search.git
cd data-txt-ai-search
2. Install the Requirements
A requirements.txt file is provided for easy installation. Run the following command to install the necessary packages:

bash
Copy
Edit
pip install -r requirements.txt
3. Environment Setup
Create a .env file in the root directory of your project and add your OpenAI API key:

ini
Copy
Edit
OPENAI_API_KEY=your_openai_api_key
Make sure to replace your_openai_api_key with your actual OpenAI API key.

Required Dependencies
Here is the optimized requirements.txt that includes only the necessary packages:

plaintext
Copy
Edit
langchain-openai
langchain
faiss-cpu
python-dotenv
Usage
1. Data Ingestion
data.txt: The data.txt file contains the text from which embeddings will be created. This file should be located in the same directory as the notebook.
2. Running the Notebook
Open the rag.ipynb Jupyter notebook and run the cells in order. The notebook is structured as follows:
Loading the data.txt file.
Splitting the text into smaller chunks for embedding creation.
Creating FAISS embeddings and saving the index locally.
Querying the data using OpenAI’s language model via similarity search.
3. Querying the Data
After setting up the FAISS vector store, you can ask specific questions regarding the content of data.txt. You can use the sample questions provided in the questions.txt file to verify the system's accuracy.
Example Queries
python
Copy
Edit
retriever_query1 = "What is India's projected GDP growth for the fiscal year 2024-2025?"
results = qa.invoke(retriever_query1)
print(results)
You can also modify the queries or add your own, based on the content in data.txt.

Files
rag.ipynb: The main notebook implementing the retrieval system.
data.txt: The file containing the manually copied website data (to be queried).
questions.txt: A sample set of 10 questions and answers used for testing.
.env: Your .env file to store your OpenAI API key (this file needs to be created).
