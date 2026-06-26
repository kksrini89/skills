# Engineering Skills

This category contains skills focused on **core software engineering practices** requirements breakdown, task planning, architecture, code quality, automation, and implementation guidance.

These skills help turn vague requirements or PRDs into actionable, well-structured engineering work.

## Available Skills

### [`generate-tasks-from-prd`](./generate-tasks-from-prd)

**Description**:  
Generates a detailed, step-by-step Markdown task list from user requirements, feature requests, or Product Requirements Documents (PRDs). 

It creates a professional task breakdown with:
- High-level parent tasks
- Actionable sub-tasks
- Relevant files (including test files)
- Progress tracking checkboxes
- Clear instructions for junior developers

**Key Features**:
- Two-phase process with mandatory user confirmation after high-level tasks
- Always starts with "Create feature branch" task
- Saves output as `tasks/tasks-[feature-name].md`
- Designed for junior-to-mid level developers
- Includes relevant files and testing guidance

**Installation**:
```bash
npx skills add https://github.com/kksrini89/skills --skill generate-tasks-from-prd
```

**Usage Examples**:

- "Generate tasks from this PRD"
- "Break down user profile editing feature into tasks"
- "Create implementation tasks for the new payment flow"

-------------------------------------------------------------------------------------
Made with ❤️ for structured engineering execution