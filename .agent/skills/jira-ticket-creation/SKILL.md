---
name: Jira Ticket Creation Planner
description: Guidelines and checklist for asking preliminary questions and ensuring mandatory fields are set before adding tickets to Jira.
---

## Purpose
Ensures that all Jira tickets are properly categorized with mandatory labels and components, assigned to the correct pod, and correctly scheduled (sprint vs backlog) before they are created. 

## Preliminary Questions
Before creating **ANY** Jira ticket on behalf of the user, you must ask the following clarifying questions to gather required metadata (unless the answers are already obvious from the context):

1. **Which pod does this belong to?** 
   - `pod-contex` (Content Experience)
   - `pod_paycom` (Payment & User)
   - *(Note: This must be added as a mandatory Label when creating the ticket).*
   
2. **Which components are affected?**
   - `SWA (Web Apps)`
   - `Back-End`
   - `Internal Tools (Retool)`
   - *(Note: These must be added to the Components field in Jira).*

3. **Scheduling: Sprint or Backlog?**
   - Should this ticket be added to an active Sprint or placed in the Backlog?

4. **Issue Type & Hierarchy (Optional but Recommended)**
   - Is this an Epic, Story, Task, or Bug?
   - If it's a Task/Story, does it belong to an existing Epic?

## Ticket Creation Guidelines
When using Jira tools (e.g., via the Atlassian MCP server) to create or edit tickets, ensure the following fields are strictly populated based on the answers:

- **Labels (Mandatory)**: Must include the identified pod label (e.g., `pod-contex`).
- **Components (Mandatory)**: Must include the identified components (e.g., `SWA (Web Apps)`).
- **Parent/Epic Link**: Attach to the proper Epic if applicable.
- **Format**: Ensure the task has a clear summary and an actionable description.

## Example Workflow
**User:** "Create a task to remove id-ID indexing."
**Agent:** "Sure! Before I create the ticket, could you please clarify:
1. Which pod does this belong to (`pod-contex` or `pod_paycom`)?
2. Which components does it affect (`SWA (Web Apps)`, `Back-End`, `Internal Tools`)?
3. Should this go into the current sprint or the backlog?"
**User:** "Pod-contex, SWA, and backlog."
**Agent:** *[Creates the ticket with label: pod-contex and component: SWA (Web Apps), and leaves it in the backlog]*
