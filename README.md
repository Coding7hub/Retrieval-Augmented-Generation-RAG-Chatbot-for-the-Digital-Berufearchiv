# RAG Chatbot for the Berufearchiv

## Project Overview

This project develops a Retrieval-Augmented Generation (RAG) chatbot for the Drupal-based Islandora Berufearchiv at the University of Koblenz. Its primary objective is to make historical vocational training regulations and archival documents easier to access through natural-language queries.

Instead of manually browsing large collections of archival documents, researchers can ask questions through an integrated chatbot interface and receive answers based on relevant information retrieved from the archive, together with source references.

## Key Features

- **Drupal and Islandora Integration:** Custom Drupal module connecting the existing archival platform with the external RAG backend.
- **Chatbot Interface:** Allows researchers to submit natural-language questions through the archive website.
- **Automated Document Ingestion:** Forwards newly uploaded archival documents to the RAG ingestion service.
- **Background Processing:** Uses Drupal queues and Cron for background document ingestion.
- **Event-Driven Integration:** Uses Node-RED and ActiveMQ for an additional document-ingestion workflow.
- **PDF Processing:** Extracts text from archival PDF documents using PyMuPDF.
- **Structure-Aware Chunking:** Divides documents into meaningful sections and passages.
- **Hybrid Retrieval:** Combines semantic and keyword-based retrieval.
- **Vector Database:** Uses Qdrant to store document chunks and their vector representations.
- **Source References:** Provides references to retrieved archival content in chatbot responses.

## Technology Stack

| Component | Technologies |
|---|---|
| Archival platform | Drupal, Islandora |
| Backend integration | PHP, Drupal APIs |
| Frontend | JavaScript, Twig, CSS |
| API communication | REST API, HTTP, JSON |
| Document orchestration | Drupal Queue, Cron, Node-RED, ActiveMQ |
| PDF extraction | PyMuPDF |
| Embeddings | BAAI/bge-m3 |
| Sparse retrieval | BM25 |
| Vector database | Qdrant |
| AI architecture | Retrieval-Augmented Generation (RAG) |
| Development environment | Docker, ISLE-DC |

## System Workflow

1. Archivists upload documents to the Islandora repository.
2. The Drupal integration or event-driven ingestion workflow forwards documents to the external ingestion API.
3. The backend extracts text and divides documents into meaningful chunks.
4. Dense and sparse representations are generated.
5. Processed chunks and metadata are stored in Qdrant.
6. Researchers submit questions through the Drupal chatbot.
7. The RAG backend retrieves relevant archival passages and generates an answer using the retrieved context.
8. The chatbot displays the response together with source references.

## Project Objective

The project aims to improve access to historical archival information by combining digital document management with modern retrieval and language-model technologies. It provides a natural-language interface while maintaining a connection to the original archival sources.
