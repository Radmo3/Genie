```mermaid
flowchart TD
    U[Manager: Asks KPI Question in plain English] --> A[Chat UI in Databricks App: Simple interface for asking questions]
    A --> B[Routing Logic: Decides which assistant should handle the request]
    B --> C[Genie Text-to-SQL: Translates English into SQL query]
    C --> D[Databricks SQL Warehouse: Runs query securely on IT KPI data]
    D --> E[Raw KPI Results: Example - avg. resolution time by quarter]
    E --> F[Analyst Assistant (LangGraph LLM): Interprets results and finds trends]
    F --> G[Business Insights and Recommendations: e.g. Resolution time increased by 36%]
    G --> H[Response streamed back to Manager: Appears live in chat]
