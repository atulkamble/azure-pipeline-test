# azure-pipeline-test

Sample repository demonstrating a minimal Azure DevOps pipeline that builds and deploys a .NET application.

## Pipeline overview
- Triggered on pushes to `main` and any `feature/*` branch.
- Uses `ubuntu-latest` as the default agent image with a Windows job override when needed.
- Build stage installs .NET 8 SDK, performs a placeholder build, and runs an example Windows job.
- Deploy stage currently echoes a placeholder command so you can wire in real deployment logic.

## Getting started
1. Import the repository into Azure DevOps or connect it to your existing project.
2. Create a new pipeline in Azure DevOps and point it to `azure-pipelines.yml` in the root of the repo.
3. Replace the placeholder build/deploy script steps with the commands required for your application.

## Customising the pipeline
- Update the `buildConfiguration` variable to match the configuration you want to build (for example, `Debug`).
- Add additional tasks or scripts within each job to run tests, publish artifacts, or deploy to your environment.
- Duplicate or rename stages if you need distinct environments such as staging and production.

## Validating changes locally
While Azure Pipelines validates the YAML when you run it, you can catch syntax issues early by parsing the file locally:

```bash
python3 -c "import yaml, pathlib; yaml.safe_load(pathlib.Path('azure-pipelines.yml').read_text())"
```

Install `pyyaml` first if the `yaml` module is unavailable.

The command succeeds silently when the YAML is valid and raises an error if the file contains invalid syntax.
