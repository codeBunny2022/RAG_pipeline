# RAG_pipeline
RAG_pipeline


## Workflow

- **Resume Upload:** Front-end sends resumes to the ingestion microservice.
<br><br>
- **Preprocessing:** Ingestion service parses the resume and passes it to the preprocessing microservice.
<br><br>
- **Clustering & Categorization:** Preprocessing results are clustered and categorized based on resume content.
<br><br>
- **RAG Matching:** A job description is uploaded, and the RAG service retrieves relevant resumes from the vector store.
<br><br>
- **Grading & Ranking:** Scores are computed for each resume based on the job description and predefined criteria.
<br><br>

- **Reporting:** The top resumes are ranked, and a report is generated.
<br><br>
- **Search:** Users can search or filter resumes through the search microservice.

<br><br>
## Major overview of skeleton

```
resume-processing-pipeline/
│
├── app/
├── config/
├── docs/
├── lib/
├── tests/
├── scripts/
├── .env
├── .gitignore
├── Dockerfile
├── requirements.txt / pom.xml (for Maven projects)
├── README.md
└── setup.py / build.gradle (for Gradle)

````

## Sub-Structure of project
```
app/
├── ingestion_service/
│   ├── __init__.py
│   ├── ingestion.py
│   ├── resume_upload.py  # Handles file upload and storage
│   ├── routes.py  # API endpoints for ingestion service
│   └── utils.py  # Helper functions
│
├── preprocessing_service/
│   ├── __init__.py
│   ├── preprocessing.py  # Resume parsing and text processing logic
│   ├── resume_parser.py  # Modules for PDF/Docx parsing
│   ├── routes.py  # API endpoints for the preprocessing service
│   └── utils.py  # Helper functions
│
├── clustering_service/
│   ├── __init__.py
│   ├── clustering.py  # Resume clustering and categorization logic
│   └── routes.py  # API endpoints for clustering service
│
├── rag_service/
│   ├── __init__.py
│   ├── rag_pipeline.py  # Handles retrieval-augmented generation matching
│   ├── vector_store.py  # Logic to interact with vector database
│   └── routes.py  # API endpoints for RAG matching
│
├── grading_service/
│   ├── __init__.py
│   ├── grading.py  # Logic for grading and ranking resumes
│   └── routes.py  # API endpoints for grading service
│
├── reporting_service/
│   ├── __init__.py
│   ├── reporting.py  # Logic for report generation
│   └── routes.py  # API endpoints for reporting
│
├── search_service/
│   ├── __init__.py
│   ├── search.py  # Implements search/filter logic
│   └── routes.py  # API endpoints for search functionality
│
└── common/
    ├── __init__.py
    ├── models.py  # Shared data models (e.g., Resume, JobDescription)
    └── utils.py  # Common utility functions
```


<br><br>

