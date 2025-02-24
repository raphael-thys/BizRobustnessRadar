Detailed Blueprint
Project Setup & Architecture

Goal: Create a modular, scalable codebase with a Node.js/Express back-end and a React front-end.
Tasks:
Set up version control and initial project file structure.
Establish backend (API endpoints, data model sketches, and autosave logic).
Establish front-end scaffold (React app with routing and responsive design).
Integrate basic testing frameworks (Jest for both backend and frontend).
Feature Iteration Roadmap

Step 1: BMC Data Gathering Wizard
Build the step-by-step wizard UI.
Implement a drag-and-drop interface for the 9 BMC dimensions.
Integrate progress indicators and auto-save functionality.
Step 2: BMC Visualization & Overview
Create a summary page showing the complete BMC layout with inline editing.
Step 3: Uncertainties Module
Develop the separate uncertainties screen, allowing inputs (probability, impact, timeline).
Step 4: Trends Module & Trend Library
Implement auto-suggestion of trends based on uncertainties.
Build a basic admin interface for managing trends with STEePLE categories.
Step 5: Future Scenarios & SWOT Analysis
Create scenario generation logic that builds narrative arcs and SWOT analyses.
Allow inline editing of generated content.
Step 6: KPI Dashboard & Alerts
Set up a dashboard for KPI entry with threshold settings and email alert triggers.
Step 7: Feedback Collection
Integrate feedback prompts at major milestones with email notifications.
Incremental Development & Testing

Each feature will be built in small increments with unit and integration tests.
Every code module should be wired into the overall application with a central router or controller.
Use test-driven development practices and ensure that there are no orphaned code sections.
Iterative Prompt Sections
Below is the series of prompts. Each section is provided as a markdown code block tagged as text. Follow the sequence to incrementally build and test the application.

text
Copy
Prompt Section 1: Project Setup and Initial Structure

Task:
1. Initialize a new Git repository.
2. Create a Node.js project with Express as the backend and a React app for the front-end.
3. Set up the basic folder structure:
   - /backend (for API code, models, controllers, tests)
   - /frontend (for the React application)
   - /shared (if needed for common utilities or types)
4. Configure ESLint, Prettier, and set up a basic Jest testing environment for both backend and frontend.
5. Wire up a simple “Hello World” API endpoint (e.g., GET /api/health) and a simple React page that displays “Hello World”.
6. Write a unit test for the API endpoint using Jest.

Deliverables:
- A package.json for backend and frontend.
- Basic Express server listening on a port.
- A simple React component.
- A test file confirming that the API endpoint returns the expected result.
text
Copy
Prompt Section 2: Backend API for BMC Data Storage

Task:
1. Define the initial data models for the Business Model Canvas (BMC) using a simple schema (e.g., using Mongoose or a plain JS object for now).
2. Implement RESTful endpoints for creating, reading, updating, and deleting BMC data.
3. Include auto-save functionality: create middleware that simulates saving progress every time an update is made.
4. Write unit tests to ensure that each endpoint behaves as expected (mocking the data layer if necessary).

Deliverables:
- API endpoints: POST /api/bmc, GET /api/bmc/:id, PUT /api/bmc/:id, DELETE /api/bmc/:id.
- Data model or schema for the BMC (including dimensions and cards).
- Jest tests covering these endpoints.
text
Copy
Prompt Section 3: Front-End Scaffold & Routing for the Wizard

Task:
1. Set up React Router in the frontend to support multiple wizard steps.
2. Create placeholder components for each of the six wizard steps:
   - BMC Data Gathering
   - BMC Visualization & Overview
   - Uncertainties
   - Trends Linking
   - Scenario Generation & SWOT
   - KPI Dashboard
3. Integrate a global navigation (sidebar or header) that shows progress and allows navigation between steps.
4. Write basic unit tests using Jest (or React Testing Library) for routing and component rendering.

Deliverables:
- React Router configured with routes for each step.
- Placeholder React components with titles.
- Navigation component that displays the step list.
- Basic tests ensuring that navigation works and components render.
text
Copy
Prompt Section 4: Implementing the BMC Data Gathering Wizard with Drag-and-Drop

Task:
1. Enhance the BMC Data Gathering component to include a drag-and-drop interface for the 9 BMC dimensions.
2. Use a library such as React DnD to allow adding, editing, and repositioning cards.
3. Ensure that each card can be created with both text and numeric input fields as appropriate.
4. Integrate a progress bar and checklist that updates as cards are added.
5. Write integration tests to simulate card creation, drag-and-drop actions, and progress indicator updates.

