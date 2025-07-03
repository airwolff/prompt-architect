# Agentic Knowledge Base Architecture

This is for designing, building AI agents. It consists of three core components: the **Prompt Architect** (the master builder), the structured **Knowledge Base** it utilizes, and the **Specialist Agents** it generates.

## 🚀 The Core Philosophy

The primary objective of this project is to systematize the creation of well-structured prompts. It applies established best practices and prompting frameworks through a Socratic dialogue that ensures clear human direction and oversight.

A second key objective is to move beyond monolithic text documents by creating a flexible Single Source of Truth for any given topic. This structured knowledge base serves as the foundational guardrails for the project's AI agents. By deconstructing complex subjects into their atomic components and storing them in a universal YAML schema, the system enables:

-   **True Customization:** Allow AI agents to combine components from different knowledge entries to create novel, hybrid solutions.
-   **Systematic Processing:** Provide a predictable structure that AI can reliably parse, analyze, and utilize.
-   **Scalability and Maintenance:** Easily add, update, or improve knowledge entries without breaking the entire system.

## Current State & Future Vision

This project currently operates as an **agentic architecture** within a general AI environment like Gemini. The user acts as the "orchestrator," manually running the different agents in sequence.

The ultimate vision is to transition this entire system to a local, automated environment using Python. The components in this repository serve as the direct blueprint for that future build, ensuring that the logic, data structures, and prompts are well-defined and tested before development begins.

## 🏛️ The "Single Source of Truth" Knowledge Schema

All files within the `/knowledge` directory must adhere to the following universal YAML schema.

```yaml
# --- File Header ---
# /knowledge/[entry_name].yaml
# Version: 1.0
# Last Updated: 2025-MM-DD
# Description: A brief, one-sentence explanation of the file's content.

# --- Data Structure ---
entry_name: "[Name of the subject]"
type:
  - "[High-level category]"
  - "[Another category]"
description: "[A concise summary of the subject.]"
core_components:
  - name: "[Name of the first core part or principle]"
    description: "[Details of the first core part.]"
  - name: "[Name of the second core part or principle]"
    description: "[Details of the second core part.]"
mechanism_and_use:
  - name: "[Name of the first mechanism or process step]"
    description: "[Details of how it works or is used.]"
  - name: "[Name of the second mechanism or process step]"
    description: "[Details of how it works or is used.]"
connections_and_applications:
  description: "[A brief note on how the subject relates to other things.]"
  related_entries:
    - "[Name of a related entry]"
    - "[Another related entry]"
  practical_examples:
    - name: "[Name of a real-world example]"
      details: "[Details of the example.]"
simple_explanation: >
  [A simple, child-level explanation of the subject to demonstrate core understanding.]
```
## 🤖 The Agentic Workflow
This ecosystem enables a powerful, end-to-end workflow:

1.  **The Research Agent:** Takes a topic as input, conducts comprehensive research, and generates a new knowledge entry that strictly adheres to the "Single Source of Truth" schema.
2.  **The Formatter/QA Agent:** Takes an existing, potentially unstructured document and reformats it to the schema, ensuring no information is lost. It also serves as a quality assurance step to validate existing files for schema compliance.
3.  **The Indexer Agent:** Reads all the individual knowledge entries and creates a master _index.yaml file, which acts as a relational map of the entire knowledge base.

## 📂 Repository Structure
The project is organized in a monorepo to keep all related components together.
```
/
├── agents/
│   ├── formatter_qa.md
│   └── indexer.md
├── knowledge/
│   ├── constraints.yaml
│   ├── context.yaml
│   ├── format.yaml
│   ├── frameworks.yaml
│   ├── persona.yaml
│   ├── process.yaml
│   └── task.yaml
├── instructions.md
└── readme.md
