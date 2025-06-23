# project_config.md  
Last-Updated: 2025-01-27

## Project Goal  
Migrate an existing **PowerBuilder** application to **Angular** frontend with **Java** backend by first extracting business logic and UI behavior into a **Business Requirements Document (BRD)** and **Business Reverse Engineering Document (BRED)**, then designing and implementing an equivalent Angular frontend and modern Java-based backend based on both documents.

## Project Structure
```
code_modernization/
├── legacy_app/                     # Original PowerBuilder application
│   └── Example_Sales_App/
├── modern_app/                     # Target Angular + Java application
│   ├── extracted_brd/              # Business Requirements Documents
│   │   ├── brd_main.md            # Main BRD document
│   │   ├── functional_requirements.md
│   │   ├── ui_requirements.md
│   │   ├── business_logic_requirements.md
│   │   ├── data_requirements.md
│   │   ├── integration_requirements.md
│   │   ├── security_requirements.md
│   │   ├── reporting_requirements.md
│   │   └── acceptance_criteria.md
│   ├── extracted_bred/             # Business Reverse Engineering Documents
│   │   ├── bred_main.md           # Main BRED document
│   │   ├── powerbuilder_analysis.md
│   │   ├── migration_mapping_rules.md
│   │   ├── ui_component_mappings.md
│   │   ├── data_access_mappings.md
│   │   ├── business_logic_mappings.md
│   │   ├── code_conversion_rules.md
│   │   ├── database_migration_rules.md
│   │   ├── testing_strategy.md
│   │   └── risk_mitigation.md
│   ├── frontend/                   # Angular application
│   └── backend/                    # Java Spring Boot application
└── cursor_kleosr/                  # Project configuration and workflow
```

## Tech Stack  
- **Frontend Language & Framework:**  
  - TypeScript  
  - Angular 17+ (component-based SPA architecture)  
- **Backend:**  
  - Java 17+ with Spring Boot 3.x
  - Spring Security for authentication/authorization
  - Spring Data JPA for database access
  - RESTful APIs with OpenAPI/Swagger documentation
- **Database:**  
  - SQL Server (matching existing PowerBuilder database)
- **Build / Tooling:**  
  - **Frontend:** Angular CLI, ESLint, Prettier, Git, Docker  
  - **Backend:** Maven or Gradle, SonarQube, Checkstyle
  - Optional: Vite (for faster dev builds), Nx (for monorepo structure)  
- **State Management:** NgRx or Signals (depending on complexity)  
- **Testing:** 
  - **Frontend:** Jasmine/Karma (unit), Cypress or Playwright (e2e)
  - **Backend:** JUnit 5, Mockito, TestContainers for integration tests

## Documentation Requirements

### **Business Requirements Document (BRD)**
**Location:** `modern_app/extracted_brd/`  
The BRD captures the **functional and non-functional requirements** of the target Angular+Java system:

#### **BRD Structure:**
1. **Executive Summary** (`brd_main.md`)
   - Project overview and migration objectives
   - Success criteria and key performance indicators

2. **Business Context** (`brd_main.md`)
   - Current PowerBuilder application purpose and scope
   - Target user personas and use cases
   - Business processes and workflows

3. **Functional Requirements** (Separate files for modularity)
   - **User Interface Requirements** (`ui_requirements.md`): Screen layouts, navigation flows, responsive design needs
   - **Business Logic Requirements** (`business_logic_requirements.md`): Rules, validations, calculations, workflows
   - **Data Management Requirements** (`data_requirements.md`): CRUD operations, data validation, reporting
   - **Integration Requirements** (`integration_requirements.md`): External systems, APIs, file imports/exports
   - **Security Requirements** (`security_requirements.md`): Authentication, authorization, data protection
   - **Reporting Requirements** (`reporting_requirements.md`): Reports, charts, export formats

4. **Non-Functional Requirements** (`functional_requirements.md`)
   - **Performance:** Response times, throughput, scalability targets
   - **Usability:** User experience standards, accessibility compliance
   - **Reliability:** Availability, fault tolerance, backup/recovery
   - **Security:** Compliance standards, encryption, audit trails
   - **Maintainability:** Code quality, documentation, deployment

5. **Acceptance Criteria** (`acceptance_criteria.md`)
   - Feature-specific acceptance criteria
   - Test scenarios and validation rules

### **Business Reverse Engineering Document (BRED)**
**Location:** `modern_app/extracted_bred/`  
The BRED documents the **technical migration rules and mappings** from PowerBuilder to Angular+Java:

#### **BRED Structure:**
1. **PowerBuilder Analysis** (`powerbuilder_analysis.md`)
   - **Application Architecture:** Windows, objects, inheritance hierarchy
   - **PBL Library Analysis:** Functions, events, global variables
   - **DataWindow Analysis:** Data access patterns, SQL queries, UI controls
   - **Database Schema:** Tables, relationships, stored procedures, triggers
   - **UI Components:** Windows, tabs, menus, toolbars, controls
   - **Business Logic Location:** Where rules are implemented (client vs. database)

