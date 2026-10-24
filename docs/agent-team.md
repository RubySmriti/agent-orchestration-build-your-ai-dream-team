# Agent team

We will use GitHub Copilot CLI in a Codespace to orchestrate a custom agent team for Mona's Project Pulse dashboard. The team is defined under `.github/agents/`, and each agent has a clear role in planning, designing, implementing, and validating the dashboard.

## Team members

- Orchestrator — Model: `Claude Opus 5.5`  
  File: `.github/agents/orchestrator.agent.md`  
  Responsibility: Coordinates the work, breaks the request into phases, delegates to the Planner, Designer, and Coder, and verifies that the final dashboard fits together before handoff.

- Planner — Model: `Claude Opus 5.5`  
  File: `.github/agents/planner.agent.md`  
  Responsibility: Researches the repo and requirements, identifies dependencies and risks, and creates the implementation plan for Project Pulse with file ownership, sequencing, and validation expectations.

- Coder — Model: `GPT-5.5`  
  File: `.github/agents/coder.agent.md`  
  Responsibility: Implements the actual dashboard code, creates required app support files, and validates that the Project Pulse experience works as expected.

- Designer — Model: `Gemini 3.7 Flash`  
  File: `.github/agents/designer.agent.md`  
  Responsibility: Focuses on the dashboard experience, including usability, accessibility, layout, hierarchy, and polished styling so Project Pulse looks like a strong project overview dashboard.

## How the team will work together

The Orchestrator will start by asking the Planner to research the repository and outline the Project Pulse implementation. After the plan is in place, the Orchestrator delegates work to the Designer and Coder in the right file scopes. The Designer shapes the UI/UX and visual direction, while the Coder builds the actual dashboard files and launch support. The Orchestrator then checks the combined result, keeps the work aligned with the plan, and ensures the final Project Pulse dashboard is ready for Mona to review and use.
