# Flipkart_Grid
Video demo link: https://drive.google.com/file/d/1vxYlYPKVpHAiLS1gBDJWlqMky2tUfAJV/view?usp=sharing
## Approach 1:With locally imported open source LLM model 
Here's an overview of the approach and key components which we have used:

1.Document Loading:
The code first defines a set of document loaders for various file types (e.g., CSV, PDF, HTML, TXT). These loaders are responsible for extracting text content from different document formats.

2.Loading and Splitting Documents:
The load_documents function is used to load documents from a specified source directory. It searches for files with supported extensions and uses multiprocessing to load documents concurrently.
Once loaded, the code splits the documents into smaller text chunks using a text splitter. This step is crucial for breaking down large documents into manageable pieces.

3.Embedding Creation:
The code creates embeddings for each text chunk. It utilizes the Hugging Face Transformers library to create embeddings based on a specified model.
Embeddings are representations of text chunks in a numerical form that capture semantic information.

4.Chroma Vector Store:
The code uses the Chroma vector store to index and store these embeddings efficiently. Chroma allows for similarity searches, making it useful for retrieving relevant text chunks given a query.

5.Updating Existing Vector Store:
If an existing vector store is found at the specified location, the code appends new documents to it. This is useful for incremental updates to the document collection.

6.Persistence:
After creating or updating the vector store, the code persists it to disk. This ensures that the vector store can be reused for future queries without re-embedding the entire document collection.

7.Main Function:
The main function orchestrates the entire process. It first checks if a vector store already exists. If it does, it appends new documents; otherwise, it creates a new vector store.
The documents are split, embedded, and added to the vector store.
Once the process is complete, the vector store is persisted, and the code provides a message indicating that the ingestion is complete and that users can run queries for finding logs with anomalies in it.

![image](https://github.com/Rishika631/Flipkart_Grid/assets/89201634/3687179d-dc89-4525-acf0-7cf27af0c268)


## Approach 2:With online AI apps LLM models like stackAI:
Here's an overview of the approach and key components which we have used:

1.Document uploading:
 Upload the documents like rules.txt and opensshlogs.txt file in the document file upload node.

2.Providing input prompt:
“Analyze the opensshlogs file while keeping all the rules file content in mind and provide which logs are anomaly and give line number of the log with how to cure that anomaly or what actions to take to prevent that anomaly.” Provide this as input prompt for the input node.

3.Document Q n A node:
 Select the model to be gpt-4 and algorithm to be sequential as it is slower but more accurate.

4.Output:
 Get the output as all the logs which are anomaly with remedies to be taken and what IP address to keep in check.

![image](https://github.com/Rishika631/Flipkart_Grid/assets/89201634/9b08c370-6c8d-45e9-b6db-e07372f52f85)

