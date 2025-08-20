```mermaid
flowchart TD
    %% User Layer
    A[1. User asks a question] --> B[2. Genie receives input]

    %% Genie Layer
    B --> C[3. Genie generates SQL or structured answer]

    %% Handoff Layer
    C --> D[4. Genie sends output package to Second Assistant]

    %% Second Assistant Layer
    D --> E[5. Second Assistant validates or interprets Genie's output]
    E --> F[6. Second Assistant analyzes results and adds explanation]

    %% Response Layer
    F --> G[7. Final enriched response streamed back to user]
