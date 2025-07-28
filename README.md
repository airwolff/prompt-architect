# Agentic Prompt Architecture

This project is a complete system for designing, building, and maintaining specialized AI agents. It consists of a suite of interconnected "agent instructions" and a structured **Knowledge Base** they utilize to perform their functions.

## 🚀 The Core Philosophy

The primary objective of this project is to systematize the creation of high-quality, architecturally sound prompts for AI agents. It replaces a monolithic, jack-of-all-trades approach with a distributed system of specialized agents, each an expert in a single domain.

A second key objective is to create a flexible **Single Source of Truth** for any given topic. By deconstructing complex subjects into their atomic components and storing them in a universal YAML schema, the system enables:

-   **True Customization:** Allows AI agents to combine components from different knowledge entries to create novel, hybrid solutions.
-   **Systematic Processing:** Provides a predictable structure that AI can reliably parse, analyze, and utilize.
-   **Scalability and Maintenance:** Easily add, update, or improve knowledge entries without breaking the entire system.

## 🤖 The Agentic Workflow

This ecosystem enables a powerful, sequential workflow for creating new, specialized agents. The user acts as the orchestrator, running each agent in the correct order to move from a broad concept to a validated, production-ready agent.

The workflow is as follows:

1.  **`1_Distillation_Agent`**: The "Strategist." This is the starting point for any new project. It takes a broad, high-level user idea and, through a socratic and analytical dialogue, decomposes it into one or more single, focused "Problem Statements."

2.  **`2_Plan_Agent`**: The "Systems Analyst." This agent takes a "Problem Statement" as input. It performs a Functional Decomposition to break the problem into its core components and defines the agent's charter and limitations. Its final output is split into two distinct documents to ensure a clean handoff:
    * A **`Prompt Brief`**, which outlines the agent's function and includes acceptance criteria for testing.
    * A **`Research Brief`**, which lists the required knowledge files for the agent.

3.  **`3_Research_Coach_Agent`**: The "Knowledge Architect." This agent receives the `Research Brief`. Its sole job is to generate a set of powerful, targeted research prompts designed to elicit the raw information needed for the knowledge files. It embeds a thematic guidance framework into each prompt to ensure a rich, analytical output.

4.  **`4_Data_Synthesis_Agent`**: The "Knowledge Engineer." This agent takes the unstructured, narrative-style research output from the previous step. Its function is to "atomize" this raw text, extracting the vital information and structuring it into the final, clean YAML knowledge files according to the "Single Source of Truth" schema.

5.  **`5_Prompt_Coach_Agent`**: The "Prompt Engineer." This agent receives the `Prompt Brief` only *after* the knowledge base has been created. It analyzes the brief to select the optimal prompting framework (e.g., the core components, `RISEN`, `BAB`) and then collaborates with the user to translate the strategic plan into a final, high-performance `instructions.md` file.

6.  **`6_Validation_Agent`**: The "QA Tester." (To be designed). This agent will take a completed agent (its instructions and knowledge files) and test it against the `Acceptance Criteria & Test Cases` defined in the `Prompt Brief`, ensuring the agent performs as designed.


## 🏛️ The "Single Source of Truth" Knowledge Schema

All files within the `/knowledge` directory must adhere to the following universal YAML schema. The one exception is the `_index.yaml` file, which serves as the master index and has its own distinct structure.

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

🔮 Future Vision: Independence and Automation
This project currently operates as an agentic architecture within a general AI environment like Gemini, with the user manually orchestrating the workflow.
The ultimate vision is to transition this entire system to a local, automated environment, likely using Python. The components in this repository—the agent instructions and knowledge files—serve as the direct blueprint for that future build. They ensure that the core logic, data structures, and prompts are well-defined, tested, and validated before any production code is written. This "prompt-first" development approach allows for rapid prototyping and iteration on the system's logic in a flexible environment before committing to a specific code implementation.