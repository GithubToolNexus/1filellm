
# Repo-Prep for LLM Ingestion

This is a collection of scripts used to download and prepare a GitHub repository or a local folder of code files for ingestion by a language model. The code files are concatenated into a single file, cleaned to remove stopwords and extra whitespaces, and transformed to lowercase to minimize token usage. Additionally, URLs from the text are extracted and saved separately.
All scripts are included when you run onefilerepo.py or they can be run individually.

## Features

- Supports downloading and processing of GitHub repositories or local folders
- Supports various file types, including Jupyter notebooks
- Cleans and preprocesses the text for better language model ingestion
- Extracts and saves all URLs from the text separately

## Scripts

### 1. onefilerepo.py

This script takes a GitHub repository URL or a local folder path as input and processes the files by concatenating them into a single output file. It supports various file types, including Jupyter notebooks.

Usage:
`python onefilerepo.py`

(jim) C:\python\OneFileRepo>onefilerepo.py
[nltk_data] Downloading package stopwords to
[nltk_data]     C:\Users\Jim\AppData\Roaming\nltk_data...
[nltk_data]   Package stopwords is already up-to-date!
Enter GitHub repo URL or local folder path: https://github.com/openai/openai-cookbook
Processing apps/web-crawl-q-and-a/web-qa.ipynb...
C:\Users\Jim\AppData\Local\Programs\Python\Python310\lib\site-packages\nbconvert\filters\strings.py:235: UserWarning: IPython is needed to transform IPython syntax to pure Python. Install ipython if you need this functionality.
  warnings.warn(
Processing examples/Classification_using_embeddings.ipynb...
Processing examples/Clustering.ipynb...
Processing examples/Clustering_for_transaction_classification.ipynb...
Processing examples/Code_search.ipynb...
Processing examples/Customizing_embeddings.ipynb...
Processing examples/Embedding_long_inputs.ipynb...
Processing examples/Entity_extraction_for_long_documents.ipynb...
Processing examples/Fine-tuned_classification.ipynb...
Processing examples/Get_embeddings.ipynb...
Processing examples/How_to_count_tokens_with_tiktoken.ipynb...
Processing examples/How_to_format_inputs_to_ChatGPT_models.ipynb...
Processing examples/How_to_handle_rate_limits.ipynb...
Processing examples/How_to_stream_completions.ipynb...
Processing examples/Multiclass_classification_for_transactions.ipynb...
Processing examples/Obtain_dataset.ipynb...
Processing examples/Question_answering_using_embeddings.ipynb...
Processing examples/Recommendation_using_embeddings.ipynb...
Processing examples/Regression_using_embeddings.ipynb...
Processing examples/Semantic_text_search_using_embeddings.ipynb...
Processing examples/Unit_test_writing_using_a_multi-step_prompt.ipynb...
Processing examples/User_and_product_embeddings.ipynb...
Processing examples/Visualizing_embeddings_in_2D.ipynb...
Processing examples/Visualizing_embeddings_in_3D.ipynb...
Processing examples/Visualizing_embeddings_in_W&B.ipynb...
Processing examples/Zero-shot_classification_with_embeddings.ipynb...
Processing examples/azure/completions.ipynb...
Processing examples/azure/embeddings.ipynb...
Processing examples/azure/finetuning.ipynb...
Processing examples/book_translation/translate_latex_book.ipynb...
Processing examples/dalle/Image_generations_edits_and_variations_with_DALL-E.ipynb...
Processing examples/fine-tuned_qa/olympics-1-collect-data.ipynb...
Processing examples/fine-tuned_qa/olympics-2-create-qa.ipynb...
Processing examples/fine-tuned_qa/olympics-3-train-qa.ipynb...
Processing examples/vector_databases/Using_vector_databases_for_embeddings_search.ipynb...
Processing examples/vector_databases/pinecone/Gen_QA.ipynb...
Processing examples/vector_databases/qdrant/Getting_started_with_Qdrant_and_OpenAI.ipynb...
Processing examples/vector_databases/qdrant/QA_with_Langchain_Qdrant_and_OpenAI.ipynb...
Processing examples/vector_databases/redis/getting-started-with-redis-and-openai.ipynb...
Processing examples/vector_databases/weaviate/getting-started-with-weaviate-and-openai.ipynb...
Processing examples/vector_databases/weaviate/hybrid-search-with-weaviate-and-openai.ipynb...
Processing examples/vector_databases/weaviate/question-answering-with-weaviate-and-openai.ipynb...
All files processed.
The input text file has 70580 tokens.




### 2. clean.py

This script takes an input file, preprocesses the text by removing stopwords, extra whitespaces, and carriage returns, and converts the text to lowercase to minimize token usage.

Usage:
`python clean.py`

### 3. urlextractor.py

This script takes an input file and extracts all URLs from the text, saving them into a separate output file.

Usage:
`python urlextractor.py`

## Getting Started

1. Clone or download the repository.
2. Install the required libraries:

You can install all required libraries in a single line using the following command:

`pip install requests nbformat nbconvert nltk`

Simply run this command in your terminal or command prompt to install the necessary libraries for the scripts.


Obtaining a GitHub Personal Access Token
A GitHub Personal Access Token (PAT) is required to authenticate with the GitHub API and access private repositories. Follow these steps to generate a token:

Log in to your GitHub account and navigate to the Settings page by clicking on your profile picture in the top-right corner and selecting Settings.

In the left sidebar, click on Developer settings.

Click on Personal access tokens in the left sidebar.

Click the Generate new token button.

Enter a descriptive name for the token in the Note field (e.g., "Repo-Prep").

Select the appropriate scopes for the token. For the onefilerepo.py script, the minimum required scope is repo (which grants full control of private repositories). You may need to select additional scopes depending on your use case.

Click the Generate token button at the bottom of the page.

Your new personal access token will be displayed. Copy the token and save it somewhere secure, as you won't be able to see it again. If you lose the token, you'll need to generate a new one.

In the onefilerepo.py script, replace the GITHUB_PERSONAL_TOKEN placeholder with your actual token:

TOKEN = "GITHUB_PERSONAL_TOKEN"
