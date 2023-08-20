# Flipkart_Grid
Approach 1:With locally imported open source LLM model 
Here's an overview of the approach and key components which we have used:
Document Loading:
The code first defines a set of document loaders for various file types (e.g., CSV, PDF, HTML, TXT). These loaders are responsible for extracting text content from different document formats.
Loading and Splitting Documents:
The load_documents function is used to load documents from a specified source directory. It searches for files with supported extensions and uses multiprocessing to load documents concurrently.
Once loaded, the code splits the documents into smaller text chunks using a text splitter. This step is crucial for breaking down large documents into manageable pieces.
Embedding Creation:
The code creates embeddings for each text chunk. It utilizes the Hugging Face Transformers library to create embeddings based on a specified model.
Embeddings are representations of text chunks in a numerical form that capture semantic information.
Chroma Vector Store:
The code uses the Chroma vector store to index and store these embeddings efficiently. Chroma allows for similarity searches, making it useful for retrieving relevant text chunks given a query.
Updating Existing Vector Store:
If an existing vector store is found at the specified location, the code appends new documents to it. This is useful for incremental updates to the document collection.
Persistence:
After creating or updating the vector store, the code persists it to disk. This ensures that the vector store can be reused for future queries without re-embedding the entire document collection.
Main Function:
The main function orchestrates the entire process. It first checks if a vector store already exists. If it does, it appends new documents; otherwise, it creates a new vector store.
The documents are split, embedded, and added to the vector store.
Once the process is complete, the vector store is persisted, and the code provides a message indicating that the ingestion is complete and that users can run queries for finding logs with anomalies in it.
![image](https://github.com/Rishika631/Flipkart_Grid/assets/89201634/05d76257-0289-42ac-953d-fe8d716755ad)

Approach 2:With online AI apps LLM models like stackAI:
Here's an overview of the approach and key components which we have used:
Document uploading:
 Upload the documents like rules.txt and opensshlogs.txt file in the document file upload node.

Providing input prompt:
“Analyze the opensshlogs file while keeping all the rules file content in mind and provide which logs are anomaly and give line number of the log with how to cure that anomaly or what actions to take to prevent that anomaly.” Provide this as input prompt for the input node.

3.Document Q n A node:
 Select the model to be gpt-4 and algorithm to be sequential as it is slower but more accurate.

4.Output:
 Get the output as all the logs which are anomaly with remedies to be taken and what IP address to keep in check.
![image](https://github.com/Rishika631/Flipkart_Grid/assets/89201634/7cf7c247-8460-4124-bbc1-4e40af1f9158)
