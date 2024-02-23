# LLAMA-2 RAG Pipeline for Career Counseling

This project provides a ready-to-use retrieval-aided generation (RAG) pipeline for building a chatbot to assist students in career counseling. The pipeline utilizes the LLAMA-2 language model and integrates various components for efficient question-answering capabilities.

## Prerequisites

Make sure to install the required dependencies using the following command:

```bash
pip install -qU \
  transformers==4.31.0 \
  sentence-transformers==2.2.2 \
  pinecone-client==2.2.2 \
  datasets==2.14.0 \
  accelerate==0.21.0 \
  einops==0.6.1 \
  langchain==0.0.240 \
  xformers==0.0.20 \
  bitsandbytes==0.41.0

```

## Usage

Ensure the LLAMA-2 model is installed:

```python
from torch import cuda, bfloat16
import transformers
from langchain.embeddings.huggingface import HuggingFaceEmbeddings
from langchain.vectorstores import Pinecone
from langchain.llms import HuggingFacePipeline
from langchain.chains import RetrievalQA

# ... (code for initializing LLAMA-2 model and other dependencies)

```

Create a career counseling response and define career-related words:

```python
career_counseling_response = "I'm here to help with career counseling. Please feel free to ask any career-related questions."

career_counseling_words = [
    # ... (list of career-related words)
]
```

Use the pipeline to answer career-related questions:

```python
question = 'can you guide me in my AI ML studies?'
question_words = question.split()

if any(word in question_words for word in career_counseling_words):
    answers = rag_pipeline(question)
else:
    answers = [career_counseling_response]

print(answers)
```

Feel free to customize the career_counseling_words list with additional keywords related to career counseling.

## Important Note

Ensure that you have the necessary API key for Pinecone and the correct LLAMA-2 model configurations before running the code. Update the code with your specific details where necessary.

Happy career counseling with your chatbot! 🚀
