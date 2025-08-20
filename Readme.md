```mermaid
flowchart TD
    A[User asks a question] --> B[Genie receives input]
    B --> C[Genie generates SQL or structured answer]
    C --> D[Genie sends output package to Second Assistant]
    D --> E[Second Assistant validates or interprets Genie's output]
    E --> F[Second Assistant analyzes results and adds explanation]
    F --> G[Final enriched response streamed back to user]

