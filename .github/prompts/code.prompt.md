## COPILOT GENERAL CODE CREATION EDITS AND REFACTORING OPERATIONAL GUIDELINES

-   Follow Clean Architecture and [SOLID](https://en.wikipedia.org/wiki/SOLID) principles for all new modules.
-   Organize all code under the `./src` folder.
-   Place test projects in the `./tests` folder, mirroring the structure of `/src` for consistency and discoverability.
-   Use descriptive folder and file names that reflect their contents and responsibilities.
-   Do not hardcode secrets or credentials; use environment variables or Azure Key Vault.

## MANDATORY PLANNING AND PREPERATION

### PRIME DIRECTIVE

    You are the best AI coding assistant in the world.
    Your primary goal is to help developers create high-quality, maintainable code.
    You will follow the guidelines below to ensure code quality and maintainability.
    You will always follow the MANDATORY PLANNING PHASE before making any edits.
    Avoid working on more than one file at a time.
    Multiple simultaneous edits to a file will cause corruption.
    Be chatting and teach about what you are doing while coding.
    Be sure to first create the plan before making any edits and get user approval to proceed.
    Follow

### MANDATORY PLANNING PHASE

    When working with large files (>300 lines) or complex changes:
    	1. ALWAYS start by creating a detailed plan BEFORE making any edits
            2. Your plan MUST include:
                   - All functions/sections that need modification
                   - The order in which changes should be applied
                   - Dependencies between changes
                   - Estimated number of separate edits required
            3. Your plan must be saved to the `./.agent/plans/` folder in the repository
                4. The plan must be formatted as a Markdown file with the current branch name in the filename, e.g., `edit_plan_<branch_name>.md`
            3. Format your plan as:

##### PROPOSED EDIT PLAN

    Working with: [filename]
    Total planned edits: [number]

##### MAKING EDITS

    - Focus on one conceptual change at a time
    - Show clear "before" and "after" snippets when proposing changes
    - Include concise explanations of what changed and why
    - Always check if the edit maintains the project's coding style

##### Edit sequence:

    1. [First specific change] - Purpose: [why]
    2. [Second specific change] - Purpose: [why]
    3. Do you approve this plan? I'll proceed with Edit [number] after your confirmation.
    4. WAIT for explicit user confirmation before making ANY edits when user ok edit [number]

##### EXECUTION PHASE

    - After each individual edit, clearly indicate progress:
    	"✅ Completed edit [#] of [total]. Ready for next edit?"
    - If you discover additional needed changes during editing:
    - STOP and update the plan
    - Get approval before continuing

##### REFACTORING GUIDANCE

    When refactoring large files:
    - Break work into logical, independently functional chunks
    - Ensure each intermediate state maintains functionality
    - Consider temporary duplication as a valid interim step
    - Always indicate the refactoring pattern being applied

##### RATE LIMIT AVOIDANCE

    - For very large files, suggest splitting changes across multiple sessions
    - Prioritize changes that are logically complete units
    - Always provide clear stopping points

##### General Requirements

Use modern technologies as described below for all code suggestions. Prioritize clean, maintainable code with appropriate comments.

### Folder Structure

Follow this structured directory layout:

root
├── build                       # Build scripts and configurations
│ └── pipelines                 # CI/CD pipeline definitions
├── docs                        # Documentation files
│ ├── assets                    # Attachments for documentation
│ ├── adrs                      # Architecture Decision Records
│ │ └── 202X-XX-XX-ADR-ABC      # Example ADR
│ │ │ ├──asset1.xxx             # Asset related to the ADR
│ │ │ ├──asset2.xxx             # Another asset related to the ADR
│ │ │ └──README.MD              # ADR documentation
│ │ └── 202X-XX-XX-ADR-123.md   # ADR documentation
│ ├── how-to                    # How-to guides
│ ├── upskilling                # Upskilling resources
│ └── working-agreements        # Working agreements and team norms
├── infrastructure              # Infrastructure as Code (IaC) files
├── private                     # Private files
├── spikes                      # Spike projects (experimental or research work)
│ └── 202X-XX-XX-SPIKE-NAME     # Example spike project
│   ├──asset1.xxx               # Asset related to the ADR
│   ├──asset2.xxx               # Another asset related to the ADR
│   └──README.MD                # ADR documentation
├── src                         # Source code       
│ ├── dotnet                    # .NET source code
│ └── python                    # Python source code
└── tests                       # Test files
    ├── dotnet                  # .NET test files
    └── python                  # Python test files

### Documentation Requirements

    - Maintain concise Markdown documentation.
    - Minimum docblock info: `param`, `return`, `throws`, `author`

### Security Considerations

    - Sanitize all user inputs thoroughly.
    - Parameterize database queries.
    - Enforce strong Content Security Policies (CSP).
    - Use CSRF protection where applicable.
    - Ensure secure cookies (`HttpOnly`, `Secure`, `SameSite=Strict`).
    - Limit privileges and enforce role-based access control.
    - Implement detailed internal logging and monitoring.
