# Azure Pipeline Test

This repository hosts a minimal Azure DevOps pipeline definition used for experimentation and validation.

## Pipeline Overview
- **Trigger:** Runs automatically on pushes to the `main` branch.
- **Agent Pool:** Targets the `Default` pool and requires an agent named `DevOps-Server`.
- **Steps:**
  - Prints a greeting to verify the agent is running.
  - Prints guidance for extending the pipeline with build, test, and deployment tasks.

## Customizing the Pipeline
1. Replace the sample `script` tasks with the build and test commands for your project.
2. Update the agent demand if you want the pipeline to run on a different self-hosted agent or Microsoft-hosted pool.
3. Add stages/jobs as needed to separate build, test, and deployment responsibilities.

## Helpful Links
- [Azure Pipelines YAML schema](https://aka.ms/yaml)
- [Azure DevOps self-hosted agent documentation](https://learn.microsoft.com/azure/devops/pipelines/agents/agents)
