
# MeetingTasksAgent

## Overview
The Meeting Tasks Agent extracts action items from meeting transcripts and helps users convert them into structured tasks in the appropriate project management system.

The agent bridges the gap between discussion and execution by ensuring that no action items are lost and that follow-up becomes part of the operational workflow.

---

## Problem
After meetings, action items are often:
- Not clearly captured
- Manually recreated in different systems
- Spread across multiple tools

This leads to inefficiencies, inconsistencies, and missed follow-ups.

---

## Solution
The Meeting Tasks Agent:
- Extracts action items from meeting transcripts
- Structures them into clear tasks
- Identifies owners, due dates, and dependencies
- Allows the user to decide where tasks should be created
- Creates tasks directly in the selected system

---

## Key Features
- Task extraction from unstructured meeting transcripts
- Detection of owner, due date, and dependencies  
- Human-in-the-loop validation before execution  
- Support for multiple project management systems  
- Direct task creation via integrated connectors  

---

## Architecture

The solution follows a structured, multi-step workflow:

1. A meeting transcript is provided (manual input or trigger)
2. The agent extracts and structures action items
3. Tasks are presented to the user for validation
4. The user selects the target system and project/plan
5. Tasks are created via system connectors

---

## Architectural Choices

### Human-in-the-loop
The agent does not automatically create tasks. Instead:
- The user validates extracted tasks
- The user selects the target system (Planner or Azure DevOps)
- The user selects the correct project or plan

This ensures:
- Higher accuracy
- Better user trust
- Flexibility across teams and tools

---

### Instruction-based orchestration
The agent uses structured instructions rather than rigid topic flows:
- Enables flexibility for different types of meetings
- Handles unstructured transcript input effectively
- Reduces dependency on predefined conversation paths

---

### Modular design with child agents
The solution separates orchestration and execution:

- Main agent → handles task extraction and user interaction  
- Child agents → handle system-specific task creation  

This allows:
- Clear separation of concerns
- Easier maintenance
- Scalable extension (e.g. adding Jira later)

---

### Tool-based execution
The agent integrates directly with external systems using connectors:

- Microsoft Planner → task creation  
- Azure DevOps → work item creation  

This enables seamless transition from meeting output to operational tools.

---

## Demo

https://youtu.be/hPbb13zlAx4

This demo shows:
- Task extraction from a meeting transcript
- Identification of dependencies
- User selection of the target system
- Task creation in Azure DevOps

---

## Scenario

The demo is based on a recruitment scenario for a shoe store:

- A meeting transcript is analysed  
- Action items are extracted  
- Dependencies between tasks are identified  
- The user selects first Planner, and then Azure DevOps  
- Tasks are created in the **Recruitment DEMO** project and plan

---

## Technologies Used
- Microsoft Copilot Studio  
- Microsoft Power Platform  
- Azure DevOps connector  
- Microsoft Planner connector  

---

## Repository Contents

- Power Platform solution export (.zip)
- README with architecture and explanation

---

## Notes
This solution was built within a Power Platform environment.  
Some system-generated metadata (such as owners or connection references) reflect the environment setup.

---

## Future Improvements
- Jira integration  
- Improved dependency detection  
- Enhanced task structuring and prioritization
- Triggered by the availability of transcription
