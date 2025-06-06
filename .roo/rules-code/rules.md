# General Coding Rules for Charts

Always try to make your changes as small and focused as possible. This will make it easier to review and test your changes, and will also help to avoid introducing bugs or breaking existing functionality.

Every task that modifies the content of the `charts/<chart-name>` directory should follow these coding rules to ensure consistency and maintainability.

## Use the `pre-commit` tool

To run checks before committing changes. This tool will help you catch common issues and enforce coding standards.

- Run `pre-commit run --all-files` to check all files.


## Use the `helm lint` command

Use the `helm lint` command to validate your Helm charts. This command checks for common issues in your chart templates and values files.
   - Run `helm lint charts/<chart-name>` to validate a specific chart.
   - Ensure that the chart passes the linting process before committing changes.


## Always update the chart version

Always ensure the chart version is updated in the `Chart.yaml` file whenever you make changes to the chart.

1. Follow [Semantic Versioning](https://semver.org/) guidelines for versioning.
2. Update the `version` field in `Chart.yaml` accordingly.
3. Always run the `pre-commit run -a` command after updating the version to ensure that the schema and documentation are regenerated correctly. This command will fail, but it will still regenerate the schema correctly. To verify that the schema is generated correctly, rerun the same `pre-commit run -a` command one more time. If the command passes without errors, it means that the schema is generated correctly and you can proceed with your changes.
