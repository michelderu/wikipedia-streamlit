# Wikipedia - What's up in the world? (Front-end)
## Introduction
Wikipedia is and amazing source of information 🧠. With all the real-time additions and updates of articles, it's a valuable source of information about what's happening in the world 🌍. Perhaps even faster than the news 📰. And that's what this project is all about: Accessing the most relevant articles from Wikipedia to answer your questions.

Additionally, this project is a good example of how to build a rock-solid, scalable, and performant enterprise architecture 🚀. It makes use of the following technologies:
- [Astra Streaming](https://www.datastax.com/products/datastax-astra-streaming): A fully managed Pulsar as a service.
- [Astra DB](https://www.datastax.com/products/datastax-astra-db): A fully managed Cassandra DB as a service.
- [Streamlit](https://streamlit.io/): A Python library for building prototype web apps.

Notable concepts used in this project are:
- [Pulsar Functions](https://pulsar.apache.org/docs/functions-overview/): Enriching the data and JSON structure of the Wikipedia articles.
- [Instructor](https://github.com/jxnl/instructor): Generate structured outputs powered by LLMs to enrich the Wikipedia articles.
- [Astra Vector DB](https://docs.datastax.com/en/astra-db-serverless/get-started/concepts.html): A [Forrester Wave Leader](https://www.datastax.com/blog/forrester-wave-names-datastax-leader-vector-databases) in the Vector Database category.
- [Astra Vectorize](https://docs.datastax.com/en/astra-db-serverless/databases/embedding-generation.html): Auto-generate embeddings with vectorize.

![Application Interface](./assets/screenshot.png)

## The architecture
This application is a front-end for the Wikipedia - What's up in the world? project. It consists of two parts:
1. A Pulsar Streaming project that consists of the following components:
    - A Pulsar producer that produces the Wikipedia articles to a Pulsar topic.
    - A Pulsar function that enriches the Wikipedia articles with and OpenAI LLM.
    - A Pulsar sink that stores the enriched Wikipedia articles in an Astra DB collection.
2. A Streamlit application that allows you to search the Wikipedia articles and chat with the articles.

![Architecture](./assets/architecture.png)

## How to run the application
### Install the dependencies
```bash
pip install -r requirements.txt
```

### Run the application
Be sure to have the back-end producing some articles before running the front-end.
```bash
streamlit run app.py
```