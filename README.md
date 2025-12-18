# readme.md
flowchart TD
    A[Start Q1] --> B[Identify Data Sources]
    
    B --> B1[FERC License eLibrary\n(PDFs, filings, exhibits)]
    B --> B2[Hydrosource Website\n(Datasets, reports, metadata)]
    
    B1 --> C[Automated Data Ingestion]
    B2 --> C
    
    C --> D[Document Cleaning & Normalization]
    D --> D1[OCR for Scanned PDFs]
    D --> D2[Remove headers, footers, tables noise]
    D --> D3[Standardize units, dates, citations]
    
    D --> E[Document Chunking]
    E --> E1[Chunk by section / license / topic]
    E --> E2[Preserve metadata\n(Project ID, River, State, License No.)]
    
    E --> F[Embedding Generation]
    F --> F1[HuggingFace Embedding Models\n(e.g., sentence-transformers)]
    
    F --> G[Vector Store Creation]
    G --> G1[FAISS / Chroma / Weaviate]
    G --> G2[Store embeddings + metadata]
    
    G --> H[Validation Checks]
    H --> H1[Coverage completeness]
    H --> H2[Chunk retrievability tests]
    
    H --> I[Q1 Deliverable:\nHydropower Vector Store]
