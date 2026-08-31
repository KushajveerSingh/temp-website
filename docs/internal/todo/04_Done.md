# Done

_Completed archive_

## (Aug 18) Docs: Framework for automated markdown documentation

- Problem
    - Existing applications currently have zero formal documentation, making onboarding, maintenance, and knowledge transfer difficult.
    - Lacking a standardized documentation template forced any prior technical writing into raw HTML—making updates tedious and prone to formatting drift.
- Impact & Benefit
    - **Markdown-first workflow** - Enables writing documentation entirely in Markdown, significantly reducing maintenance overhead and accelerating content creation.
    - **Application coverage plan** - Establishes a standardized framework to roll out dedicated documentation for every application.
    - **Structured content modules** - Standardizes documentation files per application into clear sections, including
        - User Guides: End-user application usage and workflows.
        - Implementation Details: Architectural overviews, setup guides, and instructions on how to read, modify, and extend the codebase.

## (Aug 16) Template: Case-insensitive URL parameters and utilities

- Problem
    - Application URL query parameters were case-sensitive, creating usability friction and requiring users to memorize exact capitalization when manually navigating or entering URLs.
- Impact & Benefit
    - **Improved usability** - Enforces lowercase query parameters parsing across applications, eliminating case-sensitivity errors and link-breaking issues.
    - **Standardized retrieval methods** - Consolidated scattered URL parameter handling into a single utility method for fetching individual parameter value or extracting full query parameter list.

## (Aug 16) Template: Centralize and automate fiscal year utilities

- Problem
    - Fiscal years were manually updated in text and script files anually, with individual applications re-implementing their own data calculation logic and hardcoding formats (e.g., `2617` with a July 1 start date).
- Impact & Benefit
    - **Automated calculations** - Computes fiscal year dynamically based on configurable dates and months - eliminating annual manual updates and correctly handling century-turn edge cases.
    - **Utility standardization** - Centralizes common data operations into shared helper functions (calculating next/previous fiscal years, historical ranges, and n-offset years).
    - **Flexibility across labs** - Abstracted the core logic so non-fiscal laboratories can easily toggle between fiscal and calendar years without code refactoring.

## (Aug 16) Template: Optimize database query API and execution pipeline

- Problem
    - Database queries relied on verbose frontend/backend code, inefficient runtime file system scans across multiple locations, and minimal error handling - causing server hangs on missing queries and slow debugging.
    - Additionally, legacy Microsoft Access drivers returned all data strictly as strings.
- Impact & Benefit
    - **Massive performance boost** - Implemented in-memory caching for query files, eliminating repetitive disk read and drastically reducing server load.
    - **Codebase refactoring and standardization** - Stripped out legacy boilerplate, consolidated redundant frontend helper functions, and standardized the reponse structure (returning normalized rows, columns, counts, and index maps).
    - **Robust error handling** - Replaced server hangs with explicit, step-by-step diagnostic error reporting for immediate troubleshooting.
    - **Future-proofing for PostgreSQL migration** - Added backend data-type coercion (casting strings to proper types) so frontend application logic will require zero refactoring when migrating off Access.

## (Aug 16) Template: Centralize amd self-host dependencies and fonts

- Problem
    - Applications directly import external dependencies individually, leading to version drift across apps, difficult updates, potential security vunerabilities, and reliance on third-party availability.
- Impact & Benefit
    - **Version consistency** - Centralizes dependencies in one place, ensuring every application uses uniform, easily updateable library versions.
    - **Enhanced security** - Removes exposure to third-party CDN supply-chain risks by bringing assets under local control.
    - **Performance and reliability** - Eliminates external DNS lookups and speeds up load times by serving fonts and libraries directly from the primary server.

## (Aug 16) Template: Integrate database schema and metadata into frontend

- Problem
    - The frontend lacks database schema information, leading to unvalidated inputs (such as unchecked string lengths) that silent-crop long text, as well as harcoded fiscal year logic scattered across the codebase.
- Impact & Benefit
    - **Frontend validation** - Enforces database field constraints and character limits directly in the UI before submission.
    - **Data integrity** - Prevents truncated text and protects against potential database corruption.
    - **Dynamic fiscal year tracking** - Stores fiscal year start metadata directly on each table, eliminating hardcoded fiscal year logic across the codebase.
    - **Improved UX** - Catches validation errors instantly, giving users immediate feedback before a failed or partial save.

## (Aug 16) Template: Centralized math and calculation utilities

- Problem
    - Mathematical logic and calculation helper functions were duplicated across individual applications, creating inconsistent implementation, potential rounding errors, and repetitive code maintenance.
- Impact & Benefit
    - **Code reuse and consistency** - Consolidates common calculations into a single, shared library to ensure uniform results across all lab applications.
    - **Maintainability and testing** - Simplifies updates and bug fixes by isolating complex math logic into dedicated utility functions.
    - **Future performance upgrades** - Establishes a single architectural entry point, enabling future high-performance upgrades (such as leveraging es-toolkit or WebAssembly for heavy calculations) with zero changes needed in application code.

## (Aug 16) Template: Centralized global paths and URLs

- Problem
    - Harcoded paths and URLs across applications make updates error-prone and prevent environment-specific configurations.
- Impact & Benefit
    - **Single source of truth** - Allows immediate path and URL update across all apps from one central location.
    - **Architecture readiness** - Prepares the codebase for the upcoming Vite/Go migration by enabling distinct _Development_ and _Production_ environments.
    - **Legacy Drive Migration** - Simplifies adding and updating directory as legacy H, W, J drives are deprecated and replaced by new folder structure _employees_, _instruments_.
