# Agentic Prompt Architecture

This project is a complete system for designing, building, and maintaining specialized AI agents. It consists of a suite of interconnected "agent instructions" and a structured **Knowledge Base** they utilize to perform their functions.

## 🚀 The Core Philosophy

The primary objective of this project is to systematize the creation of high-quality, architecturally sound prompts for AI agents. It replaces a monolithic, jack-of-all-trades approach with a distributed system of specialized agents, each an expert in a single domain.

A second key objective is to create a flexible **Knowledge Base** for any given topic. By using an adaptive, three-tier schema, the system enables:

-   **Intelligent Structuring:** Allows the AI to dynamically adapt the output format to best represent the source material's domain and content.
-   **Systematic Processing:** Provides a predictable yet flexible structure that AI can reliably parse, analyze, and utilize.
-   **Scalability and Maintenance:** Easily add, update, or improve knowledge entries with a schema that supports both universal standards and domain-specific extensions.

## 🤖 The Agentic Workflow

This ecosystem enables a powerful, sequential workflow for creating new, specialized agents. The user acts as the orchestrator, running each agent in the correct order to move from a broad concept to a validated, production-ready agent.

The workflow is as follows:

1.  **`architect_1_distillation`**: The "Strategist." This is the starting point for any new project. It takes a broad, high-level user idea and, through a socratic and analytical dialogue, decomposes it into one or more single, focused "Problem Statements."

2.  **`architect_2_plan`**: The "Systems Analyst." This agent takes a "Problem Statement" as input. It performs a Functional Decomposition to break the problem into its core components and defines the agent's charter and limitations. Its final output is split into two distinct documents to ensure a clean handoff:
    * A **`Prompt Brief`**, which outlines the agent's function and includes acceptance criteria for testing.
    * A **`Research Brief`**, which lists the required knowledge files for the agent.

3.  **`architect_3_research_coach`**: The "Knowledge Architect." This agent receives the `Research Brief`. Its sole job is to generate a set of powerful, targeted research prompts designed to elicit the raw information needed for the knowledge files.

4.  **`architect_4_data_synthesis`**: The "Knowledge Engineer." This intelligent agent takes unstructured research and transforms it into structured knowledge. It detects the document's domain (e.g., Technical, Business), applies a context-specific prioritization matrix, and uses an adaptive schema to generate a clean, potent, and "comprehensively minimalist" YAML file.

5.  **`architect_5_indexer`**: The "Librarian." This agent takes the newly created knowledge files and generates a dedicated `_index.yaml` file for them. This provides the final agent with a "table of contents" of its own knowledge base, improving its runtime performance.

6.  **`architect_6_prompt_coach`**: The "Prompt Engineer." This agent receives the `Prompt Brief` and the complete set of knowledge files (including the `_index.yaml`). It then collaborates with the user to translate the strategic plan into a final, high-performance `instructions.md` file.

7.  **`architect_7_validation`**: The "QA Tester." This agent takes a completed agent and tests it against the `Acceptance Criteria & Test Cases` defined in the `Prompt Brief`, ensuring the agent performs as designed.

## 🏛️ The Flexible Knowledge Schema

All files within the `/knowledge` directory are generated based on the flexible `knowledge_schema_guide.yaml`. This guide moves beyond a rigid, static template to an adaptive, three-tier system:

* **Tier 1: Required Core Fields:** A minimal set of universal keys (`entry_name`, `type`, `description`) that must be present in every file, ensuring a consistent foundation.
* **Tier 2: Standard Optional Fields:** Common keys (`core_components`, `practical_examples`, etc.) that are only included if relevant content exists in the source document. This keeps the output clean and focused.
* **Tier 3: Domain Extension Fields:** Specialized sections (`key_formulas`, `risk_factors`, `algorithms`, etc.) that the **Knowledge Engineer** agent dynamically adds to the file when it detects corresponding patterns in the source text.

This architecture ensures that each knowledge file is a "comprehensively minimalist" model of the subject—containing everything that is important but making every line earn its presence.

## 🔮 Future Vision & Roadmap

### Independence and Automation
This project currently operates as an agentic architecture within a general AI environment like Gemini, with the user manually orchestrating the workflow.

The ultimate vision is to transition this entire system to a local, automated environment, likely using Python. The components in this repository—the agent instructions and knowledge files—serve as the direct blueprint for that future build. This "prompt-first" development approach allows for rapid prototyping and iteration on the system's logic in a flexible environment before committing to a specific code implementation.

### Future Enhancements
The following are concepts for future versions to enhance the framework's robustness and analytical power.

* **Verification Agent (Step 4.5):** A potential future step involves a dedicated agent that audits the generated YAML against the source document. This agent would act as an automated quality assurance check to programmatically verify that every statement is grounded in the source text, eliminating hallucinations.
* **Field-Level Confidence Scoring:** A more granular version of the metadata block could include confidence scores on individual data points within the YAML, providing insight into which items are direct facts versus interpretations.
* **Semantic Relationship Typing:** This would evolve the `related_entries` field from a simple list to a structured object that defines the nature of the relationship, enabling more sophisticated reasoning and prompt construction by downstream agents. For example:
    ```yaml
    related_entries:
      - entry: "Accounts Payable (A/P)"
        relationship: "is a counterpart to"
      - entry: "Working Capital Management"
        relationship: "is a component of"
    ```