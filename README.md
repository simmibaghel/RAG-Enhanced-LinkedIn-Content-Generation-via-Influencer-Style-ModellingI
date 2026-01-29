# RAG-Enhanced LinkedIn Content Generation via Influencer Style Modelling

AI Post Genius is a professional Retrieval-Augmented Generation (RAG) tool designed to generate style-consistent LinkedIn content. Unlike generic AI writers, this tool analyzes an influencer's past posting history (Style DNA) to ensure every generated post matches their unique voice, tone, and structure.

The project operates in two distinct phases:
1. Preprocessing & IndexingCleaning: Uses surrogateescape encoding to handle malformed Unicode/emojis.
2. Vectorization: Converts posts into high-dimensional vectors using all-MiniLM-L6-v2.Storage: Metadata and vectors are stored in ChromaDB for sub-second retrieval.
3.  Real-Time GenerationRetrieval: Finds the top $K$ most semantically similar posts to your input topic.
4.   Augmentation: Injects these style examples into the LLM prompt.Generation: Llama 4 generates a new post that mimics the retrieved structure and tone.

Prerequisites:
Python 3.10 or higher
A Groq API Key (for Llama 4 access)

Installation:

1.Clone the repository:
git clone https://github.com/yourusername/ai-post-genius.gitcd ai-post-genius

2.Install dependencies:
pip install -r requirements.txt

3.Set up environment variables: Create a .env file in the root directory:
GROQ_API_KEY=your_api_key_here

Usage:

1.Prepare your data: Place your raw posts in data/raw_posts.json (JSONL format).

2.Build the Index:
python code/preprocess.py

3.Launch the Website:
streamlit run main.py

The website hosted using streamlit with interactive panels and options:


<img width="1920" height="1034" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/3f438945-2101-4a6c-8b6f-b911da68d764" />



