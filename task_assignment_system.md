# Akuma Style Guide: Task Assignment System

## 1. Purpose

This document outlines the system for assigning, tracking, and managing tasks related to the implementation of the Akuma Style Guide system. Its goal is to ensure clarity, accountability, and efficient progress throughout the project lifecycle.

## 2. Task Management Platform

All tasks for this project will be created, assigned, and tracked using the **Goodbye Human** dashboard once developed. In the interim, task status will be communicated directly between agents and Manus.

## 3. Task Assignment Process

1.  **Task Definition:** Manus (Project Manager) defines specific, actionable tasks based on the overall implementation plan, breaking down larger phases into manageable units.
2.  **Task Creation:** Manus creates these tasks within the Goodbye Human dashboard, assigning a unique Task ID (e.g., GS-01, DI-01), providing a clear title and description, referencing relevant documentation, setting a priority, and assigning a deadline based on the project timeline.
3.  **Assignee Allocation:** Manus assigns each task to the designated AI Agent responsible for that functional area, according to the defined roles.

## 4. Roles and Responsibilities

Task assignments are based on the established AI Agent roles:

*   **Director of Code Environment:** Responsible for all tasks related to GitHub repository setup, CI/CD pipeline configuration, deployment workflows (VitePress, GitHub Pages), and initial environment testing.
*   **0xShadow (CTO):** Oversees technical architecture. Directly responsible for backend development tasks, including the Dashboard API endpoint implementation (`/api/styleguide/review-request`) and the logic for triggering GitHub workflow dispatches (`approve_styleguide_pr`). Also serves as the primary escalation point for technical blockers.
*   **Gl1tchCTRL (UX Enforcer):** Responsible for frontend development tasks related to the style guide integration within the Goodbye Human dashboard, specifically the UI for displaying and actioning approval requests.
*   **Manus (Project Manager):** Defines and assigns tasks, monitors progress via the Goodbye Human dashboard, verifies task completion against requirements, manages the overall timeline, reports status updates, and routes blockers.
*   **Other AI Agents (0xLockjaw, DubsCrank, etc.):** May be assigned specific testing or integration tasks as needed, relevant to their focus areas, during later phases.
*   **Human Leadership (Fungible, Atlas, Matt):** Provide strategic direction, approve key milestones or changes in scope, and resolve high-level blockers escalated by Manus/0xShadow.

## 5. Status Tracking and Reporting

*   **Agent Updates:** Assigned AI Agents are responsible for updating the status of their tasks in the Goodbye Human dashboard promptly (e.g., 

'To Do', 'In Progress', 'Blocked', 'Needs Review', 'Completed'). Any blockers must be immediately flagged with the 'Blocked' status and details provided in the task comments.
*   **Reporting:** Manus will monitor the Goodbye Human dashboard daily and provide summarized progress reports (e.g., daily stand-up notes, weekly summaries) to Fungible, Atlas, and Matt.

## 6. Escalation Procedures

1.  **Technical Blockers:** Agents encountering technical issues they cannot resolve shoulflag the task as \'Blocked\' in the Goodbye Human dashboard and notify Manus. Manus will route the issue to 0xShadow for technical guidance.
2.  **Resource/Dependency Blockers:** If a task is blocked due to external dependencies or resource constraints, the Agent notifies Manus. Manus will work with relevant parties (including Human Leadership if necessary) to resolve.
3.  **Scope/Requirement Issues:** Questions or concerns about task scope or requirements should be raised to Manus, who will clarify or escalate to Fungible/Atlas/Matt for strategic decisions.
