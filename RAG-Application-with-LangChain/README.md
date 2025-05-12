# Retrieval-Augmented Generation Application
### Using LangChain and OpenAI

## Introduction
With this Retrieval-Augmented Generation (RAG) application, you can create chatbots for your documents, books, or files. You can also use it to build rich, interactive AI applications that use your data as a source. 
Examples:
1. Ask questions about a large set of documents
2. Create a customer support chatbot that helps customers by following a set of instructions.

### Steps to Build the Application:

1. **Chunk the Data:**
   Break the source documents into smaller segments (typically 500–1000 words) to enable more efficient storage and retrieval. This improves the relevance of retrieved information and enhances the LLM's response accuracy, while also reducing cost by limiting the prompt size to only the most relevant sections.

2. **Generate and Store Embeddings:**
   Convert each text chunk into vector embeddings—numerical representations that capture semantic meaning and relationships—using a language model. Store these embeddings in a **Chroma** vector database for efficient similarity-based retrieval.

3. **Perform Similarity Search:**
   When a user submits a query, use vector similarity search to retrieve the most relevant chunks from the database based on their semantic closeness to the query.

4. **Generate the Response:**
   The retrieved chunks are passed as context to the LLM (e.g., OpenAI model), which then generates a response grounded in the provided information and includes source references where applicable.



## Instructions
### Download the repository
* Go to a terminal and paste `git clone [https://github.com/mlsmall/RAG-Application-with-LangChain.git](https://github.com/Rohith1-p/retrieval-augmented-generation.git)`

### OpenAI API Key
Before you begin, set up an OpenAI account and generate a new key. You will need to put your credentials in a `.env` file.
* Go to https://platform.openai.com/api-keys and create an OpenAI key.
* Create a `.env` file in your project directory and add `OPENAI_API_KEY="your_generated_secret_key"`.
* Create a `.gitignore` file in your project directory and add `.env`.

### Copy your documents (Optional)
* Go to the `data` directory and add your document files in `.md` format.
* Go to the `create_database.py` file and set the variable `DATA_PATH = "data"` or to the directory name where you will store data.
  
### Running the application
Inside a terminal, run the following:
* Install dependencies
`pip install -r requirements.txt`

* Create the Chroma Database
`python create_database.py`

* Query the Chroma Database
`python query_data.py "What operating systems does EC2 support"`
