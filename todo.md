# TODO Checklist for MVP Development

This checklist covers all major tasks from project setup to final integration testing. Use it as a guide to track progress and ensure every piece of functionality is implemented and tested.

---

## 1. Project Setup & Architecture
- [ ] **Initialize Repository & Basic Setup**
  - [ ] Initialize a new Git repository.
  - [ ] Create separate folders for `/backend`, `/frontend`, and `/shared` (if needed).
  - [ ] Set up Node.js project for the backend (using Express).
  - [ ] Set up a React project for the frontend.
  - [ ] Configure ESLint, Prettier, and a Jest testing environment for both backend and frontend.
- [ ] **"Hello World" Implementation**
  - [ ] Create a basic Express server with a simple GET `/api/health` endpoint.
  - [ ] Develop a simple React component that displays “Hello World”.
  - [ ] Write a unit test for the `/api/health` endpoint.

---

## 2. Backend API for BMC Data Storage
- [ ] **Define Data Models**
  - [ ] Create a schema or data model for the Business Model Canvas (BMC) including dimensions and cards.
- [ ] **Implement CRUD Endpoints**
  - [ ] POST `/api/bmc` – Create a new BMC.
  - [ ] GET `/api/bmc/:id` – Retrieve a specific BMC.
  - [ ] PUT `/api/bmc/:id` – Update a specific BMC.
  - [ ] DELETE `/api/bmc/:id` – Delete a specific BMC.
- [ ] **Autosave Middleware**
  - [ ] Implement middleware to simulate auto-saving progress with each update.
- [ ] **Testing**
  - [ ] Write Jest tests for each endpoint (CRUD operations and autosave).

---

## 3. Front-End Scaffold & Wizard Routing
- [ ] **Routing Setup**
  - [ ] Configure React Router to support multiple wizard steps.
- [ ] **Create Placeholder Components for Wizard Steps**
  - [ ] BMC Data Gathering
  - [ ] BMC Visualization & Overview
  - [ ] Uncertainties
  - [ ] Trends Linking
  - [ ] Scenario Generation & SWOT
  - [ ] KPI Dashboard
- [ ] **Global Navigation**
  - [ ] Develop a sidebar or header navigation with progress indicators for the wizard steps.
- [ ] **Component Tests**
  - [ ] Write tests to ensure correct routing and component rendering.

---

## 4. BMC Data Gathering Wizard with Drag-and-Drop
- [ ] **Enhance Data Gathering UI**
  - [ ] Implement a drag-and-drop interface using a library (e.g., React DnD) for managing 9 BMC dimensions.
  - [ ] Enable adding, editing, and repositioning of cards.
- [ ] **Card Components**
  - [ ] Create card components that support both text and numeric input.
- [ ] **Progress Indicators**
  - [ ] Integrate a progress bar and checklist that update as cards are added.
- [ ] **Integration Tests**
  - [ ] Write tests to simulate card creation, drag-and-drop actions, and progress updates.

---

## 5. Autosave & State Management in the Wizard
- [ ] **State Management Implementation**
  - [ ] Use Context API, Redux, or similar to maintain wizard progress.
- [ ] **Autosave Functionality**
  - [ ] Implement debounced autosave that triggers on card edits/updates.
  - [ ] Connect autosave to the backend API.
- [ ] **Error Handling**
  - [ ] Add error handling for autosave (retries, notifications on failure).
- [ ] **Testing**
  - [ ] Write tests to simulate autosave triggers and error scenarios.

---

## 6. BMC Visualization & Inline Editing
- [ ] **Visualization Page**
  - [ ] Develop a component that displays the full BMC with all cards laid out by dimension.
- [ ] **Inline Editing**
  - [ ] Enable inline editing when a card is clicked.
  - [ ] Ensure inline edits update state and trigger autosave.
- [ ] **Testing**
  - [ ] Write tests to verify inline editing functionality and state updates.

---

## 7. Uncertainties Module
- [ ] **Uncertainties Interface**
  - [ ] Build a dedicated page to list uncertainties linked to BMC dimensions.
  - [ ] Include input fields for description, probability, impact, and timeline.
- [ ] **API Integration**
  - [ ] Connect uncertainty inputs to backend endpoints for saving/updating.
- [ ] **Validation**
  - [ ] Ensure proper validation for numeric and date inputs.
- [ ] **Testing**
  - [ ] Write unit and integration tests for the uncertainties module.

---

## 8. Trends Module & Trend Library
- [ ] **Trends Linking Page**
  - [ ] Implement a page that auto-suggests trends based on uncertainty keywords.
- [ ] **Admin Interface for Trend Library**
  - [ ] Build a simple admin interface to add/edit trends and assign STEePLE categories.
  - [ ] Display color-coded badges for STEePLE categories.
- [ ] **Probability/Impact Matrix**
  - [ ] Create a matrix to map selected trends based on user-input values.
- [ ] **Testing**
  - [ ] Write tests for trend suggestions, matrix updates, and admin functions.

---

## 9. Scenario Generation & SWOT Analysis Module
- [ ] **Scenario Generation**
  - [ ] Develop a page where users select top trends and generate scenario axes.
  - [ ] Auto-generate narrative content referencing BMC dimensions.
- [ ] **Inline Editing for Scenarios**
  - [ ] Allow users to edit the generated narrative and SWOT analysis.
- [ ] **API Integration**
  - [ ] Connect scenario data to the backend for saving/updating.
- [ ] **Testing**
  - [ ] Write tests for scenario auto-generation, narrative editing, and SWOT updates.

---

## 10. KPI Dashboard & Email Alert Integration
- [ ] **KPI Dashboard**
  - [ ] Create a page for users to add KPIs with multiple threshold settings.
- [ ] **Email Alert Functionality**
  - [ ] Implement backend logic to detect when KPI thresholds are crossed.
  - [ ] Integrate an SMTP service (simulate for MVP) to trigger email alerts.
- [ ] **Testing**
  - [ ] Write tests to simulate KPI input, threshold detection, and email alert triggers.

---

## 11. Global Integration & End-to-End Testing
- [ ] **Module Integration**
  - [ ] Wire together all modules with global navigation and consistent state management.
- [ ] **End-to-End Testing**
  - [ ] Write E2E tests simulating a full user flow from BMC creation to KPI alert.
- [ ] **Error & Edge Case Handling**
  - [ ] Verify graceful handling of network failures, incomplete data, and other edge cases.
- [ ] **Cleanup**
  - [ ] Ensure no orphaned code; all modules are integrated into the main workflow.

---

## 12. Documentation & Final Review
- [ ] **Documentation**
  - [ ] Write clear instructions on how to run the application and tests.
  - [ ] Document API endpoints, state management, and component hierarchy.
- [ ] **Code Review**
  - [ ] Conduct a thorough review to ensure adherence to best practices.
- [ ] **Final Testing**
  - [ ] Run full test suite (unit, integration, E2E, performance) and address any issues.

---

This `todo.md` serves as a comprehensive checklist to guide the development of the MVP in an incremental, test-driven manner. Use it to track progress and ensure every piece of functionality is implemented and tested before moving on to the next step.