2. **Migration Mapping Rules** (`migration_mapping_rules.md`)
   - **UI Component Mappings** (`ui_component_mappings.md`):
     ```
     PowerBuilder Window → Angular Component
     PowerBuilder Tab → Angular Tab/Router Outlet
     PowerBuilder DataWindow → Angular Data Table + Service
     PowerBuilder Menu → Angular Navigation/Routing
     PowerBuilder Controls → Angular Form Controls
     ```
   - **Data Access Mappings** (`data_access_mappings.md`):
     ```
     PowerBuilder DataWindow → Spring Boot REST API + JPA Entity
     PowerBuilder Transaction → Spring @Transactional Service
     PowerBuilder SQL → Spring Data JPA Repository
     PowerBuilder Cursor → Java Stream/Iterator
     ```
   - **Business Logic Mappings** (`business_logic_mappings.md`):
     ```
     PowerBuilder Functions → Java Service Methods
     PowerBuilder Events → Angular Event Handlers + Java API calls
     PowerBuilder Validation → Angular Validators + Java Bean Validation
     PowerBuilder Global Variables → Angular Services + Java Configuration
     ```

3. **Code Conversion Rules** (`code_conversion_rules.md`)
   - **PowerScript to TypeScript/Java conversion patterns**
   - **Data type mappings:** PowerBuilder types to Java/TypeScript types
   - **Error handling patterns:** PowerBuilder exceptions to Angular/Java exceptions
   - **Event system migration:** PowerBuilder events to Angular/Java patterns

4. **Database Migration Rules** (`database_migration_rules.md`)
   - **Schema preservation rules:** Maintain existing table structures
   - **Data migration strategy:** ETL processes, data validation
   - **Stored procedure migration:** Convert to Java services or keep as DB functions

5. **Testing Strategy** (`testing_strategy.md`)
   - **Functional equivalence testing:** Compare PowerBuilder vs. Angular+Java outputs
   - **Performance benchmarking:** Response time comparisons
   - **Data integrity validation:** Ensure data consistency post-migration

6. **Risk Mitigation** (`risk_mitigation.md`)
   - **Identified migration risks:** Complex business logic, custom controls, integrations
   - **Fallback strategies:** Rollback plans, parallel running periods
   - **Validation checkpoints:** Quality gates throughout migration

## Critical Patterns & Conventions  
- **Frontend Coding Standards:**  
  - Angular Style Guide (official)  
  - TypeScript strict mode enabled  
  - Use `eslint`, `prettier` for code formatting
- **Backend Coding Standards:**
  - Java Code Conventions (Oracle/Google Style)
  - Spring Boot best practices
  - Clean Architecture with layered separation (Controller → Service → Repository)
- **Architectural Patterns:**  
  - **Frontend:** Component-based UI with shared and core modules  
  - **Frontend:** Smart/Dumb component separation  
  - **Backend:** RESTful API design, Dependency Injection, Repository pattern
  - **Both:** Clean folder-by-feature structure  
- **Naming Conventions:**  
  - **Frontend:** `camelCase` for variables/methods, `PascalCase` for components/classes, `kebab-case` for filenames/selectors
  - **Backend:** `camelCase` for variables/methods, `PascalCase` for classes, `snake_case` for database columns
- **API Design:**  
  - RESTful endpoints following OpenAPI 3.0 specification
  - Consistent JSON response formats with proper HTTP status codes
  - Version control strategy (e.g., /api/v1/)

## Constraints  
- **Functional Parity:** Preserve all business rules and workflows from PowerBuilder, validated through BRD and BRED.  
- **Data Migration:** Existing SQL Server database schema and data must be preserved or properly migrated per BRED rules.
- **UI Modernization:** Legacy Windows-style UIs must be converted per BRED UI mapping rules while maintaining user flow fidelity.  
- **Performance / Latency Budgets:** Angular + Java stack must meet or exceed performance benchmarks defined in BRED.  
- **Security / Compliance:** Replicate compliance requirements per BRD and implement modern security practices per BRED patterns.  
- **External Interfaces:** PowerBuilder integrations must be replaced per BRED integration mapping rules.
- **Backward Compatibility:** Ensure data formats and business logic remain compatible per BRED validation strategy.

## Migration Strategy
- **Phase 1:** Analyze PowerBuilder application and create comprehensive **BRD** (`modern_app/extracted_brd/`) and **BRED** (`modern_app/extracted_bred/`)
- **Phase 2:** Design Angular frontend architecture and Java backend API contracts based on **BRED** mappings
- **Phase 3:** Implement Java backend services per **BRED** data access and business logic rules
- **Phase 4:** Develop Angular frontend components per **BRED** UI mapping rules
- **Phase 5:** Integration testing and performance validation per **BRED** testing strategy
- **Phase 6:** Deployment and user acceptance testing per **BRD** acceptance criteria

## Document Relationships
- **BRED → BRD:** Technical analysis informs business requirements
- **BRD → Design:** Business requirements drive system design decisions
- **BRED → Implementation:** Migration rules guide coding patterns and architecture
- **Both → Testing:** Combined validation ensures functional parity and quality

## Tokenization Settings  
- Estimated chars-per-token: 3.5  
- Max tokens per message: 8 000  
- Plan for summary when **workflow_state.md** exceeds ~12 K chars.

---

## Changelog  
- 2025-01-27: Added project structure with specific directories for BRD (`modern_app/extracted_brd/`) and BRED (`modern_app/extracted_bred/`) documents, organized into modular files
- 2025-01-27: Added comprehensive BRD and BRED specifications with migration mapping rules, updated migration strategy to include both documents
- 2025-01-27: Updated backend technology from Node.js to Java Spring Boot, added migration strategy, enhanced constraints for PowerBuilder-specific requirements
<!-- The agent prepends the latest summary here as a new list item after each VALIDATE phase -->
