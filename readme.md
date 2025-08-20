```mermaid
flowchart TD
    U[Manager: Asks KPI Question in plain English] --> A[Chat UI in Databricks App<br/>🔹 Simple interface for asking questions]
    A --> B[Routing Logic<br/>🔹 Decides which assistant should handle the request]
    B --> C[Genie: Text-to-SQL<br/>🔹 Translates English → SQL query]
    C --> D[Databricks SQL Warehouse<br/>🔹 Runs query securely on IT KPI data]
    D --> E[Raw KPI Results (tables/numbers)<br/>🔹 Example: avg. resolution time by quarter]
    E --> F[Analyst Assistant (LangGraph LLM)<br/>🔹 Interprets results, finds trends, adds context]
    F --> G[Business Insights + Recommendations<br/>🔹 "Resolution time increased by 36% — investigate workload"]
    G --> H[Response streamed back to Manager<br/>🔹 Appears live in chat, easy to read]
