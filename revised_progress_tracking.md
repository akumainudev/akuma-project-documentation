# Revised Progress Tracking Mechanism: Akuma Style Guide

## 1. Purpose

This document outlines a revised mechanism for tracking and reporting progress on the Akuma Style Guide implementation project and future projects utilizing this framework. It aims to prevent indefinite monitoring stalls, improve transparency, and maintain alignment with timelines, addressing the issues identified with the previous passive monitoring approach.

## 2. Primary Tracking Tool

Progress tracking will be managed within the **Goodbye Human** dashboard once developed. In the interim, task status will be communicated directly between agents and Manus.

## 3. Task Status Updates

*   **Agent Responsibility:** Each assigned AI Agent (Forge, 0xShadow, Gl1tchCTRL, etc.) remains responsible for communicating the status of their assigned tasks directly to Manus (e.g., 'To Do', 'In Progress', 'Blocked', 'Needs Review', 'Completed'). This will eventually be managed via the Goodbye Human dashboard.
*   **Blocker Protocol:** Any task encountering a blocker must be immediately set to 'Blocked', with a clear explanation provided in the task comments. The agent must *also* proactively notify Manus (Project Manager) directly about the blocker.
*   **Completion Protocol:** Upon completing a task, the agent must communicate the completion status directly to Manus. This will eventually be managed via the Goodbye Human dashboard.

## 4. Monitoring and Reporting (Revised)

*   **Proactive Monitoring by Manus:** Manus (Project Manager) will actively monitor task progress and will no longer rely solely on passive observation or user-relayed updates.
*   **Deadline-Driven Checks:** Manus will track task deadlines as defined in the project timeline (`implementation_timeline.md` or subsequent plans).
    *   If a task deadline passes and Manus has not received a 'Completed' or 'Blocked' notification from the assigned agent, Manus will automatically flag the task as 'Overdue'.
    *   Manus will then proactively query the assigned agent for a status update.
    *   If no response or clarification is received within a reasonable timeframe (e.g., 1-2 hours), Manus will escalate the issue to the relevant lead (e.g., 0xShadow for technical tasks) and notify Human Leadership (Fungible).
*   **Reporting Cadence:**
    *   **Daily:** Manus performs internal checks, follows up on overdue tasks, manages escalations, and provides brief daily updates/stand-up notes summarizing progress and blockers.
    *   **Weekly:** Manus compiles the concise progress summary report for Human Leadership, highlighting completions, ongoing work, upcoming tasks, blockers/risks, and timeline adherence.

## 5. Addressing the Monitoring Loop Issue

This revised mechanism directly addresses the previous indefinite monitoring loop by:

1.  **Shifting Responsibility:** Requiring agents to proactively notify Manus upon completion or blockage, reducing reliance on passive monitoring.
2.  **Implementing Timeouts:** Using task deadlines as triggers for proactive follow-up and escalation by Manus, preventing indefinite waiting.
3.  **Clear Escalation Path:** Defining automatic escalation for unresponsive or overdue tasks.

This approach ensures that progress continues, blockers are surfaced quickly, and the project manager (Manus) actively drives the process forward rather than passively waiting.
