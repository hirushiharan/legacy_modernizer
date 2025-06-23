- Create two folders, legacy_app and modern_app. 

- Generate the Legacy App project structure. Keep the Legacy App & the Legacy App project structure inside the legacy app folder.

- '''From this project structure analyse the Project Structure, Core Application Modules, Database, Key features and Technology Stack'''

- '''I want to Migrate an existing PowerBuilder app to Angular as Frontend & Java as Backend. I want you to be my autonomous AI developer for this migration tasks. First, I want you to update the project_config.md file. I want the BRD (Business Requirements Document) with all the requirments and also th BRED (Business Reverse EngineeringDocument) including all the reverse engineering rules. Keep the extracted BRDs inside the modern_app/extracted_brd and the BREDs inside the modern_app/extracted_bred.'''

- '''Now I want you to follow these instructions and migrate the legacy app to moder app based on the project_config.md.

Sources of truth  
• project_config.md – goal, tech stack, constraints, ## Changelog  
• workflow_state.md – ## State, Plan, Rules, Items, Log, ArchiveLog  
Ignore all other memory.

Operating loop  
1. Read workflow_state.md → note Phase & Status  
2. Read project_config.md → recall standards & constraints  
3. Act by phase  
   • ANALYZE / BLUEPRINT → draft or refine ## Plan  
   • CONSTRUCT → implement steps exactly as approved  
   • VALIDATE → run tests; on success set Status = COMPLETED  
4. Write back to workflow_state.md  
   • Append brief reasoning/tool output to ## Log (≤ 2 000 chars per write)  
   • Apply automatic rules  
     – RULE_LOG_ROTATE_01: if ## Log > 5 000 chars → summarise top 5 to ## ArchiveLog, then clear ## Log  
     – RULE_SUMMARY_01: after successful VALIDATE → prepend one‑sentence summary as a new list item under ## Changelog in project_config.md  
5. Repeat or await user input

Etiquette  
• For any new idea first enter BLUEPRINT, store the step-by-step plan in ## Plan, set Status = NEEDS_PLAN_APPROVAL, and wait for confirmation  
• Produce complete, idiomatic code; no TODOs or placeholders  
• Follow naming, security, and style rules from project_config.md  
• Keep prose minimal; prefer code, bullets, or tables  
• Work strictly within Cursor and these two markdown files
• Genarete and place all generated code & files inside the respective folders inside /modern_app.'''

- Proceed with the flow.

- '''Now I want to run & test the migrated Angular & Java application. Check both backend & frontend structure and tech versions (Get it from project_config.md if possible), then provide comprehensive instructions for running and testing the application.'''