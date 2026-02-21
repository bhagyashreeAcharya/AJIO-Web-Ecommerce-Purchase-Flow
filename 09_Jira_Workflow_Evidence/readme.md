# 🧩 Jira Implementation – AJIO Web QA Project

This section showcases how Jira was used to manage requirements, sprint execution, and defect lifecycle control for the AJIO Web E-Commerce Purchase Flow project.

The objective was not just to log work — but to simulate a structured Agile QA environment with controlled defect governance.

---

## 🔹 1. Backlog & Sprint Planning  
📂 `1_Backlog.png`

The backlog was organized based on feature flow and risk priority.  
User stories were grouped under relevant Epics and assigned story points before sprint commitment.

This demonstrates:
- Logical feature breakdown
- Epic-to-story mapping
- Sprint readiness planning

---

## 🔹 2. User Story with Acceptance Criteria  
📂 `2_User_Story_Description_focused_SS.png`

Each user story includes:
- Clear business context
- Structured acceptance criteria (Given–When–Then format)
- Priority and sprint linkage

Test cases were designed based on real user flows rather than splitting each acceptance criterion artificially.

---

## 🔹 3. QA Subtasks Inside Story  
📂 `3_User_Story_Sub_Task.png`

To simulate real sprint execution, QA activities were broken into subtasks:
- Test Scenario Creation
- Test Case Design
- Test Case Review
- Test Execution

This provides transparency of QA effort within the sprint board.

---

## 🔹 4. Active Sprint Board  
📂 `4_Active_Sprint_Board.png`

The sprint board reflects real-time execution using a simplified workflow:

To Do → In Progress → Done

This demonstrates how QA tasks move alongside development work during sprint execution.

---

# 🐞 Defect Lifecycle Management

---

## 🔹 5. Custom Bug Workflow Design  
📂 `5_Bug_Lifecycle_Design.png`

A structured defect lifecycle was implemented:

OPEN → ASSIGNED → IN PROGRESS → RESOLVED → RETEST → CLOSED

Reopen loop included to handle failed verification.

The separation between **Resolved** and **Closed** ensures QA validation before final closure.

---

## 🔹 6. Controlled Transition Enforcement  
📂 `6_Bug_Transition_Enforcement.png`

Bug closure requires a mandatory resolution selection (Done, Duplicate, Cannot Reproduce, Won’t Do).

This prevents ambiguous closure and maintains audit clarity.

---

## 🔹 7. Real Bug Lifecycle Execution

### Bug Overview  
📂 `7A_Workflow_Execution History_Bug_Overview.png`

Shows defect priority, epic linkage, ownership, and final state.

### Status Transition History  
📂 `7B_Workflow_Execution_History.png`

Demonstrates the complete lifecycle execution:

OPEN → ASSIGNED → IN PROGRESS → RESOLVED → RETEST → CLOSED

This confirms QA verification before closure.

---

## 🔹 8. Bug Tracking View  
📂 `8_Bug_Tracking_Dashboard_View.png`

Displays multiple defects in different states, including:
- In Progress
- Closed
- Duplicate resolution example

Represents realistic defect tracking rather than isolated sample entries.

---

# 🎯 Key Takeaways

Through this Jira setup, the following were demonstrated:

- Requirement breakdown using Epics and Stories  
- Acceptance-criteria driven testing  
- QA task visibility within sprint  
- Structured defect lifecycle design  
- Controlled resolution enforcement  
- Reopen management and validation stage before closure  

This project reflects practical understanding of Agile workflow execution and QA governance using Jira.
