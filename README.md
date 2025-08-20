```mermaid
flowchart TD
    %% User
    A[User] -->|Types Message| B[Chat UI (Streamlit in Databricks App)]

    %% UI Sends
    B -->|Send prompt + streaming request| C[Routing Logic (app.py)]

    %% Routing
    C -->|General Chat| D[Genie Endpoint]
    C -->|Complex Task| E[Supervisor Endpoint]

    %% Supervisor calls
    E --> F1[Knowledge Agent]
    E --> F2[SQL Agent]
    E --> F3[Tool Agent]
    E --> F4[Other Agents]

    %% Streaming Path
    D --> G1[Chunked Tokens Streamed Back]
    F1 --> G1
    F2 --> G1
    F3 --> G1
    F4 --> G1

    %% UI Updates
    G1 --> H[Chat UI Streaming Handler]
    H -->|Incrementally render tokens| I[User Sees Response Building]

    %% Fallback
    D -.-> G2[Fallback: Full Response (Non-streaming)]
    E -.-> G2
    G2 --> H
