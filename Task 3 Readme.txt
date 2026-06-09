Project Overview
Objective of the task
The primary objective of this task was to build a context-aware conversational chatbot capable of retrieving external information from a custom knowledge base during conversations. The chatbot needed to maintain conversational history and provide responses grounded in the provided data, reducing reliance on the LLM's pre-trained knowledge alone. The final goal was to deploy this chatbot with a user-friendly interface using Streamlit.

Methodology / Approach
Our approach involved using the LangChain framework to orchestrate the various components required for a Retrieval-Augmented Generation (RAG) system. The key steps included:

Environment Setup: Installed necessary libraries such as langchain, sentence-transformers, faiss-cpu, google-generativeai, and streamlit.
Data Ingestion: Loaded the custom corpus from specified webpages (urls) using WebBaseLoader.
Data Preprocessing: Split the loaded documents into smaller, manageable chunks using RecursiveCharacterTextSplitter to optimize retrieval.
Vector Store Creation: Generated embeddings for each text chunk using HuggingFaceEmbeddings and stored them in a FAISS vector store for efficient semantic search.
LLM Integration: Initialized a ChatGoogleGenerativeAI model to serve as the core language model for generating responses.
Retriever Configuration: Created a retriever from the FAISS vector store to fetch relevant document chunks based on user queries.
Conversational Memory: Implemented ConversationBufferMemory to store and manage the history of the conversation, enabling context-aware interactions.
RAG Chain Construction: Assembled all components (LLM, retriever, memory) into a ConversationalRetrievalChain to process user input, retrieve information, and generate contextually relevant answers.
Deployment: Developed a Streamlit application (app.py) that encapsulated the chatbot logic and provided an interactive chat interface. The application was then exposed publicly using ngrok for external access.
Key results or observations
Successful RAG Implementation: The RAG architecture effectively allowed the chatbot to retrieve specific information from the provided web pages, demonstrating its ability to answer questions accurately within the defined knowledge domain.
Contextual Understanding: The integration of ConversationBufferMemory significantly improved the chatbot's ability to maintain context across turns, leading to more natural and coherent conversations.
Modular Development with LangChain: LangChain proved to be highly effective for building complex LLM applications in a modular fashion, making it easy to swap components or add new functionalities.
Efficient Deployment: Streamlit enabled rapid development and deployment of a functional web interface, making the chatbot accessible for testing and demonstration with minimal effort.
Scalability Potential: The use of a vector store like FAISS allows for scalable retrieval from large corpuses, while the choice of gemini-pro provides a powerful generative model.