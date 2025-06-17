# project_config.md  
Last-Updated: 2025-06-16

## Project Goal  
Migrate an existing **PowerBuilder** application to **Angular** by first extracting business logic and UI behavior into a **Business Requirements Document (BRD)**, then designing and implementing an equivalent Angular frontend and modern backend based on the BRD.

## Tech Stack  
- **Frontend Language & Framework:**  
  - TypeScript  
  - Angular 17+ (component-based SPA architecture)  
- **Backend (Optional):**  
  - Node.js with NestJS or FastAPI (if new APIs are needed)  
- **Build / Tooling:**  
  - Angular CLI, ESLint, Prettier, Git, Docker  
  - Optional: Vite (for faster dev builds), Nx (for monorepo structure)  
- **State Management:** NgRx or Signals (depending on complexity)  
- **Testing:** Jasmine/Karma (unit), Cypress or Playwright (e2e)  

## Critical Patterns & Conventions  
- **Coding Standards:**  
  - Angular Style Guide (official)  
  - TypeScript strict mode enabled  
  - Use `eslint`, `prettier`, and optional `tslint-to-eslint-config` for legacy cleanup  
- **Architectural Patterns:**  
  - Component-based UI with shared and core modules  
  - Smart/Dumb component separation  
  - Service and Repository pattern for logic/data separation  
  - Clean folder-by-feature structure  
- **Naming Conventions:**  
  - `camelCase` for variables, methods  
  - `PascalCase` for components, classes  
  - `kebab-case` for filenames and selectors  
- **Style Guides:**  
  - Angular's official style guide  
  - Consistent HTML/CSS using BEM or Tailwind (if used)  

## Constraints  
- **Functional Parity:** Preserve all business rules and workflows from PowerBuilder, re-validated and documented in the BRD.  
- **UI Modernization:** Legacy Windows-style UIs must be converted into responsive, web-friendly components while maintaining user flow fidelity.  
- **Performance / Latency Budgets:** Angular frontend must meet or exceed perceived performance of the desktop PowerBuilder application.  
- **Security / Compliance:** Replicate any compliance (e.g., HIPAA, PCI-DSS) and perform static security checks (e.g., ESLint, OWASP ZAP).  
- **External Interfaces:** PowerBuilder integrations (e.g., mainframe, ODBC data windows) must be replaced with RESTful services or adapters and documented in the BRD.

## Tokenization Settings  
- Estimated chars-per-token: 3.5  
- Max tokens per message: 8 000  
- Plan for summary when **workflow_state.md** exceeds ~12 K chars.

---

## Changelog  
<!-- The agent prepends the latest summary here as a new list item after each VALIDATE phase -->
