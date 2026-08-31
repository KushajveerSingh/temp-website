# Next in line

_Prioritized and queued up tasks_

## TODO: Internal progress tracking

- TODO
    - [ ] **Future roadmap brain dump** - Document all planned future features, upcoming pipeline tasks, and long-term architectural initiatives into the system.
    - [ ] **Documentation template integration** - Update the [/inhouse/it/todo/](https://aesl.ces.uga.edu/inhouse/it/todo/) application to incorporate the newly standardized documentation template.
- Problem
    - Progress updates were managed entirely via manual, ad-hoc emails. This provided zero visibility into the development pipeline, leaving management without real-time insight into task statuses, upcoming features, or the technical problem/benefit rationale behind ongoing engineering work.
- Impact & Benefits
    - **Real-time visibility** - Replaces email updates with a centralized appliation ([/inhouse/it/todo](https://aesl.ces.uga.edu/inhouse/it/todo/)) where management can track active development, task progress, and remaining implementation items at any time.
    - **Transparent context** - Pairs every roadmap item with its associated technical problem statement, business benefits, and implementation checklist for full alignment.
    - **Pipeline transparency** - Acts as a centralized workspace for capturing future technical initiatives, planned updates, and architectural roadmaps in one place.

## Template: Standardize header component

- TODO
    - [ ] **Active state visual** - Automatically highlight the button for the active route.
    - [ ] **Submit state handling** - Disable header buttons during form submission; re-enable upon completition or error.
    - [ ] **Branding and navigation** - Embed AESL logo linking to home in top-left and add a global application directory link (with an option to hide on public sites).
        - [ ] AESL logo.
        - [ ] List of applications link.
    - [ ] **Accessibility widget** - Integrate core accessibility controls inspired by [UserWay](https://userway.org/), and have the settings propagate across sites.
        - [ ] Light/dark mode.
        - [ ] Contrast.
        - [ ] Text size.
        - [ ] Line height.
        - [ ] Saturation.
        - [ ] Cursor.
        - [ ] Reset settings to default.
- Problem
    - Header layouts were inconsistent across applications, and configuration logic was duplicated across individual applications, creating unnecessary code boilerplate and making cross-application UI changes tedious and inconsistent.
- Impact & Benefit
    - **Massive boilerplate reduction** - Streamlined application setup by reducing header initialization from verbose multi-line code down to a single utility function call.
    - **UI/UX consistency** - Gurantees a standardized navigation bar and header experience across applications.
    - **Effortless global updates** - Enables future header modifications (such as global navigation, branding updates, or user settings) to be pushed from one central point without modifying individual apps.

## Template: Standardize form component

- TODO
    - [ ] **Submission Lockout** - Disable all buttons on the page during form submission; re-enable upon completition or error.
    - [ ] **Enhanced success feedback** - Replace generic "Success" alerts with distinct, dynamic success messages, include a manual dismiss action, and automatically clear prior success states.
    - [ ] **Object-based validation engine** - Refactor the validation helper to accept an options object instead of positional arguments, enabling multi-field cross-validation rules and arbitrary custom functions.
- Problem
    - Applications lacked standardized form validation, ommiting essential type checks (number, dates, strings) and database schema character limits.
    - Forms failed to provide visual feedback or contextual warning messages for incorrect submissions.
- Impact & Benefit
    - **Visual field validation** - Automatically highlights valid/invalid fields with green/red indicators and clear, actionable inline error messaging.
    - **Centralized form logic** - Encapsulates form creation, validation, and submission state management into a single utility function, eliminating duplicate code and unifying edge-case handling.
    - **Built-in validation helpers** - Includes streamlined internal utilities for standardizing input sanitization, type verification, and error handling across applications.
