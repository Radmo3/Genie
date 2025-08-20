```mermaid
flowchart TD
    A[User] --> B[Chat UI: Streamlit in Databricks App]
    B --> C[Routing Logic: app.py]

    C --> D[Genie Endpoint for General Chat]
    C --> E[Supervisor Endpoint for Complex Tasks]

    E --> F1[Knowledge Agent]
    E --> F2[SQL Agent]
    E --> F3[Tool Agent]
    E --> F4[Other Agents]

    D --> G1[Streamed Tokens Back]
    F1 --> G1
    F2 --> G1
    F3 --> G1
    F4 --> G1

    G1 --> H[Chat UI Streaming Handler]
    H --> I[User Sees Response Building]

    D -.-> G2[Fallback Full Response Non Streaming]
    E -.-> G2
    G2 --> H
