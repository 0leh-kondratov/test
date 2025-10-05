```mermaid
    graph TD
        A[Google Sheets2] --> B[Split In Batches (Batch Size = 1)]
        B --> C[Split Long Message (добавляет row_number и part)]
        C --> D[Split In Batches (Batch Size = 1)]
        D --> E[Telegram]
        E --> F[Wait 1 s]
        F --> D
        D -->|все части отправлены| G[Next row]
        G --> B
```
