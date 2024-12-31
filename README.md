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
- [Kotaemon](https://github.com/Cinnamon/kotaemon): As the foundation for our RAG-based implementation

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

## Phase 2: Kotaemon Implementation

Our second phase focused on adapting the Kotaemon platform to create a specialized prompt optimization framework. This phase proved to be significantly more challenging than anticipated, leading to strategic pivots in our implementation approach.

### Initial Development Goals

Our original plan was to create a streamlined version of Kotaemon specifically tailored for prompt optimization by:
- Integrating RagBuilder's optimal configurations into the codebase
- Implementing PaperQA's scientific paper analysis capabilities
- Customizing the UI for prompt design workflows
- Simplifying the architecture for our specific use case

### Implementation Challenges

The complexity of Kotaemon's codebase presented significant hurdles:
- Multiple weeks spent understanding the architecture and dependencies
- Numerous dependency conflicts across different operating systems
- Integration challenges with external services and APIs
- Stability issues when implementing custom modifications

Given time constraints and the need for a working prototype, we pivoted to leverage Kotaemon's existing capabilities through its configuration interface rather than deep architectural modifications.

### Working Solution

Successfully deployed using Docker:
```bash
docker run \
-e OPENAI_API_KEY=xxx \
-e PDF_SERVICES_CLIENT_ID=xxxx \
-e PDF_SERVICES_CLIENT_SECRET=xxxx \
-e GRADIO_SERVER_NAME=0.0.0.0 \
-e GRADIO_SERVER_PORT=7860 \
-e DEFAULT_LLM=gpt-3.5-turbo \
-e DEFAULT_EMBEDDING_MODEL=text-embedding-3-small \
-p 7860:7860 \
-it --rm --platform linux/arm64 \
ghcr.io/cinnamon/kotaemon:main-full
```

### Framework Configuration

We achieved our core objectives through careful configuration of existing features:

1. **Reasoning Settings**
   Implemented specialized prompts for prompt design optimization:
   ```
   You are an expert prompt design assistant. Your role is to analyze developer requirements 
   and recommend the most suitable prompt design techniques from: zero-shot, few-shot, 
   chain-of-thought, tree-of-thoughts, ReAct, Reflexion, and Self-Refine. Consider factors 
   like task complexity, reasoning needs, and external tool requirements.
   ```

2. **Knowledge Base Integration**
   - Uploaded research papers using Adobe PDF Services
   - Integrated GitHub repositories and technical blogs
   - Applied RagBuilder's optimal configurations for retrieval

### Framework Validation

To test our implementation's effectiveness, we evaluated the system using two real-world examples:
- A travel planning agent implementation
- A music composition system

This approach allowed us to verify the framework's ability to:
- Analyze existing code and requirements
- Provide relevant prompt design recommendations
- Support developers in initial prompt creation



