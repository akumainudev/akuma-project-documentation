# Strategy: "Goodbye Human" Dashboard Integration

## 1. Purpose

This document outlines the integration strategy for the "Goodbye Human" dashboard, detailing how it will serve as the central control plane for the no-code development environment. It builds upon the `no_code_environment_plan.md` and incorporates the `revised_progress_tracking.md`.

## 2. Core Principles

*   **Centralization:** The dashboard is the single point of interaction for initiating projects, monitoring progress, and managing approvals.
*   **Automation:** Leverage APIs and webhooks to automate interactions between the dashboard, infrastructure services (scaffolding, CI/CD), and task management.
*   **Proactive Monitoring:** Implement the revised progress tracking mechanism within the dashboard to prevent stalls and ensure timely escalations.
*   **Modularity:** Design integrations to be modular, allowing for future expansion and changes.

## 3. Key Integration Points & Technical Approach

**3.1. Project Initiation & Scaffolding**

*   **UI (Gl1tchCTRL):** Dashboard frontend provides a form for users (e.g., COO or CEO) to input project details (name, type, description).
*   **Backend Orchestration (0xShadow):** Dashboard backend receives form data.
*   **Integration:** Backend makes a secure API call to the **Scaffolding Service** (built by Forge).
    *   **API Design:** The Scaffolding Service exposes an endpoint (e.g., `POST /scaffold`) accepting project parameters.
    *   **Response:** The service returns the new GitHub repository URL and potentially initial task identifiers.
*   **Dashboard State:** Dashboard backend stores project details and associated repository URL in its database.

**3.2. Task Assignment & Management**

*   **Integration Target:** Task assignment and status updates will be managed directly through the Goodbye Human dashboard's native functionality or via direct communication protocols between agents and Manus, as defined in `revised_progress_tracking.md`.
*   **Backend Orchestration (0xShadow):** After successful scaffolding, the dashboard backend determines initial tasks based on the project template.
*   **Integration:** Backend assigns tasks directly to agents and stores task details/status within the dashboard database.
*   **UI (Gl1tchCTRL):** Dashboard displays tasks associated with a project, showing status updates received directly from agents or managed within the dashboard.

**3.3. CI/CD Pipeline & Style Guide Workflow**

*   **Notification (CI/CD -> Dashboard):**
    *   **Mechanism:** Webhooks.
    *   **Events:** The CI/CD pipeline (managed by Forge) is configured to send webhooks to a dedicated endpoint on the dashboard backend (built by 0xShadow - likely the DI-01 task endpoint) upon specific events:
        *   Preview deployment ready (including preview URL, PR details, commit SHA).
        *   Build/test failure.
        *   Production deployment success/failure.
    *   **Security:** Webhooks should be secured (e.g., using shared secrets like `DASHBOARD_API_KEY`).
*   **Approval Trigger (Dashboard -> GitHub):**
    *   **UI (Gl1tchCTRL):** Dashboard displays preview links and approval buttons (DI-02 task).
    *   **Backend Orchestration (0xShadow):** Upon clicking "Approve", the dashboard backend triggers the GitHub repository dispatch event (DI-03 task).
    *   **Integration:** Authenticated API call to GitHub using `GH_PAT_FOR_DISPATCH` to trigger `approve_styleguide_pr` event type with the PR number.
*   **Dashboard State:** Dashboard database stores preview URLs, approval status, and links to relevant PRs.

**3.4. Progress Monitoring & Reporting (Revised)**

*   **Agent Notifications (Agent -> Manus/Dashboard):** Agents are required to *proactively* notify Manus upon task completion or blockage (as per `revised_progress_tracking.md`). This might be via direct message initially, or ideally, via a Command Center feature or a dedicated dashboard notification endpoint if built.
*   **Deadline Tracking (Dashboard Backend - 0xShadow/Manus):**
    *   The dashboard backend continuously monitors task deadlines (stored alongside tasks).
    *   If a deadline passes and the task status (polled from Command Center API or updated via agent notification) is not 'Completed' or 'Blocked', the dashboard flags it as 'Overdue'.
*   **Automated Follow-up/Escalation (Dashboard Backend - 0xShadow/Manus):**
    *   The dashboard automatically sends a notification (e.g., email, internal message) to the assigned agent requesting an update for overdue tasks.
    *   If no update is received within a configured timeframe (e.g., 2 hours), the dashboard automatically escalates by notifying the relevant lead (0xShadow) and Human Leadership.
*   **UI (Gl1tchCTRL):** Dashboard provides views summarizing project status, task statuses (including 'Overdue', 'Blocked'), upcoming deadlines, and recent activity.

## 4. Summary of Responsibilities

*   **Forge (DevOps):** Builds Scaffolding Service API, configures CI/CD webhooks.
*   **0xShadow (Backend Arch):** Builds dashboard backend logic, API integrations (Scaffolding, Command Center, GitHub), webhook receiver endpoint, automated monitoring/escalation logic.
*   **Gl1tchCTRL (Frontend/UX):** Builds dashboard UI for project creation, task display, approvals, and status monitoring.
*   **Manus (PM):** Oversees the process, ensures agents follow notification protocols, manages manual escalations if needed.

This strategy provides a framework for integrating the dashboard as the central hub, automating workflows, and implementing robust, proactive progress tracking.
