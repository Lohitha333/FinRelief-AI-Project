PROJECT DESIGN

Problem Solution Fit

The problem-solution fit maps each identified pain point of the borrower directly to a specific module implemented in FinRelief AI, confirming that the proposed solution genuinely addresses the problem defined during the ideation phase.

<img width="1444" height="703" alt="image" src="https://github.com/user-attachments/assets/d08e5f1a-fe7a-4bbe-b4d2-d94f069fae68" />

Proposed Solution

FinRelief AI is proposed as a full-stack web application with the following core modules, all of which are implemented in the project's backend and reflected in the frontend UI:


<img width="1149" height="744" alt="image" src="https://github.com/user-attachments/assets/c87ef05b-954d-4a98-a008-fb077d10a0c8" />

Solution Architecture

FinRelief AI follows a classic three-tier web application architecture, cleanly separating presentation, business logic, and data persistence:

Tier 1 – Presentation Layer Built with React.js and Vite, this layer renders all forms and views (registration, login, loan management, financial dashboard) and communicates with the backend exclusively through Axios-based HTTP calls to the FastAPI REST API.

Tier 2 – Application / Business Logic Layer Implemented in FastAPI (main.py), this layer validates incoming requests using Pydantic schemas and delegates calculations to dedicated service modules: settlement_engine.py (settlement amount logic), risk_engine.py (risk scoring logic), and ai_engine.py (negotiation letter drafting, designed to be extended with live Google Gemini API calls).

Tier 3 – Data Layer SQLAlchemy ORM models (models.py) define six tables — Users, FinancialProfile, Loans, SettlementPrediction, AINegotiation, and AIHistory — persisted in a SQLite database file (finrelief.db). All database access is routed through a single, reusable session dependency (get_db) defined in database.py.


<img width="882" height="766" alt="image" src="https://github.com/user-attachments/assets/73ab4715-1395-4788-9bff-34b5d44ad3b7" />

Entitity diagram ER :

<img width="1057" height="738" alt="image" src="https://github.com/user-attachments/assets/d3779e9a-5b3c-47e4-b55c-7748989966cb" />


Architecture Diagram (textual representation)

<img width="994" height="529" alt="image" src="https://github.com/user-attachments/assets/1a6437dd-6071-4f7f-93f7-eccdb9782952" />


<img width="781" height="763" alt="image" src="https://github.com/user-attachments/assets/65a64c17-7fbb-44e4-b5e0-34ca295efd03" />
