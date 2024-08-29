# ArabicFatwaRAG

ArabicFatwaRAG is a project that combines web scraping and Retrieval-Augmented Generation (RAG) to process and analyze Arabic fatwas from Islamweb.

## Project Overview

This project consists of two main components:

1. Web Scraping (`scrape_islamweb.ipynb`)
2. RAG Implementation (`rag.ipynb`)

### Web Scraping

The web scraping component is responsible for collecting fatwa data from Islamweb. It includes functions to:

- Retrieve URLs of fatwa pages
- Scrape content from individual fatwa pages
- Save the scraped data to a JSON file

### RAG Implementation

The RAG component uses the scraped data to answer questions about Islamic rulings. It includes:

- Loading and processing the scraped data
- Embedding the text using an Arabic-specific model
- Implementing a question-answering system using the RAG approach

## Requirements

- Python 3.7+
- Libraries: BeautifulSoup, Selenium, ChromeDriver, requests, langchain, transformers, chromadb

## Setup and Usage

1. Install the required libraries:
   ```
   pip install beautifulsoup4 selenium webdriver_manager requests langchain transformers chromadb
   ```

2. Run the web scraping notebook:
   - Open `scrape_islamweb.ipynb`
   - Execute all cells to scrape fatwa data and save it to `scraped_fatwas.json`

3. Run the RAG notebook:
   - Open `rag.ipynb`
   - Execute all cells to set up the RAG system and ask questions

## Key Functions

### Web Scraping

- `get_all_urls(base_url, max_urls=30)`: Retrieves fatwa URLs from Islamweb
- `scrape_page(url)`: Scrapes content from a single fatwa page
- `scrape_fatwa_islamweb(base_url, max_urls=30)`: Orchestrates the scraping process

### RAG

- The RAG implementation uses LangChain components to create a question-answering system
- It uses the "aubmindlab/bert-base-arabertv2" model for text embeddings

## Example Usage

After running both notebooks, you can ask questions in Arabic about Islamic rulings:

```python
question = "حكم العمل في شركة تبيع بزيادة في الثمن المؤجل"
result = qa_chain({"query": question})
print(result["result"])
```

## Note

This project is for educational and research purposes. Always refer to qualified Islamic scholars for authoritative rulings on religious matters.

## Contributing

Contributions to improve the scraping efficiency, RAG implementation, or to add new features are welcome. Please submit a pull request or open an issue to discuss proposed changes.