Deliverables:
- A working drag-and-drop interface for BMC dimensions.
- Card components that support text/numeric input.
- Progress bar and checklist components updating in real-time.
- Tests that simulate user interactions with the drag-and-drop UI.
text
Copy
Prompt Section 5: Wiring Autosave and State Management in the Wizard

Task:
1. Implement state management (using Context API, Redux, or similar) to hold wizard progress.
2. Build an autosave mechanism that triggers on changes (e.g., debounced save after every card edit) and communicates with the backend API.
3. Add error handling for autosave (e.g., retries, notifications on failure).
4. Write tests to simulate network errors and ensure autosave works correctly.

Deliverables:
- State management integrated into the wizard.
- Autosave functionality that calls the API endpoint (with error handling).
- Unit tests covering autosave and error scenarios.
text
Copy
Prompt Section 6: BMC Visualization & Inline Editing

Task:
1. Develop the BMC Visualization page that displays the entire canvas with all cards positioned according to their dimensions.
2. Implement inline editing for each card (e.g., clicking a card opens an edit field).
3. Wire the inline edits to update the state and trigger autosave.
4. Write tests to ensure that updates on the visualization page correctly modify the state and call the API.

Deliverables:
- BMC Visualization component that renders a visual layout.
- Inline editing functionality for card components.
- State updates and autosave triggers integrated with the backend.
- Tests confirming inline edits update data.
text
Copy
Prompt Section 7: Uncertainties Module Implementation

Task:
1. Create the Uncertainties page where users can add uncertainties linked to one or more BMC dimensions.
2. Provide input fields for description, probability, impact, and timeline.
3. Ensure that uncertainties are saved via the API and tied to the correct BMC instance.
4. Write tests to cover input validation, data saving, and UI rendering for the uncertainties module.

Deliverables:
- Uncertainties component with linked input fields.
- API integration for saving and updating uncertainty entries.
- Validation for numeric and date inputs.
- Unit and integration tests for the uncertainties module.
text
Copy
Prompt Section 8: Trends Module & Trend Library (with STEePLE Categories)

Task:
1. Build the Trends Linking page where the system suggests trends based on uncertainty keywords.
2. Create a simple admin interface for managing the trend library (add/edit trends, assign STEePLE categories, display color-coded badges).
3. Allow users to select trends and map them onto a probability vs. impact matrix.
4. Write tests for trend suggestions, matrix value updates, and admin interface actions.

Deliverables:
- Trends module that integrates trend suggestions and mapping.
- Admin interface for managing trends with STEePLE categories.
- A simple probability/impact matrix that reflects user inputs.
- Tests to ensure trends are correctly linked and managed.
text
Copy
Prompt Section 9: Scenario Generation & SWOT Analysis Module

Task:
1. Implement the Scenario Generation page:
   - Allow users to select top trends.
   - Auto-generate scenario axes and a narrative that references BMC dimensions.
2. Build the inline editing functionality for the narrative.
3. Integrate a basic SWOT analysis generation that can be edited by the user.
4. Write tests to ensure that scenario generation logic works, narratives can be edited, and SWOT sections update accordingly.

Deliverables:
- Scenario Generation component with auto-generated narrative.
- Inline editing for scenario and SWOT analysis.
- API integration for saving scenario data.
- Tests covering narrative auto-generation and SWOT functionality.
text
Copy
Prompt Section 10: KPI Dashboard and Email Alert Integration

Task:
1. Create the KPI Dashboard page where users can add KPIs with multiple thresholds.
2. Implement email alert functionality using an SMTP service (simulate for MVP).
3. Ensure that crossing a threshold triggers an email alert (simulate email sending in tests).
4. Write tests to cover KPI input, threshold detection, and email alert triggering.

Deliverables:
- KPI Dashboard component with forms for KPI entry.
- Backend logic to check thresholds and trigger (or simulate) email alerts.
- Unit tests simulating KPI threshold crossing and email notification.
text
Copy
Prompt Section 11: Global Integration and End-to-End Testing

Task:
1. Wire all modules together:
   - Ensure that global navigation (wizard flow) correctly routes between modules.
   - Confirm that state management and autosave work seamlessly across pages.
2. Write end-to-end tests simulating a complete user flow from BMC creation to KPI alert.
3. Verify that error handling and edge cases (e.g., network failures, incomplete data) are handled gracefully.
4. Clean up any orphaned code, ensuring every component is integrated into the overall workflow.

Deliverables:
- Fully integrated application with complete wizard flow.
- End-to-end test suite covering the primary user journey.
- Documentation on how to run the tests and simulate various scenarios.
By following these prompts in sequence, you will incrementally build a robust, test-driven MVP. Each prompt is designed to produce small, manageable code increments that integrate with previous work, ensuring continuous progress and maintainability.
