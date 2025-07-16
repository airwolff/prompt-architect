# Agentic Prompt Architecture

This project is a complete system for designing, building, and maintaining specialized AI agents. It consists of a suite of interconnected "agent instructions" and a structured **Knowledge Base** they utilize to perform their functions.

## 🚀 The Core Philosophy

The primary objective of this project is to systematize the creation of high-quality, architecturally sound prompts for AI agents. It replaces a monolithic, jack-of-all-trades approach with a distributed system of specialized agents, each an expert in a single domain.

A second key objective is to create a flexible **Single Source of Truth** for any given topic. By deconstructing complex subjects into their atomic components and storing them in a universal YAML schema, the system enables:

-   **True Customization:** Allows AI agents to combine components from different knowledge entries to create novel, hybrid solutions.
-   **Systematic Processing:** Provides a predictable structure that AI can reliably parse, analyze, and utilize.
-   **Scalability and Maintenance:** Easily add, update, or improve knowledge entries without breaking the entire system.

## 🤖 The Agentic Workflow

This ecosystem enables a powerful, end-to-end workflow for creating new agents and knowledge. The user acts as the "orchestrator," manually running the different agents in sequence.

### Agent Creation and Knowledge Generation

1.  **`The Blueprint Agent` (`instructions_blueprint.md`):** This is the starting point for creating a new agent. It acts as a systems architect, guiding the user through a structured process to create a formal **Agent Design Document**.
2.  **`The Builder Agent` (`instructions_builder.md`):** This agent takes the completed `Agent Design Document` as input and translates it into the final, high-quality `instructions.md` file for the new agent, applying prompt engineering best practices.
3.  **`The Researcher Agent` (`instructions_agent_researcher.md`):** This agent runs in parallel with the builder. It also takes the `Agent Design Document` and generates a set of optimized prompts for creating the new agent's required knowledge files, ensuring each one will adhere to the "Single Source of Truth" schema.

### Knowledge Base Maintenance

* **`The Indexer Agent` (`instructions_indexer.md`):** This agent reads all the individual knowledge entries and creates a master `_index.yaml` file, which acts as a relational map of the entire knowledge base. This is critical for efficient knowledge retrieval by other agents.

### General-Purpose Prompt Assistance

* **`The Prompt Coach` (`instructions_prompt_coach.md`):** For one-off tasks not related to agent creation, this agent acts as an expert coach, guiding the user to build a high-quality prompt for a specific analytical or creative task.
* **`The Prose Researcher` (`instructions_prose_researcher.md`):** For generating standard research documents (e.g., reports, articles) that are not part of the structured YAML knowledge base.

## 🏛️ The "Single Source of Truth" Knowledge Schema

All files within the `/knowledge` directory must adhere to the following universal YAML schema.

```yaml
# --- File Header ---
# /knowledge/[entry_name].yaml
# Version: 1.0
# Last Updated: 2025-MM-DD
# Description: A brief, one-sentence explanation of the file's content.
# Used_By: [List of instruction files that use this knowledge file]

# --- Data Structure ---
entry_name: "[Name of the subject]"
type:
  - "[High-level category]"
description: "[A concise summary of the subject.]"
core_components:
  - name: "[Name of the first core part or principle]"
    description: "[Details of the first core part.]"
mechanism_and_use:
  - name: "[Name of the first mechanism or process step]"
    description: "[Details of how it works or is used.]"
connections_and_applications:
  description: "[A brief note on how the subject relates to other things.]"
  related_entries:
    - "[Name of a related entry]"
  practical_examples:
    - name: "[Name of a real-world example]"
      details: "[Details of the example.]"
simple_explanation: >
  [A simple, child-level explanation of the subject to demonstrate core understanding.]
```
## 🔮 Future Vision: Independence and Automation

This project currently operates as an agentic architecture within a general AI environment like Gemini, with the user manually orchestrating the workflow.

The ultimate vision is to transition this entire system to a **local, automated environment, likely using Python**. The components in this repository—the agent instructions and knowledge files—serve as the direct blueprint for that future build. They ensure that the core logic, data structures, and prompts are well-defined, tested, and validated before any production code is written. This "prompt-first" development approach allows for rapid prototyping and iteration on the system's logic in a flexible environment before committing to a specific code implementation.