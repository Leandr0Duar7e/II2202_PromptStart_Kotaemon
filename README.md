# Prompt Start: A Framework Optimizing Prompt Initialization for Developers

This repository contains the research project for the II2202 Research Methodology course at KTH Royal Institute of Technology (Fall 2024, Period 1-2).

**Authors:**
- Leandro Duarte (leandrod@kth.se)
- Kusumastuti Cahyaningrum (kcah@kth.se)

## Project Overview

Prompt Start is a framework designed to assist developers in selecting appropriate prompt design techniques for their LLM-based applications. The framework addresses the "Blank Page Problem" - the challenge developers face when initially designing prompts for Large Language Models (LLMs).

The project integrates three key open-source components:
- [PaperQA](https://github.com/whitead/paper-qa): For retrieving and analyzing information from scientific papers
- [RagBuilder](https://github.com/KruxAI/ragbuilder): For optimizing RAG configurations
- [Kotaemon](https://github.com/cinnamon-github/kotaemon): As the foundation for our RAG-based implementation

## Phase 1: RagBuilder Implementation

Our initial phase focused on implementing and evaluating RagBuilder to establish optimal RAG configurations. Here's how we set it up:

### Setup Process

1. **Environment Setup**
   - Installed RagBuilder using the installation script
   - Created a clean Python environment to resolve dependency conflicts
   - Launched RagBuilder locally at http://localhost:8005/

2. **Neo4j Database Configuration**
   - Deployed Neo4j using Docker
   - Configured database access at http://localhost:7474/
   - Set credentials: username=neo4j, password=ragbuilder

3. **Environment Variables**
   Created `.env` file with necessary API keys and configurations:
   ```
   OPENAI_API_KEY=
   MISTRAL_API_KEY=
   ENABLE_ANALYTICS=
   HUGGINGFACEHUB_API_TOKEN=
   # ... (other required variables)
   ```

