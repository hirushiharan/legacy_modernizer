# project_config.md  
Last-Updated: 2025-06-11

## Project Goal  
Migrate an existing COBOL application to Python by first extracting business logic into a Business Requirements Document (BRD), then designing and implementing an equivalent Python system based on the BRD.

## Tech Stack  
- **Language(s):** Python 3.12  
- **Framework(s):** FastAPI 0.111 (for APIs), Optional: SQLAlchemy, Jinja2, etc.  
- **Build / Tooling:** Poetry, Docker, Git, pytest  

## Critical Patterns & Conventions  
- **Coding Standards:** Follow [PEP 8](https://peps.python.org/pep-0008/), [PEP 257](https://peps.python.org/pep-0257/), and use `black`, `flake8`, `mypy`, and `isort`.  
- **Architectural Patterns:**  
  - Clean Architecture for clear separation between business rules and infrastructure  
  - Layered architecture (e.g., presentation, service, data access)  
  - Repository and Service Layer patterns  
- **Naming Conventions:**  
  - `snake_case` for variables, functions  
  - `PascalCase` for classes  
  - `UPPER_CASE` for constants  
  - Lowercase module and package names  
- **Style Guides:**  
  - Google or NumPy docstring format  
  - Use `pyproject.toml` to consolidate tool configs  

## Constraints  
- **Performance / Latency Budgets:** Modernize COBOL logic while ensuring Python version meets or exceeds original throughput (TBD based on BRD analysis)  
- **Security / Compliance:** Match existing COBOL system compliance (e.g., financial or healthcare standards); perform static and dynamic security checks on Python code  
- **External Interfaces:** Existing COBOL integrations with mainframe systems and batch jobs must be mapped in the BRD; new system must simulate or replace them efficiently  

## Tokenization Settings  
- Estimated chars-per-token: 3.5  
- Max tokens per message: 8 000  
- Plan for summary when **workflow_state.md** exceeds ~12 K chars.

---

## Changelog  
<!-- The agent prepends the latest summary here as a new list item after each VALIDATE phase -->
