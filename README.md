# multimodal-pdf-rag

Multimodal PDF RAG  A multimodal Retrieval-Augmented Generation (RAG) system that enables intelligent question answering over PDF documents by analyzing both textual and visual content. The system extracts text and images from PDFs, retrieves relevant context using semantic search, and generates answers using a Vision-Language Model.

# Overview

Traditional PDF chat systems are limited to text-only retrieval and often ignore valuable information contained in charts, diagrams, figures, and images.

This project addresses that limitation by combining:

    Text Retrieval using BGE embeddings
    Image Retrieval using CLIP embeddings
    Vector Search using FAISS
    Multimodal Reasoning using Qwen2.5-VL
    PDF Processing with PyMuPDF

The result is a multimodal document assistant capable of understanding both text and visual information within PDF documents.

# Features
    Upload and analyze PDF documents
    Extract text and embedded images
    Automatic text chunking
    Semantic text retrieval
    Semantic image retrieval
    Multimodal question answering
    Support for charts, figures, diagrams, and visual elements
    Local inference using open-source models
    No OpenAI API required
    Modular architecture for future extensions

# System Architecture

PDF Document
      │
      ▼
┌─────────────────┐
│ PDF Processing  │
│ (PyMuPDF)       │
└─────────────────┘
      │
      ├───────────── Text Extraction
      │
      └───────────── Image Extraction    
                      │
                      ▼
                CLIP Embeddings              
                      │
                      ▼
                 Image FAISS                 
                      │
                      ▼
User Query ─────────► CLIP Text Encoder
      │
      ▼
 BGE Embeddings
      │
      ▼
 Text FAISS
      │
      ▼
Retrieved Text + Images
      │
      ▼
Qwen2.5-VL
      │
      ▼
Generated Answer


# Tech Stack
    # Document Processing
        PyMuPDF
        Pillow
    
    # Text Embeddings
        BAAI/bge-large-en-v1.5   ------> Used for semantic text retrieval.

    # Image Embeddings
        openai/clip-vit-base-patch32 ------> Used for image retrieval.

    # Vector Database
        FAISS  ------> Used for efficient similarity search.

    # Vision-Language Model
        Qwen/Qwen2.5-VL-3B-Instruct  ------> Used for multimodal reasoning and answer generation.

    # Frameworks
        Transformers
        LangChain
        Sentence Transformers
        PyTorch


